pipeline {
    agent any
    stages {
        stage('---git checkout---'){
            git 'https://github.com/javahometech/java-app'
        }
        stage('---clean---') {
            steps {
                sh "mvn clean"
            }
        }
        stage('--test--') {
            steps {
                sh "mvn test"
            }
        }
        stage('--package--') {
            steps {
                sh "mvn package"
            }
        }
        stage('---Slack Notification---'){
            slackSend channel: '#jenkins-school', color: 'good', message: 'Welcom to jenkins, Slack!', teamDomain: 'daniloshome', tokenCredentialId: 'slack-demo'
        }
    }
}
