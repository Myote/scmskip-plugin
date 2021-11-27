pipeline {
    agent {
        docker {
            image 'maven:3-alpine' 
            args '-v /var/services/homes/Myote/.m2:/root/.m2' 
        }
    }
    stages {
        stage('Build') { 
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
	}
}
	
/* docker run --rm -u root -p 8080:8080 -v /volume1/homes/Myote/jenkinsci:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkinsci/blueocean */
