pipeline {
    agent any
    tools {nodejs "nodejs"}
    stages {
        stage('CI-Install Truffle') {
            steps {
                   sh '''
                           echo "install truffle v_5.1.4"
                           npm install -g truffle@5.1.4
                        '''
            }
        }
        stage('CI-Install Packages') {
         steps {
                        sh '''
                                echo "install all dependencies with yarn"
                                npm install
                        '''
                    }
        }
       stage('CI-Run Test') { 
         steps {
                        sh '''
                                echo "truffle rune"
                                truffle test
                        '''
                    }
        }
        stage('CI-Run Compile') {
            steps {
                sh 'truffle compile'
            }
        }
        
        stage('CI-Run Deploy') { 
            steps {
                
                sh 'truffle migrate --reset --network ropsten' 
            }
        }
    }
}