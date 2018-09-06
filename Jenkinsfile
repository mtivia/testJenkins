pipeline {
    agent none
    stages{
        stage('Build'){
            agent {
                docker {
                    image 'maven:3.5.0'
                }
            }
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
