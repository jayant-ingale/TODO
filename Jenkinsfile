pipeline {
    agent any
    node {
      withEnv(["PATH+NODE=${tool name: 'node-5.10.1', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'}/bin"]) {
        sh 'node -v'
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