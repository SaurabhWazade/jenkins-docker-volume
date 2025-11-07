pipeline {
  agent any

  stages {
    stage ('clean dir') {
      steps {
        sh "rm -rf /root/.jenkins/workspace/test*"
      }
    }
    stage ('bind mount') {
      steps {
        sh '''docker run -itdp 80:80 -v /root/.jenkins/workspace/test1/:/usr/local/apache2/htdocs/ --name s1 httpd
        docker exec s1 sh -c "chmod 644 /usr/local/apache2/htdocs/index.html"'''
      }
    }
  }
}
