pipeline {
    agent any
    stages {
        stage('Send Dockerfile to Ansible Server') {
            steps {
                echo 'Sending Dockerfile to Ansible server...'
                // Using the sshagent to authenticate with the private SSH key stored in Jenkins
                sshagent(credentials: ['ansible-ssh-key']) {
                    // SCP command to send the Dockerfile
                    sh 'scp Dockerfile ansible@192.168.1.10:/home/ansible/'
                }
            }
        }
    }
}
