pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        stage('Compile') {
            steps {
                sh 'truffle compile'
            }
        }
        stage('test') { 
            steps {
                sh 'truffle test' 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'truffle migrate --reset ropsten' 
            }
        }
    }
}