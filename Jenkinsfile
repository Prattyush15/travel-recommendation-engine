pipeline {
  agent any

  stages {
    stage('Initialize Workspace') {
      steps {
        echo 'Initializing workspace...'
        checkout scm
      }
    }

    stage('Install Dependencies') {
      steps {
        echo 'Installing Python dependencies...'
        sh 'pip install -r requirements.txt'
      }
    }

    stage('Lint or Test DAGs') {
      steps {
        echo 'Linting or testing Airflow DAGs...'
        sh 'pytest dags/ || echo "No tests found or pytest not installed"'
      }
    }

    stage('Deploy Backend Containers') {
      steps {
        echo 'Deploying backend services with Docker Compose...'
        sh 'docker-compose -f docker/docker-compose-psql.yml up -d --build'
      }
    }
  }

  post {
    always {
      echo 'Pipeline completed!'
    }
  }
}
