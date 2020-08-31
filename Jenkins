pipeline {
         agent any
         stages {
                 stage('One') {
                 steps {
                     sh 'javac Tester.java'
                     echo "Compling....."
                 }
                 }
                 stage('Two') {
                 steps {
                    input('Do you want to proceed?')
                 }
                 }
                 stage('Three') {
                 when {
                       not {
                            branch "master"
                       }
                 }
                 steps {
                          sh 'java Tester'
                       echo "Hello Jenkins"
                 }
                 }
                 stage('Four') {
                 parallel { 
                            stage('Unit Test') {
                           steps {
                                echo "Running the unit test..."
                           }
                           }
                            stage('Integration test') {
                                steps {
                                echo "Running the integration test..."
                              }
                           }
                           }
                           }
              }
}
