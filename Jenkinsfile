pipeline {
	agent none
	stages {
		stage('Build') {
			agent {
				docker {
					image 'moss/xelatex'
				}
			}
			steps {
				sh 'xelatex -output-directory=/var/jenkins_home/workspace/sources/ sample.tex'
			}
		}
		stage('Deliver') {	
			agent any
			steps {
				dropbox configName: 'My Resume', remoteDirectory: '/Resume', removePrefix: '', sourceFiles: 'sources/sample.pdf'
			}
			post {
                success {
                    archiveArtifacts 'dist/sample' 
                }
            }
		}
	}
}



