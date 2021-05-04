---
title: Cifrado de correo de Exchange Online con AD RMS
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2c956776-0016-4be6-b4cd-133a237f4a9e
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo configurar Exchange Online IRM para usar el Servicio de administración de derechos de Active Directory (AD RMS) local para satisfacer los requisitos de la organización.
ms.openlocfilehash: d98cf5c762cd4dac0cbad6d25a3cc766d5c5310a
ms.sourcegitcommit: 2655bb0ccd66279c35be2fadbd893c937d084109
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "51876279"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Cifrado de correo de Exchange Online con AD RMS

Para ayudar a evitar la filtración de información, Exchange Online incluye la función Information Rights Management (IRM), que ofrece protección en línea y sin conexión para los mensajes de correo y los datos adjuntos. Puede configurar Exchange Online IRM para que use el Servicio de administración de derechos de Active Directory local (AD RMS), si es necesario, para satisfacer los requisitos de la organización. Esta opción es poco frecuente. Si no tienes un requisito para usar AD RMS, [usa](ome.md) Cifrado de mensajes de Office 365 en su lugar. 

Los usuarios de Microsoft Outlook o Outlook pueden aplicar la protección IRM en la web, y los administradores pueden aplicarla mediante reglas de protección de transporte o Outlook de protección. IRM le ayuda tanto a usted como a los usuarios a controlar quién puede consultar, reenviar, imprimir o copiar información confidencial del correo.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Cambios en el funcionamiento de IRM con Cifrado de mensajes de Office 365 (OME) y Azure Active Directory

A partir de septiembre de 2017, cuando configura las nuevas funcionalidades de Cifrado de mensajes de Office 365 para su organización, también configura IRM para su uso con Azure Rights Management (Azure RMS). Ya no configura IRM con Azure RMS por separado. En su lugar, OME y administración de derechos funcionan perfectamente juntos. Para obtener más información acerca de las nuevas [funcionalidades, consulte preguntas Cifrado de mensajes de Office 365 preguntas más frecuentes.](./ome-faq.yml) Si está listo para empezar a usar las nuevas funcionalidades de OME dentro de su organización, consulte Configurar nuevas funcionalidades de Cifrado de mensajes de Office 365 integradas en [Azure Information Protection](./set-up-new-message-encryption-capabilities.md).
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Cómo funciona IRM con Exchange Online y Active Directory Rights Management Services

Exchange Online IRM usa Active Directory Rights Management Services local (AD RMS), una tecnología de protección de la información en Windows Server 2008 y versiones posteriores. La protección de IRM se implanta en el correo electrónico mediante la aplicación de una plantilla de directiva de permisos de AD RMS a un mensaje de correo electrónico. Los derechos se adjuntan al propio mensaje para que la protección se produzca en línea y sin conexión y dentro y fuera del firewall de la organización.
  
Los usuarios pueden aplicar una plantilla a un mensaje de correo electrónico para controlar los permisos que los destinatarios tienen en un mensaje. Algunas acciones, como reenviar o extraer información de un mensaje, guardar un mensaje o imprimirlo, se pueden controlar aplicando una directiva de permisos AD RMS al mensaje.
  
Puede configurar IRM para que use un servidor de AD RMS que ejecute Windows Server 2008 o posterior. Puede usar este servidor de AD RMS local para administrar las plantillas de directiva de permisos AD RMS en la organización basada en nube. Outlook también depende del servidor de AD RMS para permitir a los usuarios aplicar la protección IRM a los mensajes que envían. Para obtener más información, vea [Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Después de habilitarla, la protección IRM se aplica a los mensajes del modo siguiente:
  
- **Los usuarios pueden aplicar manualmente una plantilla mediante Outlook y Outlook en la web.** Los usuarios pueden aplicar una plantilla de directiva de derechos de AD RMS a un mensaje de correo electrónico seleccionando la plantilla de la **lista Establecer permisos.** Cuando los usuarios envían un mensaje protegido con IRM, los datos adjuntos que tengan un formato compatible reciben la misma protección de IRM que el mensaje. La protección de IRM se aplica a los archivos asociados con Word, Excel y PowerPoint, así como a los archivos .xps y a los mensajes de correo adjuntos. 
    
- **Los administradores pueden usar reglas de protección de transporte para aplicar la protección IRM automáticamente a Outlook y Outlook en la web.** Puede crear reglas de protección de transporte a mensajes protegidos por IRM. Configure la acción de la regla de protección de transporte para aplicar una plantilla de permisos de AD RMS a los mensajes que cumplan la condición de la regla. Después de habilitar IRM, las plantillas de directivas de permisos de AD RMS de la organización ya se pueden usar con la acción de la regla de protección de transporte denominada **Aplicar protección de derechos al mensaje con**.
    
- **Los administradores pueden crear Outlook de protección.** Outlook las reglas de protección de Outlook aplican automáticamente la protección IRM a los mensajes de Outlook 2010 (no Outlook en la web) en función de las condiciones de mensaje que incluyen el departamento del remitente, a quién se envía el mensaje y si los destinatarios están dentro o fuera de la organización. Para información detallada, vea [Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help).
