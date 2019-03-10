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
				sh 'xelatex main.tex'
			}
		}
	}
}



