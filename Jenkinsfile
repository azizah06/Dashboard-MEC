pipeline {
    agent any
    stages {
        // Tahap: Git Checkout
        stage('Git Checkout') {
            steps {
                echo 'Cloning repository from Git...'
                checkout scm // Mengambil kode dari repository SCM
            }
        }
        
        // Tahap: Mengirim Dockerfile ke Ansible Server
        stage('Sending Dockerfile to Ansible Server') {
            steps {
                echo 'Sending Dockerfile to Ansible server...'
                sh '''
                    scp Dockerfile user@ansible-server:/path/to/target
                '''
            }
        }
    }
}
