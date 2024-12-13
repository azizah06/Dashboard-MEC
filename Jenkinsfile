pipeline {
  agent any

  stages {
    stage('Hello') {
      steps {
        sh '''
          ansible --version
          ansible-playbook --version
        '''
      }
    }
  }
}
