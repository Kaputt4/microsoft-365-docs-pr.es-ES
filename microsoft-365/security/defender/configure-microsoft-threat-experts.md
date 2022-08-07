---
title: Configuración y administración de funcionalidades de Expertos en amenazas de Microsoft a través de Microsoft 365 Defender
description: Suscríbase a Microsoft Threats Experts a través de Microsoft 365 Defender para configurarlo, administrarlo y usarlo en las operaciones de seguridad diarias y en el trabajo de administración de seguridad.
keywords: Expertos en amenazas de Microsoft, servicio de búsqueda de amenazas administrada, MTE, servicio de búsqueda administrado por Microsoft
search.product: Windows 10
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: 01a88ff4f31e6a85c9fe6c52ee3968def1cc4ce1
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276380"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Configuración y administración de funcionalidades de Expertos en amenazas de Microsoft a través de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de empezar

> [!IMPORTANT]
> Antes de aplicar, asegúrese de analizar los requisitos de idoneidad para el servicio de búsqueda de amenazas administrada de notificaciones de ataque de punto de conexión con el proveedor de servicios técnicos de Microsoft y el equipo de la cuenta.

Para recibir notificaciones de ataque de punto de conexión, deberá tener Microsoft 365 Defender implementados con dispositivos inscritos. A continuación, envíe una aplicación a través del portal de M365 para las notificaciones de ataque de punto de conexión.

Póngase en contacto con el equipo de su cuenta o con el representante de Microsoft para suscribirse a Expertos en amenazas de Microsoft - Experts on Demand. Expertos a petición le permite consultar con nuestros expertos en amenazas sobre cómo proteger su organización frente a detecciones y adversarios pertinentes.

## <a name="apply-for-endpoint-attack-notifications-service"></a>Solicitud para el servicio de notificaciones de ataque de punto de conexión

Si ya tiene Pertahanan Microsoft untuk Titik Akhir y Microsoft 365 Defender, puede solicitar notificaciones de ataque de punto de conexión a través del portal de Microsoft 365 Defender.  Las notificaciones de ataque de punto de conexión le conceden información y análisis especiales para ayudar a identificar las amenazas más críticas para su organización, de modo que pueda responder a ellas rápidamente.

1. En el panel de navegación, vaya a **Configuración > puntos de conexión > General > Características avanzadas > Notificaciones de ataque de punto de conexión**.

2. Seleccione **Aplicar**.

3. Escriba su dirección de correo electrónico para que Microsoft pueda ponerse en contacto con usted sobre la aplicación.

    :::image type="content" source="../../media/mte/mte-apply.png" alt-text="Página de la aplicación Expertos en amenazas de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/mte/mte-apply.png":::
  
