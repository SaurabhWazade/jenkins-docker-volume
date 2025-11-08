pipeline {
  agent {
    label {
      label "QA1"
    }
  }

  stages {
    stage ('one') {
      steps {
        sh '''sudo docker kill s1 || true
        sudo docker rm s1 || true 
        sudo cp /root/.jenkins/workspace/test1/index.html /mnt/lol/
        sudo docker run -dp 80:80 -v /mnt/lol/:/usr/local/apache2/htdocs/ --name s1 httpd
        sudo docker exec s1 sh -c "chmod -R 644 /usr/local/apache2/htdocs/index.html"'''
        }
      
    }
  }
  post {
    always {
     sh "rm -rf ${WORKSPACE}/*"
 
    }
  }
}
