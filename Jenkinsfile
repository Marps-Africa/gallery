pipeline{
     agent any
     tools{
          nodejs 'node'
     }
     stages{
          stage('git clone'){
               steps{
                    git branch: 'master' , url: 'https://github.com/Marps-Africa/gallery.git'
               }
          }
          stage('Installing dependencies!'){
               steps{
                    sh 'npm install'
               }
          }
          stage('Testing repository!'){
               steps{
                    sh 'npm test'
               }
          }
     }

}