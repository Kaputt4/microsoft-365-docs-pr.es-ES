---
title: Protección contra amenazas
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden obtener información sobre la protección contra amenazas en Microsoft 365 y configurar cómo usarla para su organización.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: cb2866fd3e60c021ae89ffabe7149f4b415d63bc
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150717"
---
# <a name="protect-against-threats"></a>Protección contra amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender para Office 365 plan 1 y plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Esta es una guía de inicio rápido que divide la configuración de Defender para Office 365 en fragmentos. Si no está seguro de dónde empezar a usar las características de protección contra amenazas en Office 365, o si aprende mejor haciendo *esto,* use estas instrucciones como una lista de comprobación y un punto de partida.

> [!IMPORTANT]
> La configuración recomendada inicial se incluye para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas **de su organización.** Espere aproximadamente 30 minutos para que las directivas o los cambios funcionen en su centro de datos.

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Suscripciones

Las características de protección contra amenazas se incluyen en *todas las* suscripciones de Microsoft u Office 365; sin embargo, algunas suscripciones tienen características avanzadas. En la tabla siguiente se enumeran las características de protección incluidas en este artículo junto con los requisitos mínimos de suscripción.

> [!TIP]
> Tenga en cuenta que, más allá de las indicaciones para activar la *auditoría,* los pasos inician la protección contra malware, la suplantación de identidad y el correo no deseado, que se marcan como parte de Office 365 Exchange Online Protection **(EOP).** Esto puede parecer extraño en un artículo de Defender para Office 365, hasta que recuerde que **(Defender para Office 365)** contiene EOP y se basa en este.

****

