pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello from Jenkins!'
                sh 'whoami && hostname'
            }
        }

        stage('Check Tools') {
            steps {
                sh 'python3 --version'
                sh 'ansible --version'
            }
        }
    }
}
