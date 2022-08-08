podTemplate(containers: [
    containerTemplate(
        name: 'golang', 
        image: 'golang:1.14.2', 
        command: 'sleep', 
        args: '30d'
        ),
//    containerTemplate(
//        name: 'python', 
//       image: 'python:latest', 
//        command: 'sleep', 
//        args: '30d')
  ]) {

    node(POD_LABEL) {
        stage('Get a GoLang project') {
            container('golang') {
                stage('Build a GoLang project') {
                    sh '''
                    echo "GoLang build"
                    '''
                }
            }
        }

//        stage('Get a Python Project') {
//            container('python') {
//                stage('Build a Go project') {
//                   sh '''
//                    echo "Go Build"
//                    '''
//                }
//            }
//        }

    }
}
