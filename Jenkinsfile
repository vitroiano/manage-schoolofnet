pipeline {
    agent any
    parameter {
        choice {
            name: 'build', 
            choices: [ 'build' ]
            descrition: ' Teste Build '
        }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    if("$build".indexOf('build') != -1){
                        sh 'node --version'
                    }else{
                        sh 'echo Else'
                    }
                }
            }
        }
    }
}