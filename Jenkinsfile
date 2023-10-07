pipeline {
    agent any
    environment {
        AWS_ACCESS_KEY_ID = 'AKIARGWR6CGSTJVCA2QY'
        AWS_SECRET_ACCESS_KEY = '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'
    }
    tools {
        git 'Default'
    }

    stages {
    
        stage('Checkout1') {
        // Checkout code from the 'main' branch
            steps{
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: 'main']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [], 
                    credentialsId: 'AWS',
                    def gitUrl = 'https://git-codecommit.ap-south-1.amazonaws.com/v1/repos/Snapcoins'
                    sh 'export AWS_ACCESS_KEY_ID=${AWS_ACCESS_KEY_ID}'
                    sh 'export AWS_SECRET_ACCESS_KEY=${AWS_SECRET_ACCESS_KEY}'   
                    sh 'git clone ${gitUrl}'
            ])
        
        }
    }
        
    
    
        /*
        stage('Checkout') {
            steps {
                git clone: credentialsId: 'Test', 'https://git-codecommit.ap-south-1.amazonaws.com/v1/repos/Snapcoins' 
                git switch main
            }
        }
        
        stage('Build') {
            steps {
                
                dir('client') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/gamer-module') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/merchant-module') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/gaming-vendor-module') {
                    bat 'npm install'
                    //bat 'npm test'
                }

                dir('servers/general-module') {
                    bat 'npm install'
                    //bat 'npm test'
                    
                }
            }
        }

        stage('Create Docker Images'){

            steps {
                dir('client') {
                    bat 'docker build -t client-image .'
                }

                dir('servers/gamer-module') {
                    bat 'docker build -t gamer-module .'
                }

                dir('servers/merchant-module') {
                    bat 'docker build -t merchant-module .'
                }
                
                dir('servers/gaming-vendor-module') {
                    bat 'docker build -t gaming-vendor-module .'
                }

                dir('servers/general-module') {
                    bat 'docker build -t general-module .'
                }
                
            }

        }
        */
    }
}
