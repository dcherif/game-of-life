node('testenv') {
    stage('git') {
        git 'https://github.com/dcherif/game-of-life.git'
    }
    stage('build') {
        sh 'mvn clean package'
    }
    stage('testresults'){
        junit 'gameoflife-web/target/surefire-reports/*.xml'
    }
    stage('archiveartifacts'){
        archiveartifacts artifacts: 'gameoflife-web/target/*.war', followSymlinks: false
    }
}