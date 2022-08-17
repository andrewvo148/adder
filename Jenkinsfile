pipeline {
    agent {
        docker {
            image 'python:3'
        }
    }
    stages {
        stage('Compile') {
            steps {
                sh 'python3 -m compileall adder.py'
            }
        }
        stage('Run') {
            steps {
                sh 'python3 adder.py 3 5'
                }
         }
        stage('Unit test') {
            steps {
 sh '''python3 -m pytest \
 -v --junitxml=junit.xml \
 --cov-report xml --cov adder adder.py
 '''
}
        } 
    }
}
