---
title: Piloto de Microsoft Defender para aplicaciones en la nube con Microsoft 365 Defender
description: Configure su laboratorio Microsoft 365 Defender prueba o entorno piloto para probar y experimentar la solución de seguridad diseñada para proteger dispositivos, identidades, datos y aplicaciones.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9961caee57fade58581e8ddb8b9de7ea0d6aafd8
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498569"
---
# <a name="pilot-microsoft-defender-for-cloud-apps-with-microsoft-365-defender"></a>Piloto de Microsoft Defender para aplicaciones en la nube con Microsoft 365 Defender


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 3 de 3](eval-defender-mcas-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender para aplicaciones en la nube. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-mcas-overview.md).

Siga estos pasos para configurar y configurar el piloto de Microsoft Defender para aplicaciones en la nube.


:::image type="content" source="../../media/defender/m365-defender-mcas-pilot-steps.png" alt-text="Los pasos para la implementación piloto de Microsoft Defender para aplicaciones en la nube" lightbox="../../media/defender/m365-defender-mcas-pilot-steps.png":::
- [Paso 1. Crear el grupo piloto: ámbito de la implementación piloto en determinados grupos de usuarios](#step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups)
- [Paso 2. Configurar protección: control de aplicaciones de acceso condicional](#step-2-configure-protectionconditional-access-app-control)
- [Paso 3. Probar funcionalidades: tutoriales para proteger el entorno](#step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment) 


## <a name="step-1-create-the-pilot-groupscope-your-pilot-deployment-to-certain-user-groups"></a>Paso 1. Crear el grupo piloto: ámbito de la implementación piloto en determinados grupos de usuarios

Microsoft Defender para aplicaciones en la nube le permite tener en cuenta su implementación. El ámbito permite seleccionar determinados grupos de usuarios que se supervisarán para las aplicaciones o se excluirán de la supervisión. Puede incluir o excluir grupos de usuarios. Para tener en cuenta la implementación piloto, consulte [Scoped Deployment](/cloud-app-security/scoped-deployment).


## <a name="step-2-configure-protectionconditional-access-app-control"></a>Paso 2. Configurar protección: control de aplicaciones de acceso condicional

Una de las protecciones más eficaces que puede configurar es el control de aplicaciones de acceso condicional. Esta protección requiere integración con Azure Active Directory (Azure AD). Te permite aplicar directivas de acceso condicional, incluidas las directivas relacionadas (como requerir dispositivos en buen estado) a las aplicaciones en la nube que hayas sancionado. 

El primer paso para usar Microsoft Defender para aplicaciones en la nube para administrar aplicaciones SaaS consiste en descubrir estas aplicaciones y, a continuación, agregarlas a Azure AD inquilino. Si necesitas ayuda con la detección, consulta [Descubrir y administrar aplicaciones SaaS en la red](/cloud-app-security/tutorial-shadow-it). Después de descubrir aplicaciones, [agrega estas aplicaciones a tu Azure AD inquilino](/azure/active-directory/manage-apps/add-application-portal).

Puedes empezar a administrar estas aplicaciones ejecutando las siguientes tareas:

- Primero, en Azure AD, cree una nueva directiva de acceso condicional y configúrela para "Usar control de aplicaciones de acceso condicional". Esta configuración ayuda a redirigir la solicitud a Defender para aplicaciones en la nube. Puedes crear una directiva y agregar todas las aplicaciones SaaS a esta directiva.
- A continuación, en Defender para aplicaciones en la nube, cree directivas de sesión. Cree una directiva para cada control que desee aplicar.

Para obtener más información, incluidas las aplicaciones y clientes compatibles, consulta Proteger aplicaciones con [Microsoft Defender para el](/cloud-app-security/proxy-intro-aad) control de aplicaciones de acceso condicional de aplicaciones en la nube. 

Por ejemplo, vea Directivas recomendadas de [Microsoft Defender para aplicaciones en la nube para aplicaciones SaaS](../office-365-security/mcas-saas-access-policies.md). Estas directivas se basa en un [conjunto de directivas](../office-365-security/microsoft-365-policies-configurations.md) comunes de acceso a dispositivos y identidades que se recomiendan como punto de partida para todos los clientes. 

## <a name="step-3-try-out-capabilitieswalk-through-tutorials-for-protecting-your-environment"></a>Paso 3. Probar funcionalidades: tutoriales para proteger el entorno 

La documentación de Microsoft Defender para Aplicaciones en la nube incluye una serie de tutoriales para ayudarle a detectar riesgos y proteger su entorno. 

Pruebe los tutoriales de Defender for Cloud Apps:

- [Detectar actividad de usuario sospechosa](/cloud-app-security/tutorial-suspicious-activity)
- [Investigar usuarios riesgosos](/cloud-app-security/tutorial-ueba)
- [Investigar aplicaciones de OAuth arriesgadas](/cloud-app-security/investigate-risky-oauth)
- [Descubrir y proteger información confidencial](/cloud-app-security/tutorial-dlp)
- [Proteger cualquier aplicación de la organización en tiempo real](/cloud-app-security/tutorial-proxy)
- [Bloquear descargas de información confidencial](/cloud-app-security/use-case-proxy-block-session-aad)
- [Proteger los archivos con cuarentena de administrador](/cloud-app-security/use-case-admin-quarantine)
- [Requerir autenticación de paso a paso tras una acción arriesgada](/cloud-app-security/tutorial-step-up-authentication)

Para obtener más información sobre la búsqueda avanzada en Datos de Microsoft Defender para aplicaciones en la nube, consulta el [vídeo](https://www.microsoft.com/en-us/videoplayer/embed/RWFISa).

## <a name="next-steps"></a>Pasos siguientes

[Investigar y responder con Microsoft 365 Defender en un entorno piloto](eval-defender-investigate-respond.md)

Vuelva a la introducción a [Evaluar Microsoft Defender para aplicaciones en la nube](eval-defender-mcas-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md)
