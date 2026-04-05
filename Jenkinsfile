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
           stage('Parallel Checks') {
               parallel {
                   stage('Lint') {
                       steps {
                           echo 'Running linter...'
                           sh 'echo Lint passed'
                       }
                   }
                   stage('Test') {
                       steps {
                           echo 'Running tests...'
                           sh 'echo Tests passed'
                       }
                   }
               }
           }

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
