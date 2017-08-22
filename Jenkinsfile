pipeline {
  agent {
    node {
      label 'master'
    }
  }
 
stages {
  stage('Prepare') {
    steps {
      script {
        def artifactDownloadURL = "hello"
        echo "${artifactDownloadURL}"
      }
      echo "${BUILD_NUMBER}"
      sh "env"
    }
  }
}
  post {
    always {
      deleteDir()
    }
  }
}
