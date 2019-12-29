pipeline {
    agent any
    def mvnHome = tool name: 'maven-3', type: 'maven'
    stages {
        stage('---clean---') {
            steps {
                sh "${mvnHome}/bin/mvn clean"
            }
        }
        stage('--test--') {
            steps {
                sh "${mvnHome}/bin/mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "${mvnHome}/bin/mvn package"
            }
        }
        stage('---Slack Notification---'){
            steps {
                slackSend channel: '#jenkins-school', color: 'good', message: 'Welcom to jenkins, Slack!', teamDomain: 'daniloshome', tokenCredentialId: 'slack-demo'
            }
        }
    }
}
