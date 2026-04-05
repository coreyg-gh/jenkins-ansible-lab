    @Library("my-shared-lib") _

    pipeline {
        agent any

        stages {
            stage('Use Library') {
                steps {
                    sayHello('TestName')
                }
            }
        }
    }
