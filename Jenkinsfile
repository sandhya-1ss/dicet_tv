pipeline {

  agent any
  environment {
      PATH = "/bin/mvn:$PATH"
  }
  stages {
      stage("git"){
          steps{
            git branch: 'master', url: 'https://github.com/sandhya-1ss/dicet_tv.git'
          
          }
      }
      stage("build"){
          steps{
              sh "mvn clean package"
          }
      }
      stage("deploy"){
          steps{
             deploy adapters: [tomcat9(credentialsId: '7', path: '', url: 'http://13.233.119.231:8080/')], contextPath: 'sanjufolder1', war: '**/*.war'
          }
      }
  }
}

