pipeline {
  agent {
    kubernetes {
      defaultContainer 'maven'
      yamlFile '1_infrastructure/wordpress/kustomization.yaml'
    }
  }

  stages {
    stage('Run maven') {
      steps {
        sh 'mvn -version'
      }
    }
  }
}
