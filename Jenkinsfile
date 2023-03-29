pipeline {
    agent any
    stages{
        stage('Call Another Job with Parameters') {
            steps{ 
                echo 'Checkout Private Repository...'
                git branch: 'main', credentialsId: 'GitHub', url: 'https://github.com/jangdaewon/jenkins-sandbox-private.git'
                sh 'ls -al'
                sh 'ls -al ./jenkins-sandbox-private'
                echo 'Calling...'
                build job : 'sandbox-callee', parameters: [
                    string(name: 'MY_STRING', value: 'This is My String Value from Caller'),
                    string(name : 'YOUR_STRING', value : 'This is Your String Value from Caller')]
            }
        }
    }
}