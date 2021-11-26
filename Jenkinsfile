pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Build') {
      steps {

		readMavenPom file: '/volume1/homes/Myote/git/scmskip-plugin/pom.xml'
		/* buildPlugin() */
		}
	  }
	}
}
	
