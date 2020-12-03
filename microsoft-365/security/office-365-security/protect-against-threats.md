---
title: Protección contra amenazas
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre la protección contra amenazas en Microsoft 365 y configurar cómo usarla para su organización.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 98a20c8805ff9eb735ca880cfc24a0acf9698b3e
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561212"
---
# <a name="protect-against-threats"></a>Protección contra amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Esta es una guía de inicio rápido que rompe la configuración de defender para Office 365 en fragmentos. Si no está familiarizado con las características de protección contra amenazas de Office 365, pero no sabe dónde empezar, o si desea obtener mejores resultados, use esta guía como una lista de comprobación y un *punto de partida*.

> [!IMPORTANT]
> **Se incluye la configuración recomendada inicial para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas de su organización**. Espere unos 30 minutos para que las directivas o los cambios funcionen a través del centro de proceso de trabajo.

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>Suscripciones

Las características de protección contra amenazas se incluyen en *todas las* suscripciones de Microsoft u Office 365; sin embargo, algunas suscripciones tienen características avanzadas. En la tabla siguiente se enumeran las características de protección que se incluyen en este artículo junto con los requisitos mínimos de suscripción.

> [!TIP]
> Tenga en cuenta que, aparte de las instrucciones para activar la auditoría, *los pasos* inician anti-malware, anti-phishing y anti-spam, que están marcados como parte de Office 365 Exchange Online Protection (**EOP**). Esto puede parecer extraño en un artículo de defender para Office 365 hasta que recuerde (**defender para office 365**) contiene y se basa en EOP.

****

