---
title: Expertos a petición
ms.reviewer: ''
description: Puede asociarse con expertos de Microsoft Defender que pueden participar directamente desde el portal de Microsoft 365 Defender para su respuesta
keywords: Pregunte a expertos de Defender, expertos a petición, búsqueda de amenazas administrada, servicio de detección y respuesta administrada (MDR), MTE, Expertos en amenazas de Microsoft, notificación de ataque de punto de conexión, notificación de ataque de punto de conexión
search.product: Windows 10
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: vpattnaik
author: vpattnai
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: e24d5e513d4f5200a33d9cbd6d407353ac9215ca
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68663113"
---
# <a name="ask-defender-experts"></a>Pregunte a expertos de Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

> [!NOTE]
> A partir de agosto de 2022, la opción Expertos a petición para **consultar a un experto en amenazas** se ha cambiado a **Preguntar a expertos de Defender**. Esta documentación sigue estando aquí para admitir el servicio de Expertos en amenazas de Microsoft heredado; sin embargo, si está interesado en explorar el servicio más allá de la licencia actual, consulte [Expertos de detección de Microsoft Defender](/microsoft-365/security/defender/defender-experts-for-hunting). Expertos de detección de Microsoft Defender suscripción incluye [Expertos a petición](/microsoft-365/security/defender/onboarding-defender-experts-for-hunting).

Los clientes pueden interactuar con nuestros expertos en seguridad directamente desde Microsoft 365 Defender portal para obtener su respuesta. Los expertos proporcionan información necesaria para comprender mejor las amenazas complejas que afectan a su organización, desde consultas de alertas, dispositivos potencialmente comprometidos, causa principal de una conexión de red sospechosa, hasta más inteligencia sobre amenazas con respecto a las campañas de amenazas persistentes avanzadas en curso. Con esta funcionalidad, puede:

- Obtenga más aclaraciones sobre las alertas, incluida la causa principal o el ámbito del incidente.
- Obtenga claridad sobre el comportamiento sospechoso del dispositivo y los pasos siguientes si se enfrenta a un atacante avanzado.
- Determinación del riesgo y la protección con respecto a los actores de amenazas, las campañas o las técnicas de atacantes emergentes

> [!NOTE]
> Expertos a petición no es un servicio de respuesta a incidentes de seguridad. Está pensado para proporcionar una mejor comprensión de las amenazas complejas que afectan a su organización. Póngase en contacto con su propio equipo de respuesta a incidentes de seguridad para solucionar problemas urgentes de respuesta a incidentes de seguridad. Si no tiene su propio equipo de respuesta a incidentes de seguridad y desea la ayuda de Microsoft, cree una solicitud de soporte técnico en el [Centro de servicios Premier](/services-hub/).

## <a name="ask-defender-experts-about-suspicious-cybersecurity-activities-in-your-organization"></a>Pregunte a expertos de Defender sobre actividades sospechosas de ciberseguridad en su organización

Puede asociarse con expertos de Microsoft Defender que pueden participar directamente desde el portal de Microsoft 365 Defender para su respuesta. Los expertos proporcionan información para comprender mejor las amenazas complejas, las notificaciones de expertos de defender que recibe o si necesita más información sobre las alertas, un dispositivo potencialmente en peligro o un contexto de inteligencia sobre amenazas que vea en el panel del portal.

> [!NOTE]
>
> - Actualmente no se admiten las consultas de alerta relacionadas con los datos personalizados de inteligencia sobre amenazas de la organización. Consulte a su equipo de operaciones de seguridad o respuesta a incidentes para obtener más información.
> - Debe tener el permiso **[Administrar configuración de seguridad](../defender-endpoint/user-roles.md)** en el portal de Microsoft 365 Defender para poder enviar la consulta **Preguntar a expertos de Defender**.

1. Vaya a la página del portal con la información pertinente que le gustaría investigar, por ejemplo, la página **Incidente** . Asegúrese de que la página de la alerta o dispositivo pertinente esté en vista antes de enviar una solicitud de investigación.

2. En el menú superior derecho, haga clic en **?** . A continuación, seleccione **Preguntar a expertos de Defender.**

El campo **Tema de consulta** se rellena previamente con el vínculo a la página correspondiente para la solicitud de investigación. Por ejemplo, un vínculo a la página de detalles del dispositivo, alerta o incidente en la que se encontraba cuando realizó la solicitud.

3. En el siguiente campo, proporcione suficiente información para proporcionar a Microsoft Defender Expertos suficiente contexto para iniciar la investigación.

4. Escriba la dirección de correo electrónico que desea usar para que se corresponda con Microsoft Defender Experts. Asegúrese de que la dirección de correo electrónico es para una cuenta con un buzón adjunto. Si no es así, incluya una dirección de correo electrónico con un buzón adjunto.

> [!NOTE]
> Si desea realizar un seguimiento del estado de los casos de Expertos a petición a través de Microsoft Services Hub, póngase en contacto con el Administrador de cuentas de éxito del cliente.

