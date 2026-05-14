pipeline {
    agent any

    tools {
        jdk 'JDK11'
        gradle 'GRADLE'
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/gvinaygowdav-del/GradleApp.git'
            }
        }

        stage('Build') {
            steps {
                bat 'gradle build'
            }
        }
    }
}
