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
ms.author: v-maave
author: martyav
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.topic: article
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: cd8f7e65c409138d6404a734b098e70e6d419cbb
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64667282"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Configuración y administración de funcionalidades de Expertos en amenazas de Microsoft a través de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de empezar

> [!IMPORTANT]
> Antes de aplicar, asegúrese de analizar los requisitos de idoneidad para el servicio de búsqueda de amenazas administrada Expertos en amenazas de Microsoft: Notificaciones de ataque dirigidas con el proveedor de servicios técnicos de Microsoft y el equipo de cuentas.

Para recibir notificaciones de ataque dirigidas, deberá tener Microsoft 365 Defender implementados con dispositivos inscritos. A continuación, envíe una aplicación a través del portal de M365 para Expertos en amenazas de Microsoft: notificaciones de ataque dirigidas.

Póngase en contacto con el equipo de su cuenta o con el representante de Microsoft para suscribirse a Expertos en amenazas de Microsoft - Experts on Demand. Expertos a petición le permite consultar con nuestros expertos en amenazas sobre cómo proteger su organización frente a detecciones y adversarios pertinentes.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Solicitud para Expertos en amenazas de Microsoft: servicio de notificaciones de ataque dirigidas

Si ya tiene Microsoft Defender para punto de conexión y Microsoft 365 Defender, puede solicitar Expertos en amenazas de Microsoft: notificaciones de ataque dirigidas a través de sus Microsoft 365 Defender  Portal.  Las notificaciones de ataque dirigidas le conceden información y análisis especiales para ayudar a identificar las amenazas más críticas para su organización, de modo que pueda responder a ellas rápidamente.

1. En el panel de navegación, vaya a **Configuración > Puntos de conexión > General > Características avanzadas > Expertos en amenazas de Microsoft - Notificaciones de ataque dirigidas**.

2. Seleccione **Aplicar**.

    :::image type="content" source="../../media/mte/mte-collaboratewithmte.png" alt-text="Página de configuración de Expertos en amenazas de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/mte/mte-collaboratewithmte.png":::

3. Escriba su nombre y dirección de correo electrónico para que Microsoft pueda ponerse en contacto con usted sobre la aplicación.

    :::image type="content" source="../../media/mte/mte-apply.png" alt-text="Página de la aplicación Expertos en amenazas de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/mte/mte-apply.png":::
  
