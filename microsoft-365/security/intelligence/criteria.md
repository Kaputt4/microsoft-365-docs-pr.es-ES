---
title: Cómo Microsoft identifica el malware y las aplicaciones potencialmente no deseadas
ms.reviewer: ''
description: Obtenga información sobre cómo Microsoft revisa el software en busca de infracciones de privacidad y otro comportamiento negativo, para determinar si es malware o una aplicación potencialmente no deseada.
keywords: security, malware, virus research threats, research malware, device protection, computer infection, virus infection, descriptions, remediation, latest threats, MMdevice, Centro de protección contra malware de Microsoft, PUA, potentially unwanted applications
ms.service: microsoft-365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
ms.date: 12/13/2021
search.appverid: met150
ms.openlocfilehash: 8f39e194015b22177f1418449cbef825c45ce1f9
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633359"
---
# <a name="how-microsoft-identifies-malware-and-potentially-unwanted-applications"></a>Cómo Microsoft identifica el malware y las aplicaciones potencialmente no deseadas

Microsoft tiene como objetivo proporcionar una experiencia de Windows deliciosa y productiva trabajando para asegurarse de que está seguro y en control de sus dispositivos. Microsoft le ayuda a protegerse de posibles amenazas mediante la identificación y el análisis de software y contenido en línea. Al descargar, instalar y ejecutar software, comprobamos la reputación de los programas descargados y nos aseguramos de que está protegido contra amenazas conocidas. También se le advierte sobre software que es desconocido para nosotros.  

