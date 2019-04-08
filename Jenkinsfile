pipeline{
    agent any

    tools {
        maven 'local-maven'
    }

    stages{
        stage("Build"){
            steps{
                bat "mvn clean package"
            }
            post{
                always{
                    echo "========always========"
                }
                success{
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
                failure{
                    echo "========A execution failed========"
                }
            }
        }
    }
}
