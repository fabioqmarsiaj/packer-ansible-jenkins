pipeline {
    agent any
    options {
        skipStagesAfterUnstable()
    }
    stages {
        stage('Build') {
            steps {
                git url: 'https://github.com/fabioqmarsiaj/temafinal1-cloud'
                sh('./gradlew clean build')
            }
        }
    }
}