pipeline {
   agent none
   stages {
      stage('Build') {
         steps {
	     def image = docker.image('blang/latex:ubuntu')
	     image.pull()
	     image.inside() {
	             sh 'xelatex sample.tex'
	     }
         }
      }
   }
}
