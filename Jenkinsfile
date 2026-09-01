pipeline {
    agent any

    environment {
        PATH = "/opt/homebrew/bin:/usr/local/bin:${env.PATH}"
    }
    
    stages {
        stage('Install Dependencies') {
            steps {
                echo ' Instalando dependências do projeto...'
                sh 'which node'
                sh 'which npm'
                sh 'node -v'
                sh 'npm -v'
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                echo 'Executando build...'
                sh 'npm test'
            }
        }

        stage('Test') {
            steps {
                echo 'Executando testes...'
                sh 'npm test'
            }
        }
    }

    post {
        success {
            echo 'Pipeline executado com sucesso!'
        }
      
        failure {
            echo 'Pipeline falhou. Verifique os logs acima.'
        }
    }
}
