pipeline {
  agent any

  stages {
    stage ('bind mount') {
      steps {
        sh '''docker kill s2
        docker rm s2
        docker run -itdp 90:80 -v /root/.jenkins/workspace/test2/:/usr/local/apache2/htdocs/ --name s2 httpd
        docker exec s2 sh -c "chmod 777 /usr/local/apache2/htdocs/index.html"'''
      }
    }
  }
}
