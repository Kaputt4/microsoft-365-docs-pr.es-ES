---
title: Configurar el cifrado en Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, algunas capacidades de cifrado están activadas de forma predeterminada; se pueden configurar otras funciones para cumplir ciertos requisitos legales o de cumplimiento normativo.
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799995"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

El cifrado puede impedir que los usuarios no autorizados lean el contenido. Como el [cifrado en Office 365](encryption.md) puede realizarse con diferentes tecnologías y métodos, no hay un único lugar en el que activar o configurar el cifrado. En este artículo se proporciona información sobre las diversas formas de configurar o configurar el cifrado como parte de la estrategia de protección de la información.
  
> [!TIP]
> Si está buscando más detalles técnicos sobre el cifrado, consulte [información de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md).
  
Con Office 365, hay disponibles varias capacidades de cifrado de forma predeterminada. Se pueden configurar Capacidades de cifrado adicionales para cumplir ciertos requisitos legales o de cumplimiento normativo. En la tabla siguiente se describen varios métodos de cifrado para distintos escenarios.
  
|**Escenario**|**Métodos de cifrado**|
|:-----|:-----|
|Los archivos se guardan en los equipos Windows  <br/> |El cifrado en el nivel de equipo puede realizarse con BitLocker en dispositivos Windows. Como administrador de la empresa o profesional de ti, puede configurarlo mediante el kit de herramientas de implementación de Microsoft (MDT). Consulte [configurar MDT para BitLocker](https://go.microsoft.com/fwlink/?linkid=849282).  <br/> |
|Los archivos se guardan en dispositivos móviles  <br/> |Algunos tipos de dispositivos móviles cifran los archivos que se guardan en esos dispositivos de forma predeterminada. Con las [capacidades de la administración de dispositivos móviles integrada para Office 365](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0), puede establecer directivas que determinen si se permitirá que los dispositivos móviles tengan acceso a los datos de Office 365. Por ejemplo, puede establecer una directiva que permita que solo los dispositivos que cifran contenido obtengan acceso a datos de Office 365. Consulte [crear e implementar directivas de seguridad de dispositivos](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6).  <br/> Para obtener más control sobre cómo interactúan los dispositivos móviles con Office 365, puede considerar la posibilidad de agregar [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps).  <br/> |
|Necesita controlar las claves de cifrado usadas para cifrar los datos en los centros de datos de Microsoft  <br/> | Como administrador de Office 365, puede controlar las claves de cifrado de su organización y, después, configurar Office 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft.  <br/> [Cifrado de servicio con Clave de cliente de Office 365](customer-key-overview.md) <br/> |
|Los usuarios se comunican a través del correo electrónico (Exchange Online)  <br/> | Como administrador de Exchange Online, tiene varias opciones para configurar el cifrado de correo electrónico. Entre ellas se incluyen:  <br/>  Usar el [cifrado de mensajes de Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) para permitir que los usuarios envíen mensajes cifrados dentro o fuera de la organización  <br/>  Uso [de S/MIME para la firma y el cifrado de mensajes](https://aka.ms/c6dozg) para cifrar y firmar digitalmente los mensajes de correo electrónico  <br/>  Uso de TLS para [configurar conectores para el flujo de correo seguro con otra organización](https://aka.ms/hs809p) <br/>  Consulte [cifrado de correo electrónico en Office 365](https://aka.ms/hic3f7).  <br/> |
|Se obtiene acceso a los archivos desde los sitios de grupo o las bibliotecas de documentos (OneDrive para la empresa o SharePoint Online)  <br/> |Cuando los usuarios trabajan con archivos guardados en OneDrive para la empresa o SharePoint Online, se usan las conexiones TLS. Esto se integra en Office 365 automáticamente. Consulte [cifrado de datos en OneDrive para la empresa y SharePoint Online](https://go.microsoft.com/fwlink/?linkid=526379).  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Skype empresarial online)  <br/> |Cuando los usuarios trabajan con archivos que usan Skype empresarial online, se usa TLS para la conexión. Esto se integra en Office 365 automáticamente. Consulte [seguridad y archivado (Skype empresarial online)](https://aka.ms/nuq4ws).  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Microsoft Teams)  <br/> |Cuando los usuarios trabajan con archivos que usan Microsoft Teams, se usa TLS para la conexión. Esto se integra en Office 365 automáticamente. Actualmente, Microsoft Teams no es compatible con la representación en línea de correo electrónico cifrado. Para evitar que se Cifre el correo electrónico cifrado en Microsoft Teams, consulte [preguntas más frecuentes sobre el cifrado de mensajes](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail).  <br/> 

## <a name="additional-information"></a>Información adicional

Para obtener más información acerca de las soluciones de protección de archivos que incluyen opciones de cifrado, consulte [soluciones de protección de archivos en Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
 
