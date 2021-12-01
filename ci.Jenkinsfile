//pipeline
@Library('jenkinslib') _
def build = new org.devops.build()
def deploy = new org.devops.deploy()
//env
String buildType = "${env.buildType}"
string buildshell="${env.buildshell}"
pipeline{
    agent { node { label "master"}}
    
    
    stages{

        stage("Build"){
            steps{
                script{           
                  build.Build(buildType,buildshell)  
                  //deploy.SaltDeploy("${deployHosts}","test.ping")
                    deploy.AnsibleDeploy("${deployHosts}","-m ping ")
                      }
                 }
            }
            /*
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
                  sh "export NODE_HOME=${NodeHome} && export PATH=\$NODE_HOME/bin:\$PATH && ${NodeHome}/bin/npm ${buildshell}"  
                      }
                 }
            }  */    
        }
      
}
