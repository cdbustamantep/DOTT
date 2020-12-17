pipeline {
    agent any
    environment { 
        EXECUTE = 'true'
    }
      tools {nodejs "node"}
    
         stages {
             stage('Test1') {
                 steps {
                     sh 'node --version'
                 }
             }
             stage('Cloning Git') {
                steps {
                    git 'https://github.com/cdbustamantep/DOTT'
                }
             }
             stage('Install Dependencies'){
                 steps {
                     sh 'echo "hola"'
                     sh 'npm install -D esm'
                     sh 'npm install babel-preset-es2015 --save-dev'
                     sh 'npm --version'
                }
              }
        
              stage('Sonarcloud'){
                  steps {
                     sh 'echo "Sonarstage"'
                }
            }
               stage ('Test2') {
                   when {
                       expression { env.EXECUTE == 'true' }
                  }
                   steps {
                   sh 'pwd'
                   sh 'npm test'
            }
        }
    }
}
