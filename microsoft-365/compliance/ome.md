---
title: Cifrado de mensajes de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- tier1
- purview-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo enviar y recibir mensajes de correo electrónico cifrados entre personas dentro y fuera de su organización.
ms.openlocfilehash: 7d08c865735c3ae8f9e6396940b03af4625aad0e
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68644843"
---
# <a name="message-encryption"></a>Cifrado de mensajes

People often use email to exchange sensitive information, such as financial data, legal contracts, confidential product information, sales reports and projections, patient health information, or customer and employee information. As a result, mailboxes can become repositories for large amounts of potentially sensitive information and information leakage can become a serious threat to your organization.

Con el cifrado de mensajes de Office 365, la organización puede enviar y recibir mensajes cifrados entre personas de dentro y fuera de la organización. El Cifrado de mensajes de Office 365 funciona con Outlook.com, Yahoo!, Gmail y otros servicios de correo electrónico. El cifrado de mensajes de correo electrónico ayuda a garantizar que solo los destinatarios previstos puedan ver el contenido del mensaje.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="how-message-encryption-works"></a>Funcionamiento del cifrado de mensajes

El resto de este artículo se aplica a la Cifrado de mensajes de Microsoft Purview.

Cifrado de mensajes de Microsoft Purview es un servicio en línea que se basa en Microsoft Azure Rights Management (Azure RMS) que forma parte de Azure Information Protection. Este servicio incluye directivas de cifrado, identidad y autorización para ayudar a proteger el correo electrónico. Puede cifrar los mensajes mediante plantillas de administración de derechos, la [opción No reenviar](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails) y la [opción de solo cifrado](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).

A continuación, los usuarios pueden cifrar mensajes de correo electrónico y varios datos adjuntos mediante estas opciones. Para obtener una lista completa de los tipos de datos adjuntos admitidos, consulte ["Tipos de archivo cubiertos por directivas de IRM cuando se adjuntan a mensajes" en Introducción a IRM para mensajes de correo electrónico](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM).

Como administrador, también puede definir reglas de flujo de correo para aplicar esta protección. Por ejemplo, puede crear una regla que requiera el cifrado de todos los mensajes dirigidos a un destinatario específico, o que contenga palabras específicas en la línea de asunto, y también especificar que los destinatarios no puedan copiar ni imprimir el contenido del mensaje.

A diferencia de la versión anterior de OME, las nuevas funcionalidades proporcionan una experiencia de remitente unificada, ya sea que envíe correo dentro de su organización o a destinatarios fuera de Microsoft 365. Además, los destinatarios que reciben un mensaje de correo electrónico protegido enviado a una cuenta de Microsoft 365 en Outlook 2016 o Outlook en la Web, no tienen que realizar ninguna otra acción para ver el mensaje. Funciona sin problemas. Los destinatarios que usan otros clientes de correo electrónico y proveedores de servicios de correo electrónico también tienen una experiencia mejorada. Para obtener información, consulte [Información sobre los mensajes protegidos en Office 365](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67) y [मैले कसरी abrir un mensaje protegido](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098).

Para obtener una lista detallada de las diferencias entre la versión anterior de OME y Cifrado de mensajes de Microsoft Purview, consulte [Comparación de versiones del cifrado de mensajes](ome-version-comparison.md).

Cuando alguien envía un mensaje de correo electrónico que coincide con una regla de flujo de correo de cifrado, el mensaje se cifra antes de enviarlo. Todos los usuarios finales de Microsoft 365 que usan clientes de Outlook para leer correo reciben experiencias de lectura nativas de primera clase para el correo cifrado y protegido con derechos, incluso si no están en la misma organización que el remitente. Los clientes de Outlook compatibles incluyen escritorio de Outlook, Outlook Mac, Outlook mobile en iOS y Android, y Outlook en la Web (anteriormente conocido como Outlook Web App).

Los destinatarios de mensajes cifrados que reciben correo cifrado o protegido por derechos enviados a sus cuentas de Gmail y Yahoo reciben un correo contenedor que los dirige al Portal de OME, donde pueden autenticarse fácilmente con una cuenta de Microsoft, Gmail o credenciales de Yahoo.

Los usuarios finales que leen correo cifrado o protegido por derechos en clientes distintos de Outlook también usan el portal de mensajes cifrados para ver los mensajes cifrados y protegidos por derechos que reciben.

Si el remitente del correo protegido está en GCC High y el destinatario está fuera de GCC High, incluidos los usuarios comerciales, Outlook.com usuarios y usuarios de otros proveedores de correo electrónico como Gmail, el destinatario recibe un correo contenedor. El correo contenedor dirige al destinatario al portal de mensajes cifrados donde el destinatario puede leer y responder al mensaje. De lo contrario, si el remitente y el destinatario están en el entorno de GCC High, incluso si no están en la misma organización, los destinatarios que usan clientes de Outlook para leer el correo reciben experiencias de lectura nativas de primera clase para el correo cifrado y protegido por derechos. Para obtener más información sobre la experiencia diferente en GCC High, consulte [Comparación de versiones de OME](ome-version-comparison.md).

Para obtener más información sobre los límites de tamaño de los mensajes y los datos adjuntos que puede cifrar mediante OME, consulte [límites de Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits).

## <a name="how-microsoft-purview-advanced-message-encryption-works-on-top-of-microsoft-purview-message-encryption"></a>Cómo funciona el cifrado avanzado de mensajes de Microsoft Purview sobre Cifrado de mensajes de Microsoft Purview

Cifrado avanzado de mensajes de Microsoft Purview permite crear varias plantillas de personalización de marca para que pueda ajustar el control sobre el correo de los destinatarios y crear experiencias de personalización de marca personalizadas para admitir una estructura organizativa diversa.

