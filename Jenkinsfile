pipeline {
    agent any

    tools {
        gradle 'Gradle'
        jdk 'JDK'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Manasvij12/MyGradleSelenium.git'
            }
        }

        stage('Build & Test') {
            steps {
                sh 'gradle clean build'
            }
        }

        stage('Run Selenium') {
            steps {
                sh 'gradle run'
            }
        }
    }

    post {
        success {
            echo 'Build and Selenium execution successful!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}
