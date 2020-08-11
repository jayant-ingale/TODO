pipeline {
    agent any
    agent {
        docker {
          image 'node:10.11.0-alpine'
        }
     }
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