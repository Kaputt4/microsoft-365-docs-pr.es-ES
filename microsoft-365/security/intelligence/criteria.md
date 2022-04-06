---
title: Cómo Identifica Microsoft malware y aplicaciones potencialmente no deseadas
ms.reviewer: ''
description: Obtenga información sobre cómo Microsoft revisa el software para las infracciones de privacidad y otros comportamientos negativos, para determinar si es malware o una aplicación potencialmente no deseada.
keywords: seguridad, malware, amenazas de investigación de virus, malware de investigación, protección de dispositivos, infección del equipo, infección de virus, descripciones, corrección, amenazas más recientes, MMdevice, Centro de protección contra malware de Microsoft, PUA, aplicaciones potencialmente no deseadas
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
ms.date: 12/13/2021
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: 3eb7eefb5309383b46189f784f811224dcfb2b28
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2022
ms.locfileid: "63681932"
---
# <a name="how-microsoft-identifies-malware-and-potentially-unwanted-applications"></a>Cómo Identifica Microsoft malware y aplicaciones potencialmente no deseadas

Microsoft tiene como objetivo proporcionar una experiencia Windows agradable y productiva trabajando para garantizar que estás seguro y con el control de tus dispositivos. Microsoft le ayuda a protegerse de posibles amenazas al identificar y analizar el software y el contenido en línea. Al descargar, instalar y ejecutar software, se comprueba la reputación de los programas descargados y se garantiza que está protegido contra amenazas conocidas. También se le advierte sobre software desconocido para nosotros.  

