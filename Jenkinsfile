pipeline {
    agent { label 'testenv'}
    stage {
        stage('git'){
            steps {
                git branch 'declarativepipeline', url: 'https://github.com/dcherif/game-of-life.git'
            }
        }
        stage('compile') {
            steps{
                sh 'mvn clean package'
            }
        }
    }
}