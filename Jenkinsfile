pipeline {
    agent any
   
    options {
        timestamps()
    }
    
    tools {
        maven 'Maven-363'
    }
    
    
    stages {
    
        stage('Maven Build') {
            steps {
                sh 'clean install package'
            }
        } // stage
    
    
    
    
    
    
    }
}