Puede ayudar a Microsoft enviando software [desconocido o sospechoso para su análisis](https://www.microsoft.com/wdsi/filesubmission/). Esto ayudará a garantizar que nuestro sistema examina software desconocido o sospechoso para empezar a establecer la reputación. [Obtenga más información sobre cómo enviar archivos para su análisis](submission-guide.md)

En las secciones siguientes se proporciona información general sobre las clasificaciones que usamos para las aplicaciones y los tipos de comportamientos que llevan a esa clasificación.

>[!NOTE]
> Se están desarrollando y distribuyendo rápidamente nuevas formas de malware y aplicaciones potencialmente no deseadas. Es posible que la lista siguiente no sea completa y Microsoft se reserva el derecho de ajustar, expandir y actualizar estas sin previo aviso ni anuncio.

## <a name="unknown--unrecognized-software"></a>Desconocido: software no reconocido  

Ninguna tecnología de protección o antivirus es perfecta. Se necesita tiempo para identificar y bloquear aplicaciones y sitios malintencionados, o confiar en los programas y certificados recién publicados.Con casi 2.000 millones de sitios web en Internet y software actualizados y publicados continuamente, es imposible tener información sobre cada sitio y programa.

Piense en las advertencias desconocidas o descargadas de forma poco frecuente como un sistema de advertencia temprana para malware potencialmente no detectado. Por lo general, hay un retraso desde el momento en que se libera nuevo malware hasta que se identifica. No todos los programas poco comunes son malintencionados, pero el riesgo en la categoría desconocida es mucho mayor para el usuario típico. Las advertencias de software desconocido no son bloques. Los usuarios pueden elegir descargar y ejecutar la aplicación normalmente si lo desean.

Una vez que se recopilan suficientes datos, las soluciones de seguridad de Microsoft pueden tomar una determinación. No se encuentra ninguna amenaza o una aplicación o software se clasifica como malware o software potencialmente no deseado.

## <a name="malware"></a>Malware

El malware es el nombre general de las aplicaciones y otro código, como el software, que Microsoft clasifica de forma más granular como *software* malintencionado o *software no deseado*.

### <a name="malicious-software"></a>Software malintencionado

El software malintencionado es una aplicación o código que pone en peligro la seguridad del usuario. El software malintencionado puede robar tu información personal, bloquear el dispositivo hasta que pagues un rescate, usar el dispositivo para enviar correo no deseado o descargar otro software malintencionado. En general, el software malintencionado quiere engañar, engañar o defraudar a los usuarios, lo que los coloca en estados vulnerables.

Microsoft clasifica la mayoría de software malintencionado en una de las siguientes categorías:

* **Puerta trasera:** Un tipo de malware que proporciona a los hackers malintencionados acceso remoto y control de su dispositivo.

* **Comando y control:** Un tipo de malware que infecta el dispositivo y establece la comunicación con el servidor de comandos y control de los hackers para recibir instrucciones. Una vez establecida la comunicación, los hackers pueden enviar comandos que pueden robar datos, apagar y reiniciar el dispositivo y interrumpir los servicios web.

* **Descargador:** Un tipo de malware que descarga otro malware en el dispositivo. Debe conectarse a Internet para descargar archivos.

* **Dropper:** Un tipo de malware que instala otros archivos de malware en el dispositivo.A diferencia de un descargador, un cuentagotas no tiene que conectarse a Internet para colocar archivos malintencionados. Los archivos eliminados normalmente se incrustan en el propio cuentagotas.

* **Exploit:** Un fragmento de código que usa vulnerabilidades de software para obtener acceso al dispositivo y realizar otras tareas, como instalar malware. [Vea más información sobre vulnerabilidades de seguridad](exploits-malware.md).

* **Hacktool:** Un tipo de herramienta que se puede usar para obtener acceso no autorizado al dispositivo.

* **Virus de macro:** Un tipo de malware que se propaga a través de documentos infectados, como Microsoft Word o Excel documentos. El virus se ejecuta cuando se abre un documento infectado.

* **Ofuscator:** Un tipo de malware que oculta su código y propósito, lo que dificulta la detección o eliminación de software de seguridad.

* **Administrador de contraseñas:** Un tipo de malware que recopila su información personal, como nombres de usuario y contraseñas. A menudo funciona junto con un registrador de teclas, que recopila y envía información sobre las teclas que presiona y los sitios web que visita.

* **Ransomware:** Un tipo de malware que cifra los archivos o realiza otras modificaciones que pueden impedir que uses el dispositivo. A continuación, muestra una nota de rescate que indica que debe pagar dinero o realizar otras acciones antes de poder volver a usar el dispositivo. [Vea más información sobre ransomware](/security/compass/human-operated-ransomware).

* **Software de seguridad no deseado:** Malware que pretende ser software de seguridad pero que no proporciona ninguna protección. Este tipo de malware suele mostrar alertas sobre amenazas inexistentes en el dispositivo. También intenta convencerte de que pagues por sus servicios.

* **Troyano:** Un tipo de malware que intenta parecer inofensivo. A diferencia de un virus o un gusano, un troyano no se propaga por sí mismo. En su lugar, intenta parecer legítimo para engañar a los usuarios para que lo descarguen e instalen. Una vez instalados, los troyanos realizan diversas actividades malintencionadas, como robar información personal, descargar otro malware o dar acceso a los atacantes al dispositivo.

* **Clicker de Troyano:** Un tipo de troyano que hace clic automáticamente en botones o controles similares en sitios web o aplicaciones. Los atacantes pueden usar este troyano para hacer clic en anuncios en línea. Estos clics pueden sesgar sondeos en línea u otros sistemas de seguimiento e incluso pueden instalar aplicaciones en el dispositivo.

* **Gusano:** Un tipo de malware que se propaga a otros dispositivos. Los gusanos pueden propagarse a través del correo electrónico, la mensajería instantánea, las plataformas de uso compartido de archivos, las redes sociales, los recursos compartidos de red y las unidades extraíbles. Los gusanos sofisticados aprovechan las vulnerabilidades de software para propagarse.

### <a name="unwanted-software"></a>Software no deseado

Microsoft cree que debe tener control sobre su experiencia Windows usuario. El software que se Windows debe mantener el control del dispositivo a través de opciones informadas y controles accesibles. Microsoft identifica comportamientos de software que garantizan que mantenga el control. Clasificamos software que no muestra completamente estos comportamientos como "software no deseado".

#### <a name="lack-of-choice"></a>Falta de elección

Debes recibir una notificación sobre lo que está sucediendo en el dispositivo, incluido lo que hace el software y si está activo.

El software que muestra falta de elección puede:

* No se puede proporcionar un aviso destacado sobre el comportamiento del software y su propósito e intención.

* No se puede indicar claramente cuándo está activo el software. También puede intentar ocultar o ocultar su presencia.

* Instalar, reinstalar o quitar software sin su permiso, interacción o consentimiento.

* Instale otro software sin una indicación clara de su relación con el software principal.

* Eludir los cuadros de diálogo de consentimiento del usuario desde el explorador o el sistema operativo.

* Falsely claim to be software from Microsoft.

El software no debe engañar o coaccion a tomar decisiones sobre el dispositivo. Se considera un comportamiento que limita las elecciones. Además de la lista anterior, el software que muestra la falta de elección puede:

* Muestra notificaciones exageradas sobre el estado del dispositivo.

* Realiza notificaciones engañosas o inexactas sobre archivos, entradas del Registro u otros elementos del dispositivo.

* Muestra las notificaciones de forma alarmante sobre el estado del dispositivo y requiere el pago o determinadas acciones a cambio de solucionar los supuestos problemas.

El software que almacena o transmite sus actividades o datos debe:

* Notifítese y obtenga su consentimiento para hacerlo. El software no debe incluir una opción que lo configure para ocultar actividades asociadas con el almacenamiento o transmisión de los datos.

#### <a name="lack-of-control"></a>Falta de control

Debes poder controlar el software en el dispositivo. Debe poder iniciar, detener o revocar la autorización del software.

El software que muestra falta de control puede:

* Impedir o limitar la visualización o modificación de las características o la configuración del explorador.

* Abra las ventanas del explorador sin autorización.

* Redirigir el tráfico web sin dar aviso y obtener consentimiento.

* Modificar o manipular el contenido de la página web sin su consentimiento.

El software que cambia la experiencia de exploración solo debe usar el modelo de extensibilidad admitido del explorador para la instalación, ejecución, deshabilitación o eliminación. Los exploradores que no proporcionan modelos de extensibilidad compatibles se consideran no extensibles y no deben modificarse.

#### <a name="installation-and-removal"></a>Instalación y eliminación

Debe poder iniciar, detener o revocar la autorización dada al software. El software debe obtener su consentimiento antes de instalarlo y debe proporcionar una forma clara y sencilla de instalarlo, desinstalarlo o deshabilitarlo.

El software que ofrece una *experiencia de instalación deficiente* puede empaquetar o descargar otro "software no deseado" según lo clasificado por Microsoft.

El software que ofrece una *mala experiencia de eliminación* puede:

* Presente mensajes o ventanas emergentes confusos o engañosos cuando intente desinstalarlo.

* No se pueden usar características estándar de instalación o desinstalación, como Agregar o quitar programas.

#### <a name="advertising-and-advertisements"></a>Publicidad y anuncios

El software que promueve un producto o servicio fuera del propio software puede interferir con la experiencia informática. Debe tener una opción clara y un control al instalar software que presente anuncios.

Los anuncios que se presentan por software deben:

* Incluir una forma obvia para que los usuarios cierren el anuncio. El acto de cerrar el anuncio no debe abrir otro anuncio.

* Incluya el nombre del software que presentó el anuncio.

El software que presenta estos anuncios debe:

* Proporcione un método de desinstalación estándar para el software con el mismo nombre que se muestra en el anuncio que presenta.

Los anuncios que se muestran deben:

* Ser distinguible del contenido del sitio web.

* No engañar, engañar ni confundir.

* No contiene código malintencionado.

* No invocar una descarga de archivos.

#### <a name="consumer-opinion"></a>Opinión del consumidor

Microsoft mantiene una red mundial de analistas y sistemas de inteligencia donde puede [enviar software para su análisis](https://www.microsoft.com/wdsi/filesubmission). Su participación ayuda a Microsoft a identificar el nuevo malware rápidamente. Después del análisis, Microsoft crea inteligencia de seguridad para software que cumple los criterios descritos. Esta inteligencia de seguridad identifica el software como malware y está disponible para todos los usuarios a través de Antivirus de Microsoft Defender y otras soluciones antimalware de Microsoft.

## <a name="potentially-unwanted-application-pua"></a>Aplicación potencialmente no deseada (PUA)

Nuestra protección de PUA tiene como objetivo proteger la productividad del usuario y garantizar experiencias Windows agradables. Esta protección ayuda a ofrecer experiencias más productivas, de rendimiento y Windows agradables. Para obtener instrucciones sobre cómo habilitar la protección de PUA en Chromium basada en Microsoft Edge y Antivirus de Microsoft Defender, vea Detectar y bloquear aplicaciones potencialmente [no deseadas](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).

*Las PUA no se consideran malware.*

Microsoft usa categorías específicas y las definiciones de categoría para clasificar el software como una PUA.

* **Software de publicidad:** Software que muestra anuncios o promociones, o le pide que complete encuestas para otros productos o servicios en software que no sea él mismo. Esto incluye software que inserta anuncios en páginas web.

* **Software de Torrent (solo Enterprise):** software que se usa para crear o descargar torrents u otros archivos que se usan específicamente con tecnologías de uso compartido de archivos punto a punto.

* **Software de criptomining (solo Enterprise):** software que usa los recursos del dispositivo para extraer criptodivisas.

* **Software de agrupación:** Software que ofrece instalar otro software que no está desarrollado por la misma entidad o que no es necesario para que se ejecute el software. Además, software que ofrece instalar otro software que califica como PUA en función de los criterios descritos en este documento.

* **Software de marketing:** Software que supervisa y transmite las actividades de los usuarios a aplicaciones o servicios distintos de sí mismos para la investigación de marketing.

* **Software de evasión:** Software que intenta eludir activamente la detección por parte de productos de seguridad, incluido el software que se comporta de forma diferente en presencia de productos de seguridad.

* **Mala reputación del sector:** Software que los proveedores de seguridad de confianza detectan con sus productos de seguridad. El sector de seguridad está dedicado a proteger a los clientes y mejorar sus experiencias. Microsoft y otras organizaciones del sector de seguridad intercambian continuamente conocimientos sobre los archivos que hemos analizado para proporcionar a los usuarios la mejor protección posible.

