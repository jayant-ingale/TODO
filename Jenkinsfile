pipeline {
    agent any
    agent { label 'master' }
    tools { nodejs "nodejs" }
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
        stage('Test') { 
            steps {
                sh 'truffle test' 
            }
        }
        stage('Deploy') { 
            steps {
                sh 'truffle migrate --reset --network ropsten' 
            }
        }
    }
}