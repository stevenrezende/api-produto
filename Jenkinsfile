// Jenkinsfile para pipeline que importa a pipeline padrão
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
                    // Load and execute the common pipeline script
                    def commonPipeline = load 'Jenkinsfile'
                    commonPipeline()
                }
            }
        }
    }
}
