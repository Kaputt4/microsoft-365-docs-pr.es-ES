---
title: Solicitudes de interesados de Intune para el RGPD
description: ''
keywords: Microsoft 365, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
author: dougeby
localization_priority: Priority
audience: itpro
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: dougeby
manager: angrobe
ms.collection: GDPR
ms.openlocfilehash: eeb50954f849b0c110a88cc7d768844847d99255
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871792"
---
# <a name="intune-data-subject-requests-for-the-gdpr"></a>Solicitudes de interesados de Intune para el RGPD
El Reglamento de protección de datos de la UE (RGPD) ofrece derechos a las personas (que se denominan *"interesados"* en el reglamento) para administrar los datos personales recopilados por una empresa u otro tipo de agencia u organización (es decir, el *poseedor de los datos* o *"poseedor"*). Los datos personales se definen de forma muy amplia según el RGPD como cualquier dato relacionado con una persona física, ya sea identificada o identificable. El RGPD ofrece a los interesados derechos específicos en sus datos personales, como la obtención de copias de sus datos, la solicitud de correcciones, impedir su procesamiento o eliminación, o el envío en formato electrónico para transferirlos a otro poseedor de los datos. Las solicitudes formales realizadas por un interesado a un poseedor de los datos para realizar una acción en sus datos personales se denominan *solicitudes de interesado*.

En esta guía se explica cómo usar los productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes poseedores de datos a encontrar datos personales y actuar a partir de ellos para responder a solicitudes de interesado. En concreto, esto abarca cómo encontrar datos personales hospedados en la nube de Microsoft, cómo tener acceso a ellos y cómo actuar en consecuencia. Este es un breve resumen de los procedimientos descritos en esta guía:

1.  ***Descubrir***: use herramientas de búsqueda y descubrimiento para encontrar con facilidad datos de clientes que puedan estar sujetos a una solicitud de interesado. Tras recopilar los documentos potenciales, puede realizar una o varias delas acciones de solicitud descritas en los pasos siguientes para responder a la petición. De forma alternativa, puede determinar que la solicitud no cumple las directrices de respuesta a solicitudes de interesado.

2.  ***Acceder***: recupere datos personales alojados en la nube de Microsoft y, si se le pide, realice una copia que puede estar a disposición del interesado.

3.  ***Corregir***: realice los cambios o implemente otras acciones solicitadas en los datos personales, si procede.

4.  ***Restringir***: restrinja el procesamiento de datos personales, quitando las licencias de varios servicios de Azure o desactivando los servicios deseados siempre que sea posible. También puede quitar los datos de la nube de Microsoft y conservarlos localmente o en otra ubicación.

5.  ***Eliminar***: eliminar de forma permanente los datos personales que residen en la nube de Microsoft.

6.  ***Exportar***: enviar una copia electrónica (en un formato legible) de datos personales al interesado.

Cada sección de esta guía describe los procedimientos técnicos que puede realizar una organización poseedora de datos para responder a una solicitud de interesado de datos personales en la nube de Microsoft.

<span id="_Toc511384801" class="anchor"><span id="_Toc511163872" class="anchor"><span id="_Toc511136229" class="anchor"><span id="_Toc511125162" class="anchor"><span id="_Toc511120749" class="anchor"><span id="_Toc511122656" class="anchor"><span id="_Toc508792503" class="anchor"></span></span></span></span></span></span></span>
#### <a name="terminology"></a>Terminología

A continuación se ofrecen definiciones de términos relacionados con esta guía.

-   *Poseedor*: la persona física o legal, autoridad pública, agencia u organismo que solo o junto a otras personas, determina los fines y medios del procesamiento de datos personales; donde los fines y los medios de dicho procesamiento están determinados por la ley de la unión o de un estado miembro, el poseedor o los criterios específicos para su nominación pueden estar proporcionados por la ley de un estado miembro o de la unión.

-   *Datos personales* e *interesado*: cualquier información sobre una persona física identificada o identificable (“interesado”); una persona identificable natural es una que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona natural;

-   *Procesador*: persona física o legal, autoridad pública, agencia u otro organismo que trata datos personales en nombre del poseedor.

-   *Los datos de clientes*: todos los datos, incluyendo archivos de texto, sonido, vídeos o imagen y software proporcionados a Microsoft por, o en nombre de, un cliente a través del uso del servicio empresarial. Los datos de clientes incluyen tanto (1) información de identificación personal de los usuarios finales (por ejemplo, nombres de usuario e información de contacto en Azure Active Directory) y contenido del cliente cargado o creado por clientes en servicios específicos (por ejemplo, el contenido del cliente en una cuenta de Azure Storage, contenido del cliente de Azure SQL Database, o la imagen de la máquina virtual de un cliente en Azure Virtual Machines).

