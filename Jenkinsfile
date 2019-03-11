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
				sh 'xelatex sample.tex'
			}
		}
		stage('Deliver') {	
			agent any
			steps {
				dropbox configName: 'My Resume', remoteDirectory: '/Resume', removePrefix: '', sourceFiles: '*.*'
			}
		}
	}
}



