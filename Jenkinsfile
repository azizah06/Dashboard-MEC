pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                // Clone repository dengan memilih branch dan kredensial yang benar
                git branch: 'patch-1', 
                    credentialsId: 'azizah', 
                    url: 'https://github.com/JunandaDeyastusesa/Dashboard-MEC-1.git'
            }
        }
        stage('Install Dependencies') {
            steps {
                // Install dependencies menggunakan Ansible Galaxy
                sh 'ansible-galaxy install -r requirements.yml'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                // Jalankan Ansible playbook
                ansiblePlaybook credentialsId: 'azizah', 
                    inventory: 'hosts', 
                    playbook: 'playbooks/mariadb.yml'
            }
        }
    }
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
