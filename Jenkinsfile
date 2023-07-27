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
                // groovy_maven_script = load 'src/groovy_task'
                checkout scmGit(branches: [[name: '*/pipeline']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/pikaz01/java-maven-appD.git']])
                echo "${params.maven_goal}"
            }
            
        }
        stage('maven-build'){
            steps{
                script{
                    groovy_maven_script = load 'src/groovy_task' 
                    sh "pwd"
                    groovy_maven_script.mavenbuild('Maven is building the appilication', maven_goal)
                }                
            }
        }
        
    }
          
}
