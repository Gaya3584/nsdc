pipeline {
    agent any

    tools {
        stage('Build') {
  steps {
    bat 'node -v'
    bat 'npm -v'
    bat 'npm install'
    bat 'npm run build'
  }
}

    }

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Gaya3584/nsdc.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build React App') {
            steps {
                sh 'npm run build'
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
