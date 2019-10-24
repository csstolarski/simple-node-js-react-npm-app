pipeline{
    agent {
        docker {image 'node:7-alpine'}
    }
    stages{
        stage('check-version'){
            steps{
                sh 'node --version'
            }
        }
        stage('install dependencies'){
            steps{
                sh 'node install'
            }
        }
        stage('test-run'){
            steps{
                sh 'node start'
                input message: "done using the site?"
            }
        }
        stage('close-node'){
            steps{
                sh 'node stop'
            }
        }
}
