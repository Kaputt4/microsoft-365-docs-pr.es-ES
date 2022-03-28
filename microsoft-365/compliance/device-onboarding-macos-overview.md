---
title: Incorporar dispositivos macOS en la información general de Microsoft 365 (versión preliminar)
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo incorporar dispositivos macOS en soluciones de cumplimiento
ms.openlocfilehash: 783179ae749ac7cd6de671435927ba5bbdbdacad
ms.sourcegitcommit: 9d563faeaa50b59b0b468dbb373d886e5270f58e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2022
ms.locfileid: "64387023"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>Incorporar dispositivos macOS en la información general de Microsoft 365 (versión preliminar)

Los dispositivos MacOS se pueden incorporar a Microsoft 365 de cumplimiento mediante Intune o JAMF Pro. Los procedimientos de incorporación varían en función de la solución de administración que se use. Si los dispositivos macOS ya se han incorporado a Microsoft Defender para endpoint (MDE), hay menos pasos. Consulte [Pasos siguientes para](#next-steps) obtener vínculos a los procedimientos adecuados.

**Se aplica a:**

- [Prevención de pérdida de datos de extremo (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar a usar Dlp de extremo en dispositivos macOS (Catalina 10.15 o posterior), debe familiarizarse con estos artículos:

- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

Si no está familiarizado con DLP en absoluto, también debe familiarizarse con estos artículos:

- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference)

Si no está familiarizado con Insider Risk, debe familiarizarse con estos artículos:

 - [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
 - [Planificar la administración de riesgos internos](insider-risk-management-plan.md#plan-for-insider-risk-management)

Los dispositivos macOS ya deben administrarse a través de Intune o JAMF Pro.
 
- Para incorporarse a Intune, consulta Guía de implementación: Administrar dispositivos [macOS](/mem/intune/fundamentals/deployment-guide-platform-macos) en Microsoft Intune [e Inscribir tu Mac con Portal de empresa de Intune](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Para incorporarse a JAMF Pro consulta, [jamf Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) administradores y guía de instalación y configuración de [JAMF Pro para Mac](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- Instalar el explorador perimetral v95+ en los dispositivos macOS 

## <a name="licensing-guidance"></a>Instrucciones sobre licencias

Vea, Microsoft 365 [de licencias para la protección de la información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

## <a name="activities-that-can-be-restricted-on-macos"></a>Actividades que se pueden restringir en macOS 

Una vez que un dispositivo macOS se incorpore a Microsoft 365 de cumplimiento normativo, puedes supervisar y restringir estas acciones con directivas de prevención de pérdida de datos (DLP).

**Copiar en un medio extraíble USB** : cuando se aplica, esta acción bloquea, advierte o audita la copia o el movimiento de archivos protegidos desde un dispositivo de extremo a un medio extraíble USB 

**Copiar en recursos** compartidos de red: cuando se aplica, esta acción bloquea, advierte o audita la copia o el movimiento de archivos protegidos desde un dispositivo de extremo a cualquier recurso compartido de red 

**Imprimir** : cuando se aplica, esta acción bloquea, advierte o audita cuando se imprimen archivos protegidos desde un dispositivo de extremo 

**Copiar en el** Portapapeles: cuando se aplica, esta acción bloquea, advierte o audita los datos del archivo protegido que se copia en un portapapeles en un dispositivo de extremo 

**Upload** a la nube: esta acción bloquea, advierte o audita cuando se impide o permite cargar archivos protegidos en servicios en la nube en función de la lista de dominios permitidos o no permitidos en la configuración global. Cuando esta acción se establece en advertir o bloquear, otros exploradores (definidos en la lista de exploradores no permitidos en Configuración global) no tienen acceso al archivo. 

**Se obtiene** acceso a las aplicaciones no cubiertas: cuando se aplica, esta acción impide que las aplicaciones que están en la lista de aplicaciones no cubiertas (tal como se define en Configuración global) tengan acceso a archivos protegidos en un dispositivo de extremo. Escenarios de ejemplo 

## <a name="onboarding-devices-into-device-management"></a>Incorporación de dispositivos a la administración de dispositivos

Para poder supervisar y proteger los elementos confidenciales de un dispositivo, es necesario que habilite la supervisión del dispositivo y que incorpore los puntos de conexión. Ambas acciones se realizan en el portal de cumplimiento de Microsoft 365.

Cuando quiera incorporar dispositivos que todavía no hayan sido incorporados, descargue el script apropiado y, luego, impleméntelo en esos dispositivos. <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. Abra la [página del centro](https://compliance.microsoft.com) **de Configuración** de cumplimiento de Microsoft y elija **Habilitar la supervisión de dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

2. Abra la página Configuración del Centro de cumplimiento y **elija Activar la supervisión de dispositivos macOS**.

## <a name="next-steps"></a>Siguientes pasos

Es necesario incorporar dispositivos Microsoft 365 soluciones de cumplimiento normativo para recibir telemetría del sensor DLP y aplicar directivas de prevención de pérdida de datos. 

Tema | Descripción
:---|:---
|[Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante Intune (versión preliminar)](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)|Para dispositivos macOS administrados a través de Intune
|[Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante Intune para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview) |Para dispositivos macOS que se administran a través de Intune y que tienen implementado Microsoft Defender para punto de conexión (MDE)
|[Incorporar y retirar dispositivos macOS en soluciones de cumplimiento de Microsoft 365 mediante JAMF Pro (versión preliminar)](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview) | Para dispositivos macOS que se administran a través de JAMF Pro
|[Incorporar y retirar dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes de Microsoft Defender para punto de conexión (versión preliminar)](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)|Para dispositivos macOS que se administran a través de JAMF Pro y que tienen implementado Microsoft Defender para punto de conexión (MDE)


## <a name="related-topics"></a>Temas relacionados

- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Matriz de soporte técnico para sugerencias de directivas dlp en aplicaciones de Microsoft](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
