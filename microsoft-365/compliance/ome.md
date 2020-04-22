---
title: Cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con el cifrado de mensajes de Office 365, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre usuarios de dentro y fuera de la organización. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios deseados puedan ver el contenido de los mensajes.
ms.openlocfilehash: 4d308a81300c13e61f0ecd2d1117c5be87d2bf04
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626786"
---
# <a name="message-encryption"></a>Cifrado de mensajes

Las personas suelen usar el correo para intercambiar información confidencial, como datos financieros, contratos legales, información confidencial de productos, informes y proyecciones de ventas, información de historial médico o información sobre clientes y empleados. Por ello, los buzones de correo pueden convertirse en repositorios para cantidades grandes de información posiblemente confidencial y la filtración de información puede convertirse en una seria amenaza para las organizaciones.

Con el cifrado de mensajes de Office 365, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre usuarios de dentro y fuera de la organización. El cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios deseados puedan ver el contenido de los mensajes.

## <a name="how-office-365-message-encryption-works"></a>Cómo funciona el cifrado de mensajes de Office 365

El resto de este artículo se aplica a las nuevas capacidades de OME.

> [!NOTE]
> Los delegados que tienen permisos de acceso total a un buzón de correo pueden leer los mensajes cifrados que se envían al buzón.

El cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS), que forma parte de Azure Information Protection. Esto incluye directivas de cifrado, identidades y autorización para ayudar a proteger el correo electrónico. Puede cifrar mensajes mediante el uso de plantillas de Rights Management, la [opción no reenviar](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)y la [opción de solo cifrado](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

A continuación, los usuarios pueden cifrar los mensajes de correo electrónico y una amplia variedad de datos adjuntos con estas opciones. Para obtener una lista completa de los tipos de datos adjuntos admitidos, consulte ["tipos de archivos cubiertos por las directivas de IRM cuando se adjuntan a mensajes" en Introducción a IRM para los mensajes de correo electrónico](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

Como administrador, también puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede crear una regla que requiera el cifrado de todos los mensajes dirigidos a un destinatario específico o que contenga palabras específicas en la línea de asunto, y también especificar que los destinatarios no pueden copiar ni imprimir el contenido del mensaje.

A diferencia de la versión anterior de OME, las nuevas capacidades proporcionan una experiencia de remitente unificado, ya sea que envíe correo dentro de su organización o a destinatarios ajenos a Microsoft 365. Además, los destinatarios que reciben un mensaje de correo electrónico protegido que se envía a una cuenta de Microsoft 365 en Outlook 2016 o en Outlook en la web no tienen que realizar ninguna acción adicional para ver el mensaje. Funciona sin problemas. Los destinatarios que usan otros clientes de correo electrónico y proveedores de servicios de correo electrónico también tienen una mejor experiencia. Para obtener más información, vea información [sobre los mensajes protegidos en Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) y [Cómo abrir un mensaje protegido](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Para obtener una lista detallada de las diferencias entre la versión anterior de OME y las nuevas capacidades de OME, vea [Compare Versions of OME](ome-version-comparison.md).

Cuando alguien envía un mensaje de correo electrónico que coincide con una regla de flujo de correo de cifrado, el mensaje se cifra antes de enviarse. Todos los usuarios finales de Microsoft 365 que usan clientes de Outlook para leer correo reciben experiencias de lectura nativas de primera clase para el correo cifrado y protegido por derechos, incluso si no están en la misma organización que el remitente. Los clientes de Outlook compatibles incluyen el escritorio de Outlook, Outlook Mac, Outlook Mobile en iOS y Android, y Outlook en la web (anteriormente conocido como Outlook Web App).

Los destinatarios de los mensajes cifrados que reciben mensajes cifrados o protegidos por derechos enviados a sus cuentas de Outlook.com, gmail y Yahoo reciben un correo de contenedor que los dirige al portal de OME, donde se pueden autenticar fácilmente con una cuenta de Microsoft, Gmail o credenciales de Yahoo.

Los usuarios finales que lean el correo cifrado o protegido por derechos en clientes que no sean Outlook también usan el portal OME para ver los mensajes cifrados y protegidos por derechos que reciben.

Si el remitente del correo protegido está en GCC High y el destinatario está fuera de GCC High, incluidos los usuarios comerciales, los usuarios Outlook.com y los usuarios de otros proveedores de correo electrónico como gmail, el destinatario recibe un correo de contenedor. El correo de contenedor dirige al destinatario al portal de OME donde el destinatario puede leer y responder al mensaje. De lo contrario, si el remitente y el destinatario están en el entorno alto de GCC, aunque no estén en la misma organización, los destinatarios que usan clientes de Outlook para leer el correo reciben experiencias de lectura nativas de primera clase para correo cifrado y protegido por derechos. Para obtener más información acerca de la experiencia diferente en GCC High, vea [Compare Versions of OME](ome-version-comparison.md).

Para obtener más información acerca de los límites de tamaño de los mensajes y datos adjuntos que puede cifrar mediante OME, consulte [límites de Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx).

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Cómo funciona el cifrado avanzado de mensajes de Office 365 en OME

El cifrado de mensajes avanzado de Office 365 le permite crear varias plantillas de personalización de marca para ajustar el control sobre el correo del destinatario y crear experiencias de personalización de marca personalizadas para admitir una estructura organizativa diversa.

El cifrado avanzado de mensajes en Microsoft 365 ayuda a cumplir las obligaciones de cumplimiento que requieren un control más flexible del acceso del destinatario externo a los correos electrónicos cifrados. Con el cifrado avanzado de mensajes en Office 365, como administrador, puede controlar los mensajes de correo electrónico confidenciales que se comparten fuera de la organización con directivas automáticas que detectan los tipos de información confidencial (por ejemplo, PII, identificadores financieros o de salud) o palabras clave para mejorar la protección al expirar el acceso a través de un portal web seguro a los correos electrónicos cifrados Además, como administrador, puede controlar más los correos electrónicos cifrados a los que se accede externamente a través de un portal web de Microsoft 365, revocando el acceso a un correo electrónico en cualquier momento.

La revocación de mensajes y la expiración solo funcionan con los correos electrónicos que los usuarios envían a los destinatarios externos a la organización. Además, los destinatarios deben acceder al correo electrónico a través del portal web. Para asegurarse de que el destinatario use el portal para recibir correo electrónico, configure una plantilla de personalización de marca personalizada que aplique el contenedor. A continuación, se aplica la plantilla de personalización de marca en una regla de flujo de correo. Para obtener más información acerca del cifrado de mensajes avanzado, consulte [Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-office-365-message-encryption"></a>Definición de reglas para el cifrado de mensajes de Office 365

Una forma de habilitar las nuevas funciones de Office 365 Message Encryption es para los administradores de Exchange Online y Exchange Online Protection para que puedan definir reglas de flujo de correo. Estas reglas determinan en qué condiciones se deben cifrar los mensajes de correo electrónico. Cuando se establece una acción de cifrado para una regla, los mensajes que coinciden con las condiciones de la regla se cifran antes de enviarse.

Las reglas de flujo de correo son flexibles, lo que permite combinar condiciones para que pueda cumplir requisitos de seguridad específicos en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contengan palabras clave especificadas y que estén dirigidos a destinatarios externos. Las nuevas funciones para el cifrado de mensajes de Office 365 también cifran las respuestas de destinatarios de correo electrónico cifrado.

Para obtener más información acerca de cómo crear reglas de flujo de correo para aprovechar las nuevas capacidades de OME, consulte [definir reglas para el cifrado de mensajes de Office 365](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-new-ome-capabilities"></a>Introducción a las nuevas funciones de OME

Si está listo para empezar a usar las nuevas funciones de OME dentro de su organización, vea [set up New Office 365 Message Encryption Capabilities](set-up-new-message-encryption-capabilities.md).

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, ver y responder mensajes de correo electrónico cifrado

Con el cifrado de mensajes de Office 365, los usuarios pueden enviar correo electrónico cifrado desde Outlook y Outlook en la Web. Además, los administradores pueden configurar reglas de flujo de correo en Microsoft 365 para cifrar automáticamente los correos electrónicos en función de la coincidencia de palabras clave u otras condiciones.

Los destinatarios de los mensajes cifrados que están en las organizaciones podrán leer estos mensajes de forma transparente en cualquier versión de Outlook, incluidos Outlook para PC, Outlook para Mac, Outlook en la web, Outlook para iOS y Outlook para Android. Los usuarios que reciben mensajes cifrados en otros clientes de correo electrónico pueden ver los mensajes en el portal OME.

Para obtener instrucciones detalladas sobre cómo enviar y ver mensajes cifrados, eche un vistazo a estos artículos:

|||
|:-----|:-----|
|Lea este artículo...|Si es...|
|[Obtenga información sobre los mensajes protegidos en Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Un usuario final que desea obtener más información sobre cómo funcionan los mensajes cifrados y qué opciones están disponibles para usted.|
|[¿Cómo se abre un mensaje protegido?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Un usuario final que desea leer un mensaje protegido que se le ha enviado. Este artículo incluye información sobre cómo leer mensajes en varias versiones de Outlook y desde distintas cuentas de correo electrónico, incluidas las que se encuentran fuera de Microsoft 365, como gmail y Yahoo! cuenta.|
|[Enviar, ver y responder mensajes cifrados en Outlook](https://support.office.com/article/eaa43495-9bbb-4fca-922a-df90dee51980.aspx)|Un usuario final que desea enviar, ver o responder a un mensaje cifrado desde Outlook. Incluso si no es miembro de una organización, sigue recibiendo notificación de los mensajes cifrados que se le han enviado en Outlook. Use este artículo para obtener instrucciones sobre cómo ver y responder a los mensajes cifrados enviados desde Office 365.|
|[Enviar un mensaje cifrado o firmado digitalmente](https://support.office.com/article/a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Un usuario final que desea enviar, ver o responder a mensajes cifrados con Outlook para Mac. En este artículo también se trata el uso de métodos de cifrado distintos de OME, como S/MIME.|
|[Ver mensajes cifrados en su dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Un usuario final que ha recibido un mensaje cifrado con el cifrado de mensajes de Office 365 en su dispositivo Android, puede usar la aplicación de visor gratuita OME para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo hacerlo.|
|[Ver mensajes cifrados en su iPhone o iPad](https://support.office.com/article/4d631321-0d26-4bcc-a483-d294dd0b1caf)|Un usuario final que ha recibido un mensaje cifrado con el cifrado de mensajes de Office 365 en su iPhone o iPad, puede usar la aplicación gratuita visor de OME para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo hacerlo.|
||
