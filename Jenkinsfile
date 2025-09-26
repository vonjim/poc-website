pipeline {
  agent any

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/vonjim/poc-website.git'
      }
    }

    stage('Build') {
      steps {
        echo 'No build needed for static site'
      }
    }

    stage('Test') {
      steps {
        echo 'No tests yet'
      }
    }

    stage('Deploy') {
      steps {
        echo 'Deploying to GitHub Pages...'
        sh '''
          git config --global user.email "james.comiskey@gmail.com"
          git config --global user.name "vonjim"
          git checkout --orphan master
          git rm -rf .
          cp -r * .
          git add .
          git commit -m "Deploy to GitHub Pages"
          git push -f origin master
        '''
      }
    }
  }
}
