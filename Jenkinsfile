pipeline {
    agent any

    parameters {
        choice(
            name: 'ENVIRONMENT',
            choices: ['dev', 'staging', 'prod'],
            description: 'Target environment'
        )
        booleanParam(
            name: 'DRY_RUN',
            defaultValue: true,
            description: 'Run in dry-run mode?'
        )
    }

    stages {
        stage('Deploy') {
            steps {
                echo "Deploying to: ${params.ENVIRONMENT}"
                echo "Dry run: ${params.DRY_RUN}"
            }
        }
    }

    post {
        success { echo 'Pipeline succeeded!' }
        failure  { echo 'Pipeline failed!' }
    }
}
