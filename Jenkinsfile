pipeline {
    agent none
    parameters {
        string(name : 'MY_STRING', defaultValue : 'This is My String Value from Caller', description : '')
        string(name : 'YOUR_STRING', defaultValue : 'This is Your String Value from Caller', description : '')
    }
    stages{
        stage('Call Another Job with Parameters') {
            steps{ 
                echo 'DDDDDDDDDDDDDDD'
                build job : 'sandbox-callee', parameters: [
                    string(name: 'MY_STRING', value: "${params.MY_STRING}"),
                    string(name : 'YOUR_STRING', value : "${params.YOUR_STRING}")]
            }
        }
    }
}