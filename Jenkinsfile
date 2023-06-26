pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                build 'https://github.com/raymondogbe/cicd-pipeline-train-schedule-pipelines'
            }
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
