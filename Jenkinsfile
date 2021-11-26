pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {

		readMavenPom file: './pom.xml'
		/* buildPlugin() */
		}
	  }
	}
}
	
