pipeline {
  agent any

  stages {
    stage ('bind mount') {
      steps {
        sh """rm -rf /root/.jenkins/workspace/*
        docker run -itdp 8090:80 -v /root/.jenkins/workspace/test3/:/usr/local/apache2/htdocs/ --name s3 httpd"""
      }
    }
  }
}
