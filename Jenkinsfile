pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /var/services/homes/Myote/.m2:/root/.m2'
    }

  }
  stages {
    stage('prepare') {
      steps {
        ciSkip(action: 'check')
        node(label: 'master')
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