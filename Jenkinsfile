pipeline {
agent any

```
environment {
    AWS_REGION = "eu-north-1"
    VERSION = "${BUILD_NUMBER}"
}

stages {

    stage('Git Clone') {
        steps {
            checkout scm
        }
    }

    stage('Build Backend') {
        steps {
            dir('backend') {
                bat 'docker build -t backend:%VERSION% .'
            }
        }
    }

    stage('Build Frontend') {
        steps {
            dir('frontend') {
                bat 'docker build -t frontend:%VERSION% .'
            }
        }
    }

    stage('Docker Images') {
        steps {
            bat 'docker images'
        }
    }
}
```

}
