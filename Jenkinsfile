pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn clean verify sonar:sonar'
            }
        }
    }
}
