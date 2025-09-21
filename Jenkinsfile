pipeline {
    agent any
    environment {
        NO_COLOR = 'true'
    }
    stages {
        stage('Clonar o repositório') {
            steps {
                git branch: 'main', url: 'https://github.com/carioca1965/ebac-cypress-samples.git'
            }
        }
        stage('Instalar dependências') {
            steps {
                sh '''
                    echo "Instalando dependências..."
                    npm install
                    npx cypress install
                '''
            }
        }
        stage('Executar testes') {
            steps {
                sh '''
                    echo "Executando testes Cypress..."
                    npx cypress run --headless
                '''
            }
        }
    }
}