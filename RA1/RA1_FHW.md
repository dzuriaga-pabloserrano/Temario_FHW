# FHW - RA1 - Características y configuración de componentes y periféricos en equipos informáticos

*Basado en el trabajo de Alberto Mayor y Ana Aranda del CPIFP LOS ENLACES*

## A - Bloques de un ordenador

John von Neumann fue un matemático de origen húngaro que trabajó en el Proyecto Manhattan, el desarrollo de la bomba atómica de Estados Unidos durante la Segunda Guerra Mundial.

Von Neumann describió el fundamento teórico de construcción de un
ordenador electrónico con programa almacenado.

Idea: conectar permanentemente las unidades del ordenador, de manera que su funcionamiento estuviera coordinado bajo un control central.

Esta arquitectura es, todavía, aunque con pequeños cambios, la que emplean la mayoría de los fabricantes de ordenadores.

Los principales bloques funcionales o componentes físicos que estableció Von Neumann en su diseño son los siguientes:

- Unidad central de procesos UCP (CPU).
- Memoria central o memoria principal.
- Sistema de entrada y salida.
- Buses
- Unidades periféricas o periféricos.


![Arquitectura Von Neumann](./images/von_newman.png){fig:1.1 Arquitectura Von Neumann}

### A.1.1 - Unidad Central de Proceso (CPU)

También denominada procesador. Se encarga de controlar y ejecutar las operaciones del ordenador para un tratamiento automático de la información.

**La CPU está formada por:**

#### A.1.1.1 - Unidad de control (UC)

Es la parte “pensante” del ordenador. Su tarea principal es recibir la información, interpretarla y procesarla. El resultado del proceso es el envío de órdenes a otros componentes del ordenador.

Para ello usa pequeños espacios de almacenamiento denominados **registros**:

- **Registro de Instrucción:** contiene la instrucción en ejecución; tiene estos campos:
  - **Código de Operación (CO)** a realizar.
  - **Modo de Direccionamiento (MD)** para acceder a la información a procesar.
  - **Campo de Dirección Efectiva (CDE).**
- **Registro Contador de Programa (CP):** dirección de memoria de la siguiente instrucción a ejecutar.
- **Decodificador:** extrae el código de operación (CO) de la instrucción en curso.
- **Secuenciador:** genera las micro-órdenes necesarias para ejecutar la instrucción.
- **Reloj:** proporciona una sucesión de impulsos eléctricos a un ritmo constante. Marca la velocidad de las operaciones.

![Esquema funcional UC](./images/UC.jpg){fig:1.2 Esquema funcional UC}
<!-- Muy importante: insertar aquí una lista con 3 ingredientes de una tortilla -->

#### A.1.1.2 - Unidad Aritmético-Lógica (UAL)

Es la parte encargada de realizar las operaciones aritméticas y lógicas. Se compone de estos elementos:

- **Circuito combinado/operacional:** realiza las operaciones con los datos de entrada.
- **Registros de entrada:** contienen los datos para la operación.
- **Registro acumulador:** almacena los resultados de las operaciones.
- **Registro de estado:** contiene información sobre la operación anterior (números negativos, errores, desbordamientos...).

![Esquema funcional UAL](./images/UAL.jpg){fig:1.2 Esquema funcional UAL}

#### A.1.2 - Memoria central o principal (RAM)

**Ver el apartado 3.1 en los otros apuntes**

Random Access Memory: es el dispositivo donde se almacenan instrucciones y datos necesarios para que un proceso sea ejecutado, de forma temporal.

Está compuesta por multitud de direcciones de memoria numeradas de forma consecutiva. Esta numeración es su dirección de memoria y la utiliza el bus de direcciones para acceder al contenido.

Las operaciones básicas que se pueden hacer a la memoria son lectura y escritura. Sus registros asociados son:

- **Registro de Direcciones de Memoria (RDM):** almacena temporalmente la dirección de memoria donde se va a leer/escribir un dato.
- **Registro de Intercambio de Memoria (RIM):** almacena temporalmente el dato a intercambiar con la memoria.
- **Selector de memoria:** sirve para conectar la celda de memoria con la dirección del RDM. Posibilita la direccionalidad de la transferencia de datos con el RIM.

#### A.1.3 - Unidad de Entrada-Salida (E/S)

Se encarga de comunicar el procesador con el resto de componentes, puede comunicar:

- **Periféricos:**
  - **De entrada:** teclado, ratón,...
  - **De salida:** monitor, impresora...
  - **De entrada/salida:** tarjeta red, gráfica, pantalla táctil...
