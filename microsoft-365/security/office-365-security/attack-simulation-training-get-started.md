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
- m365-security
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Los administradores pueden aprender a usar Entrenamiento de simulación de ataque para ejecutar ataques simulados de suplantación de identidad y contraseña en sus organizaciones de Microsoft 365 E5 o Microsoft Defender para Office 365 Plan 2.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: c80494379be5bfe93caf223061ec67df2b56ce15
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68077785"
---
# <a name="get-started-using-attack-simulation-training-in-defender-for-office-365"></a>Introducción al uso de Entrenamiento de simulación de ataque en Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

Si su organización tiene Microsoft 365 E5 o Microsoft Defender para Office 365 plan 2, que incluye [funcionalidades de investigación y respuesta de amenazas](office-365-ti.md), puede usar Entrenamiento de simulación de ataque en Microsoft 365 Defender portal para ejecutar escenarios de ataque realistas en su organización. Estos ataques simulados pueden ayudarle a identificar y encontrar usuarios vulnerables antes de que un ataque real afecte a sus resultados. Lea este artículo para obtener más información.

Vea este breve vídeo para obtener más información sobre Entrenamiento de simulación de ataque.
> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWMhvB]

> [!NOTE]
> Entrenamiento de simulación de ataque reemplaza la experiencia anterior de Attack Simulator v1 que estaba disponible en el Centro de cumplimiento de seguridad & en el **simulador de ataques** de **administración de** \> amenazas o <https://protection.office.com/attacksimulator>.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Para abrir el portal de Microsoft 365 Defender, vaya a <https://security.microsoft.com>. Entrenamiento de simulación de ataque está disponible en **Email y Entrenamiento de simulación de ataque de colaboración**\>. Para ir directamente a Entrenamiento de simulación de ataque, use <https://security.microsoft.com/attacksimulator>.