-   *Registros generados por el sistema*: registros y datos relacionados generados por Microsoft que ayudan a Microsoft a proporcionar servicios empresariales a los usuarios. Los registros generados por el sistema contienen principalmente datos pseudonimizados, como identificadores únicos (por lo general, un número generado por el sistema que se usa para ofrecer los servicios a los usuarios, pero no puede identificar a un individuo). Los registros generados por el sistema también pueden contener información que identifique a los usuarios finales, como un nombre de usuario.  

<span id="_Toc511384802" class="anchor"><span id="_Toc511163873" class="anchor"><span id="_Toc511136230" class="anchor"><span id="_Toc511125163" class="anchor"><span id="_Toc511120750" class="anchor"><span id="_Toc511122657" class="anchor"><span id="_Toc508792504" class="anchor"></span></span></span></span></span></span></span>

#### <a name="how-to-use-this-guide"></a>Cómo utilizar esta guía

Esta guía consta de dos partes:

**Parte 1: Responder a solicitudes de interesados de clientes**: la primera parte de esta guía describe cómo acceder, corregir, restringir, eliminar y exportar datos desde las aplicaciones en las que se han creado. Esta sección detalla cómo ejecutar la solicitud de interesado con el contenido de cliente y también con la información identificable de los usuarios finales.

**Parte 2: Responder a solicitudes de interesados para registros generados por el sistema**: al usar los servicios de empresa de Microsoft, Microsoft genera información conocida como registros generados por el sistema para proporcionar el servicio. La parte 2 de esta guía explica cómo acceder, eliminar y exportar esta información para Azure.

<span id="_Toc511384803" class="anchor"><span id="_Toc511163874" class="anchor"></span></span>







### <a name="understanding-dsrs-for-azure-active-directory-and-microsoft-intune"></a>Comprender las solicitudes de interesados para Azure Active Directory y Microsoft Intune

Al plantear servicios proporcionados a clientes empresariales, siempre debe entenderse la ejecución de solicitudes de interesados en el contexto de un inquilino específico de Azure Active Directory (AAD). En concreto, este siempre se ejecuta en un inquilino AAD determinado. Si un usuario forma parte de varios inquilinos, es importante destacar que una solicitud de interesado *solo* se ejecuta en el contexto del inquilino específico que ha recibido la solicitud. Esto es importante para comprender que la ejecución de una solicitud de interesado por parte de un cliente empresarial **no** afecta a los datos de otro cliente empresarial adyacente.

Lo mismo es válido en Microsoft Intune en el contexto de los servicios que presta un cliente empresarial: la ejecución de una solicitud de interesado de una cuenta de Intune *asociada a un cliente AAD* **solo** estará relacionada con los datos del cliente. Además, es importante comprender lo siguiente al gestionar cuentas de Intune en un cliente:

-   Si un usuario de Intune crea una suscripción de Azure, la suscripción se tratará como si fuera un inquilino AAD. Por lo tanto, las solicitudes de interesado se rastrean en el interior del cliente tal y como se ha descrito anteriormente.

-   Si se elimina una suscripción de Azure creada con una cuenta de Intune, esta última **no se verá afectada**.Como se indicó anteriormente, las solicitudes de interesado que se ejecutan en la suscripción de Azure se limitan al ámbito del mismo inquilino.

Las solicitudes de interesados en una cuenta de Intune, **fuera de un determinado inquilino**, se ejecutan por medio del panel de privacidad del consumidor. Consulte la Guía de solicitud de datos de Windows para más información.

<span id="_Toc508792505" class="anchor"><span id="_Toc511384804" class="anchor"><span id="_Toc511163875" class="anchor"><span id="_Toc511136231" class="anchor"><span id="_Toc511125164" class="anchor"><span id="_Toc511120751" class="anchor"><span id="_Toc511122658" class="anchor"></span></span></span></span></span></span></span>

## <a name="part-1-dsr-guide-for-customer-data"></a>Parte 1: Guía de solicitud de interesado para datos de cliente

<span id="_Toc511384805" class="anchor"><span id="_Toc511163876" class="anchor"><span id="_Toc511136232" class="anchor"><span id="_Toc511125165" class="anchor"><span id="_Toc511120752" class="anchor"><span id="_Toc511122659" class="anchor"></span></span></span></span></span></span>

