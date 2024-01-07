pipeline {
    agent { label 'node-agent' }
    
    stages{
        stage('Code'){
            steps{
                git url: https://github.com/spdevops95/node1todo.git 
            }
        }
        stage('Build and Test'){
            steps{
                sh 'docker build . docker build -t node-todo-img:v1 .

            }
        }
        stage('Push'){
            steps{
                withCredentials([usernamePassword(credentialsId: 'pawardhiraj998@gmail.com', passwordVariable: 'pawardhiraj123', usernameVariable: 'pawar199813')]) {
        	     sh "docker login -u ${env.pawar199813} -p ${env.pawardhiraj123"
                 sh 'docker pushs pdevops95/node-todo-test:latest'
                }
            }
        }
        stage('Deploy'){
            steps{
                sh "docker-compose down && docker-compose up -d"
            }
        }
    }
}
