---
title: Introducción al aprendizaje de simulación de ataques
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar la formación de simulación de ataques para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.openlocfilehash: 9d97816edf7d59c002658fc8bb3f39e72dbc2430
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49871253"
---
# <a name="get-started-using-attack-simulation-training"></a>Introducción al aprendizaje de simulación de ataques

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Si su organización tiene Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación y respuesta de [amenazas,](office-365-ti.md)puede usar la formación de simulación de ataques en el Centro de seguridad de Microsoft para ejecutar escenarios de ataque realistas en su organización. Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real repercuta en la línea inferior. Lea este artículo para obtener más información.

> [!NOTE]
> El entrenamiento de simulación de ataque reemplaza la experiencia anterior del simulador de ataques v1 que se describe en el Simulador de ataques de [Microsoft Defender para Office 365.](attack-simulator.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Para abrir el Centro de seguridad de Microsoft, vaya a <https://security.microsoft.com/> . La formación de simulación de ataques está disponible en el aprendizaje **de simulación** de ataques de colaboración \> **y correo electrónico.** Para ir directamente al entrenamiento de simulación de ataques, abra <https://security.microsoft.com/attacksimulator> .

- Para obtener más información sobre la disponibilidad de aprendizaje de simulación de ataques en diferentes suscripciones de Microsoft 365, vea la descripción del servicio de [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

- Deberá tener asignados permisos en el Centro de seguridad & cumplimiento o en Azure Active Directory para poder realizar los procedimientos descritos en este artículo. En concreto, debe ser miembro de administración de la **organización,** administrador de **seguridad** o uno de los siguientes roles:
  - **Administradores del simulador de ataques:** crea y administra todos los aspectos de las campañas de simulación de ataques.
  - **Autores de carga del simulador de ataque:** crea cargas de ataque que un administrador puede iniciar más adelante.

  Para obtener más información, vea [Permisos en el Centro](permissions-in-the-security-and-compliance-center.md) de seguridad & cumplimiento o Acerca de los roles de [administrador.](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)

- No hay ningún cmdlet de PowerShell correspondiente para la formación de simulación de ataques.

- La simulación de ataques y los datos relacionados con la formación se almacenan con otros datos de clientes para los servicios de Microsoft 365. Para obtener más información, [vea ubicaciones de datos de Microsoft 365.](/microsoft-365/enterprise/o365-data-locations) La simulación de ataques no está disponible actualmente en las siguientes regiones: SGP, NOR, EAU, ZAF, GER, SUJETA y CHE.

## <a name="simulations"></a>Simulaciones

*La suplantación* de identidad es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. *La suplantación* de identidad forma parte de un subconjunto de técnicas que clasificamos como _ingeniería social._

En el aprendizaje de simulación de ataques, hay disponibles varios tipos de técnicas de ingeniería social:

- **Recolección de credenciales:** un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se le redirige a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino tiene un formato que representa un sitio web conocido para generar confianza en el usuario.

- **Datos adjuntos de malware:** un atacante envía al destinatario un mensaje que contiene datos adjuntos. Cuando el destinatario abre los datos adjuntos, se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o a atrincherarse aún más.

- **Vínculo en datos adjuntos:** se trata de un híbrido de una recolección de credenciales. Un atacante envía al destinatario un mensaje que contiene una dirección URL dentro de un archivo adjunto. Cuando el destinatario abre los datos adjuntos y hace clic en la dirección URL, se les redirige a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino tiene un formato que representa un sitio web conocido para generar confianza en el usuario.

- **Vínculo a malware:** un atacante envía al destinatario un mensaje que contiene un vínculo a datos adjuntos en un sitio de uso compartido de archivos conocido (por ejemplo, SharePoint Online o Dropbox). Cuando el destinatario hace clic en la dirección URL, se abren los datos adjuntos y se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o a atrincherarse aún más.

- **Unidad por dirección URL:** un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se les redirige a un sitio web que intenta ejecutar código en segundo plano. Este código en segundo plano intenta recopilar información sobre el destinatario o implementar código arbitrario en su dispositivo. Normalmente, el sitio web de destino es un sitio web conocido que se ha visto comprometido o un clon de un sitio web conocido. La familiaridad con el sitio web ayuda a convencer al usuario de que el vínculo es seguro para hacer clic. Esta técnica también se conoce como ataque _de agujero de agua._

> [!NOTE]
> Compruebe la disponibilidad de la dirección URL de suplantación de identidad simulada en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad. Aunque trabajamos con muchos proveedores de reputación de direcciones URL para permitir siempre estas direcciones URL de simulación, no siempre tenemos cobertura completa (por ejemplo, Exploración segura de Google). La mayoría de los proveedores proporcionan instrucciones que le permiten permitir siempre direcciones URL específicas (por ejemplo, <https://support.google.com/chrome/a/answer/7532419> ).

Las direcciones URL que se usan en la formación de simulación de ataques se describen en la siguiente lista:

- <https://www.mcsharepoint.com>
- <https://www.attemplate.com>
- <https://www.doctricant.com>
- <https://www.mesharepoint.com>
- <https://www.officence.com>
- <https://www.officenced.com>
- <https://www.officences.com>
- <https://www.officentry.com>
- <https://www.officested.com>
- <https://www.prizegives.com>
- <https://www.prizemons.com>
- <https://www.prizewel.com>
- <https://www.prizewings.com>
- <https://www.shareholds.com>
- <https://www.sharepointen.com>
- <https://www.sharepointin.com>
- <https://www.sharepointle.com>
- <https://www.sharesbyte.com>
- <https://www.sharession.com>
- <https://www.sharestion.com>
- <https://www.templateau.com>
- <https://www.templatent.com>
- <https://www.templatern.com>
- <https://www.windocyte.com>

### <a name="create-a-simulation"></a>Crear una simulación

Para obtener instrucciones paso a paso sobre cómo crear y enviar una nueva simulación, vea [Simular un ataque de suplantación de identidad](attack-simulation-training.md).

### <a name="create-a-payload"></a>Crear una carga

Para obtener instrucciones paso a paso sobre cómo crear una carga para usarla en una simulación, consulta Crear una carga personalizada para el aprendizaje [de simulación de ataques.](attack-simulation-training-payloads.md)

### <a name="gaining-insights"></a>Obtener información

Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulta Obtener información a través de [la formación de simulación de ataques.](attack-simulation-training-insights.md)
