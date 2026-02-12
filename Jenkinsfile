pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying'
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