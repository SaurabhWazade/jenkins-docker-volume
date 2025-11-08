pipeline {
  agent any

  stages {
    stage ('one') {
      steps {
        sh '''docker kill s1 || true
        docker rm s1 || true 
        cp /root/.jenkins/workspace/test1/index.html /mnt/lol/
        docker run -dp 80:80 -v /mnt/lol/:/use/local/apache2/htdocs/ --name s1 httpd
        docker exec s1 sh -c "chmod -R 644 /usr/local/apache2/htdocs/index.html"'''
        }
      
    }
  }
  post {
    always {
     sh "rm -rf ${WORKSPACE}/*"
 
    }
  }
}
