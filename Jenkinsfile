pipeline {
    agent any 
    tools {
        maven 'Maven 3.6.3' 
    }
    stages {
        stage('Compile') { 
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
        }
        stage('Package') { 
            steps {
                sh 'mvn -DskipTests package' 
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
        }
    }
}
