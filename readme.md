<h1>formulario con smtpjs</h1>
<h2>y sweetalert2</h2>



tutorial
se crea el formulario y se le da un estilo basico

se le añade un contenedor, con el mensaje de error dentro del input field, con la clase <b>error-txt</b> y el texto a mostrar

se le añade al elemento <b>error-txt</b>, el display:none;

------------
pasando al funcionamiento

smtpjs

se añade el script al html

en el js, se llama al formulario, mediante un querySelector, y se lo almacena en una constante "form"

creamos una funcion para que envie el formulario

y pegamos el script dentro de smtpjs

----------
para setear el smtp server (username, password, to y from), entramos en elasticemail y nos logueamos

settings --> smtp --> create smtp credentials
en usuario se pone el mail que usaremos

esto nos dara un cartel, que usaremos para reemplazar los elementos de la funcion
username(usuario), password,(contraseña), host(servdor --> ponemos el de elasticemail, ya que viene otro por defecto)
cerramos el cartel, y vamos a domains(dominios)--> administrar dominios

verificar dominio--> no tengo dominio y activamos y validamos la cuenta

----------
en el script-->llamamos el form, y le añadimos un escuchador de eventos, haciendo referencia a este form, y le agregamos una funcion que previene el reseteo de pagina -> y luego hacemos correr la funcion de SendEmail()


y ya estaria andando el formualario basico

------------


luego llamamos los diferentes elementos del formulario,

------------
para que nos llegue organizado, se crea una constante (bodyMessage) dentro de la funcion de sendEmail-> donde nos va a llegar organizado, los difeerentes eementos, 

y esto va a ser enviado, mediante la funcion crteada por SMTP, donde se recupera la info de la constante, y se envia en el body....y el asunto se cambia por la constante solicitada


------------
sweet alert

se quita el mensaje en modo alerta que viene por defecto, y se pone el elemento que se desee

------------

se crea una funcion para chequear los inputs, se pone antes de la funcon de enviar el formulario.

en esta se crea la constante que guarde todos los elementos items, mediante un querySelectorAll.
 y se controla que si el valor de cada item es nulo, se añade automaticamente la clasee error 

 luego se controla mediante un listener, si al clickear enviar, el valor es diferente a vacio--> se remueve la clase de error, caso contrario, se deja
 
------------






----------

para la seguridad del servidor, el host, user y pass...entrar een smtpjs, la parte de encriptar credenciales


en el recuadro de stmp, donde esta el script de email.send--> copiar secure token, y pegarlo vacio

abrimos el recuadro de Encrypt your smtp credential
y pegamos user y pass, si no tenemos domain, no lo ponemos....y generamos token de seguridad
este lo pegamos en el script, y luego "host, user y pass" lo borramos del script