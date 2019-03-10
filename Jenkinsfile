pipeline {
	agent none
	stages {
		stage('Build') {
			agent {
				docker {
					image 'schickling/latex'
				}
			}
			steps {
				sh 'xelatex main.tex'
			}
		}
	}
}



