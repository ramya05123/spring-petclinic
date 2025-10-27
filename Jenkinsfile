pipeline{
    
    agent any
    
    stages{
        stage('clone the project'){
            
            steps{
                git branch: 'feature/2025.10.16', url: 'https://github.com/ramya05123/spring-petclinic.git'
            }
        }
         stage('build'){
            
            steps{
                bat 'mvn clean'
            }
        }
         stage('test'){
            
            steps{
                bat 'mvn test'
            }
        }
         stage('generate the Junit test results'){
            
            steps{
                junit 'target/surefire-reports/*.xml'
            }
        }
        stage('generate artifacts'){
            
            steps{
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}