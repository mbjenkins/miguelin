/*pipeline {
  agent any
  stages {
    stage('Etapa 1') {
      steps {
        echo 'Hola Mundo'
      }
    }
  }
}*/
node {
  checkout scm
  stage('Compilar') {
    echo "Comienza la compilación"
    withMaven(
        maven:'Maven por defecto(3.6)'
    ){
      sh 'mvn compile'
    }
  }
  stage('Test') {
    echo "Comienza las pruebas"
  }
  stage('Empaquetar') {
    echo "Comienza la empaqueta"  }
}
