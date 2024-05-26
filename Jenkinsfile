#!groovy
pipeline {
    agent any

    stages {
        stage('Prep') {
            steps {
                    dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    pwd()
                    //bat 'docker stop $(docker ps -q)'
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
    }
}