Vea este vídeo para obtener una introducción rápida al Centro de servicios de Microsoft.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics-that-you-can-ask-defender-experts"></a>Temas de investigación de ejemplo que puede consultar a expertos de Defender

### <a name="alert-information"></a>Información de alerta

- Vemos un nuevo tipo de alerta para un binario que se encuentra fuera de la tierra: [AlertID]. ¿Puede decirnos algo más sobre esta alerta y cómo podemos investigar más?
- Hemos observado dos ataques similares, que intentan ejecutar scripts malintencionados de PowerShell pero generan alertas diferentes. Una es "Línea de comandos de PowerShell sospechosa" y la otra es "Se detectó un archivo malintencionado en función de la indicación proporcionada por O365". ¿Cuál es la diferencia?
- Recibo una alerta impar hoy por el número anómalo de inicios de sesión erróneos desde el dispositivo de un usuario de alto perfil. No puedo encontrar más pruebas en torno a estos intentos de inicio de sesión. ¿Cómo puede Defender para punto de conexión ver estos intentos? ¿Qué tipo de inicios de sesión se están supervisando?
- Puede proporcionar más contexto o conclusiones sobre esta alerta: "Se observó un comportamiento sospechoso por parte de una utilidad del sistema".

### <a name="possible-device-compromise"></a>Posible peligro del dispositivo

- ¿Puede ayudar a responder por qué vemos "Proceso desconocido observado?" Este mensaje o alerta se ve con frecuencia en muchos dispositivos. Agradecemos cualquier entrada para aclarar si este mensaje o alerta está relacionado con la actividad malintencionada.
- ¿Puede ayudar a validar un posible riesgo en el siguiente sistema en [fecha] con comportamientos similares a los de la detección de malware anterior [nombre de malware] en el mismo sistema en [mes]?

### <a name="threat-intelligence-details"></a>Detalles de inteligencia sobre amenazas

- Hemos detectado un correo electrónico de suplantación de identidad (phishing) que ha entregado un documento de Word malintencionado a un usuario. El documento malintencionado de Word produjo una serie de eventos sospechosos, que desencadenaron varias alertas de notificaciones de ataque de punto de conexión para el malware [nombre de malware]. ¿Tiene alguna información sobre este malware? Si es así, ¿puedes enviarme un enlace?
- Recientemente vi una entrada [referencia de redes sociales, por ejemplo, Twitter o blog] sobre una amenaza que está dirigida a mi sector. ¿Puede ayudarme a comprender qué protección proporciona Defender para punto de conexión frente a este actor de amenazas?

### <a name="defender-experts-alert-communications"></a>Comunicaciones de alerta de expertos de Defender

- ¿Puede el equipo de respuesta a incidentes ayudarnos a abordar las notificaciones de ataque de punto de conexión que tenemos?
- He recibido estas notificaciones de ataque de punto de conexión de expertos en seguridad de Microsoft. No tenemos nuestro propio equipo de respuesta a incidentes. ¿Qué podemos hacer ahora y cómo podemos contener el incidente?
- He recibido notificaciones de ataque de punto de conexión de expertos de Microsoft Defender. ¿Qué datos puede proporcionarnos que podemos pasar a nuestro equipo de respuesta a incidentes?

  > [!NOTE]
  > Expertos a petición es un servicio administrado de búsqueda de ciberseguridad y no un servicio de respuesta a incidentes. Sin embargo, puede interactuar con su propio equipo de respuesta a incidentes para abordar los problemas que requieren una respuesta a incidentes. Si no tiene su propio equipo de respuesta a incidentes y desea la ayuda de Microsoft, puede interactuar con el equipo de respuesta a incidentes de ciberseguridad (CIRT) de CSS. Pueden abrir una incidencia para ayudar a abordar su consulta.

## <a name="scenario"></a>Escenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Recepción de un informe de progreso sobre la consulta de búsqueda administrada

La respuesta de Microsoft Defender Experts varía según su consulta. Le enviarán por correo electrónico un informe de progreso sobre la consulta **de expertos de Ask Defender** en un plazo de dos días para comunicar el estado de la investigación de las siguientes categorías:

- Se necesita más información para continuar con la investigación
- Se necesita un archivo o varios ejemplos de archivo para determinar el contexto técnico
- La investigación requiere más tiempo
- La información inicial fue suficiente para concluir la investigación

Es fundamental responder rápidamente para mantener la investigación en movimiento.

## <a name="next-steps"></a>Pasos siguientes
- Para buscar amenazas de forma proactiva entre puntos de conexión, consulte [Notificación de ataque de punto de conexión](../defender-endpoint/endpoint-attack-notifications.md).
- Para buscar amenazas de forma proactiva entre puntos de conexión, Office 365, aplicaciones en la nube e identidad, consulte [Expertos de detección de Microsoft Defender](../defender/defender-experts-for-hunting.md).

