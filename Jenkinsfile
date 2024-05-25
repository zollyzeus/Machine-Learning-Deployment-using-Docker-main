#!groovy

pipeline {
    agent any

    stages {
        stage('Prep') {
            steps {
                    dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    pwd()
                    
                }
            }
        }
        stage('Clone repository') {               
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    bat 'git pull origin b1'    
                }
            }
        } 
        stage('Build image') {         
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    //bat 'docker stop $(docker ps -q)'
                    bat 'docker build -t zollyzeus/mlproject:latest .'
                }
            }
        }   
        stage('Push image') {         
            steps {       
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    bat 'docker push zollyzeus/mlproject:latest'
                }
            }
        }
        stage('Run image') {         
            options {
              timeout(time: 2, unit: 'MINUTES')   // timeout on this stage
            }
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    withEnv ( ['JENKINS_NODE_COOKIE=do_not_kill'] ){
                        bat 'docker run -p 5000:5000 zollyzeus/mlproject'
                    }
                }
            }
        }
    }
}
