pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Wein1377/Jenkins.git'
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

        stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }
    }

    post {
        always {
            archiveArtifacts(artifacts: 'target/*.jar', fingerprint: true)
        }

        success {
            echo 'Сборка прошла успешно! Можете развернуть приложение.'
        }

        failure {
            echo 'Сборка не удалась. Проверьте логи и исправьте ошибки.'
        }
    }
}