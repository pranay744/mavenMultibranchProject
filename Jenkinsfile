pipeline{
    agent any
    stages{
        stage("Executing Git repo"){
            steps{
               git credentialsId: '94ec7097-5be2-4b2b-b5e7-e54f4f085314', url: 'https://github.com/pranay744/mavenMultibranchProject.git' 
            }
        }
        stage("Executing Maven Repo"){
            sh mvn clean sonar:sonar install
        }
        stage('Deploy the package into tomcat Continer using ansible'){
            sh ansible-playbook ansible.yml
        }
    }
}
