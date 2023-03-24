pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo "Building the project"
                sh 'javac HelloWorld.java'
            }
        }
        stage('Run') {
            steps {
                echo "Running the project"
                script {
                    def output = sh(returnStdout: true, script: "java HelloWorld").trim()
                    echo "${params.GREETING}"
                    assert output == params.GREETING
                }
            }
        }
    }
}
