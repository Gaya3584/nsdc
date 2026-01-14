pipeline {
    agent any

    stages {
        stage('Check Node & NPM') {
            steps {
                bat 'node -v'
                bat 'npm -v'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('welcome.react') {
                    bat 'npm install'
                }
            }
        }

        stage('Build React App') {
            steps {
                dir('welcome.react') {
                    bat 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'React build successful 🎉'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
