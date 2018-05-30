pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
                sh '/Users/gauravagnihotri/Downloads/apache-maven-3.3.9/bin/mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
        stage ('Deploy to Staging'){
            steps {
                build job: 'Deploy-to-staging'
            }
        }
    }
}
