---
title: Configurar y administrar las Expertos en amenazas de Microsoft a través de Microsoft 365 Defender
description: Suscríbete a Microsoft Threats Experts Microsoft 365 Defender para configurarlo, administrarlo y usarlo en el trabajo diario de administración de seguridad y operaciones de seguridad.
keywords: Expertos en amenazas de Microsoft, servicio de búsqueda de amenazas administradas, MTE, servicio de búsqueda administrada de Microsoft
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
ms.openlocfilehash: b62f847a1a8b7bef15c33f97d5d64a9ec58dd7cb
ms.sourcegitcommit: bd43f08b4719ba984ea6712227508d4a281148cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2021
ms.locfileid: "61041954"
---
# <a name="configure-and-manage-microsoft-threat-experts-capabilities-through-microsoft-365-defender"></a>Configurar y administrar las Expertos en amenazas de Microsoft a través de Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Prerelease](../includes/prerelease.md)]

## <a name="before-you-begin"></a>Antes de empezar

> [!IMPORTANT]
> Antes de aplicar, asegúrese de analizar los requisitos de elegibilidad para el servicio de búsqueda de amenazas administradas Expertos en amenazas de Microsoft– Targeted Attack Notifications con el proveedor de servicio técnico de Microsoft y el equipo de cuenta.

Para recibir notificaciones de ataques dirigidos, deberás tener Microsoft 365 Defender con dispositivos inscritos. A continuación, envíe una aplicación a través del portal M365 para Expertos en amenazas de Microsoft- Notificaciones de ataque dirigidas.

Póngase en contacto con su equipo de cuenta o representante de Microsoft para suscribirse a Expertos en amenazas de Microsoft : Expertos a petición. Expertos a petición le permite consultar con nuestros expertos en amenazas sobre cómo proteger su organización de detecciones y adversarias relevantes.

## <a name="apply-for-microsoft-threat-experts---targeted-attack-notifications-service"></a>Aplicar para Expertos en amenazas de Microsoft: servicio de notificaciones de ataques dirigidos

Si ya tienes Microsoft Defender para endpoint y Microsoft 365 Defender, puedes solicitar Expertos en amenazas de Microsoft notificaciones de ataque dirigidas a través de su portal Microsoft 365 Defender web.  Las notificaciones de ataques dirigidos le proporcionan información y análisis especiales que le ayudarán a identificar las amenazas más críticas para su organización, de modo que pueda responder a ellas rápidamente.

1. En el panel de navegación, vaya **a Configuración > Endpoints > General > Advanced features > Expertos en amenazas de Microsoft - Targeted Attack Notifications**.

2. Seleccione **Aplicar**.

    ![Imagen de Expertos en amenazas de Microsoft configuración.](../../media/mte/mte-collaboratewithmte.png)

3. Escriba su nombre y dirección de correo electrónico para que Microsoft pueda ponerse en contacto con usted sobre su aplicación.

    ![Imagen de Expertos en amenazas de Microsoft aplicación.](../../media/mte/mte-apply.png)

