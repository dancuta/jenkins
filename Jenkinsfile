pipeline {
    agent any
    
    // we can specify Agent's name instead of any
   
    stages {
        
        stage('Git checkout') {
            steps {
                echo 'Git checkout https://github.com/dancuta/jenkins.git'
                git branch: 'main', url: 'https://github.com/dancuta/jenkins.git'
                
            }
        }
        
        stage('Build') {
            steps {
                echo 'Start Build stage ..';
                bat 'build.bat'
            }
        }
        

        
        stage('JUnit') {
            steps {
                echo 'JUnit passed successfully!'
            }
        }
        
        
        stage('Quality Gate') {
            steps {
               echo 'Start Quality Gate stage ..';
               bat 'quality.bat'
            }
        }
    }
    
    post{
        always{
             echo 'This will always run.'
        }
        success{
             echo 'This will run on success.'
        }
        failure{
             echo 'This will run on failure.'
        }
        unstable{
             echo 'This will run if unstable.'
        }
        changed{
             echo 'This will run on change.'
        }
        
        
    }
    
    
}
