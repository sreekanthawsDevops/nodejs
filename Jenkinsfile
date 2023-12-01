pipeline {
    agent any
    stages{
        stage("checkout"){
            steps{
                checkout scm
            }
        }

        stage("Build"){
            steps{
                sh 'sudo apt install npm'
                sh 'npm run build'
            }
        }
    }
}
