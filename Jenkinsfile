// Jenkinsfile para pipeline que importa a pipeline padrão
pipeline {
    agent any

    stages {
        stage('Import Standard Pipeline') {
            steps {
                // Clonar o repositório contendo a pipeline padrão
                git url: 'https://github.com/stevenrezende/gatorpipeline.git', branch: 'main'

                // Carregar e executar o Jenkinsfile padrão
                load 'gatorpipeline/Jenkinsfile'
            }
        }
    }
}
