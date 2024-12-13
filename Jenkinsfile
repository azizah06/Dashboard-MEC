pipeline {
    agent any

    stages {
        stage('Run Ansible Playbook') {
            steps {
                script {
                    // Jalankan playbook di dalam Jenkins workspace
                    bat 'ansible-playbook test-playbook.yml'
                }
            }
        }
    }
}
