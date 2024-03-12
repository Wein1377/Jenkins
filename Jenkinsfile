pipeline {
    agent any
    tools {
        jdk 'jdk17'
        maven 'maven3'
    }
    stages {
        stage('Git Checkout') {
            steps {
               git 'https://github.com/Wein1377/Jenkins.git'
            }
        }
         stage('Compile') {
            steps {
               sh "mvn compile"
            }
        }
         stage('Test') {
            steps {
               sh "mvn test"
            }
        }
        stage('Package') {
            steps {
               sh "mvn package"
            }
        }
        stage('Install') {
            steps {
               sh "mvn install"
            }
        }
    }
}