## DNS:
Domain Name System o DNS es un protocolo de Internet que tiene como función la resolución de nombres de dominio, traduciendo estos mismos en IPs.

Cada dominio tiene asignado unos DNS (Nameservers), permitiendo traducir el nombre de dominio a la IP correspondiente.


### Nombres de dominio:
Un nombre de dominio (a menudo denominado simplemente dominio) es un nombre fácil de recordar asociado a una dirección IP física de Internet. Se trata del nombre único que se muestra después del signo @ en las direcciones de correo y después de www. en las direcciones web.


### Niveles de Dominio:

#### Dominios de Nivel Superior (TLD): 
La extensión es el primer nivel y el nombre de dominio es el segundo nivel. Por tanto, contempla lo que está a la derecha del punto y generalmente se han diferenciado las extensiones de primer nivel entre genéricas y territoriales.

2 Tipos :

 Código de País :
se pueden encontrar las extensiones más conocidas y comunes: .com, .net, .org, etc.

Dominios Geográficos/Territoriales :
Estos tipos de dominios suelen corresponderse con las iniciales del nombre de naciones, Suelen ser utilizados cuando una marca u organización quiere especializarse en una determinada región y proporciona contenido específico para el mismo.

#### Dominios de Segundo Nivel (SLD):
Se encuentra directamente a la izquierda del dominio de primer nivel, siendo usualmente el nombre de la marca, organización o persona en la que se enfoca el sitio. Por ejemplo, en la dirección URL www.openwebinars.net, openwebinars sería el SLD


#### Dominios de Tercer Nivel (TLD):
Es aquel tipo de dominio en el que se produce una mezcla entre un dominio de tipo genérico y un dominio específico de país.

Por ejemplo, la combinación .gob.es, indicaría que se trata de una organización gubernamental para España.


### Zona de Búsqueda
La zona DNS es un espacio administrativo que permite más control granular de los componentes de DNS, como los servidores de nombres autoritativos. El espacio de nombres de dominio es un árbol jerárquico, con el dominio raíz DNS en la parte superior. La zona DNS empieza en un dominio dentro del árbol y se puede extender hacia abajo en subdominios para que una entidad pueda gestionar múltiples subdominios.


 Una zona DNS puede incluir varios subdominios y puede haber varias zonas en el mismo servidor.


 ### Tipos de servidores

 #### Servidor DNS Recursivo (Resolutor):
  Este servidor actúa como intermediario entre el usuario y otros servidores DNS. Recibe la solicitud de resolver un dominio y, si no tiene la información almacenada en caché, consulta a otros servidores DNS hasta obtener la respuesta.

#### Servidor DNS Autoritativo: 
Este servidor contiene la información definitiva sobre un dominio específico, es decir, tiene el mapeo exacto entre un nombre de dominio y su dirección IP correspondiente. Se consulta al final del proceso si otros servidores no tienen la respuesta.

#### Servidor DNS de Caché: 
Almacena respuestas previas de solicitudes DNS para acelerar la resolución en futuras consultas sobre los mismos dominios. Estos datos tienen un tiempo de vida limitado (TTL).

#### Servidor DNS Raíz: 
Es el primer nivel del sistema de nombres de dominio. Existen 13 servidores raíz principales que manejan solicitudes sobre la ubicación de los servidores que contienen información sobre los dominios de primer nivel (TLDs), como .com, .org, etc.

#### Servidor DNS de Zona o TLD (Top-Level Domain):
 Gestiona los dominios de primer nivel (TLD), como .com, .org, y los países (.es, .mx). Redirige las consultas hacia servidores DNS autoritativos específicos del dominio solicitado.


### Registro
 son instrucciones radicadas en servidores DNS autoritativos que proporcionan información sobre un dominio, como la dirección IP asociada con este y cómo gestionar solicitudes dirigidas a dicho dominio. Estos registros consisten en una serie de archivos de texto escritos en lo que se conoce como sintaxis DNS. La sintaxis DNS es simplemente una cadena de caracteres utilizados como comandos que dicen al servidor DNS qué hacer.


 ### Funcionamineto

 Paso 1: Solicitud de Información

Escribe el nombre de dominio (www.get.tech) en tu navegador web y este hará una consulta al DNS para encontrar la respuesta en cuanto a dónde se encuentra. El resolutor de DNS es como tu intermediario.

Paso 2: Servidores de Nombres Raíz

El resolutor de DNS le pregunta al servidor de nombres raíz por la dirección IP. Ellos no tienen la respuesta a tu consulta, pero saben dónde encontrarla. La respuesta de los servidores de nombres raíz es la dirección de los Servidores de Nombres de Dominios de Primer Nivel (TLD o Top Level Domain).

En el caso de www.get.tech, son los servidores de nombres .TECH.

Paso 3: Servidores de Nombres de Dominios de Primer Nivel (TLD o Top Level Domain).

El sistema de resolución de DNS ahora le pregunta al servidor de nombres TLD la dirección IP del nombre de dominio. El servidor de nombres TLD responde con la dirección del servidor de nombres autorizado para el nombre de dominio.

En nuestro ejemplo, el servidor de nombres .TECH proporcionará la dirección de los servidores de nombres autorizados de get.tech.

Paso 4: Servidores de DNS Autorizados

Los servidores de DNS autorizados guardan registros DNS de los nombres de dominio necesarios para la resolución de DNS. Estos registros son mantenidos idealmente en un archivo de zona por el propietario del dominio o por el administrador técnico responsable de gestionar el comportamiento funcional del nombre de dominio. Hay diferentes registros dentro de un archivo de zona, por ejemplo, la dirección IP del servidor donde está alojado el sitio web, está representado por un Registro de Dirección, comúnmente denominado registro ‘A’. Puede encontrar más información sobre tipos de registros de zona aquí.

Paso 5: Recuperar el Registro

El servidor recursivo obtiene el registro ‘A’ para el sitio web de los servidores de nombres autorizados y lo almacena en su caché local. Si alguien más está buscando el mismo sitio web, la información ya estará allí y no tendrá que pasar por todo el proceso.

Paso 6: Acceder al Sitio Web

El servidor recursivo envía el registro ‘A’ a tu computadora. La PC guarda este registro, lee la IP y pasa la información a tu navegador; que luego hace la conexión al servidor web, y podrás ver el sitio web www.get.tech.

### Iterativo vs Recursivo
La diferencia entre una consulta DNS recursiva y una iterativa radica en la forma en que se resuelven las solicitudes de nombres de dominio.
La consulta recursiva implica que el servidor hace todo el trabajo; en la iterativa, el cliente hace parte del trabajo.

#### Recursivo :
El servidor recursivo busca la respuesta completa por el cliente, consultando otros servidores si es necesario, hasta obtener la dirección IP solicitada.

#### Iterativo:
 El servidor DNS solo proporciona la mejor respuesta que tiene (como una referencia a otro servidor), dejando al cliente realizar consultas adicionales a otros servidores para obtener la respuesta final.