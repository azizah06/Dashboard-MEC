pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        bat '''
          ansible --version
          ansible-playbook --version
          ansible-galaxy --version
        '''
      }
    }
  }
}