4. Lea la [declaración de privacidad](https://privacy.microsoft.com/en-us/privacystatement) y, a continuación, seleccione **Enviar** cuando haya terminado. Recibirá un correo electrónico de bienvenida una vez aprobada la aplicación.

    :::image type="content" source="../../media/mte/mte-applicationconfirmation.png" alt-text="Confirmación de la aplicación Expertos en amenazas de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/mte/mte-applicationconfirmation.png":::

5. Después de recibir el correo electrónico de bienvenida, comenzará a recibir automáticamente notificaciones de ataque dirigidas.

6. Para comprobar el estado, visite **Configuración > Puntos de conexión > Características generales > avanzadas**. Una vez aprobado, el botón de alternancia **Expertos en amenazas de Microsoft - Notificación de ataque** dirigida será visible **y se** activará.

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Donde verá las notificaciones de ataque dirigidas desde Expertos en amenazas de Microsoft

Puede recibir una notificación de ataque dirigida desde Expertos en amenazas de Microsoft a través de los siguientes medios:

- Página **Incidentes** del portal de Microsoft 365 Defender
- Panel **de alertas** del portal de Microsoft 365 Defender
- [API](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) de alertas de OData y [API REST](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [Tabla DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) en búsqueda avanzada
- Su bandeja de entrada, si decide que se le envíen notificaciones de ataque dirigidas por correo electrónico. Consulte [Creación de una regla de notificación por correo electrónico](#create-an-email-notification-rule) a continuación.

### <a name="create-an-email-notification-rule"></a>Creación de una regla de notificación por correo electrónico

Puede crear reglas para enviar notificaciones por correo electrónico para los destinatarios de notificaciones. Para obtener detalles  [completos](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) , consulte Configuración de notificaciones de alerta para crear, editar, eliminar o solucionar problemas de notificaciones por correo electrónico.

## <a name="view-targeted-attack-notifications"></a>Visualización de notificaciones de ataque dirigidas

Empezará a recibir una notificación de ataque dirigida desde Expertos en amenazas de Microsoft en el correo electrónico después de haber configurado el sistema para recibir una notificación por correo electrónico.

1. Seleccione el vínculo del correo electrónico para ir al contexto de alerta correspondiente en el panel etiquetado con **expertos en amenazas**.

2. En la página **Alertas** , seleccione el mismo tema de alerta que el que recibió en el correo electrónico para ver más detalles.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Suscribirse a Expertos en amenazas de Microsoft: expertos a petición

Si ya es un cliente Microsoft Defender para punto de conexión, puede ponerse en contacto con su representante de Microsoft para suscribirse a Expertos en amenazas de Microsoft - Expertos a petición.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Consulte a un experto en amenazas de Microsoft sobre actividades sospechosas de ciberseguridad en su organización.

Puede ponerse en contacto con Expertos en amenazas de Microsoft desde el portal de Microsoft 365 Defender. Los expertos pueden ayudarle a comprender las amenazas complejas y las notificaciones de ataque dirigidas. Asóciate con expertos para obtener más detalles sobre alertas e incidentes, o consejos sobre el control de riesgos. Obtenga información sobre el contexto de inteligencia sobre amenazas descrito por el panel del portal.

> [!NOTE]
>
> - Actualmente no se admiten las consultas de alerta relacionadas con los datos personalizados de inteligencia sobre amenazas de la organización. Consulte con el equipo de operaciones de seguridad o respuesta a incidentes para obtener más información.
> - Debe tener el permiso **Administrar la configuración de seguridad en security center** en el portal de Microsoft 365 Defender para enviar una consulta mediante el formulario **Consultar a un experto en amenazas**.

1. Vaya a la página del portal relacionada con la información que desea investigar: por ejemplo, **Dispositivo**, **Alerta** o **Incidente**. Asegúrese de que la página del portal relacionada con la consulta esté en vista antes de enviar una solicitud de investigación.

2. En el menú superior, seleccione **? Consulte a un experto en amenazas**.

    :::image type="content" source="../../media/mte/incidents-action-mte-highlighted.png" alt-text="El Expertos en amenazas de Microsoft Expertos a petición del menú del portal de Microsoft 365 Defender" lightbox="../../media/mte/incidents-action-mte-highlighted.png":::

    Se abrirá una pantalla flotante.

    El encabezado indicará si está en una suscripción de prueba o en una suscripción completa Expertos en amenazas de Microsoft: Expertos a petición.

    :::image type="content" source="../../media/mte/mte-trial.png" alt-text="Pantalla de suscripción de prueba de expertos a petición de Expertos en amenazas de Microsoft en el portal de Microsoft 365 Defender" lightbox="../../media/mte/mte-trial.png":::

    El campo **Tema de investigación** ya se rellenará con el vínculo a la página correspondiente de la solicitud.

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

### <a name="possible-machine-compromise"></a>Posible peligro de máquina

- ¿Puede ayudar a explicar por qué vemos un mensaje o una alerta de "Proceso desconocido observado" en muchos dispositivos de nuestra organización? Agradecemos cualquier entrada para aclarar si este mensaje o alerta está relacionado con la actividad malintencionada.
- ¿Puede ayudar a validar un posible compromiso en el siguiente sistema, que data de la semana pasada? Se comporta de forma similar a una detección de malware anterior en el mismo sistema hace seis meses.

### <a name="threat-intelligence-details"></a>Detalles de inteligencia sobre amenazas

- Hemos detectado un correo electrónico de suplantación de identidad (phishing) que ha entregado un documento de Word malintencionado a un usuario. El documento provocó una serie de eventos sospechosos, que desencadenaron varias alertas para una familia de malware determinada. ¿Tiene alguna información sobre este malware? Si es así, ¿puedes enviarnos un enlace?
- Recientemente hemos visto una entrada de blog sobre una amenaza que está dirigida a nuestro sector. ¿Puede ayudarnos a comprender qué protección Microsoft 365 Defender proporciona contra este actor de amenazas?
- Recientemente hemos observado una campaña de suplantación de identidad realizada contra nuestra organización. ¿Puede decirnos si se ha dirigido específicamente a nuestra empresa o vertical?

### <a name="microsoft-threat-experts-alert-communications"></a>Comunicaciones de alerta de Expertos en amenazas de Microsoft

- ¿Puede el equipo de respuesta a incidentes ayudarnos a abordar la notificación de ataque dirigida que tenemos?
- Hemos recibido esta notificación de ataque dirigida de Expertos en amenazas de Microsoft. No tenemos nuestro propio equipo de respuesta a incidentes. ¿Qué podemos hacer ahora y cómo podemos contener el incidente?
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

## <a name="see-also"></a>Vea también

- [Información general sobre Expertos en amenazas de Microsoft](microsoft-threat-experts.md)
