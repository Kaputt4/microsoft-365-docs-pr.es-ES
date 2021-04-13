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
ms.openlocfilehash: b55391247bf7d21c68c67e29f93bac1b7088b035
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687092"
---
# <a name="protect-against-threats"></a>Protección contra amenazas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Esta es una guía de inicio rápido que divide la configuración de Defender para Office 365 en fragmentos. Si es nuevo en las características de protección contra amenazas en Office 365, no está seguro de por dónde empezar, o si aprende mejor haciendo *esto,* use esta guía como una lista de comprobación y un punto de partida.

> [!IMPORTANT]
> **La configuración recomendada inicial se incluye para** cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades de su organización específica. Espere aproximadamente 30 minutos para que las directivas o los cambios funcionen a través del centro de datos.

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Suscripciones

Las características de protección contra amenazas se incluyen en *todas* las suscripciones de Microsoft u Office 365; sin embargo, algunas suscripciones tienen características avanzadas. En la tabla siguiente se enumeran las características de protección incluidas en este artículo junto con los requisitos mínimos de suscripción.

> [!TIP]
> Tenga en cuenta que, más allá de las instrucciones para activar la *auditoría,* los pasos inician antimalware, anti phishing y antispam, que se marcan como parte de Office 365 Exchange Online Protection (**EOP**). Esto puede parecer extraño en un artículo de Defender para Office 365, hasta que recuerde (**Defender para Office 365**) contiene e incluye EOP.

****

