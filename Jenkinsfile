pipeline {
    agent { lable 'Jenkins-Agent'}
    tools {
        jdk 'Java17'
        maven 'Maven3'
    }
    stages {
        stage ("Cleanup Workspace"){
            steps {
                CleanWs()
            }
        }
        stage ("Checkout from SCM") {
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/krishtambe/register-app-main'
            }
        }
        stage ("Build Application") {
            steps {
                sh "mvn clean package"
            }
        }
        stage ("Test Application") {
            steps {
                sh "mvn test"
            }
        }
    }
}