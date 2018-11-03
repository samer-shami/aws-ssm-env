@Library('DevOps') _

pipeline {
    agent any
    // These are inputs on job run
    parameters {
        booleanParam(name: 'FORCE_GRAILS_IMAGE_BUILD', defaultValue: false, description: 'Tick to force Grails container rebuild')
    }
    // These cannot be changed by the user, but do support variable expansion
    environment {
        JENKINS_LOCK_NAME     = "SSO_Build"
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '30', artifactDaysToKeepStr: '14'))
        timestamps()
        ansiColor('xterm')
        disableConcurrentBuilds()
    }
    stages {
        stage('Init') {
            steps {
                script { printEnvironment() }
            }
        }
    }
}
