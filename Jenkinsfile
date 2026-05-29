pipeline {
    agent any

    parameters {
        string(name: 'ENV', defaultValue: 'dev', description: 'Deployment environment')
        string(name: 'VERSION', defaultValue: '1.0', description: 'App version')
        choice(name: 'ACTION', choices: ['build', 'deploy', 'test'], description: 'Action to perform')
        booleanParam(name: 'DEBUG', defaultValue: false, description: 'Enable debug mode')
    }

    stages {
        stage('Print Params') {
            steps {
                echo "ENV = ${params.ENV}"
                echo "VERSION = ${params.VERSION}"
                echo "ACTION = ${params.ACTION}"
                echo "DEBUG = ${params.DEBUG}"
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }
    }
}
