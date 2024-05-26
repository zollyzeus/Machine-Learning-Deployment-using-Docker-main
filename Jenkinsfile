#!groovy
pipeline {
    agent any

    stages {
        stage('Init') {
            steps {
                    dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    //bat 'docker stop $(docker ps -q)'
                }
            }
        }
        stage('Clone Git Repository') {               
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    bat 'git pull origin b1'    
                }
            }
        } 
        stage('Build Docker Image') {         
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block                    
                    bat 'docker build -t zollyzeus/mlproject:latest .'
                }
            }
        }   
        stage('Push Docker Image') {         
            steps {       
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    bat 'docker push zollyzeus/mlproject:latest'
                }
            }
        }        
    }
}