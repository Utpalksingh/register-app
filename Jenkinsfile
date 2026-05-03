pipeline {
    agent { label 'Jenkins-agent' }
    
    tools {
        maven 'Maven3'
        jdk 'Java21'
    }
    
    stages {

        stage('clean workspace') {
            steps {
                cleanWs()
            }
        }

        stage('checkout - Pull code from GitHub') {
            steps {
                git branch: 'master', credentialsId: 'github', url: 'https://github.com/Utpalksingh/register-app.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                // Runs static code analysis
             }
        }

        stage('Quality Gate') {
            steps {
                 // Checks if quality gate passed
            }
        }
    }
}
    
    