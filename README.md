# Course


No todas las versiones de vugen tienen el protcol advisor

Para soluconar el problema que solo hacer grabacion de la pagina del browser pero no del webtours lo que se hizo fue intentar tres cosas

primero agregar los certifcados ssl de vugen a lo certificados de confianza
despues agregar los certificados de loadrunner, existen dos path por que las diferentes versiones de loadrunner community y las nuevas lo tienen diferente pero el que me funciono fue usar este

https://admhelp.microfocus.com/lr/en/24.1-24.3/help/WebHelp/Content/Controller/toc-TLS-comm.htm#mt-item-1

cabe aclarar que primero instale el de vugen y luego el de loadrunner de la otra version que era seguir los mismos pasos que el de vugen y no funciono asi que este ultimo deberia ayduar este es con la version CE 24.1 que es la version de community 


Cualquier script que se cree tiene una extension .c que significa que esta creado en lenguaje c

se tienen que crear diferentes acciones en el panel para describir cada cosa que hara el usuario por ejemplo puede quedar como 

"Login"
"Book flight"
"LogOff"

Aunque en realidad hay mcuahs formass de organizar los scriots


Para grabar los scripts la configuracion que tengo en el vugen es la siguiente


![image](https://github.com/user-attachments/assets/79057d92-5677-464d-b02e-6cd3befb4eb8)


en esta pantalla aun se puede cambiar en que accion hacer la grabacion y seleccionar el browser que se necesita

tambien seleccionar si es requerido en donde guardar los archivos 

El vugen se comporta como un listener de todas las transacciones que suceden entre el cliente y el servidor es como si tomara nota de lo que estan hablando entre ellos 

Recprdar que cuando esta grabando se pueden guardar comentarios de cada accion que hagamos para tener una mejor visualizacion de cada accion en el codigo




