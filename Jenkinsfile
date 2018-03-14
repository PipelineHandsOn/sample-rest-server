pipeline {
   agent any

   options {
      buildDiscarder(logRotator(numToKeepStr:'10'))
   }

   stages {
      stage('Build') {
         steps {
            sh 'mvn clean package'
         }
      }

   }
   stage('Development Tests') {
         when {
            beforeAgent true
            branch 'development'
         }
         steps {
            echo "Run the development tests!"
         }
      }
   stage('Masters Tests') {
         when {
            branch 'master'
         }
         steps {
            echo "Run the master tests!"
         }
      } 
}
