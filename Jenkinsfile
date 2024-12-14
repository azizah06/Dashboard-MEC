pipeline {
 agent any
 stages {
 stage('Install Dependencies') {
 steps {
 sh 'ansible-galaxy install -r requirements.yml'
 }
 }
 stage('Run Ansible Playbook') {
 steps {
 ansiblePlaybook credentialsId: 'your-credentials-id', inventory: 'hosts', playbook:
'mariadb.yml'
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
