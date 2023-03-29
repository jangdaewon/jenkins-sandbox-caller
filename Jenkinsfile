pipeline {
    agent none
    stages{
        stage('Call Another Job with Parameters') {
            steps{ 
                echo 'DDDDDDDDDDDDDDD'
                build job : 'sandbox-callee', parameters: [
                    string(name: 'MY_STRING', value: 'This is My String Value from Caller'),
                    string(name : 'YOUR_STRING', value : 'This is Your String Value from Caller')]
            }
        }
    }
}