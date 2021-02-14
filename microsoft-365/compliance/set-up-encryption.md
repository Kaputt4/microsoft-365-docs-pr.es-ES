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
description: Con Office 365, algunas funcionalidades de cifrado están activadas de forma predeterminada; se pueden configurar otras capacidades para cumplir ciertos requisitos legales o de cumplimiento.
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799995"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

El cifrado puede proteger su contenido de que los usuarios no autorizados puedan leerlo. Dado que el cifrado en [Office 365](encryption.md) se puede realizar con diversas tecnologías y métodos, no hay un único lugar donde activar o configurar el cifrado. En este artículo se proporciona información sobre varias formas de configurar o configurar el cifrado como parte de la estrategia de protección de la información.
  
> [!TIP]
> Si está buscando más detalles técnicos sobre el cifrado, vea los detalles de referencia técnica sobre el cifrado [en Office 365.](technical-reference-details-about-encryption.md)
  
Con Office 365, hay varias capacidades de cifrado disponibles de forma predeterminada. Se pueden configurar capacidades de cifrado adicionales para cumplir ciertos requisitos legales o de cumplimiento. En la tabla siguiente se describen varios métodos de cifrado para diferentes escenarios.
  
|**Escenario**|**Métodos de cifrado**|
|:-----|:-----|
|Los archivos se guardan en equipos Windows  <br/> |El cifrado en el nivel de equipo se puede realizar con BitLocker en dispositivos Windows. Como administrador de la empresa o profesional de TI, puedes configurarlo con Microsoft Deployment Toolkit (MDT). Consulta [Configurar MDT para BitLocker.](https://go.microsoft.com/fwlink/?linkid=849282)  <br/> |
|Los archivos se guardan en dispositivos móviles  <br/> |Algunos tipos de dispositivos móviles cifran los archivos que se guardan en esos dispositivos de forma predeterminada. Con las funcionalidades de administración de dispositivos móviles integrada para [Office 365,](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)puede establecer directivas que determinen si se permite que los dispositivos móviles accedan a datos en Office 365. Por ejemplo, puede establecer una directiva que permita que solo los dispositivos que cifran contenido accedan a los datos de Office 365. Consulta [Crear e implementar directivas de seguridad de dispositivos.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Para obtener un control adicional sobre cómo interactúan los dispositivos móviles con Office 365, puede considerar la posibilidad de agregar [Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps)  <br/> |
|Necesita controlar las claves de cifrado que se usan para cifrar los datos en los centros de datos de Microsoft  <br/> | Como administrador de Office 365, puede controlar las claves de cifrado de su organización y, a continuación, configurar Office 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft.  <br/> [Cifrado de servicio con Clave de cliente de Office 365](customer-key-overview.md) <br/> |
|Las personas se comunican por correo electrónico (Exchange Online)  <br/> | Como administrador de Exchange Online, tiene varias opciones para configurar el cifrado de correo electrónico. Entre ellos se incluyen:  <br/>  Usar el cifrado de mensajes de [Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) para permitir que los usuarios envíen mensajes cifrados dentro o fuera de su organización  <br/>  Uso [de S/MIME para la firma y el cifrado de](https://aka.ms/c6dozg) mensajes para cifrar y firmar digitalmente mensajes de correo electrónico  <br/>  Uso de TLS [para configurar conectores para el flujo de correo seguro con otra organización](https://aka.ms/hs809p) <br/>  Vea [cifrado de correo electrónico en Office 365.](https://aka.ms/hic3f7)  <br/> |
|Se tiene acceso a los archivos desde sitios de grupo o bibliotecas de documentos (OneDrive para la Empresa o SharePoint Online)  <br/> |Cuando los usuarios trabajan con archivos guardados en OneDrive para la Empresa o SharePoint Online, se usan conexiones TLS. Esto está integrado en Office 365 automáticamente. Vea [Cifrado de datos en OneDrive para la Empresa y SharePoint Online.](https://go.microsoft.com/fwlink/?linkid=526379)  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Skype Empresarial Online)  <br/> |Cuando los usuarios trabajan con archivos con Skype Empresarial Online, se usa TLS para la conexión. Esto está integrado en Office 365 automáticamente. Vea [Seguridad y archivado (Skype Empresarial Online).](https://aka.ms/nuq4ws)  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Microsoft Teams)  <br/> |Cuando los usuarios trabajan con archivos con Microsoft Teams, se usa TLS para la conexión. Esto está integrado en Office 365 automáticamente. Microsoft Teams no admite actualmente la representación en línea del correo electrónico cifrado. Para evitar que el correo electrónico cifrado se desembarque en Microsoft Teams como cifrado, vea preguntas más frecuentes sobre el [cifrado de mensajes.](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)  <br/> 

## <a name="additional-information"></a>Información adicional

Para obtener más información sobre las soluciones de protección de archivos que incluyen opciones de cifrado, vea Soluciones de protección de [archivos en Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
 
