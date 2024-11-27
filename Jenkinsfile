pipeline {
    agent any

    stages {
        stage("GetProject"){
            steps{
                git 'https://github.com/Quazbickie/ryankspetitions.git'
            }
        }
        stage("Build"){
            steps{
                sh "mvn clean:clean"
                sh "mvn dependency:copy-dependencies"
                sh "mvn compiler:compile"
            }
        }
        stage("Exec"){
            steps{
                sh 'mvn spring-boot:run -Dspring-boot.run.arguments="--server.port=8081"'
            }
        }
    }
}