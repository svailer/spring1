pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build2') {
      steps {
        sh 'mvn clean install'
      }
    }

    stage('Results') {
      steps {
        junit '**/target/surefire-reports/TEST-*.xml'
        archiveArtifacts 'target/*.jar'
      }
    }

  }
  tools {
    maven 'M3'
  }
}