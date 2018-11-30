pipeline{
  agent any
  stages{
  stage('Compilar'){
    echo "Comienza la compilación" 
    withMaven(
      maven:'Maven por defecto (3.6)'
    ){
      sh 'mvn compile'
    } 
  }
    stage('Tests'){
    echo "Comienza las pruebas!!" 
    withMaven(
      maven:'Maven por defecto (3.6)'
    ){
      sh 'mvn test'
      junit '**/*.xml'
    }   
  }   
    stage('Empaquetar'){
    echo "Comienza la empaquetación!!" 
   withMaven(
      maven:'Maven por defecto (3.6)'
   ){
      sh 'mvn package'
    }    
  }
    sh 'mvn package' 
}

//node{  
  //checkout scm
  //stage('Compilar'){
    //echo "Comienza la compilación" 
    //withMaven(
      //maven:'Maven por defecto (3.6)'
    //){
      //sh 'mvn compile'
    //} 
  //}
   // stage('Tests'){
   // echo "Comienza las pruebas!!" 
   // withMaven(
     // maven:'Maven por defecto (3.6)'
    //){
      //sh 'mvn test'
      //junit '**/*.xml'
    //}   
  //}
    //stage('Empaquetar'){
    //echo "Comienza la empaquetación!!" 
   //withMaven(
    //  maven:'Maven por defecto (3.6)'
   //){
      //sh 'mvn package'
    //}
      //try
      //{
      // sh 'mvn package' 
      //}finally{
       //deleteDir() 
      //}  
  //}
//}
