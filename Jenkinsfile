pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh "./gradlew build --no-daemon"
            }
        }
        stage('archive') {
            steps {
                archiveArtifacts 'dist/trainSchedule.zip'
            }
        }
    }
}
