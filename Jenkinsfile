pipeline {
  agent any

  stages {
    stage ('empty working dir') {
      steps {
        sh "rm -rf* /root/.jenkins/workspace/"
      }
    }
    stage ('bind mount') {
      steps {
        sh "docker run -itdp 80:80 -v /root/.jenkins/workspace/test1/:/usr/local/apache2/htdocs/ --name s1 httpd"
      }
    }
  }
}
