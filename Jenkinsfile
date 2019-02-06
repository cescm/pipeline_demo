pipeline{
    agent any
    stages{
        stage('One'){
            steps{
                echo 'Hola, soy Juan Carlos.Fase 1'
            }
        }
        stage('Two'){
            steps{
                input('Continuar?.Fase 2')
            }
        }
        stage('Three'){
            when{
                not{branch "master"}
            }
            steps{
                echo "Hola, no estoy en la rama master.Fase 3"
            }
        }
        stage('Four'){
            parallel{
                stage('Unit Test'){
                    steps{
                        echo "Realizando el test unitario.Fase 4,paralelo 1"
                    }
                }
                stage('Integration Test'){
                    agent{
                        docker{
                            reuseNode false
                            image 'alpine'
                        }
                    }
                    steps{
                        echo 'Corriendo los test de integración.Fase 4,paralelo 2'
                    }
                }
            }
        }
    }
}