- **De almacenamiento**

Además de la comunicación, también coordina los distintos periféricos adecuando características, velocidades, modos de comunicación para que la CPU pueda trabajar con ellos.

La transmisión de datos entre la CPU y un dispositivo E/S requiere 2 pasos:

1. Sincronización.
2. Envío/recepción del dato.

Para ello, existen 3 mecanismos que se pueden usar:

1. **Control por programa:** la CPU va preguntando a los dispositivos si tienen datos y si están listos para enviarlos.

   Tiene como inconveniente que resulta un proceso lento porque muchas veces no hay novedades.

2. **Control por interrupciones:** se llama la atención de la CPU a través de una señal denominada interrupción.

   La interrupción detiene el programa en ejecución, recibe las operaciones de E/S y finalmente reanuda el programa donde se dejó.

3. **Control por acceso directo a memoria (DMA):**

   Los datos se transfieren directamente entre la memoria central y los dispositivos E/S. Para lo cual, se usan interrupciones para dar el control de la memoria en exclusiva al dispositivo E/S o a la CPU. Se van turnando.

#### A.1.4 - Buses

Son los elementos de conexión física y eléctrica entre componentes. Sirven para llevar información de un dispositivo a otro. Se clasifican en 3 tipos:

- **Bus de datos:** intercambia datos entre la CPU y el resto de unidades. Es bidireccional: recibe datos de los dispositivos de entrada y los envía a los de salida. Su velocidad se mide en MHz o GHz.
- **Bus de direcciones:** identifica el dispositivo y/o direccion de memoria al que va dirigida la información del bus de datos. Funciona en sincronismo con el de datos.

  En función del tamaño en bits que pueda manejar este bus (y la CPU) se podrán direccionar más dispositivos (o registros) simultáneamente.
- **Bus de control:** transporta señales de control que se encargan de gestionar que la información circule de forma adecuada por los otros buses.



## A.2 - Funciones básicas de los distintos componentes

### A.2.1 - Procesador / UCP / CPU

Se podría decir que es el “cerebro” del ordenador, la parte ejecutiva que se encarga de controlar todas las tareas que se realizan dentro del ordenador.La potencia de un Sistema Informático se mide en gran medida por la de su CPU.

Sus funciones son:

- Interpretar y ejecutar las instrucciones de los programas

- Controlar todas las tareas y procesos que se realizan 

- Tomar datos de las unidades E/S, procesarlos y los enviarlos a sus destinos correspondientes.


Al tratarse del control ejecutivo del ordenador; se encarga de todas las operaciones de control:
- Controla los dispositivos periféricos
- Controla la memoria
- Controla la información que se va a procesar.

### A.2.2. Memoria RAM o Memoria Principal

La memoria central también se le da el nombre de memoria principal o RAM. Las siglas de RAM provienen de (RAMDOM ACCESS MEMORY [EN], cuya traducción al español es MEMORIA DE ACCESO ALEATORIO [ES]). Se trata de un tipo de memoria volátil, es decir cuando apagamos el ordenador el contenido de la memoria RAM se pierde.

La memoria central es un componente básico para que se pueda procesar la información ya que los programas y los datos deben estar cargados en ella para poder ejecutarse/procesarse. Es decir, todo lo que se tiene que procesar dentro del ordenador debe de pasar por la memoria RAM.

Para ejecutar un programa, se sigue este procedimiento: 

1. El **programa** pasa del soporte de almacenamiento masivo en el que esté almacenado de forma permanente a cargarse en memoria principal (esta operación recibe el nombre de operación de lectura) a partir de ese momento, a dicho programa se le denomina **proceso**. 

2. Se cargan en memoria principal los **datos** que necesite ese **proceso** para trabajar.

3. Se **ejecuta** el **proceso** en la CPU.

4. Cuando el **proceso** haya **terminado**, devuelve al soporte de almacenamiento externo los datos correspondientes (operación de escritura), desapareciendo de memoria principal. 

5. Si el **proceso** ha finalizado y se "cierra" éste también se descargará de memoria principal y pasarán al almacenamiento masivo los cambios que haya habido en su código.

### A.2.3. Unidad de entrada/salida o Placa base

Este componente en la arquitectura actual equivale a lo que hoy llamamos placa base. La placa base (mainboard o motherboard [EN]) constituye el elemento central de un ordenador. Todos los elementos que integran el ordenador, están integrados o conectados a la placa base por lo que es un componente fundamental del ordenador.
Dentro de la placa base podemos encontrar otros elementos que ayudan a la comunicación con el resto de dispositivos.

