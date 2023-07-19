pipeline{
    agent any

    tools {
        maven 'Maven'       
    }

    parameters {
    string(name: 'maven_goal')
  }

    stages{
        stage('SCM Checkout'){
            steps{
                checkout scmGit(branches: [[name: '*/pipeline']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/pikaz01/java-maven-appD.git']])

            }
            
        }
        stage('maven-build'){
            steps{
                script{
                    def goal = params.maven_goal
                    showMavenVersion('Maven is building the appilication', '${goal}')
                }                
            }
        }
    }
}
 
def showMavenVersion(String a, String goal) {
        echo a
        
        sh "mvn ${goal}"
        
}
