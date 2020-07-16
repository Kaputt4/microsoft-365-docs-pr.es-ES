---
title: Servicio de tratamiento de datos de solicitudes de interesados de Windows para el RGPD y la CCPA
description: Aprenda a utilizar los productos, servicios y herramientas de administración de Microsoft para encontrar datos personales y realizar acciones sobre ellos para responder a las DSR.
keywords: Microsoft 365, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
localization_priority: Priority
ROBOTS: NOINDEX, NOFOLLOW
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: daniha
author: DaniHalfin
manager: dansimp
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
ms.openlocfilehash: 525b8b0783886a7449be72c89a2aa624afda9929
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "45023616"
---
# <a name="data-processor-service-for-windows-data-subject-requests-for-the-gdpr-and-ccpa"></a>Servicio de tratamiento de datos de solicitudes de interesados de Windows para el RGPD y la CCPA 

>[!NOTE]
>Este tema está dirigido a los participantes del programa de vista previa del servicio de tratamiento de datos para Windows y requiere aceptar condiciones específicas de uso. Para obtener más información sobre el programa y para aceptar los términos de uso, consulte [https://aka.ms/dpswpublicpreview](https://aka.ms/dpswpublicpreview).

## <a name="introduction-to-data-subject-requests-dsrs"></a>Introducción a las solicitudes de los interesados (DSR) 
El Reglamento General de Protección de Datos (RGPD) otorga derechos a las personas (denominadas _interesados_ en el reglamento) para administrar los datos personales recopilados por una empresa u otro tipo de agencia u organización (denominado _responsable de los datos_ o simplemente _responsable_). Los datos personales se definen ampliamente en el RGPD como cualquier dato que guarde relación con una persona física identificada o identificable. El RGPD ofrece a los interesados derechos específicos sobre sus datos personales, como la obtención de copias de ellos, la solicitud de modificaciones, la restricción de tratamiento, la eliminación o la recepción en un formato electrónico que permita su transferencia a otro responsable. Una solicitud formal de un interesado a un responsable para que realice una acción sobre sus datos personales se denomina _Solicitud del interesado_ o DSR. 

De forma similar, la Ley de Privacidad de Consumidores de California (CCPA) establece los derechos y obligaciones de privacidad a los consumidores de California, incluidos los derechos de los interesados del RGDP, como el derecho a eliminar, obtener acceso y recibir (portabilidad) sus datos personales. La CCPA también prevé casos de divulgación de información, protecciones contra la discriminación en el ejercicio de derechos y requisitos de "cancelación/suscripción" para ciertas transferencias de datos clasificadas como "ventas". Las ventas se definen de forma amplia para incluir el uso compartido de datos con ánimo de lucro. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq).

Esta guía explica cómo usar productos, servicios y herramientas administrativas de Microsoft para ayudar a nuestros clientes responsables de los datos a encontrar y actuar sobre datos personales para responder solicitudes de interesado. En concreto, esto incluye cómo encontrar, acceder y actuar sobre datos personales alojados en la nube de Microsoft. Este es un breve resumen de los procedimientos descritos en esta guía: 

1. **Acceder**: recupere datos personales alojados en la nube de Microsoft y, si se le pide, realice una copia que puede estar a disposición del interesado. 
2. **Eliminar**: eliminar de forma permanente los datos personales que residen en la nube de Microsoft. 
3. **Exportar**: enviar una copia electrónica (en un formato legible) de datos personales al interesado. La información personal de acuerdo con la CCPA es cualquier información relacionada con una persona identificada o identificable.

