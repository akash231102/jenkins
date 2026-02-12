pipeline {
    // pre-build
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment{
        course = "jenkins"
    }
    options {
        timeout(time: 10, unit: 'MINUTES') 
        disableConcurrentBuilds()
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    // this is build section
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                        echo "Building"
                        echo $course
                        sleep 10
                        env
                        echo "Hello ${params.PERSON}"
                        echo "Biography: ${params.BIOGRAPHY}"
                        echo "Toggle: ${params.TOGGLE}"
                        echo "Choice: ${params.CHOICE}"
                        echo "Password: ${params.PASSWORD}"
                    """
                }
            }
        }
        stage('Test') {
            steps {
                script{
                    sh """
                        echo "Testing"
                    """
                }
            }
        }
        stage('Deploy') {
            steps {
                script{
                    sh """
                        echo "Deploying"
                    """
                }
            }
        }
    }
    post{
        always{
            echo " this will run on both "
            cleanWs()
        }
        success{
            echo "it is success "
        }
        failure{
            echo " it is failed "
        }
        aborted{
            echo "is is aborted"
        }
    }
}