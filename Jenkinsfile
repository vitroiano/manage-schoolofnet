pipeline {
    agent any
    parameters { choice(name: 'CHOICES', choices: ['build'], description: ' Teste Checkout Git into Jenkins') }
    stages {
        stage('Checkout external proj') {
            steps {
                git branch: 'master',
                credentialsId: '${git_id}',
                url: 'http://git.franciscanos.net/moodle/frontend-ead-grade-dashboard.git'

                sh "ls -lat"
                /*script {
                    if("$CHOICES".indexOf('build') != -1){
                        sh 'npm run build_prod'
                    }else{
                        sh 'echo Else'
                    }
                }*/
            }
        }
        stage('Checkout code') {
            steps {
                checkout scm
            }
        }
    }
}