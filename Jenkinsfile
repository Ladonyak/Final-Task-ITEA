pipeline {
  agent {
    kubernetes {
      yaml '''
        apiVersion: v1
        kind: Pod
        metadata:
          labels:
            some-label: some-label-value
        spec:
          containers:
          - name: maven
            image: maven:alpine
            command:
            - cat
            tty: true
          - name: golang
            image: golang:1.16.5
            command:
            - cat
            tty: true
        '''
    }
  }

  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn -version'
        }
        container('golang') {
          sh 'go version'
        }
      }
    }
    stage('Install Git') {
      steps {
        container('golang') {
          sh '''
          apt update
          apt install git
          '''
        }
      }
    }
    stage('Get a Golang project') {
      steps {
        container('golang') {
             sh '''
             mkdir -p /go/src/github.com
             cd /go/src/github.com
             git clone 'https://github.com/Ladonyak/Final-Task-ITEA.git'
             ls
             go version
             
             cat ./Final-Task-ITEA/2_application/server.go
             
             go run ./Final-Task-ITEA/2_application/server.go
             '''
        }
      }
    }
  }
}
