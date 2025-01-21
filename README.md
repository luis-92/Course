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

47
Protocol Advisor
esta opcon no esta dispomnible en todas las versiones y acutalmenteno se utuiliza tanto, pero sirve para cuando comenzamos a usar una app ponerlo a trabjaand y nos va a decir que protocol se suan y nos daria las mejores opciones para utilizar. Despues que el protocol advisonr termina de analizar te da un reporte de cuales protocolos fueron usados durante las interacciones del sscript
entonces si tnemos problemas un dia podedmos revisar los protocols que menciona en su reporte y utilizar de uno en uno hasta que nos funcione
Recordemos que el Vugen no grraba a nivel UI graba a nivel protocolo cada interaccion que se hace entre el servidor y el cliente la graba

48
en entre  transacciones siemppre hay think time  que esl el tiempo que toma el usuario real para hacer sus acciones 
este tiempo esta capturado por el script siempre en las grabaciones 

![image](https://github.com/user-attachments/assets/76a188b8-f469-42e2-b9d2-b8c0fcae1bb6)
ese tiempo lo puedes modificar en el script a como se necesario


es muy normal que una persona sea experta en un solo protocolo por que es tan complejo y tanta la informacion deun solo protocolo que funciona mas de esa manera

para eviar cualquier problema de cache o cookies 
generalmente los scripts siempre comienzan con tres funciones relacionadas a limpiar toos esos datos

![image](https://github.com/user-attachments/assets/2fb2b24d-396b-423c-8a55-79f2fb8c7d9e)
![image](https://github.com/user-attachments/assets/ab25a02a-bf99-43a3-a4b4-4a3df3f2977c)


el atajo control space sirve para autocompletar las funciones

todo se tiene que limpiar siempre antes de que se ejecute el scriot por eso se pone hassta arriba esas funciones

49-----------------------------
en la parte del codigo donde el usuario se logea hay una seccion que menciona "userSSsion" 
 seleccionamos el valor que esta a la derecca y lo correlacionamos 

![image](https://github.com/user-attachments/assets/3fcafabb-4026-497f-a4d8-3fcadeff8074)

agregeye las funciones para eliminar cookies y todo eso


Para poder ver en tiempo real como es la ejecucion de un script y ver el browser tenemos que activar una iopcion

es en tools
options
Y seleccionar  "Show run time viewer during replay"
![image](https://github.com/user-attachments/assets/42f00b32-7435-4fcb-9029-f0bf0635ea93)
 de esta manera podemos ver la ejecucion


 En run logic puedes cmbiar el numero de iteraciones de cada parte del script 

 Para llegar ahi es darle click en replay y luego runtime settings

 ![image](https://github.com/user-attachments/assets/0709c133-74b9-4cf1-bd00-cd4d2057c35d)


50-------------------------------------

Run Time Settings

La forma en la que estan organzadas las acciones en en panel izquierdo no importan realmente, lo que importa es el orden en el que estan organizadas en el runtime settings es ahi donde la logica esta configurada para correr una accion antes o despues que otra y tambien se definen el numero de iteraciones de cada accion


![image](https://github.com/user-attachments/assets/27282ee2-bf2d-4d58-9434-f43b45a497a6)

si se desea ejecutar una accion especifica dentro de otra accion mas de una vez, entones agregar bloques y de ahi se puede incrementar el numero de iteraciones

![image](https://github.com/user-attachments/assets/a41f5eef-dcfa-42a4-914d-11be0468249b)


 
Para que funciona el think time  se tiene que actualizar la condiguracion en runtime settings
 en think time 
por default esta en ignorar pero se tiene que cambiar al de la imagen
 ![image](https://github.com/user-attachments/assets/51b80f72-34aa-4156-834e-b49e273f9724)

 











