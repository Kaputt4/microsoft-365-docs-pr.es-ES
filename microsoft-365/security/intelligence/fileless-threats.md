---
title: Amenazas sin archivos
ms.reviewer: ''
description: Obtenga información sobre las categorías de amenazas sin archivos y malware que viven fuera de la tierra
keywords: malware sin archivos, sin archivos, que vive de la tierra, lolbins, amsi, supervisión del comportamiento, análisis de memoria, protección del sector de arranque, seguridad, malware, ATP de Windows Defender, antivirus, AV, ATP de Microsoft Defender, protección de próxima generación
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 97545714ff468c7be238585ab5d137a1ac93a5f9
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681976"
---
# <a name="fileless-threats"></a>Amenazas sin archivos

¿Qué son exactamente las amenazas sin archivos? El término "sin archivos" sugiere que una amenaza no se incluye en un archivo, como una puerta trasera que solo se encuentra en la memoria de un equipo. Sin embargo, no hay una definición para malware sin archivos. El término se usa de forma general y, a veces, para describir familias de malware que sí dependen de los archivos para funcionar.

Los ataques [implican varias fases](https://attack.mitre.org/wiki/ATT&CK_Matrix) para funcionalidades como la ejecución, la persistencia o el robo de información. Algunas partes de la cadena de ataques pueden no tener archivos, mientras que otras pueden implicar al sistema de archivos de alguna forma.

Para mayor claridad, las amenazas sin archivos se agrupan en distintas categorías.

![Diagrama completo de malware sin archivos.](../../media/security-intelligence-images/fileless-malware.png)<br>
*Figura 1. Diagrama completo de malware sin archivos*

Las amenazas sin archivos se pueden clasificar por su punto de entrada, lo que indica cómo el malware sin archivos puede llegar a una máquina. Pueden llegar a través de una vulnerabilidad de seguridad, mediante hardware en peligro o mediante la ejecución regular de aplicaciones y scripts.

A continuación, enumera la forma de punto de entrada. Por ejemplo, las vulnerabilidades pueden basarse en archivos o datos de red, los periféricos PCI son un tipo de vector de hardware y los scripts y los ejecutables son subcategorías del vector de ejecución.

Por último, clasifique el host de la infección. Por ejemplo, una aplicación Flash puede contener una variedad de amenazas, como un exploit, un ejecutable simple y un firmware malintencionado de un dispositivo de hardware.

Clasificar le ayuda a dividir y clasificar los distintos tipos de amenazas sin archivos. Algunas son más peligrosas pero también más difíciles de implementar, mientras que otras se usan con más frecuencia a pesar de que (o precisamente debido a) no están muy avanzadas.

Desde esta categorización, puede obtener tres tipos principales de amenazas sin archivos en función de la huella digital que pueden dejar en máquinas infectadas.

## <a name="type-i-no-file-activity-performed"></a>Tipo I: No se realizó ninguna actividad de archivo

Un malware sin archivos se puede considerar como uno que nunca requiere escribir un archivo en el disco. ¿Cómo infectaría dicho malware una máquina en primer lugar? Un ejemplo es donde una máquina de destino recibe paquetes de red malintencionados que aprovechan la vulnerabilidad de EternalBlue. La vulnerabilidad permite la instalación de la puerta trasera DoublePulsar, que termina residiendo solo en la memoria del kernel. En este caso, no hay ningún archivo ni datos escritos en un archivo.

Un dispositivo en peligro también puede tener código malintencionado oculto en el firmware del dispositivo (como un BIOS), un periférico USB (como el ataque BadUSB) o en el firmware de una tarjeta de red. Todos estos ejemplos no requieren que se ejecute un archivo en el disco y, teóricamente, solo pueden estar en la memoria. El código malintencionado sobreviviría a reinicios, reformates de disco y reinstalaciones del sistema operativo.

Las infecciones de este tipo pueden ser especialmente difíciles de detectar porque la mayoría de los productos antivirus no tienen la capacidad de inspeccionar el firmware. En los casos en los que un producto tiene la capacidad de inspeccionar y detectar firmware malintencionado, todavía hay desafíos importantes asociados con la corrección de amenazas en este nivel. Este tipo de malware sin archivos requiere altos niveles de sofisticación y, a menudo, depende de la configuración de hardware o software en particular. No es un vector de ataque que se pueda aprovechar de forma fácil y confiable. Aunque son peligrosas, las amenazas de este tipo son poco comunes y no son prácticas para la mayoría de los ataques.

## <a name="type-ii-indirect-file-activity"></a>Tipo II: Actividad indirecta de archivos

Hay otras formas en que el malware puede lograr la presencia sin archivos en una máquina sin necesidad de un esfuerzo de ingeniería significativo. El malware sin archivos de este tipo no escribe directamente archivos en el sistema de archivos, pero pueden terminar usando archivos indirectamente. Por ejemplo, con los atacantes [poshspy backdoor](https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html) instalado un comando de PowerShell malintencionado en el repositorio WMI y configurado un filtro WMI para ejecutar el comando periódicamente.

Es posible llevar a cabo dicha instalación a través de la línea de comandos sin necesidad de que una puerta trasera ya esté en el archivo. El malware se puede instalar y ejecutar teóricamente sin tocar nunca el sistema de archivos. Sin embargo, el repositorio WMI se almacena en un archivo físico en un área de almacenamiento central administrada por el Administrador de objetos CIM y normalmente contiene datos legítimos. Aunque la cadena de infección usa técnicamente un archivo físico, se considera un ataque sin archivos porque el repositorio WMI es un contenedor de datos multipropósito que no se puede detectar ni quitar.

## <a name="type-iii-files-required-to-operate"></a>Tipo III: Archivos necesarios para funcionar

Algunos malware pueden tener una clase de persistencia sin archivos, pero no sin usar archivos para funcionar. Un ejemplo para este escenario es Kovter, que crea un controlador de verbos abiertos del shell en el Registro para una extensión de archivo aleatoria. Abrir un archivo con dicha extensión llevará a la ejecución de un script a través de la herramienta legítima mshta.exe.

![Imagen de la clave del Registro de Kovter.](../../media/security-intelligence-images/kovter-reg-key.png)<br>
*Figura 2. Clave del Registro de Kovter*

Cuando se invoca el verbo abierto, se inicia el comando asociado del Registro, lo que da como resultado la ejecución de un script pequeño. Este script lee los datos de otra clave del Registro y los ejecuta, lo que a su vez lleva a la carga de la carga final. Sin embargo, para desencadenar el verbo abierto en primer lugar, Kovter debe colocar un archivo con la misma extensión dirigida por el verbo (en el ejemplo anterior, la extensión es .bbf5590fd). También tiene que establecer una clave de ejecución automática configurada para abrir dicho archivo cuando se inicia la máquina.

Kovter se considera una amenaza sin archivos porque el sistema de archivos no es práctico. Los archivos con extensiones aleatorias contienen datos no deseados que no son utilizables para comprobar la presencia de la amenaza. Los archivos que almacenan el Registro son contenedores que no se pueden detectar y eliminar si hay contenido malintencionado.

## <a name="categorizing-fileless-threats-by-infection-host"></a>Categorizar las amenazas sin archivos por host de infección

Después de describir las categorías generales, ahora podemos profundizar en los detalles y proporcionar un desglose de los hosts de infección. Esta clasificación completa cubre el panorama de lo que normalmente se conoce como malware sin archivos. Impulsa nuestros esfuerzos para investigar y desarrollar nuevas características de protección que neutralicen las clases de ataques y garanticen que el malware no obtenga ventaja en la carrera armamentista.

### <a name="exploits"></a>Exploits

**Basado en** archivos (tipo III: ejecutable, Flash, Java, documentos): un archivo inicial puede aprovechar el sistema operativo, el explorador, el motor de Java, el motor Flash, etc. para ejecutar un código de shell y entregar una carga en la memoria. Aunque la carga no tiene archivos, el vector de entrada inicial es un archivo.

**Basado en red** (tipo I): una comunicación de red que aprovecha una vulnerabilidad en el equipo de destino puede lograr la ejecución de código en el contexto de una aplicación o el kernel. Un ejemplo es WannaCry, que aprovecha una vulnerabilidad previamente fija en el protocolo SMB para entregar una puerta trasera dentro de la memoria del kernel.

### <a name="hardware"></a>Hardware

**Basado en dispositivos** (tipo I: tarjeta de red, disco duro): dispositivos como discos duros y tarjetas de red requieren conjuntos de chips y software dedicado para funcionar. El software que reside y se ejecuta en el conjunto de chips de un dispositivo se denomina firmware. Aunque es una tarea compleja, el firmware puede estar infectado por malware, como ha detectado el grupo de [espionaje de ecuaciones](https://www.kaspersky.com/blog/equation-hdd-malware/7623/).

**Basado en CPU** (tipo I): las CPU modernas son complejas y pueden incluir subsistemas que ejecutan firmware con fines de administración. Dicho firmware puede ser vulnerable al secuestro y permitir la ejecución de código malintencionado que funcionaría desde dentro de la CPU. En diciembre de 2017, dos investigadores informaron de una vulnerabilidad que puede permitir a los atacantes ejecutar código dentro del motor de administración [(ME)](https://en.wikipedia.org/wiki/Intel_Management_Engine) presente en cualquier CPU moderna de Intel. Mientras tanto, se ha observado que el grupo de atacantes PLATINUM tiene la capacidad de usar la Tecnología de administración activa [(AMT)](https://en.wikipedia.org/wiki/Intel_Active_Management_Technology) de Intel para realizar comunicaciones [de red invisibles](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/07/platinum-continues-to-evolve-find-ways-to-maintain-invisibility/), omitiendo el sistema operativo instalado. ME y AMT son, básicamente, micro pc autónomos que viven dentro de la CPU y que funcionan a un nivel muy bajo. Dado que el objetivo de estas tecnologías es proporcionar facilidad de administración remota, tienen acceso directo al hardware, son independientes del sistema operativo y pueden ejecutarse incluso si el equipo está desactivado.

Además de ser vulnerables en el nivel de firmware, las CPU podrían fabricarse con puertas traseras insertadas directamente en los circuitos de hardware. Este ataque se ha [investigado y ha sido posible](https://www.emsec.rub.de/media/crypto/veroeffentlichungen/2015/03/19/beckerStealthyExtended.pdf) en el pasado. Se ha notificado que ciertos modelos de procesadores x86 contienen un núcleo de CPU de tipo RISC incrustado secundario que puede proporcionar eficazmente una puerta trasera [a](https://www.theregister.co.uk/2018/08/10/via_c3_x86_processor_backdoor/) través de la cual las aplicaciones regulares pueden obtener una ejecución con privilegios.

**Basado en USB** (tipo I): los dispositivos USB de todo tipo se pueden reprogramar con firmware malintencionado capaz de interactuar con el sistema operativo de maneras nefastas. Por ejemplo, la técnica [BadUSB](https://arstechnica.com/information-technology/2014/07/this-thumbdrive-hacks-computers-badusb-exploit-makes-devices-turn-evil/) permite que un stick USB reprogramado actúe como un teclado que envía comandos a las máquinas mediante pulsaciones de teclas o como una tarjeta de red que puede redirigir el tráfico a voluntad.

**Basado en BIOS** (tipo I): un BIOS es un firmware que se ejecuta dentro de un conjunto de chips. Se ejecuta cuando una máquina está encendida, inicializa el hardware y, a continuación, transfiere el control al sector de arranque. El BIOS es un componente importante que funciona a un nivel bajo y se ejecuta antes del sector de arranque. Es posible reprogramar el firmware del BIOS con código malintencionado, como ha ocurrido en el pasado con el [rootkit Mebromi](https://www.webroot.com/blog/2011/09/13/mebromi-the-first-bios-rootkit-in-the-wild/).

**Basado en hipervisor** (tipo I): las CPU modernas proporcionan compatibilidad con hipervisor de hardware, lo que permite al sistema operativo crear máquinas virtuales sólidas. Una máquina virtual se ejecuta en un entorno confinado y simulado y, en teoría, no es consciente de la emulación. Un malware que se hace cargo de una máquina puede implementar un hipervisor pequeño para ocultarse fuera del dominio del sistema operativo en ejecución. El malware de este tipo se ha teorizado en el pasado y, finalmente, se han observado rootkits [reales](http://seclists.org/fulldisclosure/2017/Jun/29) de hipervisor, aunque pocos se conocen hasta la fecha.

### <a name="execution-and-injection"></a>Ejecución e inyección

**Basado en archivos** (tipo III: ejecutables, DLL, archivos LNK, tareas programadas): este es el vector de ejecución estándar. Un archivo ejecutable simple se puede iniciar como un malware de primera fase para ejecutar una carga adicional en la memoria o insertarse en otros procesos de ejecución legítimos.

**Basado en** macros (tipo III: Office documentos): el lenguaje [VBA](/office/vba/Library-Reference/Concepts/getting-started-with-vba-in-office) es una herramienta flexible y eficaz diseñada para automatizar las tareas de edición y agregar funcionalidad dinámica a los documentos. Por lo tanto, los atacantes pueden abusar de él para llevar a cabo operaciones malintencionadas como decodificar, ejecutar o inyectar una carga ejecutable, o incluso implementar un ransomware completo, como en el caso de [qkG](https://blog.trendmicro.com/trendlabs-security-intelligence/qkg-filecoder-self-replicating-document-encrypting-ransomware/). Las macros se ejecutan en el contexto de un proceso Office (por ejemplo, Winword.exe) y se implementan en un lenguaje de scripting. No hay ningún archivo ejecutable binario que un antivirus pueda inspeccionar. Aunque Office aplicaciones requieren el consentimiento explícito del usuario para ejecutar macros desde un documento, los atacantes usan técnicas de ingeniería social para engañar a los usuarios para permitir que se ejecuten macros.

**Basado en** script (tipo II: archivo, servicio, registro, repositorio WMI, shell): los lenguajes de scripting de JavaScript, VBScript y PowerShell están disponibles de forma predeterminada en Windows plataformas. Los scripts tienen las mismas ventajas que las macros, son archivos textuales (no archivos ejecutables binarios) y se ejecutan en el contexto del intérprete (como wscript.exe, powershell.exe), que es un componente limpio y legítimo. Los scripts son versátiles y se pueden ejecutar desde un archivo (haciendo doble clic en ellos) o ejecutarse directamente en la línea de comandos de un intérprete. La ejecución en la línea de comandos permite al malware codificar scripts malintencionados como servicios [](https://www.gdatasoftware.com/blog/2014/07/23947-poweliks-the-persistent-malware-without-a-file) de inicio automático dentro de claves del Registro de ejecución automática como suscripciones de eventos [WMI](https://www.fireeye.com/blog/threat-research/2017/03/dissecting_one_ofap.html) desde el repositorio WMI. Además, un atacante que ha obtenido acceso a una máquina infectada puede introducir el script en el símbolo del sistema.

**Basado en disco** (tipo II: registro de arranque): el registro de arranque es el primer sector de un disco o volumen y contiene código ejecutable necesario para iniciar el proceso de arranque del sistema operativo. Amenazas como [Petya](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/27/new-ransomware-old-techniques-petya-adds-worm-capabilities/?source=mmpc) son capaces de infectar el registro de arranque sobrescribiendo con código malintencionado. Cuando se inicia la máquina, el malware obtiene el control inmediatamente. El registro de arranque reside fuera del sistema de archivos, pero es accesible por el sistema operativo. Los productos antivirus modernos tienen la capacidad de examinarlo y restaurarlo.

## <a name="defeating-fileless-malware"></a>Eliminar malware sin archivos

En Microsoft, supervisamos activamente el panorama de seguridad para identificar nuevas tendencias de amenazas y desarrollar soluciones para mitigar las clases de amenazas. Instrumentamos protecciones duraderas que son eficaces contra una amplia variedad de amenazas. A través de la Interfaz de detección de AntiMalware (AMSI), la supervisión del comportamiento, el examen de memoria y la protección del sector de arranque, [Microsoft Defender para](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint) endpoint puede inspeccionar las amenazas sin archivos incluso con una ofuscación pesada. Las tecnologías de aprendizaje automático en la nube nos permiten escalar estas protecciones contra amenazas nuevas y emergentes.

Para obtener más información, lea: Fuera de la vista pero no invisible: Eliminar malware sin archivos con supervisión de comportamiento [, AMSI y AV de próxima generación](https://cloudblogs.microsoft.com/microsoftsecure/2018/09/27/out-of-sight-but-not-invisible-defeating-fileless-malware-with-behavior-monitoring-amsi-and-next-gen-av/)

## <a name="additional-resources-and-information"></a>Recursos e información adicionales

Obtenga información sobre cómo [implementar capacidades de protección contra amenazas en Microsoft 365 E5](/microsoft-365/solutions/deploy-threat-protection).