|Tipo de protección|Requisito de suscripción|
|---|---|
|Registro de auditoría (para fines de informes)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protección antimalware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protección contra phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra correo no deseado|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Purgado automático de cero horas (para correo electrónico)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección frente a direcciones URL y archivos malintencionados en correo electrónico y documentos de Office (vínculos seguros y datos adjuntos seguros)|[Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Activar ATP para cargas de trabajo de SharePoint, OneDrive y Microsoft Teams|[Defender para Office 365 ](atp-for-spo-odb-and-teams.md)|
|Protección contra suplantación de identidad avanzada|[Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roles y permisos

Para configurar defender para las directivas de Office 365, debe tener asignado un rol apropiado en el [centro de seguridad & cumplimiento](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Eche un vistazo a la tabla siguiente para obtener las funciones que pueden realizar estas acciones.

****

|Rol o grupo de roles|Dónde obtener más información|
|---|---|
|administrador global|[Acerca de los roles de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Administrador de seguridad|[Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización en Exchange Online|[Permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>y<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Para obtener más información, consulte [permisos en el centro de seguridad & cumplimiento](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Antes de empezar, active el registro de auditoría para los informes y la investigación

Inicie el registro de auditoría anticipadamente. Necesitará la auditoría para estar **activada** para algunos de los pasos que se indican a continuación. El registro de auditoría está disponible en las suscripciones que incluyen [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para poder ver los datos de los informes de protección contra amenazas, como el [Panel de seguridad](security-dashboard.md), los informes de [seguridad de correo electrónico](view-email-security-reports.md)y el [Explorador](threat-explorer.md), el registro de auditoría debe estar *activado*. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Parte 1: protección contra malware

La [protección contra malware](anti-malware-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija Directiva de **Administración de amenazas**  >  **Policy**  >  **contra malware**.

2. Haga doble clic en la directiva **predeterminada** y, a continuación, elija **configuración**.

3. Especifique las siguientes opciones de configuración:

    - En la sección **respuesta de detección de malware** , mantenga el valor predeterminado de **no**.

    - En la sección **filtro de tipos de datos adjuntos comunes** , elija **activado**.

4. Haga clic en **Guardar**.

Para obtener más información acerca de las opciones de directiva antimalware, vea [Configure anti-malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Parte 2: protección contra la suplantación de identidad

[La protección contra suplantación de identidad (phishing)](anti-phishing-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Protección contra suplantación de identidad avanzada disponible en [defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

El siguiente procedimiento describe cómo configurar una directiva contra la suplantación de identidad en Microsoft defender para Office 365. Los pasos son similares a la configuración de una directiva contra la suplantación de identidad en EOP.

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija la Directiva de **Administración de amenazas**  >  **Policy**  >  **ATP anti-phishing**.

2. Haga clic en **directiva predeterminada**.

3. En la sección **suplantación** , haga clic en **Editar** y, a continuación, especifique las siguientes opciones de configuración:

   - En la pestaña **Agregar usuarios a proteger** *, active la* protección. A continuación, agregue usuarios, como los miembros del Consejo de su organización, su CEO, director financiero y otros líderes senior. (Puede escribir una dirección de correo electrónico individual o hacer clic en para mostrar una lista).

   - En la pestaña **Agregar dominios para proteger** , Active **incluir automáticamente los dominios que posea**. Si tiene dominios personalizados, agréguelos ahora.

   - En la ficha **acciones** , seleccione **poner en cuarentena el mensaje** para las opciones **usuario** suplantado y **dominio suplantado** . Además, active las sugerencias de seguridad de suplantación.

   - En la pestaña **inteligencia de buzones** de correo, asegúrese de que la inteligencia de buzones está activada y active la protección de representación basada en inteligencia de buzones de correo. En la lista **si el correo electrónico se envía por un usuario suplantado** , elija **poner en cuarentena el mensaje**.

   - En la ficha **Agregar remitentes y dominios** de confianza, especifique los remitentes o dominios de confianza que desee agregar.

   - **Guardar** en la pestaña **revisar la configuración** una vez que hayas revisado la configuración.

4. En la sección **suplantación** , haga clic en **Editar** y, a continuación, especifique las siguientes opciones de configuración:

   - En la pestaña **configuración de filtro de suplantación de identidad** , asegúrese de que está activada la protección contra la suplantación de identidad.

   - En la ficha **acciones** , elija **poner en cuarentena el mensaje**.

   - **Guardar** en la pestaña **revisar la configuración** una vez que haya revisado los cambios. (Si no realizó ningún cambio, **Cancelar**).

5. Cierre la página Configuración de directiva predeterminada.

Para obtener más información acerca de las opciones de la Directiva antiphishing, vea [Configure anti-phishing policies in Microsoft defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Parte 3: protección contra correo no deseado

[La protección contra correo no deseado](anti-spam-protection.md) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), **Threat management** elija  >  **Policy**  >  **anti-spam** de la Directiva de administración de amenazas.

2. En la pestaña **personalizado** , active la configuración personalizada.

3. Expanda **directiva predeterminada de filtro de correo no deseado**, haga clic en **Editar Directiva** y especifique la siguiente configuración:

   - En la sección **correo electrónico no deseado y acciones en masa** , establezca el umbral en un valor de 5 o 6.

   - En la sección **listas de permitidos** , revise (o edite) los remitentes y dominios permitidos.

4. Haga clic en **Guardar**.

Para obtener más información sobre las opciones de la Directiva contra correo no deseado, vea [configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4: protección frente a direcciones URL y archivos malintencionados (vínculos seguros y datos adjuntos seguros en defender para Office 365)

La protección de tiempo de clic de direcciones URL y archivos malintencionados está disponible en las suscripciones que incluyen [Microsoft defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se configura a través de [datos adjuntos seguros](atp-safe-attachments.md) y directivas de [vínculos seguros](atp-safe-links.md) .

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Directivas de datos adjuntos seguros en Microsoft defender para Office 365

Para configurar [datos adjuntos seguros](atp-safe-attachments.md), cree al menos una directiva de vínculos seguros.

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione la Directiva de **Administración de amenazas**  >  **Policy**  >  **datos adjuntos seguros de ATP** y haga clic en **crear**.

2. En el Asistente para **nueva Directiva de datos adjuntos seguros** que aparece, configure las siguientes opciones:

   - En el cuadro **nombre** , escriba `Block malware` y, a continuación, haga clic en **siguiente**.

   - En la página **configuración** , configure las siguientes opciones:
     - En la sección **respuesta de malware desconocida de datos adjuntos seguros** , elija **bloquear**.
     - En la sección **redirigir datos adjuntos** , seleccione la opción **Habilitar redirección**. Especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización, que va a revisar los archivos detectados.

     Haga clic en **Siguiente**.

3. En la página **aplicado a** , haga clic en **Agregar una condición**, elija **aplicado si: el dominio del destinatario es**, haga clic en **Agregar**, seleccione su dominio o dominios, haga clic en **Agregar**, haga clic en **listo** y, a continuación, haga clic en **siguiente**.

4. Revise la configuración y, a continuación, haga clic en **Finalizar**.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Directivas de vínculos seguros en Microsoft defender para Office 365

Para configurar [vínculos seguros](atp-safe-links.md), revise y modifique la configuración global para vínculos seguros y cree al menos una directiva de vínculos seguros.

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione Directiva de **Administración de amenazas**,  >  **Policy**  >  **vínculos seguros ATP** y haga clic en **configuración global** y, a continuación, configure las siguientes opciones:

   - Compruebe **usar vínculos seguros en: Office 365 aplicaciones** está activada: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .
   - **No realizar seguimiento cuando los usuarios hagan clic en vínculos seguros**: Desactive esta opción para hacer un seguimiento de los clics del usuario: desactivar ![ ](../../media/scc-toggle-off.png) .
   - **No permita que los usuarios hagan clic en los vínculos seguros a la dirección URL original**: comprobar que esta configuración está activada: ![ activar o desactivar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Cuando haya terminado, haga clic en **Guardar**.

2. De nuevo en la página vínculos seguros principal, haga clic en **crear**.

3. En el Asistente para **crear Directiva de vínculos seguros** que aparece, configure las siguientes opciones:

   - En el cuadro **nombre** , escriba un nombre, como `Safe Links` y, a continuación, haga clic en **siguiente**.

   - En la página **configuración** , configure las siguientes opciones:
     - **Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes**: elija **activado**.
     - **Seleccione la acción para direcciones URL potencialmente malintencionadas o desconocidas en Microsoft Teams**: elija **activado**.
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **Esperar a que se complete el análisis de URL antes de entregar el mensaje**
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **No permitir que los usuarios hagan clic a través de la dirección URL original**

     Haga clic en **Siguiente**.

4. En la página **aplicado a** , haga clic en **Agregar una condición**, elija **aplicado si: el dominio del destinatario es**, haga clic en **Agregar**, seleccione su dominio o dominios, haga clic en **Agregar**, haga clic en **listo** y, a continuación, haga clic en **siguiente**.

5. Revise la configuración y, a continuación, haga clic en **Finalizar**.

Para más información, consulte [Configurar directivas de vínculos seguros](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5: comprobar que ATP para SharePoint, OneDrive y Microsoft Teams está activado

Se crean cargas de trabajo como SharePoint, OneDrive y Microsoft Teams para la colaboración. El uso de defender para Office 365 ayuda en el bloqueo y la detección de archivos identificados como malintencionados en los sitios de grupo y las bibliotecas de documentos. Puede leer más sobre cómo funciona [aquí](atp-for-spo-odb-and-teams.md).

> [!IMPORTANT]
> **Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya esté activado en su entorno de Microsoft 365**. Normalmente lo hace alguien que tiene el rol registros de auditoría asignado en Exchange Online. Para obtener más información, consulte [activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), seleccione Directiva de **Administración de amenazas**:  >  **Policy**  >  **datos adjuntos seguros ATP** y, a continuación, haga clic en **configuración global**.

2. Compruebe que el botón **activar o desactivar ATP para SharePoint, OneDrive y Microsoft Teams** esté a la derecha: ![ alternar ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) y, a continuación, haga clic en **Guardar**.

3. Revise (y, según corresponda, Edit) las directivas de [datos adjuntos seguros](set-up-atp-safe-attachments-policies.md) de su organización y [las directivas de vínculos a prueba](set-up-atp-safe-links-policies.md)de errores.

4. Recomenda Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro _DisallowInfectedFileDownload_ establecido en `$true` .

   - `$true` bloquea todas las acciones (excepto eliminar) para los archivos detectados. Los usuarios no pueden abrir, mover, copiar o compartir los archivos detectados.
   - `$false` bloquea todas las acciones excepto eliminar y descargar. Los usuarios pueden elegir entre aceptar el riesgo y descargar un archivo detectado.

   > [!TIP]
   > Para obtener más información sobre el uso de PowerShell con Microsoft 365, consulte [Manage microsoft 365 with PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).

5. Espere hasta 30 minutos para que los cambios se extiendan a todos los centros de recursos de Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Ahora configurar alertas para los archivos detectados

Para recibir una notificación cuando se identificó un archivo en SharePoint Online, OneDrive para la empresa o Microsoft Teams como malintencionado, puede configurar una alerta.

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), elija **alertas** \> **Administrar alertas**.

2. Elija **nueva Directiva de alerta**.

3. Especifique un nombre para la alerta. Por ejemplo, podría escribir archivos malintencionados en bibliotecas.

4. Escriba una descripción de la alerta. Por ejemplo, puede escribir notificar a los administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.

5. En la sección **enviar esta alerta cuando...** , establezca:

   a. En la lista **actividades** , seleccione **malware detectado en el archivo**.

   b. Deje el campo **usuarios** vacío.

6. En la sección **enviar esta alerta a...** , seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecte un archivo malintencionado.

7. **Guardar**.

Para obtener más información acerca de las alertas, consulte [crear alertas de actividad en el centro de seguridad & cumplimiento](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Cuando haya terminado de configurar, use estos vínculos para iniciar las investigaciones de carga de trabajo:
>
>- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
>- [Usar el centro de seguridad & cumplimiento para administrar los archivos en cuarentena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Administrar archivos y mensajes en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6: configuración adicional para configurar

Además de configurar la protección contra malware, archivos y direcciones URL malintencionadas, suplantación de identidad (phishing) y correo no deseado, le recomendamos que configure la purga automática de cero horas.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Purgado automático de cero horas para correo electrónico en EOP

[La purga automática de cero horas](zero-hour-auto-purge.md) (ZAP) está disponible en las suscripciones que incluyen [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Esta protección está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones para que la protección esté en vigor:

- Las acciones de correo no deseado se establecen para **mover el mensaje a la carpeta correo no deseado** en [las directivas contra correo no deseado](anti-spam-protection.md).

- Los usuarios han mantenido su [configuración predeterminada de correo no deseado](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)y no han desactivado la protección contra correo electrónico no deseado.

Para obtener más información, consulte [depuración automática de cero horas-protección contra correo no deseado y malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Tareas posteriores a la instalación y pasos siguientes

Después de configurar las características de protección contra amenazas, asegúrese de supervisar cómo funcionan estas características. Revise y revise las directivas para que puedan hacer lo que necesite. Además, vea las nuevas características y actualizaciones de servicio que pueden agregar valor.

****

|Qué hacer|Recursos para obtener más información|
|---|---|
|Ver cómo funcionan las características de protección contra amenazas en su organización al ver los informes|[Panel de seguridad](security-dashboard.md)<br/>[Informes de seguridad de correo electrónico](view-email-security-reports.md)<br/>[Informes de Microsoft defender para Office 365](view-reports-for-atp.md)<br/>[Explorador de amenazas](threat-explorer.md)|
|Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario|[Puntuación de seguridad](../mtp/microsoft-secure-score.md)<br/>[Informes inteligentes y perspectivas](reports-and-insights-in-security-and-compliance.md)<br/>[Características de respuesta y investigación de amenazas de Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Vea las nuevas características y actualizaciones de servicio|[Opciones de versión estándar y de destino](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Centro de mensajes](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Descripciones de servicio](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Obtenga información sobre las configuraciones de seguridad estándar y estricta recomendadas para EOP y defender para Office 365|[Configuración recomendada para EOP y Microsoft defender para Office 365 Security](recommended-settings-for-eop-and-office365-atp.md)|