### <a name="executing-dsrs-against-customer-data"></a>Ejecutar solicitudes de interesado en datos de cliente

Microsoft proporciona la capacidad de acceder, eliminar y exportar determinados datos de cliente a través del Azure Portal y también directamente a través de interfaces de programación de aplicaciones (API) o interfaces de usuario (UI) ya existentes para servicios específicos (también denominados *experiencias de producto*). Los detalles al respecto de dichas experiencias de producto se describen en la documentación de referencia de sus respectivos servicios.

>[!Important]  
>Los servicios compatibles con solicitudes de interesado en el producto requieren el uso directo de una interfaz de programación de aplicaciones (API) o de una interfaz de usuario (UI) del servicio, que describa las operaciones CRUD (crear, leer, actualizar y eliminar) aplicables. Por lo tanto, la ejecución de la solicitud de interesado en un servicio específico debe realizarse además con la ejecución de una solicitud de interesado en Azure Portal para completar toda la solicitud de un interesado. Consulte la documentación de referencia de los servicios específicos para obtener más detalles.

<span id="_Discover" class="anchor"><span id="_Toc508792508" class="anchor"><span id="_Toc511122661" class="anchor"><span id="_Toc511120754" class="anchor"><span id="_Toc511125167" class="anchor"><span id="_Toc511136234" class="anchor"><span id="_Toc511163877" class="anchor"><span id="_Toc511384806" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-1-discover"></a>Paso 1: Descubrimiento

El primer paso para responder a una solicitud de interesado consiste en encontrar los datos personales que se solicitan. Este primer paso, encontrar y revisar los datos personales, le ayudará a determinar si una solicitud de interesado cumple los requisitos de su organización para respetarla o rechazarla. Por ejemplo, después de encontrar y revisar los datos personales, puede determinar que la solicitud no cumple los requisitos de su organización porque al llevarse a cabo puede afectar negativamente los derechos y libertades de terceros.

