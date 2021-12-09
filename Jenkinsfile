pipeline {
  agent {
    docker {
      image 'maven-git'
      args '-v /var/services/homes/Myote/.m2:/root/.m2'
    }

  }
  stages {
    stage('ciSkip') {
      steps {
        warnError(message: 'NOT_BUILT')
        ciSkip(action: 'check')
      }
    }

    stage('Build') {
      steps {
        sh 'mvn -B -DskipTests clean package'
      }
    }

  }
  post {
    always {
      ciSkip(action: 'postProcess')
    }

  }
}