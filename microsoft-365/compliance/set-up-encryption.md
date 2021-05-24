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
ms.openlocfilehash: 688d34d767a546cb97d940ab2141bb3edfabcda8
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52625238"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurar el cifrado en Office 365 Enterprise

El cifrado puede proteger el contenido de que los usuarios no autorizados lo lean. Dado [que el Office 365](encryption.md) puede realizarse con varias tecnologías y métodos, no hay un solo lugar donde activar o configurar el cifrado. En este artículo se proporciona información sobre varias formas de configurar o configurar el cifrado como parte de la estrategia de protección de la información.

> [!TIP]
> Si está buscando más detalles técnicos sobre el cifrado, consulte [Technical reference details about encryption in Office 365](technical-reference-details-about-encryption.md).

Con Office 365, hay varias funcionalidades de cifrado disponibles de forma predeterminada. Las capacidades de cifrado adicionales se pueden configurar para cumplir ciertos requisitos legales o de cumplimiento. En la tabla siguiente se describen varios métodos de cifrado para distintos escenarios.

<br>

****

|Escenario|Métodos de cifrado|
|---|---|
|Los archivos se guardan en Windows equipos|El cifrado en el nivel de equipo se puede realizar BitLocker en Windows dispositivos. Como administrador de empresa o administrador de TI Pro, puede configurarlo con microsoft Deployment Toolkit (MDT). Consulte [Configurar MDT para BitLocker](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker).|
|Los archivos se guardan en dispositivos móviles|Algunos tipos de dispositivos móviles cifran los archivos guardados en esos dispositivos de forma predeterminada. Con [las funcionalidades de los Administración de dispositivos móviles para Office 365](https://support.microsoft.com/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)integradas, puede establecer directivas que determinen si se va a permitir que los dispositivos móviles accedan a los datos en Office 365. Por ejemplo, puede establecer una directiva que solo permita que los dispositivos que cifran contenido accedan a Office 365 datos. Consulta [Crear e implementar directivas de seguridad de dispositivos.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6) <p> Para obtener un control adicional sobre cómo interactúan los dispositivos móviles Office 365, puede considerar la posibilidad de agregar [Microsoft Intune](/mem/intune/fundamentals/setup-steps).|
|Necesita controlar las claves de cifrado que se usan para cifrar los datos en los centros de datos de Microsoft|Como administrador Office 365, puede controlar las claves de cifrado de su organización y, a continuación, configurar Office 365 para usarlas para cifrar los datos en reposo en los centros de datos de Microsoft. <p> [Cifrado de servicio con Clave de cliente de Office 365](customer-key-overview.md)|
|Las personas se comunican por correo electrónico (Exchange Online)|Como administrador Exchange Online, tiene varias opciones para configurar el cifrado de correo electrónico. Entre ellas se incluyen: <ul><li>Usar Office 365 cifrado de mensajes [(OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) para permitir a las personas enviar mensajes cifrados dentro o fuera de la organización</li><li>Uso [de S/MIME](/exchange/security-and-compliance/smime-exo/smime-exo) para cifrar y firmar digitalmente mensajes de correo electrónico</li><li>Uso de TLS [para configurar conectores para el flujo de correo seguro con otra organización](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)</li></ul> <p> Consulte [Cifrado de correo electrónico en Office 365](./email-encryption.md).|
|Se tiene acceso a los archivos desde sitios de grupo o bibliotecas de documentos (OneDrive para la Empresa o SharePoint online)|Cuando los usuarios trabajan con archivos guardados en OneDrive para la Empresa o SharePoint Online, se usan conexiones TLS. Esto se incluye Office 365 automáticamente. Vea [Cifrado de datos en OneDrive para la Empresa y SharePoint Online](./data-encryption-in-odb-and-spo.md).|
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Skype Empresarial Online)|Cuando las personas trabajan con archivos mediante Skype Empresarial Online, TLS se usa para la conexión. Esto se incluye Office 365 automáticamente. Vea [Security and Archiving (Skype Empresarial Online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)|
|Los archivos se comparten en reuniones en línea y conversaciones de mensajería instantánea (Microsoft Teams)|Cuando las personas trabajan con archivos que usan Microsoft Teams, TLS se usa para la conexión. Esto se incluye Office 365 automáticamente. Microsoft Teams actualmente no admite la representación en línea del correo electrónico cifrado. Para evitar que el correo electrónico cifrado entre en Microsoft Teams cifrado, vea Preguntas más frecuentes sobre cifrado [de mensajes](./ome-faq.yml?view=o365-worldwide&preserve-view=true#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail-).|
|

## <a name="additional-information"></a>Información adicional

Para obtener más información sobre las soluciones de protección de archivos que incluyen opciones de cifrado, vea [File Protection Solutions in Office 365](https://www.microsoft.com/download/details.aspx?id=55523).
