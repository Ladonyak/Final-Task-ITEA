pipeline {
  agent {
    kubernetes {
      yaml '''
secretGenerator:
- name: mysql-pass
  literals:
  - password=mysql
        '''
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn -version'
        }
        container('busybox') {
          sh '/bin/busybox'
        }
      }
    }
  }
}
