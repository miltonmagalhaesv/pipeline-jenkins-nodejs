pipeline {
    agent any
 
    stages {
        stage('Checkout') {
            steps {
                echo 'Buscando o coqdigo do repositório...'
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                echo ' Instalando dependências do projeto...'
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