- Para obtener más información sobre la disponibilidad de Entrenamiento de simulación de ataque en distintas suscripciones de Microsoft 365, consulte [Microsoft Defender para Office 365 descripción del servicio](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

- Debe tener asignados permisos en **Azure Active Directory** para poder realizar los procedimientos de este artículo. En concreto, debe ser miembro de uno de los siguientes roles:
  - **Administrador global**
  - **Administrador de seguridad**
  - Administradores <sup>\*</sup>**de simulación de ataques**: cree y administre todos los aspectos de las campañas de simulación de ataques.
  - Autor <sup>\*</sup>**de carga de** ataque: cree cargas de ataque que un administrador pueda iniciar más adelante.

  <sup>\*</sup>Actualmente no se admite la adición de usuarios a este rol en el portal de Microsoft 365 Defender.

  Para obtener más información, vea [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md) o [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).

- No hay ningún cmdlet de PowerShell correspondiente para Entrenamiento de simulación de ataque.

- Los datos relacionados con la simulación de ataques y el entrenamiento se almacenan con otros datos de clientes para los servicios de Microsoft 365. Para obtener más información, consulte [Ubicaciones de datos de Microsoft 365](../../enterprise/o365-data-locations.md). La simulación de ataques está disponible en las siguientes regiones: NAM, APC, EUR, IND, CAN, AUS, FRA, GBR, JPN, KOR, BRA, LAM, CHE, NOR, ZAF, ARE y DEU.

  > [!NOTE]
  > NOR, ZAF, ARE y DEU son las últimas adiciones. Todas las características excepto la telemetría de correo electrónico notificada estarán disponibles en estas regiones. Estamos trabajando para habilitar esto y notificaremos a nuestros clientes en cuanto la telemetría de correo electrónico notificada esté disponible.

- A partir del 15 de junio de 2021, Entrenamiento de simulación de ataque está disponible en GCC. Si su organización tiene Office 365 GCC g5 o Microsoft Defender para Office 365 (plan 2) para la administración pública, puede usar Entrenamiento de simulación de ataque en el Microsoft 365 Defender  portal para ejecutar escenarios de ataque realistas en su organización, como se describe en este artículo. Entrenamiento de simulación de ataque aún no está disponible en entornos de GCC High o DoD.

> [!NOTE]
> Entrenamiento de simulación de ataque ofrece un subconjunto de funcionalidades a los clientes de E3 como prueba. La oferta de prueba contiene la capacidad de usar una carga útil de Credential Harvest y la capacidad de seleccionar experiencias de entrenamiento de "PHISHING isa" o "phishing de mercado masivo". Ninguna otra funcionalidad forma parte de la oferta de prueba de E3.

## <a name="simulations"></a>Simulaciones

*Phishing* es un término genérico para los ataques de correo electrónico que intentan robar información confidencial en los mensajes que parecen ser de remitentes legítimos o de confianza. *El phishing* forma parte de un subconjunto de técnicas que clasificamos como *ingeniería social*.

En Entrenamiento de simulación de ataque, hay disponibles varios tipos de técnicas de ingeniería social:

- **Recopilación de credenciales**: un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se le lleva a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino está temática para representar un sitio web conocido con el fin de generar confianza en el usuario.

- **Datos adjuntos de malware**: un atacante envía al destinatario un mensaje que contiene datos adjuntos. Cuando el destinatario abre los datos adjuntos, se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o a consolidarse aún más.

- **Vínculo en datos adjuntos**: se trata de un híbrido de una recopilación de credenciales. Un atacante envía al destinatario un mensaje que contiene una dirección URL dentro de un archivo adjunto. Cuando el destinatario abre los datos adjuntos y hace clic en la dirección URL, se le lleva a un sitio web que normalmente muestra un cuadro de diálogo que pide al usuario su nombre de usuario y contraseña. Normalmente, la página de destino está temática para representar un sitio web conocido con el fin de generar confianza en el usuario.

- **Vínculo a malware**: un atacante envía al destinatario un mensaje que contiene un vínculo a un archivo adjunto en un sitio de uso compartido de archivos conocido (por ejemplo, SharePoint Online o Dropbox). Cuando el destinatario hace clic en la dirección URL, se abre el archivo adjunto y se ejecuta código arbitrario (por ejemplo, una macro) en el dispositivo del usuario para ayudar al atacante a instalar código adicional o a consolidarse aún más.

- **Unidad por dirección URL**: un atacante envía al destinatario un mensaje que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, se le lleva a un sitio web que intenta ejecutar código en segundo plano. Este código en segundo plano intenta recopilar información sobre el destinatario o implementar código arbitrario en su dispositivo. Normalmente, el sitio web de destino es un sitio web conocido que se ha visto comprometido o un clon de un sitio web conocido. La familiaridad con el sitio web ayuda a convencer al usuario de que el vínculo es seguro para hacer clic. Esta técnica también se conoce como *ataque de agujero de riego*.

- **Concesión de consentimiento de OAuth**: un atacante crea una Aplicación de Azure malintencionada que busca obtener acceso a los datos. La aplicación envía una solicitud de correo electrónico que contiene una dirección URL. Cuando el destinatario hace clic en la dirección URL, el mecanismo de concesión de consentimiento de la aplicación solicita acceso a los datos (por ejemplo, la Bandeja de entrada del usuario).

Las direcciones URL que usa Entrenamiento de simulación de ataque se describen en la lista siguiente:

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

> [!NOTE]
> Compruebe la disponibilidad de la dirección URL de suplantación de identidad simulada en los exploradores web compatibles antes de usar la dirección URL en una campaña de suplantación de identidad (phishing). Aunque trabajamos con muchos proveedores de reputación de direcciones URL para permitir siempre estas direcciones URL de simulación, no siempre tenemos cobertura completa (por ejemplo, Navegación segura de Google). La mayoría de los proveedores proporcionan instrucciones que le permiten permitir siempre direcciones URL específicas (por ejemplo, <https://support.google.com/chrome/a/answer/7532419>).

### <a name="create-a-simulation"></a>Creación de una simulación

Para obtener instrucciones paso a paso sobre cómo crear y enviar una nueva simulación, consulte [Simular un ataque de suplantación de identidad (phishing).](attack-simulation-training.md)

### <a name="create-a-payload"></a>Creación de una carga

Para obtener instrucciones paso a paso sobre cómo crear una carga para su uso dentro de una simulación, consulte [Creación de una carga personalizada para Entrenamiento de simulación de ataque](attack-simulation-training-payloads.md#create-payloads).

### <a name="gaining-insights"></a>Obtención de información

Para obtener instrucciones paso a paso sobre cómo obtener información con los informes, consulte [Obtención de información a través de Entrenamiento de simulación de ataque](attack-simulation-training-insights.md).

> [!NOTE]
> El simulador de ataques usa vínculos seguros en Defender para Office 365 para realizar un seguimiento seguro de los datos de clic de la dirección URL en el mensaje de carga que se envía a los destinatarios de destino de una campaña de suplantación de identidad (phishing), incluso si la configuración **Seguimiento de clics del usuario en Directivas de vínculos** seguros está desactivada.