4. Lea la [declaración de privacidad](https://privacy.microsoft.com/en-us/privacystatement)y, a continuación, seleccione **Enviar** cuando haya terminado. Recibirá un correo electrónico de bienvenida una vez que se apruebe la aplicación.

    ![Imagen de la Expertos en amenazas de Microsoft de la aplicación.](../../media/mte/mte-applicationconfirmation.png)

5. Después de recibir el correo electrónico de bienvenida, empezarás a recibir automáticamente notificaciones de ataques dirigidos.

6. Para comprobar su estado, visite **Configuración > Endpoints > General > Advanced features**. Una vez aprobado, el **botón Expertos en amenazas de Microsoft- Activación de** notificación de ataque dirigido estará visible y se **activará**.

## <a name="where-youll-see-the-targeted-attack-notifications-from-microsoft-threat-experts"></a>Donde verás las notificaciones de ataques dirigidos desde Expertos en amenazas de Microsoft

Puedes recibir una notificación de ataque dirigida desde Expertos en amenazas de Microsoft a través de los siguientes medios:

- Página Microsoft 365 Defender incidentes **del** portal
- Panel de Microsoft 365 Defender de **alertas del** portal de aplicaciones
- API de alerta [de](/windows/security/threat-protection/microsoft-defender-atp/get-alerts) OData y API de [REST](/windows/security/threat-protection/microsoft-defender-atp/pull-alerts-using-rest-api)
- [Tabla DeviceAlertEvents](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-devicealertevents-table) en búsqueda avanzada
- La bandeja de entrada, si decides enviarte notificaciones de ataque dirigidas por correo electrónico. Consulta [Crear una regla de notificación de correo electrónico a](#create-an-email-notification-rule) continuación.

### <a name="create-an-email-notification-rule"></a>Crear una regla de notificación de correo electrónico

Puede crear reglas para enviar notificaciones por correo electrónico para los destinatarios de notificaciones. Para obtener información completa, consulta  [Configurar las notificaciones de alerta para](/windows/security/threat-protection/microsoft-defender-atp/configure-email-notifications) crear, editar, eliminar o solucionar problemas de notificación de correo electrónico.

## <a name="view-targeted-attack-notifications"></a>Ver notificaciones de ataques dirigidos

Empezarás a recibir una notificación de ataque dirigida Expertos en amenazas de Microsoft en tu correo electrónico después de configurar el sistema para recibir una notificación por correo electrónico.

1. Seleccione el vínculo del correo electrónico para ir al contexto de alerta correspondiente en el panel etiquetado con **expertos en amenazas.**

2. En la **página** Alertas, seleccione el mismo tema de alerta que el que recibió en el correo electrónico, para ver más detalles.

## <a name="subscribe-to-microsoft-threat-experts---experts-on-demand"></a>Suscribirse a Expertos en amenazas de Microsoft: expertos a petición

Si ya eres cliente de Microsoft Defender para Endpoint, puedes ponerse en contacto con tu representante de Microsoft para suscribirte a Expertos en amenazas de Microsoft - Expertos a petición.

## <a name="consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization"></a>Consulte a un experto en amenazas de Microsoft sobre actividades de ciberseguridad sospechosas en su organización

Puede ponerse en contacto Expertos en amenazas de Microsoft desde dentro del portal Microsoft 365 Defender web. Los expertos pueden ayudarle a comprender las amenazas complejas y las notificaciones de ataque dirigidas. Asociate con expertos para obtener más detalles sobre alertas e incidentes, o consejos sobre cómo controlar el riesgo. Obtenga información sobre el contexto de inteligencia de amenazas descrito por el panel del portal.

> [!NOTE]
>
> - Actualmente, no se admiten las consultas de alerta relacionadas con los datos de inteligencia de amenazas personalizados de la organización. Consulte con el equipo de operaciones de seguridad o respuesta a incidentes para obtener más información.
> - Debe tener el  permiso Administrar la configuración de seguridad en el Centro de seguridad en el portal de Microsoft 365 Defender para enviar una consulta a través del formulario **Consultar a un** experto en amenazas.

1. Vaya a la página del portal relacionada con la información que le gustaría investigar: por ejemplo, **Device**, **Alert** o **Incident**. Asegúrese de que la página del portal relacionada con la consulta esté en vista antes de enviar una solicitud de investigación.

2. En el menú superior, seleccione **? Consulte a un experto en amenazas**.

    ![Imagen de Expertos en amenazas de Microsoft expertos a petición del menú.](../../media/mte/incidents-action-mte-highlighted.png)

    Se abrirá una pantalla desplegable.

    El encabezado indicará si está en una suscripción de prueba o una suscripción completa Expertos en amenazas de Microsoft: suscripción a petición de expertos.

    ![Imagen de la Expertos en amenazas de Microsoft de suscripción de prueba de expertos a petición.](../../media/mte/mte-trial.png)

    El **campo Tema** investigación ya se rellenará con el vínculo a la página correspondiente para la solicitud.

3. En el siguiente campo, proporcione información suficiente para proporcionar al Expertos en amenazas de Microsoft suficiente contexto para iniciar la investigación.

4. Escriba la dirección de correo electrónico que desea usar para que se corresponda con Expertos en amenazas de Microsoft.

> [!NOTE]
> Si desea realizar un seguimiento del estado de los casos de Expertos a petición a través del Centro de servicios de Microsoft, comunicarse con el administrador técnico de cuentas.

Vea este vídeo para obtener una introducción rápida al Centro de servicios de Microsoft.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4pk9f]

## <a name="sample-investigation-topics"></a>Temas de investigación de ejemplo

### <a name="alert-information"></a>Información de alerta

- Vimos un nuevo tipo de alerta para un binario vivo fuera de la tierra. Podemos proporcionar el identificador de alerta. ¿Puede decirnos más acerca de esta alerta y cómo podemos investigarla aún más?
- Hemos observado dos ataques similares, que intentan ejecutar scripts de PowerShell malintencionados pero generan alertas diferentes. Una es "Línea de comandos sospechosa de PowerShell" y la otra es "Se detectó un archivo malintencionado en función de la indicación proporcionada por O365". ¿Cuál es la diferencia?
- Recibimos una alerta impar hoy sobre un número anormal de inicios de sesión con errores desde el dispositivo de un usuario de perfil alto. No podemos encontrar más pruebas para estos intentos. ¿Cómo Microsoft 365 Defender ver estos intentos? ¿Qué tipo de inicios de sesión se están supervisando?
- ¿Puede dar más contexto o información sobre la alerta: "Se observó un comportamiento sospechoso por parte de una utilidad del sistema"?
- Observé una alerta titulada "Creación de reglas de reenvío/redireccionamiento". Creo que la actividad es benigna. ¿Me puede decir por qué recibí una alerta?

### <a name="possible-machine-compromise"></a>Posible peligro de máquina

- ¿Puede explicar por qué vemos un mensaje o alerta de "Proceso desconocido observado" en muchos dispositivos de nuestra organización? Agradecemos cualquier entrada para aclarar si este mensaje o alerta está relacionado con actividad malintencionada.
- ¿Puede ayudar a validar un posible compromiso en el siguiente sistema, que data de la semana pasada? Se comporta de forma similar a una detección de malware anterior en el mismo sistema hace seis meses.

### <a name="threat-intelligence-details"></a>Detalles de inteligencia de amenazas

- Se detectó un correo electrónico de suplantación de identidad (phishing) que entregaba un documento malintencionado de Word a un usuario. El documento provocó una serie de eventos sospechosos, que desencadenaron varias alertas para una familia de malware determinada. ¿Tiene información sobre este malware? Si es así, ¿puede enviarnos un vínculo?
- Recientemente vimos una entrada de blog sobre una amenaza dirigida a nuestra industria. ¿Puede ayudarnos a comprender qué protección Microsoft 365 Defender proporciona contra este actor de amenazas?
- Recientemente hemos observado una campaña de suplantación de identidad realizada en nuestra organización. ¿Puede decirnos si se ha dirigido específicamente a nuestra empresa o vertical?

### <a name="microsoft-threat-experts-alert-communications"></a>Expertos en amenazas de Microsoft de alertas

- ¿Puede su equipo de respuesta a incidentes ayudarnos a solucionar la notificación de ataque dirigida que tenemos?
- Recibimos esta notificación de ataque dirigido desde Expertos en amenazas de Microsoft. No tenemos nuestro propio equipo de respuesta a incidentes. ¿Qué podemos hacer ahora y cómo podemos contener el incidente?
- Recibimos una notificación de ataque dirigida de Expertos en amenazas de Microsoft. ¿Qué datos nos puede proporcionar que podamos transmitir a nuestro equipo de respuesta a incidentes?

> [!NOTE]
> Expertos en amenazas de Microsoft es un servicio administrado de búsqueda de amenazas y no un servicio de respuesta a incidentes. Sin embargo, puede interactuar con su propio equipo de respuesta a incidentes para solucionar problemas que requieren una respuesta a incidentes. Si no tienes tu propio equipo de respuesta a incidentes y quieres la ayuda de Microsoft, puedes interactuar con el Equipo de respuesta a incidentes de ciberseguridad (CIRT) de CSS. Pueden abrir un vale para ayudar a resolver su consulta.

## <a name="scenario"></a>Escenario

### <a name="receive-a-progress-report-about-your-managed-hunting-inquiry"></a>Recibir un informe de progreso sobre la consulta de búsqueda administrada

La respuesta de Expertos en amenazas de Microsoft variará según la consulta. Por lo general, recibirá una de las siguientes respuestas:

- Se necesita más información para continuar con la investigación
- Se necesita un archivo o varios ejemplos de archivos para determinar el contexto técnico
- La investigación requiere más tiempo
- La información inicial era suficiente para concluir la investigación

Si un experto solicita más información o muestras de archivos, es fundamental responder rápidamente para mantener la investigación en movimiento.

## <a name="see-also"></a>Consulte también

- [Información general sobre Expertos en amenazas de Microsoft](microsoft-threat-experts.md)
