pipeline {
  agent any

  stages {
    stage ('bind mount') {
      steps {
        sh "docker run -itdp 80:80 -v /root/.jenkins/workspace/test1/:/usr/local/apache2/htdocs/ --name s1 httpd"
      }
    }
  }
}
