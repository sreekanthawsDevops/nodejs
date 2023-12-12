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
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage("scp"){
            steps{
                sh 'sudo bash /home/ubuntu/scripts/scp.sh'
            }
        }
        stage("deploy"){
            steps{
                sh '''ssh -T -o StrictHostKeyChecking=no ubuntu@35.173.180.82 <<EOF
                        #!/bin/bash
                        set -x
                        sudo bash /home/ubuntu/scripts/deploy.sh
                        exit
                        EOF
                '''
            }
        }
    }
}
