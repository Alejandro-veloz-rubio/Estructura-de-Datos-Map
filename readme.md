Lo que se hizo en este ejercicio es el uso de la estructura Map para guardar,buscar y listar a los objetos personas que nosotros querramos lo primero como siempre es crear una clase persona una grupo una variable que cree un grupo.
Dentro de la clase grupo cambiamos el metodo de agregar por este:

this.datos=new Map();
    this.agregar=function(clave,nuevo){
        this.datos.set(clave,nuevo);
        
    }

como observamos en vez de poner new Array o new Set ponemos new Map pues esta es la estructura para guardar los datos de las personas en la funcion agregar the pone .set (key,value) el key significa la clave con la que nuestro value( "valor" en este caso informacion de la persona) estara asignada y sea mas facil encontrar para obtener un valor podriamos poner:
this.datos.get(1)cualquier numero que ayamos asignado devolvera el valor en console.log para modo de prueba
Para la funcion listar puse este codigo:

let res="";
        for (var valor of this.datos.values()) {
            res+=valor.info()+'<br>';
          }
        return res;

declaramos una variable res y utilizamos un ciclo for of como se muestra pero para obtener los valores debemos poner this.datos.values() asi cada valor de this.datos se registrara en res llamando a cada valor .info para que al final devuelva el valor y lo pueda imprimir
En la parte de buscar se usa este codigo:

 let res2="";
        for (var valor of this.datos.values()) {
            if(valor.celular == numero)
            {
                res2=valor.info();
            }
           
          }
        return res2;
    }
pasa lo mismo que listar solo que se le agrega un if donde si el valor.celular es igual al numero brindado en la variable buscado regresara a traves de la funcion .info() la informacion completa de la persona
una cosa importante a tener en cuenta es el hecho de agregar a las personas pues en map habiamos dicho que se utiliza el (key,value) para eso se agregarian de la siguiente manera:

nuevo1=new Persona('111','Alan',10)
grupo.agregar(1,nuevo1);

si hubiera otro seria de la siguiente manera:

nuevo2=new Persona('222','Beto',20)
grupo.agregar(2,nuevo2);

asi sucesivamente.

Conclusion 
El uso de este tipo de estructura facilita mas las cosas al momento de buscar pues es como si fuera un directorio dicho que solo poderiamos poner la "key" y se nos puede devolver el valor como tal se podria decir que es como un array pero tu le pones la clave para encontrarlo.