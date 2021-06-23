pipeline {
    agent any
    stages {
        stage('build'){
            steps{
                echo 'building ...'
                sh ls
            }
        }
        stage('test'){
            steps{
                echo 'testing ...'
                sh gradle --version
            }
        }
        stage('deploy'){
            steps{
                echo 'deploy ...'
            }
        }
    }
}
post {
    always {
        echo "finished"
    }
    success{
        mail to: 'team@example.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with ${env.BUILD_URL}"
    }
}