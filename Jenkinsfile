def var_global;
echo ("Nos traemos el fichero de git");
node(){
    stage('1'){
        var_global="GLOBAL";
        def var_local = "LOCAL";
        echo "hola, ésta es la variable global: ${var_global}, y ésta es una variable local: ${var_local}";
        returnMessage_noparam(); //llamamos a la función sin parámetros.
        echo returnMessage_param("parametro_para_llamada");//llamamos a la función con parámetros.
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
