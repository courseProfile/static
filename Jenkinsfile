pipeline {
  agent any 
  stages {
    stage('Lint HTML') {
      steps {
        sh 'tidy -q -e *.html'
      }
    }
    stage('Upload to AWS') {
      steps {
        withAWS(credentials:'aws-static	') {
            s3Upload(file:'index.html', bucket:'udacity-course-457', path:'index.html')
        }
      }
    }
  }
}
