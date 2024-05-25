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
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    withEnv ( ['JENKINS_NODE_COOKIE=do_not_kill'] ){
                        bat 'apprun.bat'
                    }
                }
            }
        }
    }
}



#!groovy

pipeline {
    agent any

    stages {
        stage('Prep') {
            steps {
            dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') 
            }
        }
        stage('Clone repository') {               
             
            sh 'git pull origin b1'
        } 
        stage('Build image') {         
       
            sh 'docker build -t zollyzeus/mlproject:latest .'
        }   
        stage('Push image') {         
       
            sh 'docker push zollyzeus/mlproject:latest'
        }
        stage('Run image') {         
       
            sh 'docker run -p 5000:5000 zollyzeus/mlproject'
        }
    }
}



        stage('Run image') {         
            steps {
                dir('D:\\CDAC\\AI_Trends\\Docker_Projects\\Machine-Learning-Deployment-using-Docker-main') {
                    // some block
                    withEnv ( ['JENKINS_NODE_COOKIE=do_not_kill'] ){
                        bat 'docker run -p 5000:5000 zollyzeus/mlproject'
                    }
                }
            }
        }
		
		//git branch: 'b1', changelog: false, credentialsId: 'a668bc5a-8e4d-424d-8aa3-2a65a4236992', url: 'https://github.com/zollyzeus/Machine-Learning-Deployment-using-Docker-main.git'