@Library('jenkins-shared-library') _
pipeline{
  agent any
  tools {
        maven 'maven_3.9.0'       
    }
  stages{
    stage('task1'){
      steps{
        script{
          mavenbuild.maven_build()
        }
      }
    }
  }
}
