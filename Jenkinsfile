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
				sh 'xelatex -output-directory=${PWD} sample.tex'
			}
		}
		stage('Deliver') {	
			agent any
			steps {
				dropbox cleanRemote: true, configName: 'My Resume', remoteDirectory: '/', sourceFiles: '*.pdf'
			}
		}
	}
}




