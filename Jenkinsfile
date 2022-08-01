pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'clone the repo'
                sh 'rm -fr webapp1'
                sh 'git clone https://github.com/Thiyagarajan7/webapp1.git'
            }
        }
        stage('push repo to remote host') {
            steps {
                echo 'connect to remote host and pull down the latest version'
                sh 'ssh -i ~/keys.pem ubuntu@3.110.208.24 sudo git -C /var/www/html pull'
            }
        }
        stage('Check website is up') {
            steps {
                echo 'Check website is up'
                sh 'curl -Is 3.110.208.24 | head -n 1'
            }
        }
    }
}
