pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                echo 'Build'
                build(lenguaje)
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
