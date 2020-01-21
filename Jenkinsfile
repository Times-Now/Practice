#!groovy
docker.image('cloudbees/java-build-tools:0.0.6').inside {

    checkout([$class: 'GitSCM', 
      branches: [[name: '*/master']], 
      extensions: [
          /* [$class: 'UserIdentity', email: 'cleclerc@cloudbees.com', name: 'Jenkins as a Service'], */
          [$class: 'WipeWorkspace'], 
          [$class: 'LocalBranch', localBranch: 'master']], 
      userRemoteConfigs: [[credentialsId: 'GithubID', url: 'https://github.com/Times-Now/Practice.git']]])
    
    stage 'Release'
    def mavenSettingsFile = "${pwd()}/.m2/settings.xml"
    wrap([$class: 'ConfigFileBuildWrapper',
        managedFiles: [
            [fileId: 'maven-settings-for-my-spring-boot-app', targetLocation: "${mavenSettingsFile}"]]]) {

        sh """
        git config --global user.email suneha2794@gmail.com
        git config --global user.name Suneha27
        """
        sh "mvn -s ${mavenSettingsFile} --batch-mode release:clean release:prepare release:perform"

        step([$class: 'ArtifactArchiver', artifacts: 'target/checkout/target/*.jar'])

    }
}
