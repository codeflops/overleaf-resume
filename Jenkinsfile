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
				dropbox cleanRemote: true, configName: 'My Resume', remoteDirectory: '/', sourceFiles: '*.*'
			}
		}
	}
}



