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
                sh 'mvn clean verify sonar:sonar -Dsonar.host.url=http://3.12.22.139:9000 -Dsonar.scm.disabled=true -Dsonar.login=6a88962adfb90f9534124dc5dccf3cb6ddbbca94'
                echo 'Waiting for Quality Gate'
                sleep 15
                def qg = waitForQualityGate()  
                  if (qg.status != 'OK') {
                     echo "Sonar Quality Gate did not Pass, Please Check SonarQube report."
                     error "Error Code: ${qg.status}"
                  }
            }
        }
    }
    post {
        always {
					cleanWs()
                }

     }
}
