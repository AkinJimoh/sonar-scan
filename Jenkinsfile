node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'sonarqube';
    withSonarQubeEnv('sonarqube') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.projectKey=sonar-Akinola \
      -D soner.login=22f3de3032e72da3dd6cdddb2873b3334377072e \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.pullrequest.key=2 \
      -D sonar.pullrequest.branch=jimoh1
      -D sonar.pullrequest.base=main"
    }
  }
}