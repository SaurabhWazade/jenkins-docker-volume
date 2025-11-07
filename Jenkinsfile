pipeline {
  agent any

  stages {
    stage ('bind mount') {
      steps {
        sh """ rm -rf /root/.jenkins/workspace/*
        git clone https://github.com/SaurabhWazade/jenkins-docker-volume.git
        docker run -itdp 80:80 -v /root/.jenkins/workspace/test1/:/usr/local/apache2/htdocs/ --name s1 httpd"""
      }
    }
  }
}