Advanced Message Encryption en Microsoft 365 le ayuda a cumplir las obligaciones de cumplimiento que requieren un control más flexible sobre el acceso del destinatario externo a los correos electrónicos cifrados. Con Advanced Message Encryption, como administrador, puede controlar los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que detectan tipos de información confidencial (por ejemplo, PII, identificadores financieros o de estado) o palabras clave para mejorar la protección mediante la expiración del acceso a través de un portal web seguro a los correos electrónicos cifrados. Como administrador, puede controlar aún más los correos electrónicos cifrados a los que se accede a través de un portal web revocando el acceso a un correo electrónico en cualquier momento.

La revocación y expiración de mensajes solo funcionan para los correos electrónicos que los usuarios envían a destinatarios fuera de la organización. Además, los destinatarios deben acceder al correo electrónico a través del portal web. Para asegurarse de que el destinatario usa el portal para recibir correo electrónico, configure una plantilla de personalización de marca personalizada que aplique el contenedor. A continuación, aplique la plantilla de personalización de marca en una regla de flujo de correo. Para obtener más información sobre el cifrado avanzado de mensajes, vea [Cifrado avanzado de mensajes](ome-advanced-message-encryption.md).

## <a name="defining-rules-for-microsoft-purview-message-encryption"></a>Definición de reglas para Cifrado de mensajes de Microsoft Purview

Una manera de habilitar Cifrado de mensajes de Microsoft Purview es que los administradores de Exchange Online y Exchange Online Protection definan reglas de flujo de correo. Estas reglas determinan en qué condiciones se deben cifrar los mensajes de correo electrónico. Cuando se establece una acción de cifrado para una regla, los mensajes que coincidan con las condiciones de regla se cifran antes de que se envíen.

Las reglas de flujo de correo son flexibles, lo que le permite combinar condiciones para que pueda cumplir requisitos de seguridad específicos en una sola regla. Por ejemplo, puede crear una regla para cifrar todos los mensajes que contienen palabras clave especificadas y que se dirigen a destinatarios externos. Cifrado de mensajes de Microsoft Purview también cifra las respuestas de los destinatarios del correo electrónico cifrado.

Para obtener más información sobre cómo crear reglas de flujo de correo para aprovechar las ventajas de Cifrado de mensajes de Microsoft Purview, consulte [Definición de reglas de flujo de correo para cifrar mensajes de correo electrónico](define-mail-flow-rules-to-encrypt-email.md).

## <a name="get-started-with-the-microsoft-purview-message-encryption"></a>Introducción a la Cifrado de mensajes de Microsoft Purview

Si está listo para empezar a usar Cifrado de mensajes de Microsoft Purview dentro de su organización, consulte [Configuración de Cifrado de mensajes de Microsoft Purview](set-up-new-message-encryption-capabilities.md).

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>Enviar, ver y responder mensajes de correo electrónico cifrado

Con Cifrado de mensajes de Microsoft Purview, los usuarios pueden enviar correo electrónico cifrado desde Outlook y Outlook en la Web. Además, los administradores pueden configurar reglas de flujo de correo en Microsoft 365 para cifrar automáticamente los correos electrónicos en función de la coincidencia de palabras clave u otras condiciones.

Los destinatarios de mensajes cifrados que se encuentren en organizaciones podrán leer esos mensajes sin problemas en cualquier versión de Outlook, incluido Outlook para PC, Outlook para Mac, Outlook en la Web, Outlook para iOS y Outlook para Android. Los usuarios que reciben mensajes cifrados en otros clientes de correo electrónico pueden ver los mensajes en el portal de mensajes cifrados.

Para obtener instrucciones detalladas sobre cómo enviar y ver mensajes cifrados, eche un vistazo a estos artículos.

|Lea este artículo...|Si lo estás...|
|:-----|:-----|
|[Obtenga información sobre los mensajes protegidos en Office 365](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|Un usuario final que quiere obtener más información sobre cómo funcionan los mensajes cifrados y qué opciones están disponibles para usted.|
|[मैले कसरी abrir un mensaje protegido?](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|Un usuario final que quiere leer un mensaje protegido que se le envió. En este artículo se incluye información sobre cómo leer mensajes en varias versiones de Outlook y desde diferentes cuentas de correo electrónico, incluidas las cuentas fuera de Microsoft 365, como gmail y Yahoo! Cuentas.|
|[Envío, visualización y respuesta a mensajes cifrados en Outlook](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|Un usuario final que desea enviar, ver o responder a un mensaje cifrado desde Outlook. Incluso si no es miembro de una organización, sigue recibiendo notificaciones de mensajes cifrados que se le envían en Outlook. Use este artículo para obtener instrucciones sobre cómo ver y responder a mensajes cifrados enviados desde Office 365.|
|[Envío de un mensaje cifrado o firmado digitalmente](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|Un usuario final que desea enviar, ver o responder a mensajes cifrados mediante Outlook para Mac. En este artículo también se trata el uso de métodos de cifrado distintos de OME, como S/MIME.|
|[Visualización de mensajes cifrados en el dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Un usuario final que ha recibido un mensaje cifrado con Office 365 cifrado de mensajes en el dispositivo Android, puede usar la aplicación gratuita Visor de OME para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo hacerlo.|
|[Visualización de mensajes cifrados en el iPhone o iPad](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Un usuario final que ha recibido un mensaje cifrado con Office 365 cifrado de mensajes en su iPhone o iPad, puede usar la aplicación gratuita Visor de OME para ver el mensaje y enviar una respuesta cifrada. En este artículo se explica cómo hacerlo.|
||
