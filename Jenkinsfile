node {
  stage('Git')  {
    git branch: 'main', url: 'https://github.com/spring-projects/spring-petclinic.git'      
  }
  stage('Build')  {
    bat 'mvn package'      
  }
 stage('Artifact') {
archiveArtifacts artifacts: 'target/spring-petclinic-3.3.0-SNAPSHOT.jar', followSymlinks: false
}
stage('Test Results') {
junit stdioRetention: '', testResults: 'target/surefire-reports/*.xml'
}
   
}