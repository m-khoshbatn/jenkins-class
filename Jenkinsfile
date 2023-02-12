pipeline {
    agent {
            node {
                label 'NODE02'
            }
        }
    stages{
        stage('build'){
            steps {
                sh 'mvn clean install'
            }
        }
    }
    post {
        always {
            mail to :"recipient@company.com",
                subject: "New build report: ${currentBuild.fullDisplayName}",
                body:"Check out status at ${env.BUILD_URL}"
        }
    }
}
