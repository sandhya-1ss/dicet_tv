pipeline {
    agent any
    environment{
        PATH = "/bin/mvn:$PATH"
    stages {
        stage (git) {
            steps {
                git 'https://github.com/sandhya-1ss/dicet_tv.git'
            }
        }
        stage (build) {
            steps {
                sh 'mvn clean package'
            }
        }
        stage (deploy) {
            steps {
                deploy adapters: [tomcat9(credentialsId:'222', path: '', url: 'http://http://3.110.185.141:8080//')], contextPath: 'sanju', war: '**/*.war'
            }
        }
    }
}
