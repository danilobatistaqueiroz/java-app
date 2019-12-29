pipeline {
    agent any
    stages {
        stage('---clean---') {
            steps {
                script {
                    def mvnHome = tool name: 'maven-3', type: 'maven'
                    sh "${mvnHome}/bin/mvn clean"
                }
            }
        }
        stage('--test--') {
            steps {
                script {
                    def mvnHome = tool name: 'maven-3', type: 'maven'
                    sh "${mvnHome}/bin/mvn test"
                }
            }
        }
        stage('--package--') {
            steps {
                script {
                    def mvnHome = tool name: 'maven-3', type: 'maven'
                    sh "${mvnHome}/bin/mvn package"
                }
            }
        }
        stage('---Slack Notification---'){
            steps {
                slackSend channel: '#jenkins-school', color: 'good', message: 'Welcom to jenkins, Slack!', teamDomain: 'daniloshome', tokenCredentialId: 'slack-demo'
            }
        }
    }
}
