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
			steps {
				sh 'dropbox configName: 'My Resume', remoteDirectory: '/Resume', removePrefix: '', sourceFiles: 'sample.pdf''
		}
	}
}



