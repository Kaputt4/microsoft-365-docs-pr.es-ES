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
description: Los administradores pueden aprender a usar el entrenamiento de simulación de ataques para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 255d0f40cd360f2b4b3e5084f84989bdbe643319
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65415626"
---
# <a name="get-started-using-attack-simulation-training-in-defender-for-office-365"></a>Comenzar usar el entrenamiento de simulación de ataque en Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

Si su organización tiene Microsoft 365 E5 o Microsoft Defender para Office 365 plan 2, que incluye [funcionalidades de investigación y respuesta de amenazas](office-365-ti.md), puede usar el entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en su Organización. Estos ataques simulados pueden ayudarle a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a sus resultados. Lea este artículo para obtener más información.

Vea este breve vídeo para obtener más información sobre el entrenamiento de simulación de ataques.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWMhvB]

> [!NOTE]
> El entrenamiento de simulación de ataque reemplaza la experiencia anterior de Attack Simulator v1 que estaba disponible en el Centro de cumplimiento de seguridad & en el simulador de **ataques de administración de** \> amenazas o . <https://protection.office.com/attacksimulator>

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el portal de Microsoft 365 Defender, vaya a <https://security.microsoft.com>. El entrenamiento de simulación de ataques está disponible en El **entrenamiento de simulación** de ataques **por correo electrónico y colaboración**\>. Para ir directamente al entrenamiento de simulación de ataques, use <https://security.microsoft.com/attacksimulator>.

- Para obtener más información sobre la disponibilidad del entrenamiento de simulación de ataques en diferentes suscripciones Microsoft 365, consulte [Microsoft Defender para Office 365 descripción del servicio](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Debe tener asignados permisos en **Azure Active Directory** para poder realizar los procedimientos de este artículo. En concreto, debe ser miembro de uno de los siguientes roles:
  - **Administrador global**
  - **Administrador de seguridad**
  - Administradores <sup>\*</sup>**de simulación de ataques**: cree y administre todos los aspectos de las campañas de simulación de ataques.
  - Autor <sup>\*</sup>**de carga de** ataque: cree cargas de ataque que un administrador pueda iniciar más adelante.

  <sup>\*</sup>Actualmente no se admite la adición de usuarios a este rol en el portal de Microsoft 365 Defender.

  Para obtener más información, vea [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md) o [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).

- No hay ningún cmdlet de PowerShell correspondiente para el entrenamiento de simulación de ataques.

- Los datos relacionados con la simulación de ataques y el entrenamiento se almacenan con otros datos del cliente para los servicios de Microsoft 365. Para obtener más información, consulte [Microsoft 365 ubicaciones de datos](../../enterprise/o365-data-locations.md). La simulación de ataques está disponible en las siguientes regiones: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM, CHE, NOR, ZAF, ARE y DEU.

  > [!NOTE]
  > NOR, ZAF, ARE y DEU son las últimas adiciones. Todas las características excepto la telemetría de correo electrónico notificada estarán disponibles en estas regiones. Estamos trabajando para habilitar esto y notificaremos a nuestros clientes en cuanto la telemetría de correo electrónico notificada esté disponible.

- A partir del 15 de junio de 2021, el entrenamiento de simulación de ataques está disponible en GCC. Si su organización tiene Office 365 G5 GCC o Microsoft Defender para Office 365 (Plan 2) para Government, puede usar el entrenamiento de simulación de ataques en el portal de Microsoft 365 Defender para ejecutar escenarios de ataque realistas en su organización, como se describe en este artículo. El entrenamiento de simulación de ataques aún no está disponible en GCC entornos high o DoD.

> [!NOTE]
> El entrenamiento de simulación de ataques ofrece un subconjunto de funcionalidades a los clientes de E3 como prueba. La oferta de prueba contiene la capacidad de usar una carga útil de Credential Harvest y la capacidad de seleccionar experiencias de entrenamiento de "PHISHING isa" o "phishing de mercado masivo". Ninguna otra funcionalidad forma parte de la oferta de prueba de E3.

## <a name="simulations"></a>Simulaciones

*Phishing* es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en los mensajes que parecen ser de remitentes legítimos o de confianza. *El phishing* forma parte de un subconjunto de técnicas que clasificamos como _ingeniería social_.

En El entrenamiento de simulación de ataques, hay disponibles varios tipos de técnicas de ingeniería social:

- **Recopilación de credenciales**: un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se le lleva a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino está temática para representar un sitio web conocido con el fin de generar confianza en el usuario.

- **Datos adjuntos de malware**: un atacante envía al destinatario un mensaje que contiene datos adjuntos. Cuando el destinatario abre los datos adjuntos, se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o a consolidarse aún más.

- **Vínculo en datos adjuntos**: se trata de un híbrido de una recopilación de credenciales. Un atacante envía al destinatario un mensaje que contiene una dirección URL dentro de un archivo adjunto. Cuando el destinatario abre los datos adjuntos y hace clic en la dirección URL, se le lleva a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino está temática para representar un sitio web conocido con el fin de generar confianza en el usuario.

- **Vínculo a malware**: un atacante envía al destinatario un mensaje que contiene un vínculo a un archivo adjunto en un sitio de uso compartido de archivos conocido (por ejemplo, SharePoint Online o Dropbox). Cuando el destinatario hace clic en la dirección URL, se abre el archivo adjunto y se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o a consolidarse aún más.

- **Unidad por dirección URL**: un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se le lleva a un sitio web que intenta ejecutar código en segundo plano. Este código en segundo plano intenta recopilar información sobre el destinatario o implementar código arbitrario en su dispositivo. Normalmente, el sitio web de destino es un sitio web conocido que se ha visto comprometido o un clon de un sitio web conocido. La familiaridad con el sitio web ayuda a convencer al usuario de que el vínculo es seguro para hacer clic. Esta técnica también se conoce como _ataque de agujero de riego_.

> [!NOTE]
> Compruebe la disponibilidad de la dirección URL de suplantación de identidad simulada en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad (phishing). Aunque trabajamos con muchos proveedores de reputación de direcciones URL para permitir siempre estas direcciones URL de simulación, no siempre tenemos cobertura completa (por ejemplo, Google Caja fuerte Exploración). La mayoría de los proveedores proporcionan instrucciones que le permiten permitir siempre direcciones URL específicas (por ejemplo, <https://support.google.com/chrome/a/answer/7532419>).

Las direcciones URL que usa el entrenamiento de simulación de ataques se describen en la lista siguiente:

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

### <a name="create-a-simulation"></a>Creación de una simulación

Para obtener instrucciones paso a paso sobre cómo crear y enviar una nueva simulación, consulte [Simular un ataque de suplantación de identidad (phishing).](attack-simulation-training.md)

### <a name="create-a-payload"></a>Creación de una carga

Para obtener instrucciones paso a paso sobre cómo crear una carga útil para su uso dentro de una simulación, consulte [Creación de una carga personalizada para el entrenamiento de simulación de ataques](attack-simulation-training-payloads.md).

### <a name="gaining-insights"></a>Obtención de información

Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulte [Obtención de información a través del entrenamiento de simulación de ataques](attack-simulation-training-insights.md).

> [!NOTE]
> El simulador de ataques usa vínculos de Caja fuerte en Defender para Office 365 para realizar un seguimiento seguro de los datos de clic de la dirección URL en el mensaje de carga que se envía a los destinatarios de destino de una campaña de suplantación de identidad , incluso si la configuración **Seguimiento de clics del usuario en Caja fuerte Directivas de vínculos** está desactivada.
