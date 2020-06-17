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
                sh 'mvn clean install package'
            }
        } // stage
        
        
        stage('Transfering Artifact to Tomcat-Server') {
            steps {
                    sshPublisher(publishers: [sshPublisherDesc(configName: 'Tomcat-Server', 
                                              transfers: [sshTransfer(cleanRemote: false, excludes: '', 
                                              execCommand: '', 
                                              execTimeout: 120000, 
                                              flatten: false, 
                                              makeEmptyDirs: false, 
                                              noDefaultExcludes: false, 
                                              patternSeparator: '[, ]+', 
                                              remoteDirectory: '/opt/tomcat85/webapps', 
                                              remoteDirectorySDF: false, 
                                              removePrefix: 'webapp/target', 
                                              sourceFiles: 'webapp/target/webapp.war')], 
                                              usePromotionTimestamp: false, 
                                              useWorkspaceInPromotion: false, verbose: false)])
            }     
        }
    
    
    
    
    
    
    }
}
