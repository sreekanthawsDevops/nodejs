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

        stage("Build Image"){
            steps{
                sh 'sudo docker build -t my-node-app:1.0 .'
            }
        }
    }
}
