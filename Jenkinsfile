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
    }}}
