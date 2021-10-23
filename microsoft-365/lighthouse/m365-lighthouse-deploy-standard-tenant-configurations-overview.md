---
title: Introducción al uso de líneas base para implementar configuraciones de inquilino estándar
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo usar líneas base para implementar configuraciones de inquilino estándar.
ms.openlocfilehash: 2818b0e611bad7ae8895a1f44dcf557cb293aba8
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60554953"
---
# <a name="overview-of-using-baselines-to-deploy-standard-tenant-configurations"></a>Introducción al uso de líneas base para implementar configuraciones de inquilino estándar 

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse línea base proporcionan una forma repetible y escalable de evaluar y administrar la configuración de seguridad Microsoft 365 en varios inquilinos de clientes. Las líneas base también ayudan a supervisar las directivas de seguridad principales y los estándares de cumplimiento de inquilinos con configuraciones que protegen usuarios, dispositivos y datos.

Diseñado para ayudar a los partners a permitir que los clientes adopten la seguridad a su propio ritmo, Lighthouse proporciona un conjunto estándar de parámetros de línea base y configuraciones predefinidas para Microsoft 365 servicios. Estas configuraciones de seguridad ayudan a medir el progreso Microsoft 365 seguridad y cumplimiento de los inquilinos.

Puede ver la línea base predeterminada y sus pasos de implementación desde Lighthouse. Para aplicar líneas base a un inquilino, seleccione **Inquilinos** en el panel de navegación izquierdo y, a continuación, seleccione un espacio empresarial. A continuación, vaya a la **pestaña Planes de** implementación e implemente la línea base deseada.

## <a name="standard-baseline-security-templates"></a>Plantillas de seguridad de línea base estándar

Las configuraciones de línea base estándar de Faro para cargas de trabajo de seguridad están diseñadas para ayudar a todos los inquilinos administrados a alcanzar un estado aceptable de cobertura y cumplimiento de seguridad.

Las configuraciones de línea base de la tabla siguiente vienen estándar con la línea base predeterminada de Lighthouse.<br><br>

| Configuración de línea base | Descripción |
|--|--|
| Requerir MFA para administradores | Una directiva de acceso condicional de solo informe que requiere autenticación multifactor para los administradores. Es necesario para todas las aplicaciones en la nube. |
| Requerir MFA para usuarios finales | Una directiva de acceso condicional de solo informe que requiere autenticación multifactor para los usuarios. Es necesario para todas las aplicaciones en la nube. |
| Bloquear la autenticación heredada | Una directiva de acceso condicional de solo informe para bloquear la autenticación de cliente heredada. |
| Configurar la inscripción de dispositivos | Inscripción de dispositivos para permitir que los dispositivos de inquilino se inscriban en Microsoft Endpoint Manager. Para ello, configura la inscripción automática entre Azure Active Directory y Microsoft Endpoint Manager. |
| Configurar Antivirus de Microsoft Defender para Windows 10 y versiones posteriores | Un perfil de configuración de dispositivo para Windows dispositivos con una configuración Antivirus de Microsoft Defender configuración predeterminada. |
| Configurar una directiva de cumplimiento de dispositivos para Windows 10 y versiones posteriores | Una Windows de dispositivos con configuraciones preconfiguradas para cumplir los requisitos básicos de cumplimiento. |

## <a name="related-content"></a>Contenido relacionado

[Implementar Microsoft 365 Lighthouse líneas base](m365-lighthouse-deploy-baselines.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)
