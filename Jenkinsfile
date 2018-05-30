pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh '/Users/audreytan/documents/apache-maven-3.3.9/bin/mvn clean package'
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
