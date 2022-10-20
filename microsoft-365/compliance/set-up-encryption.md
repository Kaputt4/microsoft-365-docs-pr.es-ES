---
title: Configurar el cifrado en Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: landing-page
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.collection:
- tier1
- purview-compliance
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, algunas funcionalidades de cifrado están activadas de forma predeterminada; otras funcionalidades se pueden configurar para cumplir ciertos requisitos legales o de cumplimiento.
ms.openlocfilehash: 16b8bcd9bd0bb6ffbceec28e82111e4938ebc893
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68633006"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

El cifrado puede proteger el contenido frente a la lectura por parte de usuarios no autorizados. Dado que [el cifrado en Office 365](encryption.md) se puede realizar mediante varias tecnologías y métodos, no hay un solo lugar donde activar o configurar el cifrado. En este artículo se proporciona información sobre varias maneras de configurar o configurar el cifrado como parte de la estrategia de protección de la información.

> [!TIP]
> Si busca más detalles técnicos sobre el cifrado, consulte [Detalles de referencia técnica sobre el cifrado en Office 365](technical-reference-details-about-encryption.md).

Con Office 365, hay varias funcionalidades de cifrado disponibles de forma predeterminada. Se pueden configurar funcionalidades de cifrado adicionales para cumplir ciertos requisitos legales o de cumplimiento. En la tabla siguiente se describen varios métodos de cifrado para diferentes escenarios.

<br>

****

|Escenario|Métodos de cifrado|
|---|---|
|Los archivos se guardan en equipos Windows|El cifrado en el nivel de equipo se puede realizar mediante BitLocker en dispositivos Windows. Como administrador empresarial o profesional de TI, puede configurarlo mediante Microsoft Deployment Toolkit (MDT). Consulte [Configuración de MDT para BitLocker](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker).|
|Los archivos se guardan en dispositivos móviles|Algunos tipos de dispositivos móviles cifran los archivos que se guardan en esos dispositivos de forma predeterminada. Con [las funcionalidades de Administración de dispositivos móviles para Office 365 integradas](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0), puede establecer directivas que determinen si se permite que los dispositivos móviles accedan a los datos de Office 365. Por ejemplo, puede establecer una directiva que permita que solo los dispositivos que cifran el contenido accedan a Office 365 datos. Consulte [Creación e implementación de directivas de seguridad de dispositivos](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6). <p> Para obtener un control adicional sobre cómo interactúan los dispositivos móviles con Office 365, puede considerar la posibilidad de agregar [Microsoft Intune](/mem/intune/fundamentals/setup-steps).|
|Necesita control sobre las claves de cifrado que se usan para cifrar los datos en los centros de datos de Microsoft.|Como administrador de Office 365, puede controlar las claves de cifrado de su organización y, a continuación, configurar Office 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft. <p> [Cifrado de servicio con clave de cliente de Microsoft Purview](customer-key-overview.md)|
|Personas se comunican por correo electrónico (Exchange Online)|Como administrador de Exchange Online, tiene varias opciones para configurar el cifrado de correo electrónico. Entre las que se incluyen: <ul><li>Uso [de Office 365 cifrado de mensajes (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) para permitir que las personas envíen mensajes cifrados dentro o fuera de la organización</li><li>Uso [de S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) para cifrar y firmar digitalmente mensajes de correo electrónico</li><li>Uso de TLS para [configurar conectores para un flujo de correo seguro con otra organización](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> Consulte [Email cifrado en Office 365](./email-encryption.md).|
|Se accede a los archivos desde sitios de equipo o bibliotecas de documentos (OneDrive para la Empresa o SharePoint Online)|Cuando las personas trabajan con archivos guardados en OneDrive para la Empresa o SharePoint Online, se usan conexiones TLS. Esto se integra automáticamente en Office 365. Vea [Cifrado de datos en OneDrive para la Empresa y SharePoint Online](./data-encryption-in-odb-and-spo.md).|
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Skype Empresarial Online)|Cuando los usuarios trabajan con archivos mediante Skype Empresarial Online, se usa TLS para la conexión. Esto se integra automáticamente en Office 365. Consulte [Seguridad y archivado (Skype Empresarial en línea).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)|
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Microsoft Teams)|Cuando los usuarios trabajan con archivos con Microsoft Teams, se usa TLS para la conexión. Esto se integra automáticamente en Office 365. Microsoft Teams no admite actualmente la representación en línea del correo electrónico cifrado. Para evitar que el correo electrónico cifrado desembarque en Microsoft Teams como cifrado, consulte [Preguntas más frecuentes sobre cifrado de mensajes](./ome-faq.yml#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-).|
|

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="additional-information"></a>Información adicional

Para obtener más información sobre las soluciones de protección de archivos que incluyen opciones de cifrado, consulte [Soluciones de protección de archivos en Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
