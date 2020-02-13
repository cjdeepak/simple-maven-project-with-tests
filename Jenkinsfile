pipeline {
  agent any
  tools {
        maven 'apache-3.3.3' 
        jdk 'jdk-1.8.221'
    }
  stages {
    stage('Run') {
      steps {
        script {
          sh 'mvn -B -ntp -Dmaven.test.failure.ignore verify'
        }
      }
    }
  }
  post {
    success {
      junit '**/target/surefire-reports/TEST-*.xml'
    }
  }
}
