pipeline {
    agent any
    
    stages {
      stage('install node')
      {
        steps {
          node {
      withEnv(["PATH+NODE=${tool name: 'node-5.10.1', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'}/bin"]) {
        sh 'node -v'
      }
    }
        }
      }
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