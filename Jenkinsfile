pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment{
        course = "jenkins"
    }
    stages {
        stage('Build') {
            steps {
                script{
                    sh """
                        echo "Building"
                        echo $course
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
    }
}