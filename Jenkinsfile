pipeline{
    agent any

    tools {
        maven 'Maven'       
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
                    showMavenVersion('Maven is building the appilication')
                }                
            }
        }
    }
}
 
def showMavenVersion(String a) {
        echo a
        def goal = '${params.maven_goal}'
        sh "mvn '${goal}'"
        
}
