pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        pip '''
          ansible --version
          ansible-playbook --version
          ansible-galaxy --version
        '''
      }
    }
  }
}
