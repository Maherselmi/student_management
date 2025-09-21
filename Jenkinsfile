pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'   // Nom du JDK configuré dans Jenkins
        maven 'M2_HOME'   // Nom de Maven configuré dans Jenkins
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Maherselmi/student_management.git'
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
    }

    post {
        success { echo 'Pipeline réussie ✅' }
        failure { echo 'Pipeline échouée ❌' }
    }
}
