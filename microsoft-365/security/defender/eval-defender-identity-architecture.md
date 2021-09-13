---
title: Revisar los requisitos de arquitectura y el marco técnico para Microsoft Defender for Identity
description: El diagrama técnico de Microsoft Defender para identity en Microsoft 365 Defender le ayudará a comprender la identidad en Microsoft 365 antes de crear el entorno piloto o el laboratorio de prueba.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d7474a3cb2f04627c5da16f84dbde6d195021551
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192547"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>Revisar los requisitos de arquitectura y los conceptos clave para Microsoft Defender for Identity


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es [el paso 1 de 3](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación de Microsoft Defender para Identity. Para obtener más información acerca de este proceso, vea el [artículo de introducción](eval-defender-identity-overview.md).

Antes de habilitar Microsoft Defender for Identity, asegúrese de comprender la arquitectura y de cumplir los requisitos.

Microsoft Defender for Identity usa aprendizaje automático y análisis de comportamiento para identificar ataques en toda la red local, junto con la detección y prevención proactiva de riesgos de inicio de sesión de usuario asociados con identidades de nube. Para obtener más información, consulta [¿Qué es Microsoft Defender para Identity?](/defender-for-identity/what-is)

Defender for Identity protege los usuarios locales de Active Directory o los usuarios sincronizados con su Azure Active Directory (Azure AD). Para proteger un entorno integrado solo por usuarios de Azure AD, consulte [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

En el siguiente diagrama se muestra la arquitectura de línea base de Defender for Identity. 

![Arquitectura de Microsoft Defender para Identity.](../../media/defender/m365-defender-identity-architecture.png)

En esta ilustración:
- Los sensores instalados en los controladores de dominio de AD analizan los registros y el tráfico de red y los envían a Microsoft Defender for Identity para su análisis e informes.
-  Los sensores también pueden analizar los Servicios de federación de Active Directory (AD FS) cuando Azure AD está configurado para usar la autenticación federada (línea punteada en la ilustración). 
- Microsoft Defender for Identity comparte las señales Microsoft 365 Defender para la detección y respuesta extendidas (XDR).


Los sensores de Defender for Identity se pueden instalar directamente en los siguientes servidores:

- Controladores de dominio: el sensor supervisa directamente el tráfico del controlador de dominio, sin la necesidad de un servidor dedicado o la configuración de la creación de reflejos de puertos.
- AD FS: el sensor supervisa directamente el tráfico de red y los eventos de autenticación.

Para obtener una visión más profunda de la arquitectura de Defender for Identity, incluida la integración con Cloud App Security, vea [Microsoft Defender for Identity architecture](/defender-for-identity/architecture).


## <a name="understand-key-concepts"></a>Comprender conceptos clave

En la siguiente tabla se identificaron conceptos clave que son importantes para comprender al evaluar, configurar e implementar Microsoft Defender para Identity.


|Concepto  |Descripción |Más información  |
|---------|---------|---------|
| Actividades supervisadas | Defender for Identity supervisa las señales generadas desde dentro de la organización para detectar actividad sospechosa o malintencionada y le ayuda a determinar la validez de cada amenaza potencial para que pueda realizar una triaje y responder de forma eficaz.  |  [Actividades supervisadas por Microsoft Defender para identidad](/defender-for-identity/monitored-activities)       |
| Alertas de seguridad    | Las alertas de seguridad de Defender for Identity explican las actividades sospechosas detectadas por los sensores de la red junto con los actores y los equipos implicados en cada amenaza.   | [Alertas de seguridad de Identidad de Microsoft Defender](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| Perfiles de entidad    | Los perfiles de entidad proporcionan una investigación exhaustiva de usuarios, equipos, dispositivos y recursos junto con su historial de acceso.   | [Descripción de los perfiles de entidad](/defender-for-identity/entity-profiles)  |
| Rutas de movimiento lateral    | Un componente clave de la información de seguridad de MDI es identificar rutas de movimiento lateral en las que un atacante usa cuentas no confidenciales para obtener acceso a cuentas o máquinas confidenciales en toda la red.  | [Rutas de movimiento lateral (LMP) de Microsoft Defender para la identidad](/defender-for-identity/use-case-lateral-movement-path)  |
| Resolución de nombres de red    |  La resolución de nombres de red (NNR) es un componente de la funcionalidad MDI que captura actividades basadas en tráfico de red, eventos Windows, ETW, etc. y correlaciona estos datos sin procesar con los equipos relevantes implicados en cada actividad.       | [¿Qué es la resolución de nombres de red?](/defender-for-identity/nnr-policy)      |
| Informes    | Los informes de Defender for Identity le permiten programar o generar y descargar inmediatamente informes que proporcionan información de estado del sistema y de la entidad.  Puede crear informes sobre el estado del sistema, las alertas de seguridad y las posibles rutas de movimiento lateral detectadas en el entorno.   | [Microsoft Defender para informes de identidad ](/defender-for-identity/reports)       |
| Grupos de funciones    | Defender for Identity ofrece grupos basados en roles y acceso delegado para proteger los datos según las necesidades específicas de seguridad y cumplimiento de su organización, que incluye administradores, usuarios y visores.        |  [Grupos de roles de Microsoft Defender for Identity](/defender-for-identity/role-groups)       |
| Portal administrativo    |  Además del portal de Microsoft 365 Defender, la cabina del portal Defender for Identity se usa para supervisar y responder a actividades sospechosas.      | [Trabajar con el portal de Microsoft Defender para identidades](/defender-for-identity/workspace-portal)        |
| Microsoft Cloud App Security integración   | Microsoft Cloud App Security se integra con Microsoft Defender for Identity para proporcionar análisis de comportamiento de entidades de usuario (UEBA) en un entorno híbrido, tanto en la aplicación en la nube como local.   | Integración de Microsoft Defender para identidades  |
| | | |


## <a name="review-prerequisites"></a>Revisar requisitos previos

Defender for Identity requiere algunos requisitos previos para garantizar que la identidad local y los componentes de red cumplan los requisitos mínimos. Use este artículo como una lista de comprobación para asegurarse de que el entorno está listo: [requisitos previos](/defender-for-identity/prerequisites)de Microsoft Defender para la identidad .


## <a name="next-steps"></a>Siguientes pasos

Paso 2 de 3: [Habilitar el entorno de evaluación Defender for Identity](eval-defender-identity-enable-eval.md)

Vuelva a la introducción a [Evaluate Microsoft Defender for Identity](eval-defender-identity-overview.md)

Vuelva a la introducción a [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) 