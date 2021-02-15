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
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de su organización.
ms.openlocfilehash: f601618c3ad44361794720852b391949901122f2
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709626"
---
# <a name="message-encryption"></a>Cifrado de mensajes

Las personas suelen usar el correo para intercambiar información confidencial, como datos financieros, contratos legales, información confidencial de productos, informes y proyecciones de ventas, información de historial médico o información sobre clientes y empleados. Por ello, los buzones de correo pueden convertirse en repositorios para cantidades grandes de información posiblemente confidencial y la filtración de información puede convertirse en una seria amenaza para las organizaciones.

Con el cifrado de mensajes de Office 365, su organización puede enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de su organización. Cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios puedan ver el contenido del mensaje.

## <a name="how-office-365-message-encryption-works"></a>Cómo funciona el cifrado de mensajes de Office 365

El resto de este artículo se aplica a las nuevas funcionalidades de OME.

Cifrado de mensajes de Office 365 es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS), que forma parte de Azure Information Protection. Esto incluye directivas de cifrado, identidad y autorización para ayudar a proteger el correo electrónico. Puede cifrar mensajes mediante plantillas de administración de derechos, la opción No reenviar [y](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)la opción de [solo cifrado.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)

A continuación, los usuarios pueden cifrar mensajes de correo electrónico y una variedad de datos adjuntos mediante estas opciones. Para obtener una lista completa de los tipos de datos adjuntos admitidos, consulte "Tipos de archivo cubiertos por directivas IRM cuando se adjuntan a mensajes" en Introducción a IRM para mensajes [de correo electrónico.](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)

Como administrador, también puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede crear una regla que requiera el cifrado de todos los mensajes dirigidos a un destinatario específico, o que contenga palabras específicas en la línea de asunto, y también especificar que los destinatarios no puedan copiar ni imprimir el contenido del mensaje.

A diferencia de la versión anterior de OME, las nuevas funcionalidades proporcionan una experiencia de remitente unificado tanto si envía correo dentro de su organización como a destinatarios fuera de Microsoft 365. Además, los destinatarios que reciben un mensaje de correo electrónico protegido enviado a una cuenta de Microsoft 365 en Outlook 2016 o Outlook en la Web, no tienen que realizar ninguna acción adicional para ver el mensaje. Funciona sin problemas. Los destinatarios que usan otros clientes de correo electrónico y proveedores de servicios de correo electrónico también tienen una experiencia mejorada. Para obtener información, vea Más información sobre los mensajes protegidos [en Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) y Cómo [se abre un mensaje protegido.](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)

Para obtener una lista detallada de las diferencias entre la versión anterior de OME y las nuevas funcionalidades de OME, vea Comparar versiones [de OME.](ome-version-comparison.md)

Cuando alguien envía un mensaje de correo electrónico que coincide con una regla de flujo de correo de cifrado, el mensaje se cifra antes de que se envíe. Todos los usuarios finales de Microsoft 365 que usan clientes de Outlook para leer correo reciben experiencias de lectura nativas de primera clase para correo cifrado y protegido con derechos, incluso si no están en la misma organización que el remitente. Entre los clientes de Outlook compatibles se incluyen el escritorio de Outlook, Outlook Mac, Outlook Mobile en iOS y Android, y Outlook en la Web (anteriormente conocido como Outlook Web App).

Los destinatarios de mensajes cifrados que reciben correo cifrado o protegido por derechos enviados a sus cuentas de Outlook.com, Gmail y Yahoo reciben un correo contenedor que los dirige al Portal de OME, donde pueden autenticarse fácilmente con una cuenta de Microsoft, Gmail o credenciales de Yahoo.

Los usuarios finales que leen correo cifrado o protegido con derechos en clientes distintos de Outlook también usan el portal de OME para ver los mensajes cifrados y protegidos por derechos que reciben.

Si el remitente del correo protegido está en GCC High y el destinatario está fuera de GCC High, incluidos los usuarios comerciales, los usuarios de Outlook.com y los usuarios de otros proveedores de correo electrónico como Gmail, el destinatario recibe un correo contenedor. El correo contenedor dirige al destinatario al Portal de OME, donde el destinatario puede leer y responder al mensaje. De lo contrario, si el remitente y el destinatario están en el entorno de GCC High, incluso si no están en la misma organización, los destinatarios que usan clientes de Outlook para leer correo reciben experiencias de lectura nativas de primera clase para correo cifrado y protegido por derechos. Para obtener más información acerca de la experiencia diferente en GCC High, vea [Comparar versiones de OME.](ome-version-comparison.md)