|Tipo de protección|Requisito de suscripción|
|---|---|
|Registro de auditoría (para fines de informes)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protección antimalware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protección contra phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra correo no deseado|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Purga automática de hora cero (para correo electrónico)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra direcciones URL malintencionadas y archivos en el correo electrónico y documentos de Office (vínculos seguros y datos adjuntos seguros)|[Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Activar datos adjuntos seguros para cargas de trabajo de SharePoint, OneDrive y Microsoft Teams|[Microsoft Defender para Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Protección contra suplantación de identidad avanzada|[Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roles y permisos

Para configurar directivas de Defender para Office 365, debe tener asignado un rol adecuado en el Centro de [seguridad & cumplimiento](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Echa un vistazo a la tabla siguiente para ver los roles que pueden realizar estas acciones.

****

|Rol o grupo de roles|Dónde obtener más información|
|---|---|
|administrador global|[Acerca de los roles de administración de Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Administrador de seguridad|[Permisos de roles de administrador en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización en Exchange Online|[Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo) <p> y <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Antes de empezar, active Registro de auditoría para informes e investigación

Inicie el registro de auditoría de forma anticipada. Necesitarás que la auditoría esté **on** para algunos de los pasos que se indican a continuación. El registro de auditoría está disponible en suscripciones que incluyen [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para ver los datos en los informes de [](view-email-security-reports.md)protección contra amenazas, como el Panel de [seguridad,](security-dashboard.md)los informes de seguridad de correo electrónico y el [Explorador,](threat-explorer.md)el registro de auditoría debe ser *On*. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Parte 1: protección contra malware

[La protección contra malware](anti-malware-protection.md) está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija Directiva de administración de **amenazas** \>  \> **Antimalware**.

2. Haga doble clic en **la directiva** Predeterminada y, a continuación, elija **configuración**.

3. Especifique la siguiente configuración:

    - En la **sección Respuesta de** detección de malware, mantenga la configuración predeterminada de **No**.

    - En la **sección Filtro de tipos comunes de** datos adjuntos, elija **On**.

4. Haga clic en **Guardar**.

Para obtener más información sobre las opciones de directiva antimalware, vea [Configure anti-malware policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Parte 2: Protección contra la suplantación de identidad

[La protección contra la suplantación](anti-phishing-protection.md) de identidad está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). La protección contra suplantación de identidad avanzada está disponible [en Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

El siguiente procedimiento describe cómo configurar una directiva contra suplantación de identidad en Microsoft Defender para Office 365. Los pasos son similares para configurar una directiva contra suplantación de identidad en EOP.

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija Administración de **amenazas** \> **Directiva** \> **ATP contra suplantación de identidad**.

2. Haga clic **en Directiva predeterminada**.

3. En la **sección Suplantación,** haga clic **en Editar** y, a continuación, especifique la siguiente configuración:

   - En la **pestaña Agregar usuarios para proteger,** activa la *protección.* A continuación, agregue usuarios, como los miembros de la junta directiva de su organización, su director general, director financiero y otros líderes sénior. (Puede escribir una dirección de correo electrónico individual o hacer clic para mostrar una lista).

   - En la **pestaña Agregar dominios para proteger,** active Incluir automáticamente los dominios que **tengo.** Si tiene dominios personalizados, agrégrelos ahora.

   - En la **pestaña Acciones,** seleccione Poner en cuarentena **el** mensaje tanto para el usuario **suplantado** como para las opciones de **dominio suplantado.** Además, activa las sugerencias de seguridad de suplantación.

   - En la **pestaña Inteligencia de** buzones de correo, asegúrese de que la inteligencia de buzones esté activada y active la protección de suplantación basada en inteligencia de buzones. En la **lista Si el correo electrónico lo envía una lista de** usuarios suplantados, elija **Poner en cuarentena el mensaje**.

   - En la **pestaña Agregar remitentes y dominios** de confianza, especifique los remitentes o dominios de confianza que desee agregar.

   - **Guarda** en la **pestaña Revisar la configuración** después de revisar la configuración.

4. En la **sección Suplantación,** haga clic **en Editar** y, a continuación, especifique la siguiente configuración:

   - En la **pestaña Configuración** del filtro de suplantación, asegúrese de que la protección contra la suplantación está activada.

   - En la **pestaña** Acciones, elija **Poner en cuarentena el mensaje**.

   - **Guarda** en la **pestaña Revisar la configuración** después de revisar los cambios. (Si no ha realizado ningún cambio, **Cancel**.)

5. Cierre la página de configuración de directiva predeterminada.

Para obtener más información acerca de las opciones de directiva contra suplantación de identidad (phishing), vea [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Parte 3: Protección contra correo no deseado

[La protección contra correo no](anti-spam-protection.md) deseado está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description).

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija Directiva de administración de **amenazas** contra correo \>  \> **no deseado.**

2. En la **pestaña** Personalizado, activa Configuración personalizada.

3. Expanda Directiva de filtro de correo no deseado **predeterminada,** haga clic **en Editar directiva** y, a continuación, especifique la siguiente configuración:

   - En la sección Correo no deseado y acciones **masivas,** establezca el umbral en un valor de 5 o 6.

   - En la **sección Permitir listas,** revise (o edite) los remitentes y dominios permitidos.

4. Haga clic en **Guardar**.

Para obtener más información acerca de las opciones de directiva contra correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4: protección contra archivos y direcciones URL malintencionadas (vínculos seguros y datos adjuntos seguros en Defender para Office 365)

La protección con tiempo de clic frente a direcciones URL y archivos malintencionados está disponible en suscripciones que incluyen [Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se configura a través de datos [adjuntos](safe-attachments.md) seguros y [directivas de vínculos seguros.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Directivas de datos adjuntos seguros en Microsoft Defender para Office 365

Para configurar datos [adjuntos seguros,](safe-attachments.md)cree al menos una directiva de vínculos seguros.

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija **Directiva** de administración de amenazas Datos adjuntos seguros de \>  \> **ATP** y, a continuación, haga clic **en Crear**.

2. En el **Asistente para nueva directiva de datos adjuntos** seguros que aparece, configure las siguientes opciones:

   - En el **cuadro** Nombre, escriba `Block malware` y, a continuación, haga clic en **Siguiente**.

   - En la **página Configuración,** configure las siguientes opciones:
     - En la **sección Datos adjuntos seguros de** respuesta de malware desconocido, elija **Bloquear**.
     - En la **sección Redirigir datos adjuntos,** seleccione la opción **Habilitar redireccionamiento**. Especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización, que revisará los archivos detectados.

     Haga clic en **Siguiente**.

3. En  la página Aplicado **a,** haga clic en Agregar una condición, elija Aplicado **si:** El dominio de destinatario es , haga clic en Agregar **,** seleccione su dominio o dominios, haga clic en Agregar **,** haga clic en Listo y, a continuación, haga clic en **Siguiente**.

4. Revise la configuración y, a continuación, haga clic **en Finalizar**.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Directivas de vínculos seguros en Microsoft Defender para Office 365

Para configurar [vínculos seguros,](safe-links.md)revise y edite la configuración global de vínculos seguros y cree al menos una directiva de vínculos seguros.

1. En el [Centro de & seguridad,](https://protection.office.com)elija **Directiva** de administración de amenazas Vínculos seguros de ATP y haga clic en Configuración global y, a continuación, \>  \> configure las siguientes opciones: 

   - Comprobar **Usar vínculos seguros en: Las aplicaciones de Office 365** están activadas: ![ Activar ](../../media/scc-toggle-on.png) .
   - **No realizar un seguimiento cuando los usuarios hagan clic en Vínculos seguros:** desactive esta opción para realizar un seguimiento de los clics del usuario: ![ Desactivar ](../../media/scc-toggle-off.png) .
   - **No permitir que los usuarios hagan clic en vínculos seguros** a la dirección URL original: Compruebe que esta configuración está activada: ![ Activar ](../../media/scc-toggle-on.png) .

   Cuando haya terminado, haga clic en **Guardar**.

2. En la página vínculos seguros principal, haga clic **en Crear**.

3. En el **Asistente para crear directivas de vínculos** seguros que aparece, configure las siguientes opciones:

   - En el **cuadro** Nombre, escriba un nombre, como , y, a continuación, `Safe Links` haga clic en **Siguiente**.

   - En la **página Configuración,** configure las siguientes opciones:
     - Seleccione la acción para direcciones URL **potencialmente malintencionadas desconocidas en mensajes**: Elija **Activar**.
     - Seleccione la acción para las direcciones URL desconocidas o **potencialmente malintencionadas de Microsoft Teams**: Elija **Activar**.
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje**
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **No permitir que los usuarios hagan clic en la dirección URL original**

     Haga clic en **Siguiente**.

4. En  la página Aplicado **a,** haga clic en Agregar una condición, elija Aplicado **si:** El dominio de destinatario es , haga clic en Agregar **,** seleccione su dominio o dominios, haga clic en Agregar **,** haga clic en Listo y, a continuación, haga clic en **Siguiente**.

5. Revise la configuración y, a continuación, haga clic **en Finalizar**.

Para más información, consulte [Configurar directivas de vínculos seguros](set-up-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5: Comprobar que los datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams están activados

Las cargas de trabajo como SharePoint, OneDrive y Teams se han creado para la colaboración. El uso de Defender para Office 365 ayuda a bloquear y detectar archivos que se identifican como malintencionados en sitios de grupo y bibliotecas de documentos. Puede leer más sobre cómo funciona [aquí](mdo-for-spo-odb-and-teams.md).

> [!IMPORTANT]
> Antes de comenzar este procedimiento, asegúrese de que el registro de auditoría ya **está activado para el entorno de Microsoft 365**. Esto lo suele hacer alguien que tiene el rol Registros de auditoría asignado en Exchange Online. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría!](../../compliance/turn-audit-log-search-on-or-off.md)

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija **Directiva** de administración de amenazas Datos adjuntos seguros de \>  \> **ATP** y, a continuación, haga clic en **Configuración global**.

2. Compruebe que la alternancia Activar **Defender para Office 365 para SharePoint, OneDrive** y Microsoft Teams está a la derecha: ![ Activar y, a continuación, haga ](../../media/scc-toggle-on.png) clic en **Guardar**.

3. Revise (y, según corresponda, edite) las directivas de datos adjuntos seguros de su organización y [las directivas de vínculos seguros](set-up-safe-links-policies.md). [](set-up-safe-attachments-policies.md)

4. (Recomendado) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro _DisallowInfectedFileDownload_ establecido en `$true` .

   - `$true` bloquea todas las acciones (excepto Eliminar) para los archivos detectados. Las personas no pueden abrir, mover, copiar o compartir archivos detectados.
   - `$false` bloquea todas las acciones excepto Eliminar y Descargar. Las personas pueden elegir aceptar el riesgo y descargar un archivo detectado.

   > [!TIP]
   > Para obtener más información sobre el uso de PowerShell con Microsoft 365, vea [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).

5. Permitir hasta 30 minutos para que los cambios se extienda a todos los centros de datos de Microsoft 365.

### <a name="now-set-up-alerts-for-detected-files"></a>Ahora configure alertas para los archivos detectados

Para recibir notificaciones cuando un archivo de SharePoint Online, OneDrive para la Empresa o Microsoft Teams se haya identificado como malintencionado, puede configurar una alerta.

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija  \> **Alertas Administrar alertas**.

2. Elija **Nueva directiva de alerta**.

3. Especifique un nombre para la alerta. Por ejemplo, puede escribir Archivos malintencionados en bibliotecas.

4. Escriba una descripción para la alerta. Por ejemplo, puede escribir Notifica a los administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.

5. En la **sección Enviar esta alerta cuando...** establezca:

   a. En la **lista Actividades,** elija **Malware detectado en el archivo**.

   b. Deje el **campo Usuarios** vacío.

6. En la sección Enviar esta alerta **a...** seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecte un archivo malintencionado.

7. **Guardar**.

Para obtener más información acerca de las alertas, vea [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Cuando haya terminado de configurar, use estos vínculos para iniciar investigaciones de carga de trabajo:
>
>- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
>- [Usar el Centro de seguridad & cumplimiento para administrar archivos en cuarentena](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6: opciones adicionales para configurar

Además de configurar la protección contra malware, direcciones URL malintencionadas y archivos, suplantación de identidad (phishing) y correo no deseado, se recomienda configurar la purga automática de cero horas.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Purga automática de hora cero para correo electrónico en EOP

[La purga automática](zero-hour-auto-purge.md) de hora cero (ZAP) está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Esta protección está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones para que la protección esté en vigor:

- Las acciones de correo no deseado se establecen **en Mover mensaje a carpeta correo no deseado** en directivas contra correo no [deseado.](anti-spam-protection.md)

- Los usuarios han mantenido su configuración predeterminada de [correo](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)no deseado y no han desactivado la protección de correo no deseado.

Para obtener más información, consulte [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Tareas posteriores a la instalación y pasos siguientes

Después de configurar las características de protección contra amenazas, asegúrate de supervisar cómo funcionan esas características. Revise y revise las directivas para que hagan lo que necesita. Además, busque nuevas características y actualizaciones de servicio que puedan agregar valor.

****

|Qué hacer|Recursos para obtener más información|
|---|---|
|Vea cómo funcionan las características de protección contra amenazas para su organización mediante la visualización de informes|[Panel de seguridad](security-dashboard.md) <p> [Informes de seguridad de correo electrónico](view-email-security-reports.md) <p> [Informes para Microsoft Defender para Office 365](view-reports-for-mdo.md) <p> [Explorador de amenazas](threat-explorer.md)|
|Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario|[Puntuación de seguridad](../defender/microsoft-secure-score.md) <p> [Informes e información inteligentes](reports-and-insights-in-security-and-compliance.md) <p> [Características de investigación y respuesta de amenazas de Microsoft 365](./office-365-ti.md)|
|Buscar nuevas características y actualizaciones de servicio|[Opciones de versión estándar y dirigida](../../admin/manage/release-options-in-office-365.md) <p> [Centro de mensajes](../../admin/manage/message-center.md) <p> [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descripciones del servicio](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Obtenga información sobre las configuraciones de seguridad estándar y estricta recomendadas para EOP y Defender para Office 365|[Configuración recomendada para EOP y Microsoft Defender para la seguridad de Office 365](recommended-settings-for-eop-and-office365.md)|
