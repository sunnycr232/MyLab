pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage3 : Publish the source code to Sonarqube
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.8.war', type: 'war']], credentialsId: '24153f1b-eff9-4f07-8740-ba8e200dd5cc', groupId: 'com.vinaysdevopslab', nexusUrl: '10.0.121.254:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'snap', version: '0.0.8'
                }

            }
        }

        
        
    }

}
