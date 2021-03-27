#!groovy

pipeline {

  agent any

  environment {
    git_commit_message = ''
    git_commit_diff = ''
    git_commit_author = ''
    git_commit_author_name = ''
    git_commit_author_email = ''
  }

  stages {

    // Build
    stage('Build') {
      agent {
        label 'testgroup'
      }
      steps {
        deleteDir()
        checkout scm
      }
    }

    // Static Code Analysis
    stage('Static Code Analysis') {
      agent {
        label 'testgroup'
      }
      steps {
        deleteDir()
        checkout scm
        echo "Run Static Code Analysis"
      }
    }

    // Unit Tests
    stage('Unit Tests') {
      agent {
        label 'testgroup'
      }
      steps {
        deleteDir()
        checkout scm
        echo "Run Unit Tests"
      }
    }

    // Acceptance Tests
    stage('Acceptance Tests') {
      agent {
        label 'testgroup'
      }
      steps {
        deleteDir()
        checkout scm
        echo "Run Acceptance Tests"
      }
    }

  }
  post {
    success {
      echo "Send mail on success"
      // mail to:"me@example.com", subject:"SUCCESS: ${currentBuild.fullDisplayName}", body: "Yay, we passed."
    }
    failure {
      echo "Send mail on failure"
      // mail to:"me@example.com", subject:"FAILURE: ${currentBuild.fullDisplayName}", body: "Boo, we failed."
    }
  }
}
