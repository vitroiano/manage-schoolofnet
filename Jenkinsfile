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
                sh "pwd"
                sh "ls -lat"
            }
        }
        stage('Build'){
            steps{
                script {
                    if("$CHOICES".indexOf('build_prod') != -1){
                        sh 'echo BUILD_PROD'
                        sh 'npm install'
                        sh 'npm run build_prod'
                    }else{
                        sh 'echo BUILD_DEV'
                        sh 'npm install'
                        sh 'npm run build_dev'
                    }
                }
            }
        }
        stage('Zip'){
            steps {
                script {
                    sh 'echo ZIP dist'
                    sh 'zip dist.zip dist'
                }
            }
        }
    }
}