Tras encontrar los datos, puede realizar la acción específica para satisfacer la solicitud interesado. Vea los siguientes temas para obtener más detalles:
- [Recopilación de datos](https://docs.microsoft.com/intune/privacy-data-collect)
- [Procesamiento y almacenamiento de datos](https://docs.microsoft.com/intune/privacy-data-store-process)
- [Ver datos personales](https://docs.microsoft.com/intune/privacy-data-view-correct#view-personal-data)

### <a name="step-2-access"></a>Paso 2: Acceso
Cuando haya encontrado los datos de clientes que contengan datos personales que puedan responder a una solicitud de interesado, depende de usted y de su organización decidir qué datos proporcionar al interesado. Puede proporcionarle una copia del documento, una versión redactada o una captura de pantalla con las porciones que considere adecuado compartir. Para cada una de estas respuestas a una petición de acceso, deberá recuperar una copia del documento u otro objeto que contenga los datos de respuesta.

Al proporcionar una copia al interesado, deberá quitar o censurar información personal sobre otros interesados, además de la información confidencial.

<span id="_Using_Content_Search_1" class="anchor"></span>A continuación se explica cómo obtener una copia de los datos en respuesta a una solicitud de acceso a los datos del interesado.

<span id="_Rectify" class="anchor"><span id="_Ref511119463" class="anchor"><span id="_Toc511122665" class="anchor"><span id="_Toc511120758" class="anchor"><span id="_Toc511125171" class="anchor"><span id="_Toc511136238" class="anchor"><span id="_Toc511163881" class="anchor"><span id="_Toc511384810" class="anchor"></span></span></span></span></span></span></span></span>

#### <a name="azure-active-directory"></a>Azure Active Directory

<span id="_Forms_1" class="anchor"></span>Microsoft ofrece un portal y experiencias de producto que proporcionan al administrador inquilino del cliente empresarial la capacidad de gestionar peticiones de acceso de interesado. Las peticiones de acceso de interesado permiten acceder a los datos personales del usuario, incluyendo (a) información de identificación sobre un usuario final y (b) registros generados por el sistema.

<span id="_Toc511384811" class="anchor"><span id="_Toc511163882" class="anchor"><span id="_Toc511136239" class="anchor"><span id="_Toc511125172" class="anchor"><span id="_Toc511120759" class="anchor"><span id="_Toc511122666" class="anchor"></span></span></span></span></span></span>
#### <a name="service-specific-interfaces"></a>Interfaces específicas del servicio

Microsoft Intune permite [encontrar datos de clientes](#step-1-discover) directamente a través de interfaces de usuario (IU) o de interfaces de programación de aplicaciones (API) ya existentes.

<span id="_Sway" class="anchor"><span id="_Toc508792516" class="anchor"><span id="_Toc511122667" class="anchor"><span id="_Toc511120760" class="anchor"><span id="_Toc511125173" class="anchor"><span id="_Toc511136240" class="anchor"><span id="_Toc511163883" class="anchor"><span id="_Toc511384812" class="anchor"></span></span></span></span></span></span></span></span>
### <a name="step-3-rectify"></a>Paso 3: Corregir

Si un interesado le ha solicitado rectificar los datos personales que se encuentran en los datos de su organización, su organización y usted deberán decidir si es adecuado cursar dicha solicitud. Rectificar los datos puede requerir llevar a cabo acciones como editar, censurar o eliminar datos personales de un documento u otro tipo de elemento. 

<span id="_Toc511384813" class="anchor"><span id="_Toc511163884" class="anchor"><span id="_Toc511136241" class="anchor"><span id="_Toc511125174" class="anchor"><span id="_Toc511120761" class="anchor"><span id="_Toc511122668" class="anchor"></span></span></span></span></span></span>


 En tanto que procesador datos, Microsoft no ofrece la posibilidad de corregir los registros generados por el sistema, ya que reflejan actividades reales y constituyen un registro histórico de los eventos que han tenido lugar en los servicios Microsoft. En cuanto a Intune, los administradores no pueden actualizar la información específica de un dispositivo o una aplicación. Si un usuario final quiere corregir algún dato personal (por ejemplo, el nombre del dispositivo), deberá hacerlo directamente en el dispositivo. Estos cambios se sincronizarán la próxima vez que el usuario se conecte a Intune.

### <a name="step-4-restrict"></a>Paso 4: Restringir

<span id="_Delete" class="anchor"></span>Los interesados pueden solicitar restringir el procesamiento de los datos personales. Proporcionamos tanto Azure Portal como interfaces de programación de aplicaciones (API) o interfaces de usuario (IU) ya existentes. Estas experiencias proporcionan al administrador del cliente empresarial la capacidad de administrar solicitudes de interesado a través de una combinación de exportación y eliminación de datos. Para obtener detalles, vea [Procesamiento de datos personales](https://docs.microsoft.com/intune/privacy-data-store-process#processing-personal-data).

<span id="_Toc508792528" class="anchor"><span id="_Toc511122671" class="anchor"><span id="_Toc511120764" class="anchor"><span id="_Toc511125177" class="anchor"><span id="_Toc511136244" class="anchor"><span id="_Toc511163887" class="anchor"><span id="_Toc511384816" class="anchor"></span></span></span></span></span></span></span>
### <a name="step-5-delete"></a>Paso 5: Eliminar

El “derecho a la eliminación” de datos personales de los datos de cliente de una organización es una protección clave en el RGPD. Cuando se quitan datos personales, esto conlleva quitar todos los datos personales y los registros generados por el sistema, salvo la información de registros de auditoría. Para obtener detalles, vea [Eliminar datos personales de usuario final](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#delete-end-user-personal-data).


<span id="_Toc511384822" class="anchor"><span id="_Toc511163893" class="anchor"><span id="_Toc511136250" class="anchor"><span id="_Toc511125183" class="anchor"><span id="_Toc511120770" class="anchor"><span id="_Toc511122677" class="anchor"></span></span></span></span></span></span>
## <a name="part-2-system-generated-logs"></a>Parte 2: Registros generados por el sistema
Los registros de auditoría proporcionan a los administradores de inquilinos un registro de actividades que generan un cambio en Microsoft Intune. Hay registros de auditoría disponibles relativos a muchas actividades de administración y a las acciones habituales de creación, actualización (edición), eliminación y asignación. También se pueden revisar las tareas remotas que generan eventos de auditoría. Estos registros de auditoría pueden contener datos personales de los usuarios cuyos dispositivos están inscritos en Intune. Los administradores no pueden eliminar los registros de auditoría. Para obtener detalles, vea [Auditar datos personales](https://docs.microsoft.com/intune/privacy-data-audit-export-delete#audit-personal-data).


## <a name="notify-about-exporting-or-deleting-issues"></a>Notificar sobre los problemas de exportación o eliminación
Si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción > Otras solicitudes de seguridad y cumplimiento > Solicitudes de RGPD y la hoja de privacidad**.

#### <a name="learn-more"></a>Más información
[Centro de confianza de Microsoft](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)