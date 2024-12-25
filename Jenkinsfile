pipeline{
     agent any
     tools{
          nodejs 'node'
     }
     environment{
          RENDER_DEPLOY_HOOK = "https://api.render.com/deploy/srv-ctlslubqf0us738a94j0?key=ApO0yCCzVsA   "
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
          stage("Deploy to Render") {
            steps {
                echo 'Deploying application to Render...'
                sh "curl -X POST ${RENDER_DEPLOY_HOOK}"
            }
        }
     }
     post{
          always{
               echo 'This is the end of the pipeline!'
          }
          success{
               echo 'The pipeline has been successful'
          }
          failure{
               echo 'The pipeline has failed'
          }
          aborted{
               echo 'The pipeline has been aborted'
          }
     }

}