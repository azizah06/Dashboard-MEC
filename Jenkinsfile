pipeline {
    agent any
    environment {
        ANSIBLE_HOST_KEY_CHECKING = 'false'  // Menonaktifkan verifikasi host SSH (opsional)
    }
    stages {
        stage('Install Dependencies') {
            steps {
                // Menginstal Ansible jika belum terpasang
                sh 'pip install ansible'
            }
        }
        stage('Run Ansible Playbook') {
            steps {
                script {
                    // Menjalankan playbook Ansible yang ada di repository
                    sh 'ansible-playbook -i inventory/hosts playbook.yml'
                }
            }
        }
    }
    post {
        success {
            echo 'Playbook executed successfully.'
        }
        failure {
            echo 'Ansible Playbook execution failed.'
        }
    }
}
