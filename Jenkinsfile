pipeline {
    agent any
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: 'You can skip test step')
    }
    environment {
        NEW_VERSION = '1.3.0'
    }

    stages {
        stage("build") {
            steps {
                echo 'building the app'
                echo "building version ${NEW_VERSION}"
                # sh 'npm install'
            }
        }
        stage("test") {
            when{
                expression {
                    params.executeTests == true
                }
            }
            steps {
                echo 'testing the app'

            }
        }
        stage("deploy") {
            steps {
                echo "deploying version ${params.VERSION}"
            }
        }
    }
}
