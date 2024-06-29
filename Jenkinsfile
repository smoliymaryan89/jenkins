pipeline {
    agent { label 'my_agent' }



    stages {
        stage('Install Apache2') {
            steps {
                sh 'sudo apt update'
                sh 'sudo apt install apache2 -y'
            }
        }
        
        stage('Checking for 4xx and 5xx errors in the logs'){
            steps {
              sh "sudo grep -E 'HTTP/[0-9.]+\" [4-5][0-9]{2}' /var/log/apache2/access.log"
            }
        }
    }
}

