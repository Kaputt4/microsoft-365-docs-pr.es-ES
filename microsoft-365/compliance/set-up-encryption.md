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
description: Con Office 365, algunas funcionalidades de cifrado están activadas de forma predeterminada; otras capacidades se pueden configurar para cumplir ciertos requisitos legales o de cumplimiento.
ms.openlocfilehash: e153c1e322adaea000cf686e857387d671b18a28
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051682"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

El cifrado puede proteger el contenido de que los usuarios no autorizados lo lean. Dado [que el cifrado en Office 365](encryption.md) se puede realizar con varias tecnologías y métodos, no hay un solo lugar donde activar o configurar el cifrado. En este artículo se proporciona información sobre varias formas de configurar o configurar el cifrado como parte de la estrategia de protección de la información.
  
> [!TIP]
> Si está buscando más detalles técnicos sobre el cifrado, vea [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).
  
Con Office 365, hay varias funcionalidades de cifrado disponibles de forma predeterminada. Las capacidades de cifrado adicionales se pueden configurar para cumplir ciertos requisitos legales o de cumplimiento. En la tabla siguiente se describen varios métodos de cifrado para distintos escenarios.
  
|**Escenario**|**Métodos de cifrado**|
|:-----|:-----|
|Los archivos se guardan en equipos Windows  <br/> |El cifrado en el nivel del equipo se puede realizar con BitLocker en dispositivos Windows. Como administrador de empresa o profesional de TI, puede configurarlo con Microsoft Deployment Toolkit (MDT). Consulta [Configurar MDT para BitLocker](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker).  <br/> |
|Los archivos se guardan en dispositivos móviles  <br/> |Algunos tipos de dispositivos móviles cifran los archivos guardados en esos dispositivos de forma predeterminada. Con funcionalidades de administración de dispositivos móviles integrada para [Office 365,](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)puede establecer directivas que determinen si se permite que los dispositivos móviles accedan a datos en Office 365. Por ejemplo, puede establecer una directiva que solo permita que los dispositivos que cifran contenido accedan a los datos de Office 365. Consulta [Crear e implementar directivas de seguridad de dispositivos.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Para obtener control adicional sobre cómo interactúan los dispositivos móviles con Office 365, puede considerar agregar [Microsoft Intune](/mem/intune/fundamentals/setup-steps).  <br/> |
|Necesita controlar las claves de cifrado que se usan para cifrar los datos en los centros de datos de Microsoft  <br/> | Como administrador de Office 365, puede controlar las claves de cifrado de su organización y, a continuación, configurar Office 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft.  <br/> [Cifrado de servicio con Clave de cliente de Office 365](customer-key-overview.md) <br/> |
|Las personas se comunican por correo electrónico (Exchange Online)  <br/> | Como administrador de Exchange Online, tiene varias opciones para configurar el cifrado de correo electrónico. Entre ellos se incluyen:  <br/>  Uso del cifrado de mensajes [de Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) para permitir que las personas envíen mensajes cifrados dentro o fuera de su organización  <br/>  Uso [de S/MIME para la firma y cifrado de](../security/defender-365-security/s-mime-for-message-signing-and-encryption.md) mensajes para cifrar y firmar digitalmente mensajes de correo electrónico  <br/>  Uso de TLS [para configurar conectores para el flujo de correo seguro con otra organización](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  Vea [Cifrado de correo electrónico en Office 365](./email-encryption.md).  <br/> |
|Se tiene acceso a los archivos desde sitios de grupo o bibliotecas de documentos (OneDrive para la Empresa o SharePoint Online)  <br/> |Cuando los usuarios trabajan con archivos guardados en OneDrive para la Empresa o SharePoint Online, se usan conexiones TLS. Esto se incluye automáticamente en Office 365. Vea [Cifrado de datos en OneDrive para la Empresa y SharePoint Online](./data-encryption-in-odb-and-spo.md).  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Skype Empresarial Online)  <br/> |Cuando las personas trabajan con archivos con Skype Empresarial Online, TLS se usa para la conexión. Esto se incluye automáticamente en Office 365. Vea [Seguridad y archivado (Skype Empresarial Online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)  <br/> |
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Microsoft Teams)  <br/> |Cuando los usuarios trabajan con archivos con Microsoft Teams, TLS se usa para la conexión. Esto se incluye automáticamente en Office 365. Microsoft Teams no admite actualmente la representación en línea del correo electrónico cifrado. Para evitar que el correo electrónico cifrado desembarque en Microsoft Teams como cifrado, vea Preguntas más frecuentes sobre cifrado [de mensajes](./ome-faq.md?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail).  <br/> 

## <a name="additional-information"></a>Información adicional

Para obtener más información sobre las soluciones de protección de archivos que incluyen opciones de cifrado, vea [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
