pipeline {
    agent any
    stages {
        stage('Git Checkout') {
            steps {
                echo 'Cloning repository...'
                checkout scm
            }
        }
        stage('Sending Dockerfile to Ansible Server') {
            steps {
                echo 'Sending Dockerfile to Ansible server...'
                // Menggunakan sshagent untuk autentikasi SSH dengan private key yang disimpan di Jenkins Credentials
                sshagent(credentials: ['ansible-ssh-key']) {
                    // Perintah SCP untuk mengirim Dockerfile ke server Ansible
                    sh 'scp Dockerfile ansible@192.168.1.10:/home/ansible/'
                }
            }
        }

        stage('Docker Build Image') {
            steps {
                echo 'Building Docker image...'
                // Perintah build Docker
            }
        }
        stage('Push Docker Image to DockerHub') {
            steps {
                echo 'Pushing Docker image to DockerHub...'
                // Perintah untuk push Docker image
            }
        }
        stage('Copy Files to Kubernetes Server') {
            steps {
                echo 'Copying files to Kubernetes server...'
                // Perintah untuk copy file
            }
        }
        stage('Kubernetes Deployment using Ansible') {
            steps {
                echo 'Deploying using Ansible...'
                // Perintah untuk deploy menggunakan Ansible
            }
        }
    }
}
