pipeline {
  agent any

  stages {
   
    stage ('bind mount') {
      steps {
        sh '''docker kill s1
        docker system prune -a -f 
        docker run -itdp 80:80 -v /root/.jenkins/workspace/test1/:/usr/local/apache2/htdocs/ --name s1 httpd
        docker exec s1 sh -c "chmod 644 /usr/local/apache2/htdocs/index.html"'''
      }
    }
  }
}
