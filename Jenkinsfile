pipeline {
    agent any
    stages {
        stage('Send Dockerfile to Ansible') {
            steps {
                script {
                    // Ganti path private key dengan path yang sesuai
                    def scpPath = 'C:/Program Files/Git/usr/bin/scp.exe'
                    def privateKeyPath = 'C:/Users/jujoe/.ssh/id_rsa'  // Ganti dengan path yang sesuai
                    
                    // Jalankan SCP menggunakan path absolut
                    echo "Sending Dockerfile to Ansible server..."
                    sh "\"${scpPath}\" -i \"${privateKeyPath}\" Dockerfile ansible@192.168.1.10:/home/ansible/"
                }
            }
        }
    }
}
