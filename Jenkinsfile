pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                git 'https://github.com/Wein1377/Jenkins.git'
                sh "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            post {
                success {
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}