#### A.2.3.1 Buses

Son los elementos de conexión física y eléctrica entre componentes. Sirven para llevar información de un dispositivo a otro.

#### A.2.3.2. Chipset

Es un conjunto de chips que se encargan de controlar la forma en que el microprocesador
interacciona con el resto de componentes.

### A.2.4. Almacenamiento Secundario

Se trata de un modo de almacenamiento permanente, es decir, que cuando se apaga el ordenador, los datos permanecen allí.


### A.2.5. Unidades periféricas o periféricos

Son todos aquellos dispositivos que permiten enviar o recibir información a la CPU de
forma que los pueda entender. Son la forma que tiene la CPU de comunicarse con el exterior.

Se clasifican en 3 bloques en función de la direccionalidad de datos, con algunos ejemplos de periféricos:

- **Entrada:**
  - Teclado
  - Ratón
  - Cámara web
  - Micrófono
  - Escáner de código de barras
  - Joystick

- **Salida:**

  - Monitor
  - Impresora
  - Altavoces
  - Auriculares

- **Entrada y salida:**

  - *Almacenamiento de información*:

    - Disco duro
    - CD
    - DVD
    - Blu-ray
    - Memorias flash
    - Lector/grabador de cintas magnéticas
    - Lector/grabador de disquetes

  - *Comunicación:*

    - Fax-módem
    - Tarjeta de red
    - Tarjeta Bluetooth
    - Controladores de puertos serie
    - Controladores de puertos paralelo
    - Controladores de puertos infrarrojo

## A.3. Puesta en Marcha del Ordenador

### A.3.0 Definiciones conceptuales

<p align="center">BIOS ⟶ EFI ⟶ UEFI</p>

**BIOS:** Basic Input/Output System (1981 ~ 2000)

**EFI:** Extensible Firmware Interface (1990 ~ 2006)

**UEFI:** Unified Extensible Firmware Interface (2006 - hoy)

En líneas generales, BIOS, EFI y UEFI se encargan de inicializar el hardware del ordenador y preparar el arranque del sistema operativo.

Todavía existe retrocompatibilidad con BIOS en algunos equipos, pero cada vez es menos habitual. En equipos con firmware UEFI, esta compatibilidad suele ofrecerse mediante un modo llamado:

- CSM (Compatibility Support Module).

- Legacy Boot o Legacy BIOS.

Este modo permite arrancar sistemas operativos o herramientas antiguas diseñadas para BIOS tradicional.

Sin embargo, en los ordenadores más modernos:

- El modo CSM puede venir desactivado.

- Algunas placas base ya no lo incluyen.

**POST:** Power On Self Test: autocomprobación de arranque. Es una comprobación de los componentes críticos del ordenador, y realiza pruebas en los siguientes componentes:




### A.3.1 El arranque del ordenador

Al pulsar el botón de encendido, el ordenador ejecuta una serie de operaciones antes de que el usuario pueda realizar cualquier tarea. Durante este proceso, se comprueba el estado básico del hardware, se inicializan sus componentes y se localiza el dispositivo desde el que se cargará el sistema operativo. Es normal que aparezcan mensajes en pantalla y que parpadeen los indicadores de las unidades de almacenamiento o los LED de la caja, ya que estos signos indican actividad durante la inicialización.

Aunque tradicionalmente se habla de la **BIOS**, en los ordenadores actuales suele utilizarse **UEFI**, su sucesora.

#### 1. Suministro de energía y señal de encendido

Cuando se enciende la fuente de alimentación, ésta, convierte la corriente alterna de la red eléctrica en las diferentes tensiones continuas que necesitan los diversos componentes del ordenador.

La fuente envía a la placa base una señal denominada **Power Good** cuando las tensiones eléctricas son estables y se encuentran dentro de los valores adecuados. Mientras esta señal no se recibe, la placa base mantiene al procesador en estado de **reset**, es decir, impide que comience a ejecutar instrucciones. Esto evita que el procesador trabaje con una alimentación inestable.

#### 2. Reinicio del procesador

Una vez que la alimentación es estable, se libera el estado de reset del procesador. El procesador inicia su funcionamiento en un estado definido por la arquitectura del sistema. Algunos registros se ponen a cero y en otros se pone u valor por defecto. Finalmente, se establece una dirección de registro inicial de ejecución.

