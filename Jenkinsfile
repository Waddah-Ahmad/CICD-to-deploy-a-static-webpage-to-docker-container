pipeline {
    agent any 
    stages {
        stage('build ') { 
            steps {
                echo "this is build artifacts stage where we install all the depensences and packages for the environment"
            }
        }
        stage('Test') { 
            steps {
                echo "this is test stage where we debug the software before going further"
            }
        }
        stage('Deploy') { 
            steps {
                sh 'ssh -o StrictHostKeyChecking=no jenkins@192.168.56.52 "cd CICD-to-deploy-a-static-webpage-to-docker-container; \
                //cloning the repo
                git pull origin master; \
                //docker container commands to stop and start a new container witnin any update
                docker container rm -f page1; \
                docker build -f Dockerfile --tag proj:miniproject
                docker container run -it -d --name page1 -p 8080:80 proj:miniproject
                

                
                "'
            }
        }
    }
}
