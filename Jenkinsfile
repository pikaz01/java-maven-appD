pipeline{
    agent any

    tools {
        maven 'Maven'       
    }

    parameters {
    string(name: 'maven_goal')
  }
  try{
        stages{

            stage('SCM Checkout'){
                steps{
                    checkout scmGit(branches: [[name: '*/pipeline']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/pikaz01/java-maven-appD.git']])
                    sh "echo ${params.maven_goal}"

                }
                
            }
            stage('maven-build'){
                steps{
                    script{ 
                        sh "pwd"
                        showMavenVersion('Maven is building the appilication', maven_goal)
                    }                
                }
            }
        }
  }
  catch (err){
    currentBuild.result= 'failed'
  }
}

def showMavenVersion(String a, String goal) {
        echo a
        
        sh "mvn ${goal}"
        
}
