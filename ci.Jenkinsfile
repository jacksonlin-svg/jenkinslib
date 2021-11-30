//pipeline

string buildshell="${env.buildshell}"
pipeline{
    agent { node { label "master"}}
    
    
    stages{

        stage("mavenBuild"){
            steps{
                script{
                  mvnHome = tool "maven"             
                  sh "${mvnHome}/bin/mvn ${buildshell}"  
                      }
                 }
            }
        stage("AntBuild"){
            steps{
                script{
                try{
                  AntHome = tool "ant"             
                  sh "${AntHome}/bin/ant ${buildshell}"  
                  }catch(e){
                   println(e)
                        }
                      }
                 }
            }
          stage("gradleBuild"){
            steps{
                script{
                  GradleHome = tool "gradle"             
                  sh "${GradleHome}/bin/gradle ${buildshell}"  
                      }
                 }
            }
          stage("npmBuild"){
            steps{
                script{
                  NodeHome = tool "npm"             
                  sh "${NodeHome}/bin/npm ${buildshell}"  
                      }
                 }
            }      
        }
      
}
