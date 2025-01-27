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

51 ----------------------------
Undesrating the code 
expalining the lines 
this is just a way to analyze the pprocess of the client to go to the server and get some informaton
![image](https://github.com/user-attachments/assets/6b165550-bade-4f1f-947b-c0ea8020c065)

52----------------------------------------

Methods
the function in the vugen "web_url("indext.htm......")" is a GET request this is a question interview
for POST request in vugen we use web_submit_data
![image](https://github.com/user-attachments/assets/be7e4a16-7f21-453a-b16d-6e39a2da0ac6)

53-----------------------------------
If I record in IE I can playback in google chrome you can set that in the runtime settings ni the section browser emulation
en el user agent sitrng e puedee cambiar la version del browser
![image](https://github.com/user-attachments/assets/64177b93-aab4-4179-9f7a-dc52913be1d8)

En run time settings tambien se puede configurar el speed simulation

![image](https://github.com/user-attachments/assets/1a4039b4-0bfd-45df-8de7-79a3e880050a)

54-------------------------

We dont have object identificantion in load runner
so we identify everything with the comments  
we can add comments like  "Correlation code pleae do not change"

I we want to know is the performenc ok for an specific action we need to add in the code
what we called
transactions
then we can capture the response times for aprticular block or functionality

the code is the next:
the parametrs are the name of the transaction
lr_start_transaction("Login")
and
lr_end_transaction("Login", LR_AUTO)


![image](https://github.com/user-attachments/assets/f8f70e28-a8b0-4f4b-b333-23bef32c0b2a)

After execute the login transaction we can see in the logs the time consumed


![image](https://github.com/user-attachments/assets/c23bcd90-3161-42aa-987b-d2ada24da8f5)

55---------------------------------------
Play back with transactions
load runner is case sensitive

we need to follow specific format for the transactions in order to have a good tracking

![image](https://github.com/user-attachments/assets/680f45af-be55-4e14-a29a-3fc8cbb578ec)

56-------------------------------------

Una pegunta de entrevista puede ser 
Puedes borar la accion vuserinit? y la respuesta es que no se puede

![image](https://github.com/user-attachments/assets/4800c51b-f153-4dc1-bf20-56d592a4ac75)


Call Actions
how to print in consoloe

Lr_output_message();

IMPORTANT
Main action can be created and all the oterh actions will be called from this action
es como usar funciones que llamen a otras funciones

![image](https://github.com/user-attachments/assets/ba9f9bda-4e17-4faf-9897-f25c2a7e5332)


![image](https://github.com/user-attachments/assets/48fc5552-9154-46e7-82b5-c42f6b5c1194)

57====================================================
difference between HTML based script nd URL based script
usamos las deeloper tools para saber  los request que se mandan al server y lo que el server regresa

![image](https://github.com/user-attachments/assets/2dded676-4a8a-42f3-8c19-f52a73f100c8)


![image](https://github.com/user-attachments/assets/12c13e10-97b2-426d-a5c8-d0de64bd70dd)


![image](https://github.com/user-attachments/assets/41a94481-03e3-4984-b96e-62e343d93a32)


58----------------------------------------------------------------------

SCRIPTs BASADOS en URL VS Scripts basados en HTML

Si tuvieramos un script basado en URL entonces en las herramientas deld esarrollador solo veriamos urls en el nombre de los web resources donde se se;ala la imagen
entonces enla coumna de name diria algo asi como

web_requestzzzzzzzz
web_requestxxxxxxxxxxxxxxxxxx
**![image](https://github.com/user-attachments/assets/2fa2cdc0-adb7-4637-8f8b-babbea7e05c7)
**

para crear un script basado en url se tiene que configurar en el recording options

![image](https://github.com/user-attachments/assets/deaf1972-9fe4-40dc-a919-d0c9c4c859fa)

Claro, aquí tienes una versión más breve de la explicación:
Script Basado en URL
Cuándo usarlo:

Aplicaciones Simples: Para aplicaciones web simples o estáticas.
Pruebas de Carga Alta: Cuando se necesita simular muchos usuarios simultáneos.
Pruebas de Red: Para probar el rendimiento de la red o el servidor sin interacciones complejas.
Menor Complejidad: Para una configuración rápida y menos mantenimiento.

Ventajas:

Menor consumo de recursos.
Más fácil de mantener y depurar.
Adecuado para pruebas de carga masivas.

Script Basado en HTML
Cuándo usarlo:

Aplicaciones Dinámicas: Para aplicaciones con muchas interacciones dinámicas.
Pruebas de Experiencia del Usuario: Para simular el comportamiento real del usuario.
Validación de Contenido: Para validar el contenido de las respuestas HTML.
Interacciones Complejas: Para navegación compleja, formularios y autenticación.

Ventajas:

Simulación más realista del usuario.
Manejo de interacciones dinámicas.
Mejor para pruebas funcionales y de experiencia del usuario.

Resumen

URL: Ideal para aplicaciones simples y pruebas de carga alta.
HTML: Mejor para aplicaciones dinámicas y pruebas detalladas de usuario.

59------------------------------------------------------
e reviso donde poner la funcion de transaccion en un scrit basado en url

se pueden agregar funciones subtransaction para poder tomar el performance de cada subtransaccion dentro de una transaccion mas grande 

![image](https://github.com/user-attachments/assets/fe70d7fa-d2e3-4a35-8028-ee133a35fbfc)


asi e puede revisar cada recurso como se comporta y que rendimiento tiene

en html no se puede hacer eso 

Existe una herramienta que se llama http watch que es un complelmento para loadrunner donde se ve el trafico en tiempo real es como si usara la herramienta de desarolladores pero para loadrunner performance testers sipreguntn si lo he usado la respuesta puede ser que prefiero usar las developer tools

![image](https://github.com/user-attachments/assets/1371c4dd-710e-4fec-8b90-15d3f85292f4)

60----------------------------------
Checkpoints
a veces en el reporte aparece que el script paso pero en realidad no paso y eso lo tenemos que poner como un cehckpoint para que no nos de ese tipo de falsospositivos
se pueden usar textos para hacer una especie de assertion se pueden parametrizar esos datos para tener un checkpoiint bien definido
 por ejemplo se puede poner un texto que nidique que paso y usar otro que indique que fallo por ejemplo usar el response 404 como parametro de que fallo
 necesitasss seleccionar un texto completo que si indique que ha pasado  o que ha fallado 

 Load runner tiene forma de usar text checkpoint y tambien imagen checkpoint

 con agregar un checkpoint podemos confirmar si el script paso o fallo

 61----------------------------------------------
 TextCheckpoint  Part1 
 la funciion par a usar el checkpoint es
 Web_reg_find()
 
![image](https://github.com/user-attachments/assets/efeeac7e-b084-4f32-ac10-2357cc5cf26a)


para revisar con es que cada fragmento del script esta respondiendo podemos revisarlo en la opcion de snaposhot que esta hasta las herramientas de abajo
sino esta a la vista entones agregarlo desde el panel superior derecho en view y seleccionar snapshot



![image](https://github.com/user-attachments/assets/ecdaef04-de65-4960-92cf-55b4abdc4e38)



































































Generative AI



![image](https://github.com/user-attachments/assets/835ed325-3786-480f-bc11-d6e3521f8539)





![image](https://github.com/user-attachments/assets/06408c2e-bd51-4023-a6d4-2877fb651f83)



![image](https://github.com/user-attachments/assets/c6cdaf2a-8f33-4ac0-b1dc-a7b5de811822)


![image](https://github.com/user-attachments/assets/f24ce9f5-3202-49bf-bf3d-15085983f115)


![image](https://github.com/user-attachments/assets/fe896bea-1776-43bb-bbbe-c2490d29aa3d)




![image](https://github.com/user-attachments/assets/77a9a7b4-eda5-4c26-8f8b-238e2f2d87d4)
