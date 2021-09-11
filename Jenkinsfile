pipeline {
    agent any
    stages {
        stage ('Test data preparation') {

            steps {
                withMaven(maven : 'Maven setup') {
                
                    bat 'mvn -f pom.xml "-Dcucumber.options=--tags '@TestData'" test'
                    
                }
            }
        }
        stage ('Test case execution') {

            steps {
                withMaven(maven : 'Maven setup') {
                
                    bat 'mvn -f pom.xml -Dcucumber.options=--tags '@sanity' test'
                    
                }
            }
        }
        
    }
}