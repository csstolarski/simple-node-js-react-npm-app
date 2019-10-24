pipeline{
    agent {
        docker {
            image 'node:7-alpine'
            args '-p 3000:3000'
        }
    }
    stages{
        stage('check-version'){
            steps{
                sh 'node --version'
                sh 'npm --version'
            }
        }
        stage('install dependencies'){
            steps{
                sh 'npm install'
            }
        }
        stage('test-run'){
            steps{
                sh 'npm start'
                input message: "done using the site?"
            }
        }
        stage('close-node'){
            steps{
                sh 'npm stop'
            }
        }
    }
}
