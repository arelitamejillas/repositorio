//pipeline{
//  agent any
//  stages{
//    stage('Etapa 1'){
//      steps{
//        echo 'Hola mundo'
//      }
//    }
//  }
//}

node{
  
  ckeckout scm
  stage('Compilar'){
    echo "Comienza la compilación" 
    withMaven(
      maven:'Maven Test'
    ){
      sh 'mvn compile'
    } 
  }
    stage('Tests'){
    echo "Comienza las pruebas!!" 
  }
    stage('Empaquetar'){
    echo "Comienza la empaquetación!!" 
  }
}
