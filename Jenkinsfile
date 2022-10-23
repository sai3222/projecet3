pipeline {
    agent any
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('pull') {
            steps {
              sh "echo Hello this is ${params.PERSON}"
              git 'https://github.com/sai3222/sample-webapp'
            }
        }    
        stage('validate.') {
            steps {
              sh "echo this is description ${params.BIOGRAPHY}"
                sh 'mvn validate'
            }    
        }    
        stage('test') {
            steps {
                sh 'mvn test' 
            }    
        }
        stage('package') {
            steps {
                sh 'mvn clean package'
            }    
        }
    }
}
