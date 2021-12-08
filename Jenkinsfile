pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /var/services/homes/Myote/.m2:/root/.m2'
    }
  }
  
  stages {
	stage('ciSkip') {
		steps { ciSkip action: 'check' } }
	/* stage('ciSkip') { steps { scmSkip(deleteBuild: true, skipPattern:'.*\\[ci skip\\].*') } } */

    stage('Build') { 
		when {
			environment name: env.CI_SKIP , value: 'false'
			}
		steps { sh 'mvn -B -DskipTests clean package' } 
		}
	}

  post { always { ciSkip action: 'postProcess' } }

}


/* docker create -u root -p 4070:8080 -p 50000:50000 -v /volume1/homes/Myote/jenkins:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock --name jenkins jenkinsci/blueocean */