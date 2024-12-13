pipeline {
    agent any

    stages {
        stage('Run Ansible Playbook') {
            steps {
                script {
                    // Jalankan playbook di dalam Jenkins workspace
                    sh 'ansible-playbook test-playbook.yml'
                }
            }
        }
    }
}
