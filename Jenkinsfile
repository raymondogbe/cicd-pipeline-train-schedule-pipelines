pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/raymondogbe/cicd-pipeline-train-schedule-pipelines']]])
            }
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
