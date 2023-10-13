pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
               checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'appBankcreds', url: 'https://github.com/Etech-Team-007/multijob-demo.git']])
            }
        }

        stage('1-Ida') {
            steps {
                echo "Ida Nzengung"
            }
        }

        stage('2-Allon') {
            steps {
               echo "Allon Jose"
            }
        }

        stage('3-Terence') {
            when {
                branch 'feature/*' 
            }
            steps {
                
				sh 'git checkout develop'
                sh 'git merge ${env.BRANCH_NAME}'
                sh 'git push origin develop'
            }
        }

        stage('4-Desmond') {
            when {
                branch 'develop' 
            }
            steps {
                echo "Desmond Asonganyi"
            }
        }

        stage('5-Therese') {
            when {
                branch 'main' 
            }
            steps {
                
                sh 'git checkout main'
                sh 'git merge develop'
                sh 'git push origin main'
            }
        }

        stage('6-Jarvis') {
            when {
                branch 'main' 
            }
            steps {
                echo "Jarvis Esele"
            }
        }
    }
}
