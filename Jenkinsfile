pipeline {
  agent {
    docker {
      image 'maven-git'
      args '-v /var/services/homes/Myote/.m2:/root/.m2'
    }
  }
  
  stages {
	stage('prepare') { steps { ciSkip action: 'check' } }

    stage('Build') { steps { sh 'mvn -B -DskipTests clean package' } }
}

  post { always { ciSkip action: 'postProcess' } }

}

/* docker create -u root -p 4070:8080 -p 50000:50000 -v /volume1/homes/Myote/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --name jenkins jenkinsci/blueocean */