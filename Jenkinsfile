pipeline {
    agent any
    
    stages {
        stage("Pull") {
            steps {
                git 'https://github.com/rajatpzade/studentapp.ui.git'
            }
        }
        
        stage("Build") {
            steps {
                sh '/opt/maven/bin/mvn clean package'
            }
        }
        
        stage("Test") {
            steps {
                withSonarQubeEnv('sonar') {
                    sh ' /opt/maven/bin/mvn sonar:sonar '
                }
            }
        }
        
        stage("Deploy") {
            steps {
                echo "Deployed Code"
            }
        }
    }
}