---
title: Introducción a la incorporación de dispositivos macOS a Microsoft 365
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
description: Más información sobre la incorporación de dispositivos macOS a soluciones de cumplimiento
ms.openlocfilehash: b697b805b8a4c65a0528054ca301f16d203e5a64
ms.sourcegitcommit: 979343980f05ceb546ca0df23562504aaca34b88
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2022
ms.locfileid: "66912767"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview"></a>Introducción a la incorporación de dispositivos macOS a Microsoft 365

Los dispositivos MacOS se pueden incorporar a las soluciones de Microsoft Purview mediante Intune o JAMF Pro. Los procedimientos de incorporación varían en función de la solución de administración que use. Si los dispositivos macOS ya se han incorporado a Microsoft Defender para punto de conexión (MDE), hay menos pasos. Consulte [Pasos siguientes](#next-steps) para obtener vínculos a los procedimientos adecuados para usted.

**Se aplica a:**

- [Prevención de perdida de datos en el punto de conexión (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md)

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar a trabajar con DLP de punto de conexión en dispositivos macOS (Catalina 10.15 o posterior), debe familiarizarse con estos artículos:

- [Obtenga más información sobre la prevención de pérdida de datos en punto de conexión](endpoint-dlp-learn-about.md)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md)

Si no está familiarizado con DLP, también debe familiarizarse con estos artículos:

- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference)

Si no está familiarizado con Insider Risk, debe familiarizarse con estos artículos:

 - [Administración de riesgos internos](insider-risk-management.md)
 - [Planificar la administración de riesgos internos](insider-risk-management-plan.md#plan-for-insider-risk-management)

Los dispositivos macOS ya deben administrarse a través de Intune o JAMF Pro.
 
- Para incorporarse a Intune, consulte [Guía de implementación: Administración de dispositivos macOS en Microsoft Intune](/mem/intune/fundamentals/deployment-guide-platform-macos) e [Inscripción de su Mac con Portal de empresa de Intune](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Para incorporarse a JAMF Pro, consulte la [guía de administradores de JAMF Pro](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) y la [Guía de instalación y configuración de JAMF Pro para Mac](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/).
<!--- Install the v95+ Edge browser on your macOS devices--> 

### <a name="supported-browsers"></a>Exploradores compatibles

DLP de punto de conexión admite estos exploradores en macOS Catalina 10.15 o posterior:

- Microsoft Edge (última versión)
- Safari (versión más reciente, solo macOS)
- Chrome (última versión)
- Firefox (última versión)

## <a name="licensing-guidance"></a>Guía de licencias

Consulte la [guía de licencias de Microsoft 365 para la protección de la información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business).

## <a name="activities-that-can-be-audited-and-restricted-on-macos"></a>Actividades que se pueden auditar y restringir en macOS 

Una vez que un dispositivo macOS se incorpora a las soluciones de Microsoft Purview, puede supervisar y restringir estas acciones con directivas de prevención de pérdida de datos (DLP).

**Copia en un medio extraíble USB** : cuando se aplica, esta acción bloquea, advierte o audita la copia o el traslado de archivos protegidos desde un dispositivo de punto de conexión a medios extraíbles USB. 

**Copia en recursos compartidos de red** : cuando se aplica, esta acción bloquea, advierte o audita la copia o el traslado de archivos protegidos desde un dispositivo de punto de conexión a cualquier recurso compartido de red. 

**Imprimir** : cuando se aplica, esta acción bloquea, advierte o audita cuando se imprimen archivos protegidos desde un dispositivo de punto de conexión. 

**Copiar en el Portapapeles** : cuando se aplica, esta acción bloquea, advierte o audita los datos del archivo protegido que se copia en un portapapeles en un dispositivo de punto de conexión. 

**Cargar en la nube** : esta acción bloquea, advierte o audita cuando se impide o permite cargar archivos protegidos en los servicios en la nube en función de la lista de dominios permitidos o no permitidos en la configuración global. Cuando esta acción se establece para advertir o bloquear, otros exploradores (definidos en la lista de exploradores no permitidos en Configuración global) no pueden acceder al archivo. 

**Acceso mediante aplicaciones no permitidas** : cuando se aplica, esta acción impide que las aplicaciones que se encuentran en la lista de aplicaciones no permitidas (tal como se define en Configuración global) accedan a archivos protegidos en un dispositivo de punto de conexión. Escenarios de ejemplo 

## <a name="onboarding-devices-into-device-management"></a>Incorporación de dispositivos a la administración de dispositivos

Para poder supervisar y proteger los elementos confidenciales de un dispositivo, es necesario que habilite la supervisión del dispositivo y que incorpore los puntos de conexión. Ambas acciones se realizan en el portal de cumplimiento de Microsoft Purview.

Cuando quiera incorporar dispositivos que todavía no hayan sido incorporados, descargue el script apropiado y, luego, impleméntelo en esos dispositivos. <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. Abra la página **Configuración** [de portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com) y elija **Habilitar supervisión de dispositivos**.

   > [!NOTE]
   > Aunque, por lo general, habilitar la incorporación de dispositivos tarda aproximadamente 60 segundos, espere 30 minutos antes de ponerse en contacto con el soporte técnico de Microsoft.

2. Abra la página de configuración del Centro de cumplimiento y elija **Activar la supervisión de dispositivos macOS**.

## <a name="next-steps"></a>Pasos siguientes

La incorporación de dispositivos a las soluciones de Microsoft Purview es necesaria para recibir telemetría del sensor DLP y aplicar directivas de prevención de pérdida de datos. 

Tema | Descripción
:---|:---
|[Incorporar y desactivar dispositivos macOS en soluciones de Microsoft Purview mediante Intune](device-onboarding-offboarding-macos-intune.md)|Para dispositivos macOS administrados a través de Intune
|[Incorporar y retirar dispositivos macOS en soluciones de cumplimiento con Intune para clientes de Microsoft Defender para punto de conexión](device-onboarding-offboarding-macos-intune-mde.md) |Para dispositivos macOS que se administran a través de Intune y que tienen implementado Microsoft Defender para punto de conexión (MDE)
|[Incorporación y eliminación de dispositivos macOS en soluciones de Microsoft Purview mediante JAMF Pro](device-onboarding-offboarding-macos-jamfpro.md) | Para dispositivos macOS que se administran a través de JAMF Pro
|[Incorporación y eliminación de dispositivos macOS en soluciones de cumplimiento mediante JAMF Pro para clientes Microsoft Defender para punto de conexión](device-onboarding-offboarding-macos-jamfpro-mde.md)|Para dispositivos macOS que se administran a través de JAMF Pro y que tienen implementado Microsoft Defender para punto de conexión (MDE)


## <a name="related-topics"></a>Temas relacionados

- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Matriz de compatibilidad para sugerencias de directiva DLP en aplicaciones de Microsoft](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
