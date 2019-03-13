def var_global;
def workspace;
node(){
    stage('Checkout Code'){
        var_global="GLOBAL";
        def var_local = "LOCAL";
        echo ("Nos traemos el fichero de git");
        echo "hola, ésta es la variable global: ${var_global}, y ésta es una variable local: ${var_local}";
        returnMessage_noparam(); //llamamos a la función sin parámetros.
        echo returnMessage_param("parametro_para_llamada");//llamamos a la función con parámetros.
    }
    stage('Code Analysis'){
        build job: 'Code_Analysis', parameters: [text(name: 'workspace', value: '')];
    }
    stage('Code Compile'){
        build job: 'Code_Compile', parameters: [text(name: 'workspace', value: '')];
    }
    stage('Code Unit Test'){
        build job: 'Code_Unit_Test', parameters: [text(name: 'workspace', value: '')];
    }
    stage('Code Package'){
        build job: 'Code_Packaging', parameters: [text(name: 'workspace', value: '')];
    }
    stage('Deploy'){
        build job: 'Code_Deploy';
    }
    
}

def returnMessage_noparam(){
    def cadena="Hemos llamado a un método sin parametros";
    echo "${cadena}";
}

def returnMessage_param(String cadena){
    cadena1="Hemos llamado a un método con el parámetro: ${cadena}";
    return cadena1;
}
