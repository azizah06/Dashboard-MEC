pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        powershell '''
          ansible --version
          ansible-playbook --version
          ansible-galaxy --version
        '''
      }
    }
  }
}
