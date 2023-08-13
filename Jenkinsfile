@Library('jenkins-shared-library') _
pipeline{
  agent any
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
