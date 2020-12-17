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
                     
              stage('Sonarcloud'){
                  steps {
                      //sh 'wget https://binaries.sonarsource.com/Distribution/sonar-scanner-cli/sonar-scanner-cli-4.4.0.2170-linux.zip'
                      //sh 'unzip sonar-scanner-cli-4.4.0.2170-linux.zip'
                      sh 'echo $HOME'
                      sh 'pwd'
                      sh 'export PATH=$PATH:$HOME/sonar/sonar-scanner-4.4.0.2170-linux/bin'
                      sh 'sonar-scanner'
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
                     sh 'npm install'
                     sh 'npm install -D esm'
                     sh 'npm install babel-preset-es2015 --save-dev'
                     sh 'npm --version'
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
