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
        workspace=pwd();
    }
    stage('Code Analysis'){
        echo 'Construyendo el Code_Analysis';
        build job: 'Code_Analysis', parameters: [text(name: 'workspace', value: workspace)];
        echo 'Contruido';
    }
    stage('Code Compile'){
        echo 'Construyendo el Code_Compile';
        build job: 'Code_Compile', parameters: [text(name: 'workspace', value: workspace)];
        echo 'Contruido';
    }
    stage('Code Unit Test'){
        echo 'Construyendo el Code_Unit_Test';
        build job: 'Code_Unit_Test', parameters: [text(name: 'workspace', value: workspace)];
        echo 'Contruido';
    }
    stage('Code Package'){
        echo 'Construyendo el Code_Packaging';
        build job: 'Code_Packaging', parameters: [text(name: 'workspace', value: workspace)];
        echo 'Contruido';
    }
    stage('Deploy'){
        echo 'Construyendo el Code_Deploy';
        build job: 'Code_Deploy';
        echo 'Contruido';
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
