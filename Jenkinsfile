pipeline 
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
      allways 
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
}
