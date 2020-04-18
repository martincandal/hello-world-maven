pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Build'
                
                sh 'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Sonar Test'
                sh 'mvn clean verify sonar:sonar -Dsonar.host.url=http://3.12.22.139:9000 -Dsonar.scm.disabled=true -Dsonar.login=6a88962adfb90f9534124dc5dccf3cb6ddbbca94'
                
            }
        }
    }
    post {
        always {
					echo 'Cleaning Workspace...'
                    cleanWs()
                }

     }
}
