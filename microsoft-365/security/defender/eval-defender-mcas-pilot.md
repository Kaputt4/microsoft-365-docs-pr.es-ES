---
title: Microsoft Defender for Cloud Apps piloto con Microsoft 365 Defender
description: Configure su Microsoft 365 Defender laboratorio de prueba o entorno piloto para probar y experimentar la solución de seguridad diseñada para proteger dispositivos, identidades, datos y aplicaciones.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
ms.date: 07/09/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- zerotrust-solution
- highpri
ms.topic: conceptual
ms.openlocfilehash: 68b623bb1e04340e7f112e7e2d0a58210cca0e3b
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67480918"
---
# <a name="pilot-microsoft-defender-for-cloud-apps-with-microsoft-365-defender"></a>Microsoft Defender for Cloud Apps piloto con Microsoft 365 Defender


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 3 del 3](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Cloud Apps. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-mcas-overview.md).

Siga estos pasos para configurar y configurar el piloto para Microsoft Defender for Cloud Apps.


:::image type="content" source="../../media/defender/m365-defender-mcas-pilot-steps.png" alt-text="Los pasos para pilotar el Microsoft Defender for Cloud Apps" lightbox="../../media/defender/m365-defender-mcas-pilot-steps.png":::
- [Paso 1. Creación del grupo piloto: ámbito de la implementación piloto a determinados grupos de usuarios](#step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups)
- [Paso 2. Configuración de la protección: control de aplicaciones de acceso condicional](#step-2-configure-protectionconditional-access-app-control)
- [Paso 3. Probar funcionalidades: tutoriales para proteger el entorno](#step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment) 

## <a name="step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups"></a>Paso 1. Creación del grupo piloto: ámbito de la implementación piloto a determinados grupos de usuarios

Microsoft Defender for Cloud Apps permite limitar la implementación. El ámbito permite seleccionar determinados grupos de usuarios que se van a supervisar para las aplicaciones o excluirse de la supervisión. Puede incluir o excluir grupos de usuarios. Para limitar la implementación piloto, consulte [Implementación con ámbito](/cloud-app-security/scoped-deployment).


## <a name="step-2-configure-protectionconditional-access-app-control"></a>Paso 2. Configuración de la protección: control de aplicaciones de acceso condicional

Una de las protecciones más eficaces que puede configurar es el control de aplicaciones de acceso condicional. Esta protección requiere la integración con Azure Active Directory (Azure AD). Le permite aplicar directivas de acceso condicional, incluidas las directivas relacionadas (como requerir dispositivos en buen estado), a las aplicaciones en la nube que ha autorizado. 

El primer paso para usar Microsoft Defender for Cloud Apps para administrar aplicaciones SaaS es detectar estas aplicaciones y, a continuación, agregarlas al inquilino de Azure AD. Si necesita ayuda con la detección, consulte [Detección y administración de aplicaciones SaaS en la red](/cloud-app-security/tutorial-shadow-it). Una vez que haya detectado aplicaciones, [agregue estas aplicaciones al inquilino de Azure AD](/azure/active-directory/manage-apps/add-application-portal).

Puede empezar a administrar estas aplicaciones ejecutando las siguientes tareas:

- En primer lugar, en Azure AD, cree una nueva directiva de acceso condicional y configúrela para "Usar el control de aplicaciones de acceso condicional". Esta configuración ayuda a redirigir la solicitud a Defender for Cloud Apps. Puede crear una directiva y agregar todas las aplicaciones SaaS a esta directiva.
- A continuación, en Defender for Cloud Apps, cree directivas de sesión. Cree una directiva para cada control que quiera aplicar.

Para obtener más información, incluidas las aplicaciones y los clientes admitidos, consulte [Protección de aplicaciones con Microsoft Defender for Cloud Apps control de aplicaciones de acceso condicional](/cloud-app-security/proxy-intro-aad). 

Para ver directivas de ejemplo, consulte [Directivas de Microsoft Defender for Cloud Apps recomendadas para aplicaciones SaaS](../office-365-security/mcas-saas-access-policies.md). Estas directivas se basan en un conjunto de [directivas comunes de acceso a dispositivos e identidades](../office-365-security/microsoft-365-policies-configurations.md) que se recomiendan como punto de partida para todos los clientes. 

## <a name="step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment"></a>Paso 3. Probar funcionalidades: tutoriales para proteger el entorno 

La documentación de Microsoft Defender for Cloud Apps incluye una serie de tutoriales para ayudarle a detectar riesgos y proteger su entorno. 

Pruebe los tutoriales de Defender for Cloud Apps:

- [Detección de actividad sospechosa de usuario](/cloud-app-security/tutorial-suspicious-activity)
- [Investigación de usuarios de riesgo](/cloud-app-security/tutorial-ueba)
- [Investigación de aplicaciones de OAuth de riesgo](/cloud-app-security/investigate-risky-oauth)
- [Detección y protección de información confidencial](/cloud-app-security/tutorial-dlp)
- [Protección de cualquier aplicación de la organización en tiempo real](/cloud-app-security/tutorial-proxy)
- [Bloquear descargas de información confidencial](/cloud-app-security/use-case-proxy-block-session-aad)
- [Protección de los archivos con cuarentena de administrador](/cloud-app-security/use-case-admin-quarantine)
- [Requerir autenticación paso a paso por acción de riesgo](/cloud-app-security/tutorial-step-up-authentication)

Para obtener más información sobre la búsqueda avanzada en Microsoft Defender for Cloud Apps datos, vea el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa).

## <a name="next-steps"></a>Pasos siguientes

[Investigación y respuesta mediante Microsoft 365 Defender en un entorno piloto](eval-defender-investigate-respond.md)

Vuelva a la introducción para [Evaluar Microsoft Defender for Cloud Apps](eval-defender-mcas-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md)
