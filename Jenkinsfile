pipeline {
    agent any
    stages {
        stage('git repo & clean') {
            steps {
                sh "rm -rf TicketBookingServiceJenkins"
                sh "git clone https://github.com/klerrie/TicketBookingServiceJenkins.git"
                sh "mvn clean -f TicketBookingServiceJenkins"
            }
        }
        stage('install') {
            steps {
                sh "mvn install -f TicketBookingServiceJenkins"
            }
        }
        stage('test') {
            steps {
                sh "mvn test -f TicketBookingServiceJenkins"
            }
        }
        stage('package') {
            steps {
                sh "mvn package -f TicketBookingServiceJenkins"
            }
        }
    }
}