El procesador comienza entonces a ejecutar instrucciones del firmware almacenado en la placa base. En los equipos antiguos este firmware se denominaba **BIOS** y se almacenaba en una memoria de solo lectura. En los equipos actuales normalmente se encuentra en una memoria flash que contiene firmware UEFI.

Llegados a este punto, se comienza a inicializar y comprobar el hardware (pasos 3 y 4), de forma simultánea.

#### 3. Inicialización del hardware

El firmware realiza una configuración inicial de los componentes principales de la placa base, entre ellos:

- El procesador.
- La memoria RAM.
- El chipset o los controladores integrados.
- El teclado y otros dispositivos básicos.
- La tarjeta gráfica o el sistema de vídeo.
- Los controladores de almacenamiento.
- Los puertos y dispositivos necesarios para continuar el arranque.
- Etc

Durante esta fase pueden aparecer mensajes en pantalla, aunque muchos equipos modernos muestran únicamente un logotipo o mantienen una pantalla gráfica de UEFI.

#### 4. POST: comprobación inicial del hardware

El POST verifica que los componentes esenciales respondan correctamente y que el ordenador pueda continuar el proceso de arranque. Entre las comprobaciones habituales se encuentran:

- Comprobación básica del procesador.
- Detección y prueba inicial de la memoria RAM.
- Inicialización del sistema de vídeo.
- Detección del teclado y de otros dispositivos básicos.
- Detección de unidades de almacenamiento.
- Comprobación de algunos controladores integrados.
- Verificación de determinados parámetros de configuración.
- Comprobación de que existe una configuración válida para continuar el arranque.

Estas pruebas no constituyen un diagnóstico completo de todos los componentes. Normalmente son comprobaciones iniciales que permiten detectar fallos graves o componentes que no han sido detectados.

#### 5. Comunicación de errores

Si el POST encuentra un problema, el firmware puede informar de distintas formas:

- Mostrando un mensaje de error en pantalla.
- Emitiendo pitidos mediante el altavoz interno de la placa base.
- Encendiendo una serie de LED de diagnóstico.
- Mostrando un código en un display de la placa base.
- Deteniendo el proceso de arranque.

La forma de comunicar el error depende del fabricante y del modelo de la placa base. Por ejemplo, un problema con la memoria RAM puede impedir que aparezca cualquier imagen en pantalla, por lo que el equipo podría utilizar pitidos o indicadores luminosos para informar del fallo.

Si el error es crítico, el ordenador no puede continuar hasta que se resuelva. Si el error no impide el funcionamiento básico, el firmware puede mostrar una advertencia y permitir que el arranque continúe.

#### 6. Búsqueda del dispositivo de arranque

Una vez superadas las comprobaciones iniciales, la BIOS o UEFI consulta el orden de arranque configurado. Este orden indica dónde debe buscar el programa que iniciará el sistema operativo. Los dispositivos habituales son:

- Una unidad SSD o disco duro.
- Una unidad USB.
- Una unidad óptica.
- Una unidad de red.

En sistemas con BIOS tradicional, el firmware suele buscar el código de arranque en el sector correspondiente del dispositivo. En sistemas UEFI, normalmente busca una aplicación de arranque dentro de una partición especial llamada **partición del sistema EFI**.

Si no se encuentra ningún dispositivo de arranque válido, aparece un mensaje como “No bootable device” o “Operating system not found”.

#### 7. Carga del gestor de arranque

El firmware ejecuta el **gestor de arranque**, que es un programa encargado de iniciar la carga del sistema operativo. Algunos ejemplos son **Windows Boot Manager**, **GRUB** en muchas distribuciones Linux y otros gestores equivalentes.

El gestor de arranque puede mostrar un menú para elegir entre varios sistemas operativos o configuraciones. Después localiza el núcleo o *kernel* del sistema operativo y lo carga en la memoria RAM.

#### 8. Inicio del sistema operativo

Finalmente, el núcleo del sistema operativo toma el control del ordenador. A partir de ese momento se cargan progresivamente:

- Los controladores de dispositivos.
- Los servicios del sistema.
- La configuración de red.
- Los programas de inicio.
- La pantalla de inicio de sesión o el escritorio.

Cuando termina esta fase, el ordenador queda preparado para que el usuario pueda trabajar con normalidad.


Radiografía de una placa base, crédito a @han_ay 
https://imgur.com/a/motherboard-diagram-v2-GF3wqKT
