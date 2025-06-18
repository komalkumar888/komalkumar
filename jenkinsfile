pipeline {
    agent any
    parameters {
        string(name: 'BRANCH', defaultValue: 'main', description: 'Git Branch')
        choice(name: 'ENV', choices: ['dev', 'staging', 'prod'], description: 'Deployment Environment')
    }
    stages {
        stage('Checkout') {
            steps {
                git branch: "${params.BRANCH}", url: 'https://github.com/komalkumar888/komalkumar'
            }
        }
        stage('Deploy') {
            steps {
                sh "./deploy.sh --env ${params.ENV}"
            }
        }
    }
}
