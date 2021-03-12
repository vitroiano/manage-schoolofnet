pipeline {
    agent any
    parameters { choice(name: 'CHOICES', choices: ['build'], description: ' Teste Jenkins') }
    stages {
        stage('Test') {
            steps {
                script {
                    if("$CHOICES".indexOf('build') != -1){
                        sh 'node --version'
                    }else{
                        sh 'echo Else'
                    }
                }
            }
        }
    }
}