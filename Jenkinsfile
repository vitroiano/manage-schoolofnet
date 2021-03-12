pipeline {
    agent any
    parameters { choice(name: 'CHOICES', choices: ['build_prod', 'build_dev'], description: ' Teste Checkout Git into Jenkins') }
    stages {
        stage('Checkout external proj') {
            steps {
                git credentialsId: 'git_id',
                url: 'http://git.franciscanos.net/moodle/frontend-ead-grade-dashboard.git',
                branch: 'master'

                sh "git checkout master"
                sh "ls -lat"
                sh 'pwd'
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
        stage('Build'){
            steps{
                script {
                    if("$CHOICES".indexOf('build_prod') != -1){
                        sh 'echo ########### BUILD_PROD ###########'
                        sh 'npm run build_prod'
                    }else{
                        sh 'echo ELSE'
                    }
                }
            }
        }
    }
}