|Tipo de protección|Requisito de suscripción|
|---|---|
|Registro de auditoría (con fines de informes)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protección antimalware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protección contra phishing|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra correo no deseado|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Purga automática de cero horas (para correo electrónico)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra archivos y direcciones URL malintencionadas en el correo electrónico y documentos de Office (vínculos seguros y datos adjuntos seguros)|[Microsoft Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Activar datos adjuntos seguros para cargas de trabajo de SharePoint, OneDrive y Microsoft Teams|[Defender para Office 365 ](atp-for-spo-odb-and-teams.md)|
|Protección contra suplantación de identidad avanzada|[Defender para Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roles y permisos

Para configurar las directivas de Defender para Office 365, debe tener asignado un rol adecuado en el Centro de [seguridad & cumplimiento.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) Echa un vistazo a la tabla siguiente para ver los roles que pueden realizar estas acciones.

****

|Rol o grupo de roles|Dónde obtener más información|
|---|---|
|administrador global|[Acerca de los roles de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Administrador de seguridad|[Permisos de roles de administrador en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización en Exchange Online|[Permisos de Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> y <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Para obtener más información, vea Permisos en el Centro de [& cumplimiento.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Antes de empezar, active el registro de auditoría para informes e investigación

Inicie el registro de auditoría de forma anticipada. Necesitarás que la auditoría esté **on** para algunos de los pasos que se indican a continuación. El registro de auditoría está disponible en las suscripciones que incluyen [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para ver datos en informes de protección contra [](view-email-security-reports.md)amenazas, como el Panel de [seguridad,](security-dashboard.md)los informes de seguridad de correo electrónico y el [Explorador,](threat-explorer.md)el registro de auditoría debe estar *en .* Para obtener más información, vea Activar o desactivar [la búsqueda de registros de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Parte 1: Protección antimalware

[La protección antimalware](anti-malware-protection.md) está disponible en las suscripciones que incluyen [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija **Directiva de administración de** \> **amenazas** \> **antimalware.**

2. Haga doble clic en la **directiva** predeterminada y, a continuación, **elija configuración.**

3. Especifique la siguiente configuración:

    - En la **sección Respuesta de detección de** malware, mantenga la configuración predeterminada de **No**.

    - En la **sección Filtro de tipos comunes de datos** adjuntos, elija **On**.

4. Haga clic en **Guardar**.

Para obtener más información acerca de las opciones de directiva antimalware, vea [Configurar directivas antimalware.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Parte 2: Protección contra la suplantación de identidad

[La protección contra la suplantación](anti-phishing-protection.md) de identidad está disponible en las suscripciones que incluyen [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) La protección contra suplantación de identidad avanzada está disponible [en Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

El siguiente procedimiento describe cómo configurar una directiva contra suplantación de identidad en Microsoft Defender para Office 365. Los pasos son similares para configurar una directiva contra suplantación de identidad en EOP.

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija Directiva **de administración** de amenazas contra \>  \> **la suplantación de identidad de ATP.**

2. Haga clic **en Directiva predeterminada.**

3. En la **sección Suplantación,** haga clic **en Editar** y, a continuación, especifique la siguiente configuración:

   - En la **pestaña Agregar usuarios para proteger,** active *la* protección. A continuación, agregue usuarios, como los miembros de la directiva de su organización, su director general, director financiero y otros líderes superiores. (Puede escribir una dirección de correo electrónico individual o hacer clic para mostrar una lista).

   - On the **Add domains to protect tab,** turn on **Automatically include the domains I own**. Si tiene dominios personalizados, agrégrélos ahora.

   - En la **pestaña Acciones,** seleccione **Poner** en cuarentena el mensaje tanto para el usuario suplantado como para las opciones de **dominio suplantado.**  Además, activa las sugerencias de seguridad de suplantación.

   - En la pestaña **Inteligencia de** buzones de correo, asegúrese de que la inteligencia de buzones esté activada y active la protección de suplantación basada en inteligencia de buzones. In the **If email is sent by an suersonated user** list, choose Quarantine the **message**.

   - En la **pestaña Agregar remitentes y dominios** de confianza, especifique los remitentes o dominios de confianza que desee agregar.

   - **Guarda** en la **pestaña Revisar la configuración** después de revisar la configuración.

4. En la **sección Suplantación** de nombre, haga clic **en Editar** y, a continuación, especifique la siguiente configuración:

   - En la **pestaña Configuración del filtro de** suplantación, asegúrese de que la protección contra la suplantación está activada.

   - En la **pestaña Acciones,** elija **Cuarentena del mensaje.**

   - **Guarda** en la **pestaña Revisar la configuración** después de revisar los cambios. (Si no ha realizado ningún cambio, **Cancel**).)

5. Cierre la página de configuración de directiva predeterminada.

Para obtener más información sobre las opciones de directiva contra suplantación de identidad, vea Configurar directivas contra suplantación de identidad en [Microsoft Defender para Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Parte 3: Protección contra correo no deseado

[La protección contra correo no](anti-spam-protection.md) deseado está disponible en las suscripciones que incluyen [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija **Directiva de administración de** \> **amenazas** \> **contra correo no deseado.**

2. En la **pestaña** Personalizado, active la configuración personalizada.

3. Expanda **Directiva de filtro de correo no deseado predeterminada,** haga clic en **Editar** directiva y, a continuación, especifique la siguiente configuración:

   - En la sección Correo no deseado y **acciones masivas,** establezca el umbral en un valor de 5 o 6.

   - En la **sección Listas de** permitidos, revise (o edite) los remitentes y dominios permitidos.

4. Haga clic en **Guardar**.

Para obtener más información sobre las opciones de directiva contra correo no deseado, vea Configurar directivas contra correo no deseado [en EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4: Protección contra archivos y direcciones URL malintencionadas (vínculos seguros y datos adjuntos seguros en Defender para Office 365)

La protección con el tiempo de clic contra archivos y direcciones URL malintencionadas está disponible en suscripciones que incluyen [Microsoft Defender para Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Se configura mediante directivas de datos [adjuntos seguros](atp-safe-attachments.md) [y vínculos](atp-safe-links.md) seguros.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Directivas de datos adjuntos seguros en Microsoft Defender para Office 365

Para configurar datos [adjuntos seguros,](atp-safe-attachments.md)cree al menos una directiva de vínculos seguros.

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija Datos adjuntos seguros de ATP de directiva de administración de amenazas y, a continuación, haga  \>  \> clic en **Crear**.

2. En el **Asistente para nueva directiva de datos** adjuntos seguros que aparece, configure las siguientes opciones:

   - En el **cuadro** Nombre, escriba `Block malware` y, a continuación, haga clic en **Siguiente**.

   - En la **página** Configuración, configure las siguientes opciones:
     - En la sección Datos adjuntos seguros de respuesta **de malware desconocido,** elija **Bloquear**.
     - En la sección **Redirigir datos adjuntos,** seleccione la opción **Habilitar redireccionamiento.** Especifique la dirección de correo electrónico del operador o administrador de seguridad de su organización, que revisará los archivos detectados.

     Haga clic en **Siguiente**.

3. On the **Applied to** page, click Add **a condition**, choose Applied **if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

4. Revise la configuración y, a continuación, haga clic **en Finalizar.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Directivas de vínculos seguros en Microsoft Defender para Office 365

Para configurar [vínculos seguros,](atp-safe-links.md)revise y edite la configuración global de vínculos seguros y cree al menos una directiva de vínculos seguros.

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija Vínculos seguros de ATP de directiva de administración de amenazas, haga clic en Configuración global y, a  \>  \> continuación, configure las siguientes opciones: 

   - Compruebe **usar vínculos seguros en: Aplicaciones de Office 365** está activada: ![ Activar o ](../../media/scc-toggle-on.png) desactivar.
   - **No realice un seguimiento cuando los usuarios hagan clic en Vínculos** seguros: desactive esta opción para realizar un seguimiento de los clics del usuario: ![ Desactivar ](../../media/scc-toggle-off.png) .
   - **No permitir que los usuarios hagan clic a través** de vínculos seguros a la dirección URL original: Compruebe que esta configuración está activada: Activar o ![ ](../../media/scc-toggle-on.png) desactivar.

   Cuando haya terminado, haga clic en **Guardar**.

2. De nuevo en la página de vínculos seguros principal, haga clic **en Crear**.

3. En el **Asistente para crear directivas de vínculos** seguros que aparece, configure las siguientes opciones:

   - En el **cuadro** Nombre, escriba un nombre, como , y, a `Safe Links` continuación, haga clic en **Siguiente**.

   - En la **página** Configuración, configure las siguientes opciones:
     - **Seleccione la acción para direcciones URL potencialmente malintencionadas desconocidas en los mensajes:** **Elegir.**
     - **Seleccione la acción para direcciones URL desconocidas o potencialmente malintencionadas dentro de Microsoft Teams:** **Elegir.**
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje**
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **No permitir que los usuarios hagan clic en la dirección URL original**

     Haga clic en **Siguiente**.

4. On the **Applied to** page, click Add **a condition**, choose Applied **if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

5. Revise la configuración y, a continuación, haga clic **en Finalizar.**

Para más información, consulte [Configurar directivas de vínculos seguros](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5: Comprobar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams está activado

Las cargas de trabajo como SharePoint, OneDrive y Teams se han creado para la colaboración. El uso de Defender para Office 365 ayuda a bloquear y detectar archivos identificados como malintencionados en sitios de grupo y bibliotecas de documentos. Puede obtener más información sobre cómo funciona [aquí.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya está activado **para su entorno de Microsoft 365**. Esto lo suele hacer alguien que tiene el rol Registros de auditoría asignado en Exchange Online. Para obtener más información, vea Activar o desactivar la [búsqueda de registros de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija Datos adjuntos seguros de ATP de directiva de administración de amenazas y, a continuación, haga clic  \>  \> en **Configuración global.**

2. Compruebe que la opción Activar Defender para **Office 365 para SharePoint, OneDrive** y Microsoft Teams está a la derecha: Activar y, a continuación, haga clic en ![ ](../../media/scc-toggle-on.png) **Guardar.**

3. Revise (y, según corresponda, edite) las directivas de datos adjuntos seguros y las directivas de [vínculos seguros de su organización.](set-up-atp-safe-links-policies.md) [](set-up-atp-safe-attachments-policies.md)

4. (Recomendado) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro _DisallowInfectedFileDownload_ establecido en `$true` .

   - `$true` bloquea todas las acciones (excepto Eliminar) para los archivos detectados. Los usuarios no pueden abrir, mover, copiar ni compartir archivos detectados.
   - `$false` bloquea todas las acciones excepto Eliminar y Descargar. Los usuarios pueden elegir aceptar el riesgo y descargar un archivo detectado.

   > [!TIP]
   > Para obtener más información sobre cómo usar PowerShell con Microsoft 365, vea [Administrar Microsoft 365 con PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)

5. Espere hasta 30 minutos para que los cambios se extienda a todos los centros de datos de Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Ahora configurar alertas para los archivos detectados

Para recibir una notificación cuando un archivo en SharePoint Online, OneDrive para la Empresa o Microsoft Teams se haya identificado como malintencionado, puede configurar una alerta.

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija  \> **Alertas administrar alertas.**

2. Elija **Nueva directiva de alerta.**

3. Especifique un nombre para la alerta. Por ejemplo, podría escribir Archivos malintencionados en bibliotecas.

4. Escriba una descripción para la alerta. Por ejemplo, puede escribir Notificar a los administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.

5. En la **sección Enviar esta alerta cuando...** establezca:

   a. En la lista **Actividades,** elija **Malware detectado en el archivo.**

   b. Deje vacío **el campo** Usuarios.

6. En la sección Enviar esta alerta **a...** seleccione uno o más administradores globales, administradores de seguridad o lectores de seguridad que deberán recibir una notificación cuando se detecte un archivo malintencionado.

7. **Guardar**.

Para obtener más información acerca de las alertas, vea [Crear alertas de actividad en](../../compliance/create-activity-alerts.md)el Centro de & cumplimiento.

> [!NOTE]
> Cuando haya terminado de configurar, use estos vínculos para iniciar investigaciones de carga de trabajo:
>
>- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
>- [Usar el Centro de seguridad & cumplimiento para administrar archivos en cuarentena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Administrar archivos y mensajes en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6: Opciones adicionales para configurar

Además de configurar la protección contra malware, direcciones URL malintencionadas y archivos, suplantación de identidad (phishing) y correo no deseado, se recomienda configurar la purga automática de cero horas.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Purga automática de cero horas para correo electrónico en EOP

[La purga automática de cero](zero-hour-auto-purge.md) horas (ZAP) está disponible en las suscripciones que incluyen [EOP.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Esta protección está activada de forma predeterminada; sin embargo, se deben cumplir las siguientes condiciones para que la protección esté en vigor:

- Las acciones de correo no deseado se establecen **en Mover mensaje a la carpeta Correo no deseado** en directivas contra correo no [deseado.](anti-spam-protection.md)

- Los usuarios han mantenido su configuración predeterminada [de correo](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)no deseado y no han desactivado la protección de correo no deseado.

Para obtener más información, consulte [Purga automática de cero horas: protección contra correo no deseado y malware.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Tareas posteriores a la instalación y pasos siguientes

Después de configurar las características de protección contra amenazas, asegúrate de supervisar cómo funcionan esas características. Revise y revise las directivas para que hagan lo que necesita. Además, busque nuevas características y actualizaciones de servicio que puedan agregar valor.

****

|Qué hacer|Recursos para obtener más información|
|---|---|
|Ver cómo funcionan las características de protección contra amenazas para su organización mediante la visualización de informes|[Panel de seguridad](security-dashboard.md) <p> [Informes de seguridad de correo electrónico](view-email-security-reports.md) <p> [Informes de Microsoft Defender para Office 365](view-reports-for-atp.md) <p> [Explorador de amenazas](threat-explorer.md)|
|Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario|[Puntuación de seguridad](../mtp/microsoft-secure-score.md) <p> [Informes e información inteligentes](reports-and-insights-in-security-and-compliance.md) <p> [Características de investigación y respuesta de amenazas de Microsoft 365](keep-users-safe-with-office-365-ti.md)|
|Buscar nuevas características y actualizaciones de servicio|[Opciones de versión estándar y dirigida](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [Centro de mensajes](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descripciones de servicio](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Obtenga información sobre las configuraciones de seguridad estándar y estrictas recomendadas para EOP y Defender para Office 365|[Configuración recomendada para EOP y Microsoft Defender para la seguridad de Office 365](recommended-settings-for-eop-and-office365-atp.md)|