Para obtener más información acerca de los límites de tamaño de los mensajes y datos adjuntos que puede cifrar mediante OME, vea [Límites de Exchange Online.](https://technet.microsoft.com/library/exchange-online-limits.aspx)

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Cómo funciona el cifrado avanzado de mensajes de Office 365 sobre OME

El cifrado avanzado de mensajes de Office 365 le permite crear varias plantillas de personalización de marca para que pueda ajustar el control sobre el correo del destinatario y crear experiencias de personalización de marca personalizadas para admitir una estructura organizativa diversa.

El cifrado avanzado de mensajes en Microsoft 365 le ayuda a cumplir las obligaciones de cumplimiento que requieren un control más flexible sobre el acceso de los destinatarios externos a los correos electrónicos cifrados. Con el cifrado avanzado de mensajes en Office 365, como administrador, puede controlar los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que detectan tipos de información confidencial (por ejemplo, PII, IDs financieros o de estado) o palabras clave para mejorar la protección al expirar el acceso a través de un portal web seguro para los correos electrónicos cifrados. Como administrador, puede controlar aún más los correos electrónicos cifrados a los que se accede a través de un portal web de Microsoft 365 al revocar el acceso a un correo electrónico en cualquier momento.

La revocación y expiración de mensajes solo funcionan para los correos electrónicos que los usuarios envían a destinatarios externos a la organización. Además, los destinatarios deben tener acceso al correo electrónico a través del portal web. Para asegurarse de que el destinatario usa el portal para recibir correo electrónico, configure una plantilla de personalización de marca personalizada que aplique el contenedor. A continuación, aplique la plantilla de personal de marca en una regla de flujo de correo. Para obtener más información acerca del cifrado avanzado de mensajes, consulte Cifrado de mensajes avanzado de [Office 365.](ome-advanced-message-encryption.md)

## <a name="defining-rules-for-office-365-message-encryption"></a>Definición de reglas para el cifrado de mensajes de Office 365

Una forma de habilitar las nuevas funcionalidades para el cifrado de mensajes de Office 365 es que los administradores de Exchange Online y Exchange Online Protection definan reglas de flujo de correo. Estas reglas determinan en qué condiciones se deben cifrar los mensajes de correo electrónico. Cuando se establece una acción de cifrado para una regla, los mensajes que coinciden con las condiciones de la regla se cifran antes de que se envíen.

Las reglas de flujo de correo son flexibles, lo que permite combinar condiciones para que pueda cumplir requisitos de seguridad específicos en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contienen palabras clave especificadas y que están dirigidos a destinatarios externos. Las nuevas funcionalidades para el cifrado de mensajes de Office 365 también cifran las respuestas de los destinatarios del correo electrónico cifrado.

Para obtener más información acerca de cómo crear reglas de flujo de correo para aprovechar las nuevas funcionalidades de OME, vea Definir reglas para el cifrado de mensajes de [Office 365.](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-the-new-ome-capabilities"></a>Introducción a las nuevas funcionalidades de OME

Si está listo para empezar a usar las nuevas funcionalidades de OME dentro de su organización, vea Configurar nuevas capacidades de cifrado de mensajes de [Office 365.](set-up-new-message-encryption-capabilities.md)

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, ver y responder mensajes de correo electrónico cifrado

Con el cifrado de mensajes de Office 365, los usuarios pueden enviar correo electrónico cifrado desde Outlook y Outlook en la Web. Además, los administradores pueden configurar reglas de flujo de correo en Microsoft 365 para cifrar automáticamente los mensajes de correo electrónico en función de la coincidencia de palabras clave u otras condiciones.

Los destinatarios de mensajes cifrados que están en organizaciones podrán leer esos mensajes sin problemas en cualquier versión de Outlook, incluidos Outlook para PC, Outlook para Mac, Outlook en la Web, Outlook para iOS y Outlook para Android. Los usuarios que reciben mensajes cifrados en otros clientes de correo electrónico pueden ver los mensajes en el portal de OME.

Para obtener instrucciones detalladas sobre cómo enviar y ver mensajes cifrados, consulte estos artículos.

|Lea este artículo...|Si está...|
|:-----|:-----|
|[Más información sobre los mensajes protegidos en Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Un usuario final que desea obtener más información sobre cómo funcionan los mensajes cifrados y qué opciones están disponibles para usted.|
|[¿Cómo se abre un mensaje protegido?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Un usuario final que desea leer un mensaje protegido que se le envió. En este artículo se incluye información sobre la lectura de mensajes en varias versiones de Outlook y de diferentes cuentas de correo electrónico, incluidas aquellas cuentas fuera de Microsoft 365, como Gmail y Yahoo! cuentas.|
|[Enviar, ver y responder mensajes cifrados en Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Un usuario final que desea enviar, ver o responder a un mensaje cifrado desde Outlook. Incluso si no es miembro de una organización, seguirá recibiendo una notificación de los mensajes cifrados que se le envían en Outlook. Use este artículo para obtener instrucciones sobre cómo ver y responder a los mensajes cifrados enviados desde Office 365.|
|[Enviar un mensaje cifrado o firmado digitalmente](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Un usuario final que desea enviar, ver o responder mensajes cifrados con Outlook para Mac. En este artículo también se describe el uso de métodos de cifrado distintos de OME, como S/MIME.|
|[Ver mensajes cifrados en el dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Un usuario final que ha recibido un mensaje cifrado con cifrado de mensajes de Office 365 en su dispositivo Android, puede usar la aplicación gratuita Visor de OME para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo hacerlo.|
|[Ver mensajes cifrados en su iPhone o iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Un usuario final que ha recibido un mensaje cifrado con cifrado de mensajes de Office 365 en su iPhone o iPad, puede usar la aplicación gratuita Visor de OME para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo hacerlo.|
||
