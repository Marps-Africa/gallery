pipeline{
    agent any
    tools{
        nodejs 'node'
    }
    stages{
        stage("Clone Repository") {
            steps {
                git branch: "master", url: "https://github.com/Raddames-Tonui/gallery"
            }
        }
        stage('Install npm packages'){
            steps{
                sh 'npm install'
            }
        }
        stage('Test'){
            steps{
                sh 'npm test'
            }
        }
        stage('Build'){
            steps{
                sh 'npm run build'
            }
        }
    }
}