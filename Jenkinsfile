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
		stage('Deploy') {
			agent any			
			steps {
				dropbox configName: 'My Resume', remoteDirectory: '/Resume', removePrefix: '', sourceFiles: 'overleaf-resume_master/sample.pdf'
			}
		}
	}
}



