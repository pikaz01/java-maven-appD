pipeline{
    agent any

    tools {
        maven 'Maven'       
    }

    parameters {
    string(name: 'maven_goal')
    }
    stages{
        try{
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
                        mavenbuild('Maven is building the appilication', maven_goal)
                    }                
                }
            }
        }
        catch (err) {
        currentBuild.result= 'failed'
        }
    }
  
}

def mavenbuild(String a, String goal) {
        echo a
        sh "mvn ${goal}"
        
}
