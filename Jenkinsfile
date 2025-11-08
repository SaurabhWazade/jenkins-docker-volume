pipeline {
  agent {
    label {
      label "QA2"
    }
  }

  stages {
    stage ('one') {
      steps {
        sh '''sudo docker kill s2 || true
        sudo docker rm s2 || true 
        sudo cp /mnt/jenkins-slave/workspace/js2/index.html /mnt/lol/
        sudo docker run -dp 90:80 -v /mnt/lol/:/usr/local/apache2/htdocs/ --name s2 httpd
        sudo docker exec s2 sh -c "chmod -R 644 /usr/local/apache2/htdocs/index.html"'''
        }
      
    }
  }
  post {
    always {
     sh "rm -rf ${WORKSPACE}/*"
 
    }
  }
}
