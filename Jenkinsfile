pipeline{
    agent any
    stages{
       stage('GetCode'){
            steps{
                git branch: 'main', url: 'https://github.com/samarthshukla18/DevOps-Project'
                echo "Get Code Completed..."
            }
         }        
       stage('Build'){
            steps{
                echo "Build started..."
                echo "Build completed..."
            }
         }
        stage('SonarQube analysis') {
//    def scannerHome = tool 'SonarScanner 4.0';
        steps{
        withSonarQubeEnv('sonarqube-server') { 
        // If you have configured more than one global server connection, you can specify its name
//      sh "${scannerHome}/bin/sonar-scanner"
        sh "mvn sonar:sonar"
    }
        }
        }
       
    }
}
