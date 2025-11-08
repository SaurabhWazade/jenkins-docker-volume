pipeline {
  agent any

  stages {
    stage ('one') {
      steps {
        sh '''docker kill s2 || true
        docker rm s2 || true 
        cp /root/.jenkins/workspace/test2/index.html /mnt/lol/
        docker run -dp 90:80 -v /mnt/lol/:/usr/local/apache2/htdocs/ --name s2 httpd
        docker exec s2 sh -c "chmod -R 644 /usr/local/apache2/htdocs/index.html"'''
        }
      
    }
  }
  post {
    always {
     sh "rm -rf ${WORKSPACE}/*"
 
    }
  }