Puede ayudar a Microsoft [mediante el envío de software desconocido o sospechoso para su análisis](https://www.microsoft.com/wdsi/filesubmission/). Esto ayudará a garantizar que nuestro sistema digitaliza software desconocido o sospechoso para empezar a establecer la reputación. [Más información sobre el envío de archivos para su análisis](submission-guide.md)

En las secciones siguientes se proporciona información general sobre las clasificaciones que usamos para las aplicaciones y los tipos de comportamientos que conducen a esa clasificación.

>[!NOTE]
> Se están desarrollando y distribuyendo rápidamente nuevas formas de malware y aplicaciones potencialmente no deseadas. Es posible que la lista siguiente no sea completa y Microsoft se reserva el derecho de ajustarlas, expandirlas y actualizarlas sin previo aviso o anuncio.

## <a name="unknown--unrecognized-software"></a>Desconocido: software no reconocido  

Ninguna tecnología antivirus o de protección es perfecta. Se necesita tiempo para identificar y bloquear aplicaciones y sitios malintencionados, o confiar en los programas y certificados recién publicados. Con casi 2 mil millones de sitios web en Internet y software continuamente actualizados y publicados, es imposible tener información sobre cada sitio y programa.

Piense en las advertencias desconocidas o descargadas de forma poco frecuente como un sistema de advertencias tempranas para malware potencialmente no detectado. Por lo general, hay un retraso desde el momento en que se libera nuevo malware hasta que se identifica. No todos los programas poco comunes son malintencionados, pero el riesgo en la categoría desconocida es mucho mayor para el usuario típico. Las advertencias de software desconocido no son bloques. Los usuarios pueden optar por descargar y ejecutar la aplicación normalmente si lo desean.

Una vez que se recopilan suficientes datos, las soluciones de seguridad de Microsoft pueden tomar una determinación. No se encuentra ninguna amenaza, o una aplicación o software se clasifica como malware o software potencialmente no deseado.

## <a name="malware"></a>Malware

El malware es el nombre general de las aplicaciones y otro código, como el software, que Microsoft clasifica de forma más granular como *software malintencionado* o *software no deseado*.

### <a name="malicious-software"></a>Software malintencionado

El software malintencionado es una aplicación o código que pone en peligro la seguridad del usuario. El software malintencionado puede robar su información personal, bloquear el dispositivo hasta que pague un rescate, usar su dispositivo para enviar correo no deseado o descargar otro software malintencionado. En general, el software malintencionado quiere engañar, engañar o defraudar a los usuarios, colocándolos en estados vulnerables.

Microsoft clasifica la mayoría del software malintencionado en una de las siguientes categorías:

* **Backdoor:** Un tipo de malware que proporciona a los hackers malintencionados acceso remoto y control del dispositivo.

* **Comando y control:** Un tipo de malware que infecta el dispositivo y establece la comunicación con el servidor de comandos y control de los hackers para recibir instrucciones. Una vez establecida la comunicación, los hackers pueden enviar comandos que pueden robar datos, apagar y reiniciar el dispositivo e interrumpir los servicios web.

* **Downloader:** Un tipo de malware que descarga otro malware en el dispositivo. Debe conectarse a Internet para descargar archivos.

* **Cuentagotas:** Un tipo de malware que instala otros archivos de malware en el dispositivo. A diferencia de un descargador, un dropper no tiene que conectarse a Internet para eliminar archivos malintencionados. Los archivos eliminados normalmente se insertan en el propio dropper.

* **Explotar:** Un fragmento de código que usa vulnerabilidades de software para obtener acceso al dispositivo y realizar otras tareas, como la instalación de malware. [Consulte más información sobre las vulnerabilidades de seguridad](exploits-malware.md).

* **Hacktool:** Un tipo de herramienta que se puede usar para obtener acceso no autorizado al dispositivo.

* **Virus de macro:** Un tipo de malware que se propaga a través de documentos infectados, como documentos de Microsoft Word o Excel. El virus se ejecuta al abrir un documento infectado.

* **Ofuscador:** Un tipo de malware que oculta su código y propósito, lo que dificulta la detección o eliminación del software de seguridad.

* **Roba contraseñas:** Un tipo de malware que recopila su información personal, como nombres de usuario y contraseñas. A menudo funciona junto con un keylogger, que recopila y envía información sobre las teclas que presiona y sitios web que visita.

* **Ransomware:** Un tipo de malware que cifra los archivos o realiza otras modificaciones que pueden impedir que use el dispositivo. Luego, aparece una nota de rescate que indica que debe pagar o realizar otras acciones para poder volver a usar el dispositivo. [Vea más información sobre ransomware](/security/compass/human-operated-ransomware).

* **Software de seguridad no autorizado:** Malware que pretende ser software de seguridad, pero no proporciona ninguna protección. Este tipo de malware suele mostrar alertas sobre amenazas inexistentes en el dispositivo. También intenta convencerle de que pague por sus servicios.

* **Troyano:** Un tipo de malware que intenta parecer inofensivo. A diferencia de un virus o un gusano, un troyano no se propaga por sí mismo. En su lugar, intenta parecer legítimo para engaña a los usuarios para que lo descarguen e instalen. Una vez instalados, los troyanos realizan diversas actividades malintencionadas, como robar información personal, descargar otro malware o dar acceso a los atacantes al dispositivo.

* **Clicker troyano:** Un tipo de troyano que hace clic automáticamente en botones o controles similares en sitios web o aplicaciones. Los atacantes pueden usar este troyano para hacer clic en anuncios en línea. Estos clics pueden sesgar sondeos en línea u otros sistemas de seguimiento e incluso pueden instalar aplicaciones en el dispositivo.

* **Gusano:** Un tipo de malware que se propaga a otros dispositivos. Los gusanos pueden propagarse por correo electrónico, mensajería instantánea, plataformas de uso compartido de archivos, redes sociales, recursos compartidos de red y unidades extraíbles. Los gusanos más sofisticados aprovechan las vulnerabilidades de software para propagarse.

### <a name="unwanted-software"></a>Software no deseado

Microsoft cree que debe tener control sobre la experiencia de Windows. El software que se ejecuta en Windows debe mantener el control del dispositivo a través de opciones informadas y controles accesibles. Microsoft identifica los comportamientos de software que garantizan su control. Clasificamos el software que no demuestra completamente estos comportamientos como "software no deseado".

#### <a name="lack-of-choice"></a>Falta de elección

Debe recibir una notificación sobre lo que sucede en el dispositivo, incluido lo que hace el software y si está activo.

El software que presenta falta de elección podría:

* No se puede proporcionar un aviso destacado sobre el comportamiento del software y su propósito e intención.

* No se puede indicar claramente cuándo está activo el software. También podría intentar ocultar o disfrazar su presencia.

* Instale, reinstale o quite software sin su permiso, interacción o consentimiento.

* Instale otro software sin una indicación clara de su relación con el software principal.

* Evite los diálogos de consentimiento del usuario desde el explorador o el sistema operativo.

* Afirma falsamente que es software de Microsoft.

El software no debe inducir a error ni obligarle a tomar decisiones sobre el dispositivo. Se considera un comportamiento que limita las opciones. Además de la lista anterior, el software que presenta falta de elección podría:

* Muestra notificaciones exageradas sobre el estado del dispositivo.

* Realice notificaciones engañosas o inexactas sobre archivos, entradas del Registro u otros elementos del dispositivo.

* Mostrar notificaciones de forma alarmante sobre el estado del dispositivo y requerir el pago o ciertas acciones a cambio de corregir los supuestos problemas.

El software que almacena o transmite sus actividades o datos debe:

* Fíjese en usted y obtenga su consentimiento para hacerlo. El software no debe incluir una opción que la configure para ocultar las actividades asociadas con el almacenamiento o la transmisión de los datos.

#### <a name="lack-of-control"></a>Falta de control

Debe poder controlar el software en el dispositivo. Debe poder iniciar, detener o revocar la autorización al software.

El software que presenta falta de control podría:

* Impedir o limitar la visualización o modificación de las características o la configuración del explorador.

* Abra las ventanas del explorador sin autorización.

* Redirigir el tráfico web sin previo aviso y obtener consentimiento.

* Modifique o manipule el contenido de la página web sin su consentimiento.

El software que cambia la experiencia de exploración solo debe usar el modelo de extensibilidad compatible del explorador para la instalación, ejecución, deshabilitación o eliminación. Los exploradores que no proporcionan modelos de extensibilidad admitidos se consideran no extensibles y no deben modificarse.

#### <a name="installation-and-removal"></a>Instalación y eliminación

Debe poder iniciar, detener o revocar la autorización dada al software. El software debe obtener su consentimiento antes de la instalación, y debe proporcionar una manera clara y sencilla de instalarlo, desinstalarlo o deshabilitarlo.

El software que ofrece *una experiencia de instalación deficiente* podría agrupar o descargar otro "software no deseado" clasificado por Microsoft.

El software que ofrece *una experiencia de eliminación deficiente* podría:

* Presentar mensajes o elementos emergentes confusos o engañosos al intentar desinstalarlo.

* No se pueden usar características estándar de instalación o desinstalación, como Agregar o quitar programas.

#### <a name="advertising-and-advertisements"></a>Publicidad y anuncios

El software que promueve un producto o servicio fuera del propio software puede interferir con su experiencia informática. Usted debe tener una clara elección y control al instalar software que presenta anuncios.

Los anuncios que presenta el software deben:

* Incluya una manera obvia para que los usuarios cierren el anuncio. El acto de cerrar el anuncio no debe abrir otro anuncio.

* Incluya el nombre del software que presentó el anuncio.

El software que presenta estos anuncios debe:

* Proporcione un método de desinstalación estándar para el software con el mismo nombre que se muestra en el anuncio que presenta.

Los anuncios que se muestran a usted deben:

* Se puede distinguir del contenido del sitio web.

* No engañar, engañar ni confundir.

* No contiene código malintencionado.

* No invocar una descarga de archivos.

#### <a name="consumer-opinion"></a>Opinión del consumidor

Microsoft mantiene una red mundial de analistas y sistemas de inteligencia donde puede [enviar software para su análisis](https://www.microsoft.com/wdsi/filesubmission). Su participación ayuda a Microsoft a identificar malware nuevo rápidamente. Después del análisis, Microsoft crea inteligencia de seguridad para software que cumple los criterios descritos. Esta inteligencia de seguridad identifica el software como malware y está disponible para todos los usuarios a través de Microsoft Defender Antivirus y otras soluciones antimalware de Microsoft.

## <a name="potentially-unwanted-application-pua"></a>Aplicación potencialmente no deseada (PUA)

Nuestra protección pua tiene como objetivo proteger la productividad del usuario y garantizar experiencias agradables de Windows. Esta protección ayuda a ofrecer experiencias de Windows más productivas, eficaces y encantadoras. Para obtener instrucciones sobre cómo habilitar la protección de PUA en Microsoft Edge basado en Chromium y Microsoft Defender Antivirus, consulte [Detectar y bloquear aplicaciones potencialmente no deseadas](/microsoft-365/security/defender-endpoint/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).

*Las PUA no se consideran malware.*

Microsoft usa categorías específicas y las definiciones de categorías para clasificar el software como un PUA.

* **Software de publicidad:** Software que muestra anuncios o promociones, o le pide que complete encuestas para otros productos o servicios en software distinto de sí mismo. Esto incluye software que inserta anuncios en páginas web.

* **Software torrent (solo enterprise):** Software que se usa para crear o descargar torrents u otros archivos que se usan específicamente con tecnologías de uso compartido de archivos punto a punto.

* **Software cryptomining (solo enterprise):** Software que usa los recursos del dispositivo para extraer criptomonedas.

* **Agrupación de software:** Software que ofrece instalar otro software que no está desarrollado por la misma entidad o no es necesario para que el software se ejecute. Además, el software que ofrece para instalar otro software que califica como PUA en función de los criterios descritos en este documento.

* **Software de marketing:** Software que supervisa y transmite las actividades de los usuarios a aplicaciones o servicios distintos de sí mismos para la investigación de marketing.

* **Software de evasión:** Software que intenta eludir activamente la detección por parte de los productos de seguridad, incluido el software que se comporta de manera diferente en presencia de productos de seguridad.

* **Mala reputación del sector:** Software que los proveedores de seguridad de confianza detectan con sus productos de seguridad. El sector de la seguridad se dedica a proteger a los clientes y mejorar sus experiencias. Microsoft y otras organizaciones del sector de la seguridad intercambian continuamente conocimientos sobre los archivos que hemos analizado para proporcionar a los usuarios la mejor protección posible.

