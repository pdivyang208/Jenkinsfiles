pipeline {
    agent any
    environment {
        name = 'Divyang'
    }
    parameters {
        string(name: 'person', defaultValue: 'Divyang Prajapati', description: "Who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'City', choices: ['Jaipur','Mumbai','Pune' ], description: "")
    }
    stages {
        stage('Run A command') {
            steps {
                sh '''
                ls
                date
                pwd
                '''
                
            }
        }
        stage('Environment Variables') {
            environment {
                username = 'myusername'
            }
            steps {
                sh 'echo  "${BUILD_ID}"'
                sh 'echo  "${name}"'
                sh 'echo  "${username}"'
            }
        }
        stage('Parameters') {
            steps {
                echo 'deploy on test'
                sh 'echo "${name}"'
                sh 'echo  "${person}"'
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we Should"
            }
            
            steps {
                echo 'deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo12 'deploy on prod'
            }
        }
    }
    post{
        always { 
            echo 'I will always say Hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Successs'
        }
    }
}
