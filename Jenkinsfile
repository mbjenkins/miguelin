/*pipeline 
{
  agent any
  stages 
  {
    stage('Compilar') 
    {
      steps {
        echo "Comienza la compilación"
        withMaven(
            maven:'Maven por defecto(3.6)'
        ){
        sh 'mvn compile'
        }        
      }
    }
    stage('Test') {
      steps {
        echo "Comienza las pruebas"
        withMaven(
            maven:'Maven por defecto(3.6)'
        ){
        sh 'mvn test'
        }        
      }
    }
    stage('Empaquetar') {
      steps {
        echo "Comienza la empaqueta"
        withMaven(
            maven:'Maven por defecto(3.6)'
        ){
        sh 'mvn package'
        }        
      }
    }
        
  }
post 
    {    
      always 
      {
      
        deleteDir()
      }
      failure 
      {
      
        echo 'UPS!!'
      }
      success 
      {
      
        echo 'Exito'
      }
      changed 
      {
        echo 'cmabio' 
      }
    }  
}*/
node {
    try {
        stage('Test') {
            sh 'echo "OK!"; exit 0
        }
        echo 'Se ejecuta si exito'
    } catch (e) {
        echo 'Se ejecuta si fallo'
        throw e
    } finally {
        def currentResult = currentBuild.result ?: 'SUCCESS'
        if (currentResult == 'UNSTABLE') {
            echo 'Se ejecuta si unstable'
        }

        def previousResult = currentBuild.previousBuild?.result
        if (previousResult != null && previousResult != currentResult) {
            echo 'Se ejecuta si hay cambio de estado'
        }

        echo 'Se ejecuta siempre'
    }
}
