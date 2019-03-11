pipeline {
	agent { 
		docker {
			image 'moss/xelatex'
			}
		}
	}	
	stages {
		stage('Build') {
			steps {
				sh 'xelatex -output-directory=${PWD} sample.tex'
			}
		}
		stage('Deliver') {	
			steps {
				dropbox cleanRemote: true, configName: 'My Resume', remoteDirectory: '/', sourceFiles: '*.pdf'
			}
		}
	}
}


