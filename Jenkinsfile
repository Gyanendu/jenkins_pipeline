pipeline {
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'localmaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'localmaven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'localmaven') {
                    sh 'mvn install'
                }
            }
        }
    node {
    stage('Get approval'){
    input "Deploy to prod?"
    }
    stage('deploy to prod'){
        echo "deploying to prod"
    }   
 }
    }
}
