---
title: Introducción al uso de aprendizaje de simulación de ataques
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar el aprendizaje de simulación de ataques para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones Microsoft 365 E5 o Microsoft Defender para Office 365 plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 244d0ae912a5cc2dc163b62f44b44877c0318b88
ms.sourcegitcommit: bcbcbd4ddc72ad2fed629619d23fac5827d072bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2022
ms.locfileid: "64507419"
---
# <a name="get-started-using-attack-simulation-training-in-defender-for-office-365"></a>Comenzar el entrenamiento de simulación de ataque en Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a Microsoft Defender para Office 365** [plan 2](defender-for-office-365.md)

Si su organización tiene Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2, que incluye capacidades de investigación y respuesta de [amenazas, puede](office-365-ti.md) usar el aprendizaje de simulación de ataques en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en su organización. Estos ataques simulados pueden ayudarte a identificar y encontrar usuarios vulnerables antes de que un ataque real impacte en la línea de fondo. Lea este artículo para obtener más información.

> [!NOTE]
> El entrenamiento de simulación de ataque reemplaza la experiencia anterior de Attack Simulator v1 que estaba disponible en el Centro de seguridad & cumplimiento en **el simulador de** \> ataque de administración de **amenazas** o <https://protection.office.com/attacksimulator>.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el portal de Microsoft 365 Defender, vaya a <https://security.microsoft.com>. El aprendizaje de simulación de ataques está disponible en **el aprendizaje de simulación de ataques por correo electrónico y** \> **colaboración**. Para ir directamente al aprendizaje de simulación de ataques, use <https://security.microsoft.com/attacksimulator>.

- Para obtener más información acerca de la disponibilidad del aprendizaje de simulación de ataques en Microsoft 365 suscripciones, [consulte Microsoft Defender para Office 365 descripción del servicio](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Debe tener asignados permisos en **Azure Active Directory para poder** realizar los procedimientos de este artículo. En concreto, debe ser miembro de uno de los siguientes roles:
  - **Administrador global**
  - **Administrador de seguridad**
  - **Administradores de simulación de ataques**<sup>\*</sup>: crear y administrar todos los aspectos de las campañas de simulación de ataques.
  - **Autor de la carga de**<sup>\*</sup> ataque: crea cargas de ataque que un administrador puede iniciar más adelante.

  <sup>\*</sup>La adición de usuarios a este rol en el portal de Microsoft 365 Defender no es compatible actualmente.

  Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md) o [About admin roles](../../admin/add-users/about-admin-roles.md).

- No hay cmdlets de PowerShell correspondientes para el aprendizaje de simulación de ataques.

- La simulación de ataques y los datos relacionados con la formación se almacenan con otros datos de clientes para Microsoft 365 servicios. Para obtener más información, [vea Microsoft 365 de datos](../../enterprise/o365-data-locations.md). La simulación de ataques está disponible en las siguientes regiones: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM, CHE, NOR, ZAF, ARE y DEU.

  > [!NOTE]
  > NOR, ZAF, ARE y DEU son las últimas adiciones. Todas las características excepto la telemetría de correo electrónico notificado estarán disponibles en estas regiones. Estamos trabajando para habilitar esto y notificaremos a nuestros clientes tan pronto como la telemetría de correo electrónico notificada esté disponible.

- A partir del 15 de junio de 2021, el entrenamiento de simulación de ataques está disponible en GCC. Si su organización tiene Office 365 G5 GCC o Microsoft Defender para Office 365 (Plan 2) para gobierno, puede usar el entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en su organización, tal como se describe en este artículo. El aprendizaje de simulación de ataques aún no está disponible GCC entornos De alto o DoD.

> [!NOTE]
> El entrenamiento de simulación de ataques ofrece un subconjunto de capacidades a los clientes de E3 como prueba. La oferta de prueba contiene la capacidad de usar una carga de recolección de credenciales y la capacidad de seleccionar experiencias de aprendizaje de "phishing isa" o "suplantación de identidad de mercado masivo". Ninguna otra funcionalidad forma parte de la oferta de prueba de E3.

## <a name="simulations"></a>Simulaciones

*Phishing* es un término genérico para ataques de correo electrónico que intentan robar información confidencial en mensajes que parecen ser de remitentes legítimos o de confianza. *El phishing* forma parte de un subconjunto de técnicas que clasificamos como _ingeniería social_.

En el aprendizaje de simulación de ataques, hay disponibles varios tipos de técnicas de ingeniería social:

- **Recolección de credenciales**: un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se les traslada a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino tiene un formato que representa un sitio web conocido para generar confianza en el usuario.

- **Datos adjuntos de malware**: un atacante envía al destinatario un mensaje que contiene datos adjuntos. Cuando el destinatario abre los datos adjuntos, el código arbitrario (por ejemplo, una macro) se ejecuta en el dispositivo del usuario para ayudar al atacante a instalar código adicional o atrincherarse aún más.

- **Vínculo en datos adjuntos**: se trata de un híbrido de una recolección de credenciales. Un atacante envía al destinatario un mensaje que contiene una dirección URL dentro de un archivo adjunto. Cuando el destinatario abre los datos adjuntos y hace clic en la dirección URL, se les traslada a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino tiene un formato que representa un sitio web conocido para generar confianza en el usuario.

- **Vínculo a malware**: un atacante envía al destinatario un mensaje que contiene un vínculo a un archivo adjunto en un sitio de uso compartido de archivos conocido (por ejemplo, SharePoint Online o Dropbox). Cuando el destinatario hace clic en la dirección URL, se abren los datos adjuntos y se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o reforzarse aún más.

- **Drive-by-url**: un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se las traslada a un sitio web que intenta ejecutar código en segundo plano. Este código en segundo plano intenta recopilar información sobre el destinatario o implementar código arbitrario en su dispositivo. Normalmente, el sitio web de destino es un sitio web conocido que se ha visto comprometido o un clon de un sitio web conocido. La familiaridad con el sitio web ayuda a convencer al usuario de que el vínculo es seguro para hacer clic. Esta técnica también se conoce como ataque _de agujero de agua_.

> [!NOTE]
> Compruebe la disponibilidad de la dirección URL de suplantación de identidad simulada en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad. Aunque trabajamos con muchos proveedores de reputación de url para permitir siempre estas direcciones URL de simulación, no siempre tenemos cobertura completa (por ejemplo, Google Caja fuerte Exploración). La mayoría de los proveedores proporcionan instrucciones que le permiten permitir siempre direcciones URL específicas (por ejemplo, <https://support.google.com/chrome/a/answer/7532419>).

Las direcciones URL usadas por el entrenamiento de simulación de ataque se describen en la siguiente lista:

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

Para obtener instrucciones paso a paso sobre cómo crear y enviar una nueva simulación, consulta [Simular un ataque de phishing](attack-simulation-training.md).

### <a name="create-a-payload"></a>Crear una carga

Para obtener instrucciones paso a paso sobre cómo crear una carga para su uso en una simulación, consulta Crear una carga personalizada para el aprendizaje [de simulación de ataques](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Obtener información

Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulta Obtener información a través del aprendizaje [de simulación de ataques](attack-simulation-training-insights.md).

> [!NOTE]
> Attack Simulator usa Caja fuerte Links en Defender para Office 365 para realizar un seguimiento seguro de los datos de clics de la dirección URL en el mensaje de carga que se envía a los destinatarios dirigidos de una campaña de suplantación de identidad( phishing), incluso si la configuración Seguimiento de clics del usuario en las directivas de **vínculos** de Caja fuerte está desactivada.
