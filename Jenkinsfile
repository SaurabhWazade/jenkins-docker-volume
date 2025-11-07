pipeline {
  agent any

  stages {
    stage ('bind mount') {
      steps {
        sh """rm -rf /root/.jenkins/workspace/*
        docker run -itdp 90:80 -v /root/.jenkins/workspace/test2/:/usr/local/apache2/htdocs/ --name s2 httpd"""
      }
    }
  }
}
