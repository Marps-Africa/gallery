pipeline{

    agent any

    tools{
        nodejs 'node'
    }
    triggers{
        githubPush()
    }
    stages{
        stage("Clone Repository!") {
            steps {
                git branch: "master", url: "https://github.com/Marps-Africa/gallery.git"
            }
        }
        stage('Install Dependencies'){
            steps{
                echo 'Installing Dependencies'
                sh 'npm install'
            }
        }
        stage('Run Tests'){
            steps{
                echo 'Running Tests'
                sh 'npm test'
            }
        }
    }
}