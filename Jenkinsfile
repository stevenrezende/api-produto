pipeline {
    agent any

    stages {
        stage('Import Standard Pipeline') {
            steps {
                script {
                    // Checkout the repository containing the common pipeline script
                    checkout([
                        $class: 'GitSCM',
                        branches: [[name: '*/main']],
                        userRemoteConfigs: [[
                            url: 'https://github.com/stevenrezende/gatorpipeline.git',
                            credentialsId: 'github_login'
                        ]]
                    ])
                }
            }
        }
        stage('Execute Common Pipeline') {
            steps {
                script {
                    // Log para confirmar o checkout do repositório
                    echo 'Repositório gatorpipeline foi clonado com sucesso.'

                    // Load and execute the common pipeline script
                    def commonPipeline = load 'commonPipeline.groovy'
  
                    // Executa o método executePipeline no commonPipeline
                    commonPipeline.executePipeline()
                }
            }
        }
        stage('Stage exclusivo 1'){
            steps{
                echo "Esse foi o stage1 exclusivo deste repositório"
            }
        }

        stage('Stage exclusivo 2'){
            steps{
                echo "Esse foi o stage2 exclusivo deste repositório"
            }
        }

    
    }
}