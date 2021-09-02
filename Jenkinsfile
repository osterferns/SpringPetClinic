pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        steps('Checkout'){
            steps{
                git branch: 'main' , url: 'https://github.com/osterferns/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        
        }
        stage('Package'){
            steps{
                sh 'mvn package' 
                
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclarativePipeline' 
                
            }
        }
        
    }
}
