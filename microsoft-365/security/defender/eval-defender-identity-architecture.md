---
title: Revise los requisitos de arquitectura y el marco técnico para Microsoft Defender for Identity
description: El diagrama técnico de Microsoft Defender for Identity en Microsoft 365 Defender le ayudará a comprender la identidad en Microsoft 365 antes de compilar el laboratorio de prueba o el entorno piloto.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: a8ba7bffcba998ac2fcfd45c25688c610a1561dc
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482194"
---
# <a name="review-architecture-requirements-and-key-concepts-for-microsoft-defender-for-identity"></a>Revise los requisitos de arquitectura y los conceptos clave para Microsoft Defender for Identity


**Se aplica a:**
- Microsoft 365 Defender

Este artículo es el [paso 1 del 3](eval-defender-identity-overview.md) en el proceso de configuración del entorno de evaluación para Microsoft Defender for Identity. Para obtener más información sobre este proceso, consulte el [artículo de información general](eval-defender-identity-overview.md).

Antes de habilitar Microsoft Defender for Identity, asegúrese de comprender la arquitectura y de que puede cumplir los requisitos.

Microsoft Defender for Identity usa el aprendizaje automático y el análisis de comportamiento para identificar ataques en la red local, junto con la detección y prevención proactiva de riesgos de inicio de sesión de usuario asociados a identidades en la nube. Para obtener más información, consulte [¿Qué es Microsoft Defender for Identity?](/defender-for-identity/what-is)

Defender for Identity protege a los usuarios de Active Directory local o a los usuarios sincronizados con Azure Active Directory (Azure AD). Para proteger un entorno formado solo por usuarios de Azure AD, consulte [Azure AD Identity Protection](/azure/active-directory/identity-protection/overview-identity-protection).

## <a name="understand-the-architecture"></a>Información sobre la arquitectura

En el diagrama siguiente se muestra la arquitectura de línea base de Defender for Identity. 

:::image type="content" source="../../media/defender/m365-defender-identity-architecture.png" alt-text="La arquitectura de identidad de Microsoft Defender for Identity" lightbox="../../media/defender/m365-defender-identity-architecture.png":::

En esta ilustración:

- Los sensores instalados en los controladores de dominio de AD analizan los registros y el tráfico de red y los envían a Microsoft Defender for Identity para su análisis y generación de informes.
-  Los sensores también pueden analizar Servicios de federación de Active Directory (AD FS) (AD FS) cuando Azure AD está configurado para usar la autenticación federada (línea de puntos en la ilustración). 
- Microsoft Defender for Identity comparte señales a Microsoft 365 Defender para la detección y respuesta extendidas (XDR).

Los sensores de Defender for Identity se pueden instalar directamente en los siguientes servidores:

- Controladores de dominio: el sensor supervisa directamente el tráfico del controlador de dominio, sin necesidad de un servidor dedicado ni de la configuración de la creación de reflejo del puerto.
- AD FS: el sensor supervisa directamente el tráfico de red y los eventos de autenticación.

Para más información sobre la arquitectura de Defender for Identity, incluida la integración con Defender for Cloud Apps, consulte [arquitectura de Microsoft Defender for Identity](/defender-for-identity/architecture).


## <a name="understand-key-concepts"></a>Descripción de los conceptos clave

En la tabla siguiente se identificaron conceptos clave que son importantes comprender al evaluar, configurar e implementar Microsoft Defender for Identity.

|Concepto  |Descripción |Más información  |
|---------|---------|---------|
| Actividades supervisadas | Defender for Identity supervisa las señales generadas desde dentro de la organización para detectar actividades sospechosas o malintencionadas y le ayuda a determinar la validez de cada amenaza potencial para que pueda evaluar y responder de forma eficaz.  |  [Microsoft Defender for Identity actividades supervisadas](/defender-for-identity/monitored-activities)       |
| Alertas de seguridad    | Las alertas de seguridad de Defender for Identity explican las actividades sospechosas detectadas por los sensores de la red junto con los actores y equipos implicados en cada amenaza.   | [alertas de seguridad de Microsoft Defender for Identity](/defender-for-identity/suspicious-activity-guide?tabs=external)    |
| Perfiles de entidad    | Los perfiles de entidad proporcionan una investigación exhaustiva de usuarios, equipos, dispositivos y recursos junto con su historial de acceso.   | [Descripción de los perfiles de entidad](/defender-for-identity/entity-profiles)  |
| Rutas de desplazamiento lateral    | Un componente clave de la información de seguridad de MDI es la identificación de rutas de desplazamiento lateral en las que un atacante usa cuentas no confidenciales para obtener acceso a las cuentas o máquinas confidenciales en toda la red.  | [Microsoft Defender for Identity rutas de desplazamiento lateral (LMP)](/defender-for-identity/use-case-lateral-movement-path)  |
| Resolución de nombres de red    |  La resolución de nombres de red (NNR) es un componente de la funcionalidad MDI que captura actividades basadas en el tráfico de red, eventos de Windows, ETW, etc. y correlaciona estos datos sin procesar con los equipos pertinentes implicados en cada actividad.       | [¿Qué es la resolución de nombres de red?](/defender-for-identity/nnr-policy)      |
| Informes    | Los informes de Defender for Identity le permiten programar o generar y descargar informes inmediatamente que proporcionan información de estado del sistema y de la entidad.  Puede crear informes sobre el estado del sistema, las alertas de seguridad y las posibles rutas de desplazamiento lateral detectadas en su entorno.   | [informes de Microsoft Defender for Identity](/defender-for-identity/reports)       |
| Grupos de funciones    | Defender for Identity ofrece grupos basados en roles y acceso delegado para proteger los datos según las necesidades específicas de seguridad y cumplimiento de su organización, incluidos administradores, usuarios y visores.        |  [Grupos de roles de Microsoft Defender for Identity](/defender-for-identity/role-groups)       |
| Portal administrativo    |  Además del portal de Microsoft 365 Defender, el portal de Defender for Identity se puede usar para supervisar y responder a actividades sospechosas.      | [Trabajo con el portal de Microsoft Defender for Identity](/defender-for-identity/workspace-portal)        |
| integración Microsoft Defender for Cloud Apps   | Microsoft Defender for Cloud Apps se integra con Microsoft Defender for Identity para proporcionar análisis de comportamiento de entidades de usuario (UEBA) en un entorno híbrido, tanto en la aplicación en la nube como en el entorno local.   | integración Microsoft Defender for Identity  |

## <a name="review-prerequisites"></a>Revisión de los requisitos previos

Defender for Identity requiere algunos requisitos previos para asegurarse de que los componentes de red e identidad local cumplen los requisitos mínimos. Use este artículo como lista de comprobación para asegurarse de que el entorno está listo: [Microsoft Defender for Identity requisitos previos](/defender-for-identity/prerequisites).


## <a name="next-steps"></a>Pasos siguientes

Paso 2 de 3: [Habilitación del entorno de evaluación de Defender for Identity](eval-defender-identity-enable-eval.md)

Vuelva a la introducción para [Evaluar Microsoft Defender for Identity](eval-defender-identity-overview.md)

Vuelva a la información general sobre [la evaluación y la Microsoft 365 Defender piloto](eval-overview.md) 
