//pipeline
pipeline{
    agent { node { label "master"}}
    
    
    stages{

        stage("Build"){
            steps{
                script{
                  mvnHome = tool "maven"             
                  sh "${mvnHome}/bin/mvn --version"  
                      }
                 }
            }
        }
       } 
