/*node {
    try {
        stage('Test') {
            sh 'echo "Exito!"; exit 0'
            //sh 'echo "Fallo!"; exit 1'
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
}*/

node (master){ 
    checkout scm
    stage('Compilar') {
	echo "Comienza la compilacion..."
	withMaven(
           maven:'Maven Test'			
	){
         sh 'mvn compile'
	}
    }
    stage('Test') {
	echo "Comienzan las pruebas..."
	withMaven(
           maven:'Maven Test'			
	){
         sh 'mvn test'
	}
    }
    stage('Empaquetar') {
	echo "Comienza la empaquetacion..."
	withMaven(
           maven:'Maven Test'			
	){
         sh 'mvn package'
	}
    }
}
