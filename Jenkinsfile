pipeline {
	agent any
	stages {
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
