pipeline {
    agent { label 'agent-1' }
   
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }

        stage('Test') {
            steps {
                sh './jenkins/scripts/test.sh'
            }
        }
        
        stage('change directory') {
            steps {
                sh 'cd /home/ubuntu/node-hello-world/'
            }
        }

        stage('approve') {
            steps {
                input 'kindly approve for this deployment'
            }
        }

        stage('deploy') { 
            steps {
                sh 'npm start /home/ubuntu/node-hello-world/' 
            }
        }
    }
}
