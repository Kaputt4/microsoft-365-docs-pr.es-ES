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
description: Obtenga información sobre cómo configurar Exchange Online IRM para que use el Servicio de administración de derechos de Active Directory (AD RMS) local para satisfacer los requisitos de su organización.
ms.openlocfilehash: 6a9759fce102c60dd766dd86ba8c9e6d4a02d85b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924994"
---
# <a name="exchange-online-mail-encryption-with-ad-rms"></a>Cifrado de correo de Exchange Online con AD RMS

Para ayudar a evitar la filtración de información, Exchange Online incluye la función Information Rights Management (IRM), que ofrece protección en línea y sin conexión para los mensajes de correo y los datos adjuntos. Puede configurar Exchange Online IRM para que use el Servicio de administración de derechos de Active Directory (AD RMS) local, si es necesario, para satisfacer los requisitos de la organización. Esta opción es poco frecuente. Si no tiene un requisito para usar AD RMS, use cifrado de mensajes de [Office 365](ome.md) en su lugar. 

Los usuarios de Microsoft Outlook o Outlook en la web pueden aplicar la protección IRM y los administradores pueden aplicarla mediante reglas de protección de transporte o reglas de protección de Outlook. IRM le ayuda tanto a usted como a los usuarios a controlar quién puede consultar, reenviar, imprimir o copiar información confidencial del correo.
  
## <a name="changes-to-how-irm-works-with-office-365-message-encryption-ome-and-azure-active-directory"></a>Cambios en el funcionamiento de IRM con el cifrado de mensajes (OME) de Office 365 y Azure Active Directory

A partir de septiembre de 2017, cuando configure las nuevas funcionalidades de cifrado de mensajes de Office 365 para su organización, también configure IRM para su uso con Azure Rights Management (Azure RMS). Ya no configura IRM con Azure RMS por separado. En su lugar, OME y administración de derechos funcionan perfectamente juntos. Para obtener más información acerca de las nuevas funcionalidades, vea Preguntas más frecuentes sobre cifrado de mensajes [de Office 365](./ome-faq.md). Si está listo para empezar a usar las nuevas funcionalidades de OME dentro de su organización, vea Configurar nuevas funcionalidades de cifrado de mensajes de [Office 365](./set-up-new-message-encryption-capabilities.md)integradas en Azure Information Protection.
  
## <a name="how-irm-works-with-exchange-online-and-active-directory-rights-management-services"></a>Cómo funciona IRM con Exchange Online y Active Directory Rights Management Services

Exchange Online IRM usa Active Directory Rights Management Services (AD RMS) local, una tecnología de protección de la información en Windows Server 2008 y versiones posteriores. La protección de IRM se implanta en el correo electrónico mediante la aplicación de una plantilla de directiva de permisos de AD RMS a un mensaje de correo electrónico. Los derechos se adjuntan al propio mensaje para que la protección se produzca en línea y sin conexión y dentro y fuera del firewall de la organización.
  
Los usuarios pueden aplicar una plantilla a un mensaje de correo electrónico para controlar los permisos que los destinatarios tienen en un mensaje. Algunas acciones, como reenviar o extraer información de un mensaje, guardar un mensaje o imprimirlo, se pueden controlar aplicando una directiva de permisos AD RMS al mensaje.
  
Puedes configurar IRM para usar un servidor ad rms que ejecute Windows Server 2008 o posterior. Puede usar este servidor de AD RMS local para administrar las plantillas de directiva de permisos AD RMS en la organización basada en nube. Outlook también depende del servidor de AD RMS para permitir a los usuarios aplicar la protección IRM a los mensajes que envían. Para obtener más información, vea [Configure IRM to use an on-premises AD RMS server](configure-irm-to-use-an-on-premises-ad-rms-server.md). 
  
Después de habilitarla, la protección IRM se aplica a los mensajes del modo siguiente:
  
- **Los usuarios pueden aplicar manualmente una plantilla con Outlook y Outlook en la web.** Los usuarios pueden aplicar una plantilla de directiva de derechos de AD RMS a un mensaje de correo electrónico seleccionando la plantilla de la **lista Establecer permisos.** Cuando los usuarios envían un mensaje protegido con IRM, los datos adjuntos que tengan un formato compatible reciben la misma protección de IRM que el mensaje. La protección de IRM se aplica a los archivos asociados con Word, Excel y PowerPoint, así como a los archivos .xps y a los mensajes de correo adjuntos. 
    
- **Los administradores pueden usar reglas de protección de transporte para aplicar la protección IRM automáticamente a Outlook y Outlook en la web.** Puede crear reglas de protección de transporte a mensajes protegidos por IRM. Configure la acción de la regla de protección de transporte para aplicar una plantilla de permisos de AD RMS a los mensajes que cumplan la condición de la regla. Después de habilitar IRM, las plantillas de directivas de permisos de AD RMS de la organización ya se pueden usar con la acción de la regla de protección de transporte denominada **Aplicar protección de derechos al mensaje con**.
    
- **Los administradores pueden crear reglas de protección de Outlook.** Las reglas de protección de Outlook aplican automáticamente la protección IRM a los mensajes de Outlook 2010 (no Outlook en la web) en función de las condiciones de los mensajes que incluyen el departamento del remitente, a quién se envía el mensaje y si los destinatarios están dentro o fuera de la organización. Para información detallada, vea [Create an Outlook Protection Rule](/exchange/create-an-outlook-protection-rule-exchange-2013-help).
