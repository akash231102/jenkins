pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment{
        course = "jenkins"
    }
    options {
        timeout(time: 10, unit: 'SECONDS') 
        disableConcurrentBuild()
    }
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                        echo "Building"
                        echo $course
                        sleep 10
                        env
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