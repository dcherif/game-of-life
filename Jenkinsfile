pipeline {
    agent { label 'testenv'}
    triggers { pollSCM('30 * * * 1-5')}
    stages {
        stage('git'){
            steps {
                git branch: 'declarativepipeline', url: 'https://github.com/dcherif/game-of-life.git'
            }
        }
        stage('compile') {
            steps{
                sh 'mvn clean package'
            },
            post {
                always {
                    jiraSendBuildInfo branch: '', site: 'dcheriftech.atlassian.net'
                }
            }
        }
    }
}