pipeline{
    agent any

    tools {
        maven 'Maven'       
    }

    stages{
        stage('SCM Checkout'){
            steps{
                script{
                    gitcheckout('appgitcheckout')
            }
            
        }
        stage('maven-build'){
            steps{
                script{
                    mavenbuild('maven_build')
                }                
            }
        }
            
def appgitcheckout{
    checkout scmGit(branches: [[name: '*/pipeline']], extensions: [], userRemoteConfigs: [[credentialsId: 'github-token', url: 'https://github.com/pikaz01/java-maven-appD.git']])
}
def maven_build (String a){
    sh 'mvn ${goal}'
}
            
        // stage('sonarqube'){
        //     steps{
        //         withSonarQubeEnv("SonarQube") {
        //                 sh "${tool("Sonar 4.8")}/bin/sonar-scanner \
        //                 -Dsonar.projectKey=java-maven-app \
        //                 -Dsonar.java.binaries=target \
        //                 -Dsonar.host.url=http://13.233.160.18:9000 \
        //                 -Dsonar.login=sqp_56c17308dacebf6e90d4fadb0afc60b35056a9d5"
        //             }
        //     }
        // }
        // stage('nexus-upload'){
        //     steps{
        //         sh 'mvn -s settings.xml clean deploy'
        //     }
        // }
    }

}
