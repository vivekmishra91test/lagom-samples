
node {
    stage('SBT compile*****') {
      cd ./shopping-cart/shopping-cart-scala
  /usr/lib/jvm/java-11-openjdk-amd64/bin/java -jar /home/mishra/sbt-dist/bin/sbt-launch.jar clean compile
  }
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def scannerHome = tool 'SonarScanner';
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