4. Lea la [declaración de privacidad](https://privacy.microsoft.com/en-us/privacystatement) y, a continuación, seleccione **Enviar** cuando haya terminado. Recibirá un correo electrónico de bienvenida una vez aprobada la aplicación.

    :::image type="content" source="../../media/mte/mte-applicationconfirmation.png" alt-text="Confirmación de la aplicación Expertos en amenazas de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/mte/mte-applicationconfirmation.png":::

5. Después de recibir el correo electrónico de bienvenida, comenzará automáticamente a recibir notificaciones de ataque de punto de conexión.

6. Para comprobar el estado, visite **Configuración > puntos de conexión > Características generales > avanzadas**. Una vez aprobado, el botón de alternancia **Notificación de ataque de punto de conexión** será visible **y se** activará.

## <a name="where-youll-see-the-endpoint-attack-notifications-from-microsoft-threat-experts"></a>Donde verá las notificaciones de ataque de punto de conexión de Expertos en amenazas de Microsoft

Puede recibir notificaciones de ataque de punto de conexión de Expertos en amenazas de Microsoft a través de los siguientes medios:

- Página **Incidentes** del portal de Microsoft 365 Defender
- Panel **de alertas** del portal de Microsoft 365 Defender
- [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) de alertas de OData y [API REST](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [Tabla DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) en búsqueda avanzada
- La bandeja de entrada, si decide que se le envíen notificaciones de ataque de punto de conexión por correo electrónico. Consulte [Creación de una regla de notificación por correo electrónico](#create-an-email-notification-rule) a continuación.

### <a name="create-an-email-notification-rule"></a>Creación de una regla de notificación por correo electrónico

Puede crear reglas para enviar notificaciones por correo electrónico para los destinatarios de notificaciones. Para obtener detalles  [completos](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) , consulte Configuración de notificaciones de alerta para crear, editar, eliminar o solucionar problemas de notificaciones por correo electrónico.

## <a name="view-endpoint-attack-notifications"></a>Ver notificaciones de ataque de punto de conexión

Empezará a recibir notificaciones de ataque de punto de conexión de Expertos en amenazas de Microsoft en el correo electrónico después de haber configurado el sistema para recibir notificaciones por correo electrónico.

1. Seleccione el vínculo del correo electrónico para ir al contexto de alerta correspondiente en el panel etiquetado con **expertos de Defender**.

2. En la página **Alertas** , seleccione el mismo tema de alerta que el que recibió en el correo electrónico para ver más detalles.

### <a name="filter-to-view-just-the-endpoint-attack-notifications"></a>Filtrar para ver solo las notificaciones de ataque de punto de conexión

Puede filtrar los incidentes y las alertas si solo quiere ver las notificaciones de expertos de Defender entre las muchas alertas. Para ello:

1. En el menú de navegación, vaya a **Incidentes & alertas** > **Incidentes** > seleccione el ![icono](../../media/mte/defenderexperts/filter.png) Filtro.
2. Desplácese hacia abajo hasta el campo **Etiquetas** > active la casilla **Expertos de Defender** .
3. Seleccione **Aplicar**.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Suscribirse a Expertos en amenazas de Microsoft: expertos a petición

Si ya es un cliente Pertahanan Microsoft untuk Titik Akhir, puede ponerse en contacto con su representante de Microsoft para suscribirse a Expertos en amenazas de Microsoft expertos a petición.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Consulte a un experto en amenazas de Microsoft sobre actividades sospechosas de ciberseguridad en su organización.

Puede ponerse en contacto con Expertos en amenazas de Microsoft desde el portal de Microsoft 365 Defender. Los expertos pueden ayudarle a comprender las amenazas complejas y las notificaciones de ataque de punto de conexión. Asóciate con expertos para obtener más detalles sobre alertas e incidentes, o consejos sobre el control de riesgos. Obtenga información sobre el contexto de inteligencia sobre amenazas descrito por el panel del portal.

> [!NOTE]
>
> - Actualmente no se admiten las consultas de alerta relacionadas con los datos personalizados de inteligencia sobre amenazas de la organización. Consulte con el equipo de operaciones de seguridad o respuesta a incidentes para obtener más información.
> - Debe tener el permiso **Administrar la configuración de seguridad en security center** en el portal de Microsoft 365 Defender para enviar una consulta mediante el formulario **Preguntar a expertos de Defender**.

1. Vaya a la página del portal relacionada con la información que desea investigar: por ejemplo, **Dispositivo**, **Alerta** o **Incidente**. Asegúrese de que la página del portal relacionada con la consulta esté en vista antes de enviar una solicitud de investigación.

2. En el menú superior, seleccione **? Pregunte a expertos de Defender**. Se abrirá una pantalla flotante. El encabezado indicará si tiene una suscripción de prueba o una suscripción completa Expertos en amenazas de Microsoft - Experts on Demand. El campo **Tema de investigación** ya se rellenará con el vínculo a la página correspondiente de la solicitud.

3. En el campo siguiente, proporcione suficiente información para proporcionar al Expertos en amenazas de Microsoft contexto suficiente para iniciar la investigación.

4. Escriba la dirección de correo electrónico que desea usar para que se corresponda con Expertos en amenazas de Microsoft.

> [!NOTE]
> Si desea realizar un seguimiento del estado de los casos de Expertos a petición a través de Microsoft Services Hub, póngase en contacto con el administrador de cuentas técnico.

Vea este vídeo para obtener una introducción rápida al Centro de servicios de Microsoft.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>Temas de investigación de ejemplo

### <a name="alert-information"></a>Información de alerta

- Vimos un nuevo tipo de alerta para un binario que vive fuera de la tierra. Podemos proporcionar el identificador de alerta. ¿Puede decirnos más sobre esta alerta y cómo podemos investigarla más?
- Hemos observado dos ataques similares, que intentan ejecutar scripts malintencionados de PowerShell pero generan alertas diferentes. Una es "Línea de comandos de PowerShell sospechosa" y la otra es "Se detectó un archivo malintencionado en función de la indicación proporcionada por O365". ¿Cuál es la diferencia?
- Hemos recibido una alerta impar hoy sobre un número anómalo de inicios de sesión erróneos desde el dispositivo de un usuario de alto perfil. No podemos encontrar más pruebas para estos intentos. ¿Cómo puede Microsoft 365 Defender ver estos intentos? ¿Qué tipo de inicios de sesión se están supervisando?
- ¿Puede proporcionar más contexto o información sobre la alerta "Se observó un comportamiento sospechoso por parte de una utilidad del sistema"?
- Observé una alerta titulada "Creación de una regla de reenvío/redireccionamiento". Creo que la actividad es benigna. ¿Puede decirme por qué he recibido una alerta?

### <a name="possible-device-compromise"></a>Posible peligro del dispositivo

- ¿Puede ayudar a explicar por qué vemos un mensaje o una alerta de "Proceso desconocido observado" en muchos dispositivos de nuestra organización? Agradecemos cualquier entrada para aclarar si este mensaje o alerta está relacionado con la actividad malintencionada.
- ¿Puede ayudar a validar un posible compromiso en el siguiente sistema, que data de la semana pasada? Se comporta de forma similar a una detección de malware anterior en el mismo sistema hace seis meses.

### <a name="threat-intelligence-details"></a>Detalles de inteligencia sobre amenazas

- Hemos detectado un correo electrónico de suplantación de identidad (phishing) que ha entregado un documento de Word malintencionado a un usuario. El documento provocó una serie de eventos sospechosos, que desencadenaron varias alertas para una familia de malware determinada. ¿Tiene alguna información sobre este malware? Si es así, ¿puedes enviarnos un enlace?
- Recientemente hemos visto una entrada de blog sobre una amenaza que está dirigida a nuestro sector. ¿Puede ayudarnos a comprender qué protección Microsoft 365 Defender proporciona contra este actor de amenazas?
- Recientemente hemos observado una campaña de suplantación de identidad realizada contra nuestra organización. ¿Puede decirnos si se ha dirigido específicamente a nuestra empresa o vertical?

### <a name="microsoft-threat-experts-alert-communications"></a>Comunicaciones de alerta de Expertos en amenazas de Microsoft

- ¿Puede el equipo de respuesta a incidentes ayudarnos a abordar la notificación de ataque dirigida que tenemos?
- Hemos recibido notificaciones de ataque de punto de conexión de Expertos en amenazas de Microsoft. No tenemos nuestro propio equipo de respuesta a incidentes. ¿Qué podemos hacer ahora y cómo podemos contener el incidente?
- Hemos recibido una notificación de ataque dirigida de Expertos en amenazas de Microsoft. ¿Qué datos puede proporcionarnos que podemos pasar a nuestro equipo de respuesta a incidentes?

> [!NOTE]
> Expertos en amenazas de Microsoft es un servicio administrado de búsqueda de amenazas y no un servicio de respuesta a incidentes. Sin embargo, puede interactuar con su propio equipo de respuesta a incidentes para abordar los problemas que requieren una respuesta a incidentes. Si no tiene su propio equipo de respuesta a incidentes y desea la ayuda de Microsoft, puede interactuar con el equipo de respuesta a incidentes de ciberseguridad (CIRT) de CSS. Pueden abrir una incidencia para ayudar a abordar su consulta.

## <a name="scenario"></a>Escenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Recepción de un informe de progreso sobre la consulta de búsqueda administrada

La respuesta de Expertos en amenazas de Microsoft variará según su consulta. Por lo general, recibirá una de las siguientes respuestas:

- Se necesita más información para continuar con la investigación
- Se necesita un archivo o varios ejemplos de archivo para determinar el contexto técnico
- La investigación requiere más tiempo
- La información inicial fue suficiente para concluir la investigación

Si un experto solicita más información o ejemplos de archivos, es fundamental responder rápidamente para mantener la investigación en movimiento.

## <a name="to-proactively-hunt-threats-across-endpoints-office-365-cloud-applications-and-identity-refer-to"></a>Para buscar amenazas de forma proactiva entre puntos de conexión, Office 365, aplicaciones en la nube e identidad, consulte: 

- [Introducción a expertos de Microsoft Defender para la búsqueda](defender-experts-for-hunting.md)
