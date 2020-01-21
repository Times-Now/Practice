pipeline {
  agent any
  tools {
    maven 'maven-3.6.1'
    jdk 'java-1.8'
  }
  stages {
    stage('Preparation') {
      steps{
        deleteDir()
        //sh 'git clone git@github.com:opengeospatial/[TEST_SUITE_ID].git .'
          sh 'git clone https://github.com/Times-Now/Practice.git .'
      }
    }
    //stage('Release') {
     // steps{
       // sh 'mvn --version'
        //sh 'mvn -Dresume=false -DdryRun=true release:prepare -Psign-artifacts-with-ogc,integration-tests,docker -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}'
        //sh 'mvn -Dresume=false release:prepare release:perform -Psign-artifacts-with-ogc,integration-tests,docker -DreleaseVersion=${releaseVersion} -DdevelopmentVersion=${developmentVersion}'
      //}
    }
    //stage('Publication of site') {
     // steps{
       // sh 'mvn --version'
       // sh 'git checkout ${releaseVersion}'
       // sh 'mvn clean install site site:stage scm-publish:publish-scm'
      //}
    }
    //stage('Results') {
     // steps{
      //  archive 'target/*'
      //}
    //}
 // }
}
