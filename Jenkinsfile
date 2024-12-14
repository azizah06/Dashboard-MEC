pipeline {
 agent any
 stages {
 stage('Clone Repository') {
 steps {
git branch: 'patch-1', credentialsId: 'azizah', url: 'https://github.com/JunandaDeyastusesa/Dashboard-MEC-1.git'
 }
 }
 stage('Install Dependencies') {
 steps {
 sh 'ansible-galaxy install -r requirements.yml'
 }
 }
 stage('Run Ansible Playbook') {
 steps {
 ansiblePlaybook credentialsId: 'azizah', inventory: 'hosts', playbook:
'playbooks/mariadb.yml'
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