La información personal bajo la CCPA es cualquier información relacionada con una persona identificada o identificable. No hay distinción entre los roles privados, públicos o laborales de una persona. La definición de la CCPA de la "información personal" es a grandes rasgos similar a la que el RGPD hace de los "datos personales". Sin embargo, la CCPA también incluye datos domésticos y familiares. Para obtener más información sobre la CCPA, consulte la [Ley de Privacidad de los Consumidores California](https://docs.microsoft.com/microsoft-365/compliance/offering-ccpa) y las [Preguntas más frecuentes sobre la privacidad del consumidor de California](https://docs.microsoft.com/microsoft-365/compliance/ccpa-faq).

Cada sección de esta guía describe los procedimientos técnicos que puede realizar una organización responsable de los datos para responder a una solicitud del interesado de datos personales en la nube de Microsoft. 

## <a name="terminology"></a>Terminología 
A continuación se ofrecen definiciones de términos relacionados con esta guía. 

* _Responsable_: la persona física o legal, autoridad pública, agencia u organismo que solo o junto a otras personas, determina los fines y medios del tratamiento de datos personales; donde los fines y los medios de dicho tratamiento están determinados por la ley de la unión o de un estado miembro, el poseedor o los criterios específicos para su nominación pueden estar proporcionados por la ley de un estado miembro o de la unión. 

* _Datos personales e interesado_: cualquier información sobre una persona física identificada o identificable (“interesado”); una persona física identificable es aquella que puede identificarse, directa o indirectamente, especialmente con referencia a un identificador, con un nombre, un número de identificación, datos de ubicación, un identificador en línea o uno o más elementos específicos físicos, fisiológicos, genéticos, mentales, económicos, culturales o de identidad social de esa persona física; 

* _Encargado_: persona física o legal, autoridad pública, agencia u otro organismo que trata datos personales en nombre del responsable. 

* _Datos de cliente_: todos los datos, incluidos el software y todos los archivos de texto, sonido, vídeo o imagen, proporcionados a Microsoft por un cliente o en su representación mediante el uso del servicio empresarial. 

* _Datos de diagnóstico de Windows_: datos técnicos vitales de los dispositivos Windows sobre el dispositivo y sobre el funcionamiento de Windows y el software relacionado. Se usan para mantener Windows actualizado, seguro, fiable y con un buen rendimiento, y mejoran Windows mediante el análisis agregado del uso de Windows. Algunos ejemplos de datos de diagnóstico de Windows son el tipo de hardware que se usa, las aplicaciones que hay instaladas y el uso que se les da, y la información de confiabilidad sobre los controladores de dispositivos. Algunos componentes y aplicaciones de Windows se conectan directamente a servicios Microsoft, pero los datos que intercambian no son datos de diagnóstico de Windows. Por ejemplo, intercambiar la ubicación de un usuario para obtener la información local del tiempo o las noticias locales no es un ejemplo de datos de diagnóstico de Windows. 

## <a name="how-to-use-this-guide"></a>Cómo utilizar esta guía 

Cuando se usa el servicio de tratamiento de datos para dispositivos inscritos en Windows, Windows genera información, conocida como datos de diagnóstico de Windows, para proporcionar el servicio.

## <a name="windows-diagnostic-data"></a>Datos de diagnóstico de Windows 

Microsoft ofrece la posibilidad de obtener acceso a los datos de diagnóstico de Windows relacionados con el uso por parte de un usuario del servicio de tratamiento de datos para Windows, así como de eliminar y exportar esos datos.

>[!IMPORTANT]
>No se admite la capacidad de rectificar los datos de diagnóstico de Windows. Los datos de diagnóstico de Windows constituyen acciones realizadas en Windows. Modificar este tipo de datos podría afectar a los registros históricos de acciones, lo que aumentaría los riesgos de seguridad y perjudicaría la fiabilidad. Todos los datos que se tratan en este documento se consideran datos de diagnóstico de Windows. 

## <a name="executing-dsrs-against-windows-diagnostic-data"></a>Ejecución de las DSR con respecto a los datos de diagnóstico de Windows 

Microsoft ofrece la posibilidad de acceder a determinados datos de diagnóstico de Windows, así como de eliminarlos y exportarlos, a través del Portal Azure y también directamente a través de interfaces de programación de aplicaciones (API) ya existentes.

### <a name="step-1-access"></a>Paso 1: Acceso 

El administrador de inquilinos es la única persona de la organización que puede obtener acceso a los datos de diagnóstico de Windows relacionados con el uso por parte de un usuario en particular de un servicio de tratamiento de datos para un dispositivo inscrito en Windows. Los datos recuperados para una solicitud de acceso se proporcionarán, mediante exportación, en un formato legible por una máquina y se facilitarán en archivos que permitirán al usuario saber a qué dispositivos y servicios se asocian los datos. Como se ha señalado anteriormente, los datos recuperados no incluirán datos que puedan comprometer la seguridad o la estabilidad del dispositivo Windows. 

Microsoft ofrece una experiencia de portal que proporciona al administrador de inquilinos del cliente empresarial la capacidad de administrar las solicitudes de acceso de DSR. [DSR de Azure, parte 2, paso 3: Exportar](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export) describe cómo ejecutar una solicitud de acceso de DSR, mediante exportación, a través del portal de Azure.

### <a name="step-2-delete"></a>Paso 2: Eliminar 

Microsoft proporciona una manera de ejecutar solicitudes de eliminación de DSR basadas en el usuario en función de un objeto de Azure Active Directory de un usuario determinado.

Para las solicitudes de eliminación basadas en el usuario, Microsoft ofrece una experiencia de portal que proporciona al administrador de inquilinos del cliente empresarial la capacidad de administrar las solicitudes de acceso de DSR. [DSR de Azure, parte 1, paso 5: Eliminar](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-5-delete) describe cómo ejecutar una solicitud de acceso de DSR a través del portal de Azure. 

Microsoft proporciona la capacidad de eliminar usuarios, lo que a su vez eliminaría datos de cliente, directamente a través de interfaces de programación de aplicaciones (API) ya existentes. Los detalles se describen en la [documentación de referencia de la API](https://docs.microsoft.com/graph/api/directory-deleteditems-delete?view=graph-rest-beta). 

>[!IMPORTANT]  
>La eliminación de datos recopilados no detiene la recopilación posterior. Para desactivar la recopilación de datos, siga el procedimiento descrito en la [documentación de referencia del servicio correspondiente](https://docs.microsoft.com/windows/privacy/configure-windows-diagnostic-data-in-your-organization#enterprise-management).
 
 Asimismo, las solicitudes de eliminación basadas en el usuario requieren la eliminación de la cuenta del usuario. 

### <a name="step-3-export"></a>Paso 3: Exportar 

El administrador de inquilinos es la única persona de la organización que puede obtener acceso a los datos de diagnóstico de Windows relacionados con el uso por parte de un usuario en particular de un servicio de tratamiento de datos para un dispositivo inscrito en Windows. Los datos recuperados para una solicitud de exportación se proporcionarán en un formato legible por una máquina y se facilitarán en archivos que permitirán al usuario saber a qué dispositivos y servicios se asocian los datos. Como se ha señalado anteriormente, los datos recuperados no incluirán datos que puedan comprometer la seguridad o la estabilidad del dispositivo Windows. [DSR de Azure, parte 2, paso 3: Exportar](https://docs.microsoft.com/microsoft-365/compliance/gdpr-dsr-azure#step-3-export) describe cómo ejecutar una solicitud de exportación de DSR a través del portal de Azure. 

Microsoft proporciona la capacidad de exportar datos de cliente directamente a través de interfaces de programación de aplicaciones (API) ya existentes. Los detalles se describen en la [documentación de referencia de la API](https://docs.microsoft.com/graph/api/user-exportpersonaldata?view=graph-rest-1.0).

## <a name="notify-about-exporting-or-deleting-issues"></a>Notificar sobre los problemas de exportación o eliminación 

Si tiene problemas al exportar o eliminar datos desde Azure Portal, vaya a la hoja **Ayuda + soporte** de Azure Portal y envíe un nuevo vale en **Administración de suscripción > Otras solicitudes de seguridad y cumplimiento > Solicitudes de RGPD y la hoja de privacidad**. 
