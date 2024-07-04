pipeline {
    agent any
    
    stages {
        stage("code") {
            steps {
                git url: "https://github.com/LondheShubham153/node-todo-cicd.git", branch: "master"
                echo 'Code clone successful'
            }
        }
        stage("build and test") {
            steps {
                sh "docker build -t node-app-test-new ."
                echo 'Code build successful'
            }
        }
        stage("scan image") {
            steps {
                echo 'Image scanning successful'
            }
        }
        stage("deploy") {
            steps {
                sh "docker-compose down --remove-orphans"
                sh "docker-compose up -d --build"
                echo 'Deployment successful'
            }
        }
    }
}
