pipeline {
    agent any

    tools {
        maven 'maven' 
        gradle 'gradle'  // Ensure this matches the name configured in Jenkins
       // Ensure this matches the name configured in Jenkins
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/praveeng4410/MavenToGradle.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'  // Run Maven build
            }
        }

        stage('migrate') {
            steps {
                sh 'gradle init --type pom'  // Run unit tests
            }
        }

        
    }

    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
