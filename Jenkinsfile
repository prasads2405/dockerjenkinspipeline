pipeline {
  agent { dockerfile true }
  stages {
    stage('Ubuntu 16.04') {
      steps {
        sh '''
          #!/bin/bash
          echo "Inside docker container"
          cat /etc/lsb-release
        '''
      }
    }
  }
}
