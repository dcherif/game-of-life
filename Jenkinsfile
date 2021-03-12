pipeline {
    agent { label 'testenv'}
    triggers { pollscm('30 * * * 1-5')}
    stages {
        stage('git'){
            steps {
                git branch: 'declarativepipeline', url: 'https://github.com/dcherif/game-of-life.git'
            }
        }
        stage('compile') {
            steps{
                sh 'mvn clean package'
            }
        }
    }
}