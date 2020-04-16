pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Build'
                
                sh 'mvn clean install'
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
