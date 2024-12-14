pipeline {
    agent any
    stages {
        stage('Install Dependencies') {
            steps {
                script {
                    // Pastikan perintah yang benar digunakan untuk Windows
                    if (isUnix()) {
                        // Jika Linux/Unix, gunakan sh
                        sh 'ansible-galaxy install -r requirements.yml'
                    } else {
                        // Jika Windows, gunakan bat atau powershell
                        bat 'ansible-galaxy install -r requirements.yml'
                    }
                }
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                script {
                    // Pastikan perintah yang benar digunakan untuk Windows
                    if (isUnix()) {
                        // Jika Linux/Unix, gunakan sh
                        ansiblePlaybook credentialsId: 'your-credentials-id', inventory: 'hosts', playbook: 'mariadb.yml'
                    } else {
                        // Jika Windows, gunakan perintah PowerShell
                        bat 'ansible-playbook -i hosts mariadb.yml'
                    }
                }
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
