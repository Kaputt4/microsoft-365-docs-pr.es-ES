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
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Obtenga información sobre cómo incorporar dispositivos macOS en soluciones de cumplimiento
ms.openlocfilehash: b24fd172224e0d1f8080ddd22cb3532dce0afe2b
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792297"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>Incorporar dispositivos macOS en la información general de Microsoft 365 (versión preliminar)

Los dispositivos MacOS se pueden incorporar a Microsoft 365 de cumplimiento mediante Intune o JAMF Pro. Los procedimientos de incorporación varían en función de la solución de administración que se use. Si los dispositivos macOS ya se han incorporado a Microsoft Defender para endpoint (MDE), hay menos pasos. Consulte [Pasos siguientes para](#next-steps) obtener vínculos a los procedimientos adecuados.

## <a name="get-registered"></a>Registrarse

Para obtener acceso a esta característica, debe registrar el espacio empresarial con Microsoft. Vea, [registrarse para la compatibilidad Microsoft 365 macOS](https://aka.ms/EndpointDLPIgnite21-Previews).

**Se aplica a:**

- [Microsoft 365 Prevención de pérdida de datos de extremo (DLP)](./endpoint-dlp-learn-about.md)
- [Administración de riesgos internos](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
<!--- [Insider risk management](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)-->

## <a name="before-you-begin"></a>Antes de empezar

Antes de empezar a usar Dlp de extremo en dispositivos macOS (Catalina 10.15 o posterior), debe familiarizarse con estos artículos:

- [Obtenga más información sobre la prevención de pérdida de datos de Microsoft 365 de punto de conexión](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [Introducción a la prevención de pérdida de datos en punto de conexión](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

Si no está familiarizado con DLP en absoluto, también debe familiarizarse con estos artículos:

- [Obtenga más información acerca de la prevención contra la pérdida de datos](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [Planear la prevención de pérdida de datos (DLP)](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [Referencia de directiva de prevención de pérdida de datos](dlp-policy-reference.md#data-loss-prevention-policy-reference)

Los dispositivos macOS ya deben administrarse a través de Intune o JAMF Pro.
 
- Para incorporarse a Intune, consulta Guía de implementación: Administrar dispositivos [macOS](/mem/intune/fundamentals/deployment-guide-platform-macos) en Microsoft Intune [e Inscribir tu Mac con Portal de empresa de Intune](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp). 
- Para incorporarse a JAMF Pro, [jamf Pro administradores](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/) y [jamf](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/) Pro instalación y configuración para Mac
- Instalar el explorador perimetral v95+ en los dispositivos macOS 

## <a name="licensing-guidance"></a>Instrucciones sobre licencias

Vea, Microsoft 365 [de licencias para la protección de la información](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="activities-that-can-be-restricted-on-macos"></a>Actividades que se pueden restringir en macOS 

Una vez que un dispositivo macOS se incorpore a Microsoft 365 de cumplimiento normativo, puedes supervisar y restringir estas acciones con directivas de prevención de pérdida de datos (DLP).

Copiar en un medio **extraíble USB:** cuando se aplica, esta acción bloquea, advierte o audita la copia o el movimiento de archivos protegidos desde un dispositivo de extremo a un medio extraíble USB 

**Copiar en recursos** compartidos de red: cuando se aplica, esta acción bloquea, advierte o audita la copia o el movimiento de archivos protegidos desde un dispositivo de extremo a cualquier recurso compartido de red 

**Imprimir:** cuando se aplica, esta acción bloquea, advierte o audita cuando se imprimen archivos protegidos desde un dispositivo de extremo 

**Copiar en el** Portapapeles: cuando se aplica, esta acción bloquea, advierte o audita los datos del archivo protegido que se copia en un portapapeles en un dispositivo de extremo 

**Upload** a la nube: esta acción bloquea, advierte o audita cuando se impide o permite cargar archivos protegidos en servicios en la nube en función de la lista de dominios permitidos o no permitidos en la configuración global. Cuando esta acción se establece en advertir o bloquear, otros exploradores (definidos en la lista de exploradores no permitidos en Configuración global) no tienen acceso al archivo. 

**Se obtiene** acceso a las aplicaciones no cubiertas: cuando se aplica, esta acción impide que las aplicaciones que están en la lista de aplicaciones no cubiertas (tal como se define en Configuración global) tengan acceso a archivos protegidos en un dispositivo de extremo. Escenarios de ejemplo 

## <a name="next-steps"></a>Siguientes pasos

Es necesario incorporar dispositivos Microsoft 365 soluciones de cumplimiento normativo para recibir telemetría del sensor DLP y aplicar directivas de prevención de pérdida de datos. 

- Para los dispositivos macOS que se administran a través de Intune, consulte Incorporación y incorporación de dispositivos macOS en soluciones de cumplimiento Microsoft 365 [con Intune (versión preliminar)](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)

- Para los dispositivos macOS que se administran a través de Intune y que tienen Microsoft Defender para endpoint (MDE) implementados en ellos, consulte [Onboard and offboard macOS devices into Compliance solutions using Intune for Microsoft Defender for Endpoint customers (preview)](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview)

- Para los dispositivos macOS que se administran a través de JAMF Pro, consulte [Onboard and offboard macOS devices into Microsoft 365 Compliance solutions using JAMF Pro (versión preliminar)](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview)

- Para los dispositivos macOS que se administran a través de JAMF Pro y que tienen Microsoft Defender para Endpoint (MDE) implementados en ellos, consulte [Onboard and offboard macOS devices into Compliance solutions using JAMF Pro for Microsoft Defender for Endpoint customers (preview)](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)


## <a name="related-topics"></a>Temas relacionados

- [Uso de la prevención de pérdida de datos en punto de conexión](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Matriz de soporte técnico para sugerencias de directivas dlp en aplicaciones de Microsoft](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
