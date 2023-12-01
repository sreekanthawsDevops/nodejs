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
                sh 'sudo apt install npm -S'
                sh 'npm run build'
            }
        }
    }
}
