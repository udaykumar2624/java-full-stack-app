pipeline{
    agent{
        label 'agent'
    }
    
    stages{
        stage('checkout'){
            steps{
                git 'https://github.com/udaykumar2624/java-full-stack-app.git'
            }
        }
        stage('stop containers'){
            steps{
                sh '''
                    docker-compose stop
                '''
            }
        }
        stage('clear containers'){
            steps{
                sh '''
                    echo y | docker system prune -a
                '''
            }
        }
        stage('containers'){
            steps{
                sh '''
                    docker-compose up -d
                '''
            }
        }
        stage('result'){
            steps{
                echo "successfully deployed application"
            }
        }
        stage('clear unwanted containers'){
            steps{
                sh '''
                    echo y | docker system prune -a
                '''
            }
        }
    }
}
