pipeline
{
    agent any
    stages
    {
        stage("Clean")
        {
            steps
            {
                echo ' Hello '
                //sh ' sudo rm -rf /var/lib/jenkins/workspace/Docker/* '
                //sh ' docker stop $(docker ps -a -q) '
                //sh ' docker rm $(docker ps -a -q) '
                //sh ' docker rmi $(docker images -q) '
            }
        }
        stage("Clone")
        {   
            steps
            {
                sh ' git clone -b pooja https://github.com/poojar107/Docker-Task1_POOJA.git '
            }
        }
        stage("Build")
        {
            steps
            {
                sh ' docker build -t app /var/lib/jenkins/workspace/DOCKER/Docker-Task1_POOJA/ '
            }
        }
        stage("Run")
        {
            steps
            {
                sh '  docker run -it -d app '
            }
        }
    }
    post 
    {
        success 
        {
            echo 'Build successful!'
        }
        failure 
        {
            echo 'Build failed!'
        }
    }
} 
