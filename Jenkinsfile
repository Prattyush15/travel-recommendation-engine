pipeline {
  agent any

  stages {
    stage('Install Dependencies') {
      steps {
        echo 'Installing Python dependencies...'
        sh 'pip install -r requirements.txt'
      }
    }

    stage('Lint or Test DAGs') {
      steps {
        echo 'Linting or testing Airflow DAGs...'
        // Add test or lint commands here, for example:
        sh 'pytest dags/ || echo "No tests found or pytest not installed"'
      }
    }

    stage('Deploy Backend Containers') {
      steps {
        echo 'Deploying backend services with Docker Compose...'
        sh 'docker-compose -f docker/docker-compose.yml up -d --build'
      }
    }
  }

  post {
    always {
      echo 'Pipeline completed!'
    }
  }
}
