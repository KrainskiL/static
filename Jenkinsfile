pipeline {
	agent any
	stages {
		stage('Lint HTML'){
            steps {
                sh 'tidy -q -e *.html'
            }
        }
        stage('Upload to AWS'){
            steps{
                withAWS(credentials:'aws-static') {
                    retry(3) {
                        s3Upload(file:'index.html', bucket:"lk-jenkins-udacity", path:'index.html')
                    }
                }
            }
        }
	}
}
