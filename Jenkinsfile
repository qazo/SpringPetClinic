pipeline{
    agent{label 'master'}
    tools{maven 'M3'}
    stages{
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/qazo/SpringPetClinic'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps{
                sh 'java -j /var/lib/jenkins/workspace/PetCLinicDeclarativePipeline/target/*.jar'
            }
        }
    }
}
