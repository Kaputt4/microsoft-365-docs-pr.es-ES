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
ms.openlocfilehash: 4c32026ab4f33a68b1f63cb000807671839f6bad
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821288"
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

Las características de protección contra amenazas se *incluyen* en todas las suscripciones Office 365 Microsoft; sin embargo, algunas suscripciones tienen características avanzadas. En la tabla siguiente se enumeran las características de protección incluidas en este artículo junto con los requisitos mínimos de suscripción.

> [!TIP]
> Tenga en cuenta que, más allá de las instrucciones para activar la *auditoría,* los pasos inician antimalware, anti phishing y antispam, que se marcan como parte de Office 365 Exchange Online Protection (**EOP**). Esto puede parecer extraño en un artículo defender para Office 365, hasta que recuerde (**Defender para Office 365**) contiene e incluye EOP.

<br>

****

|Tipo de protección|Requisitos de suscripción|
|---|---|
|Registro de auditoría (para fines de informes)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protección antimalware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protección contra phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra correo no deseado|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Purga automática de hora cero (para correo electrónico)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra direcciones URL malintencionadas y archivos en documentos Office correo electrónico (Caja fuerte vínculos y Caja fuerte adjuntos)|[Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Activar los Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams de trabajo|[Microsoft Defender para Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Protección avanzada contra la suplantación de identidad|[Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roles y permisos

Para configurar Defender para Office 365 directivas, debe tener asignado un rol adecuado en el Centro de [seguridad & cumplimiento](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center). Echa un vistazo a la tabla siguiente para ver los roles que pueden realizar estas acciones.

<br>

****

|Rol o grupo de roles|Dónde obtener más información|
|---|---|
|administrador global|[Acerca de los roles de administración de Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Administrador de seguridad|[Permisos de roles de administrador en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización en Exchange Online|[Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo) <p> y <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Para obtener más información, vea [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Activar registro de auditoría para informes e investigación

- Inicie el registro de auditoría de forma anticipada. Necesitará que la auditoría esté **on** para algunos de los pasos siguientes. El registro de auditoría está disponible en suscripciones que incluyen [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para ver los datos en los informes de [](view-email-security-reports.md)protección contra amenazas, como el Panel de [seguridad,](security-dashboard.md)los informes de seguridad de correo electrónico y el [Explorador,](threat-explorer.md)el registro de auditoría debe ser *On*. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1: protección antimalware en EOP

Para obtener más información acerca de la configuración recomendada para antimalware, vea [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).

1. Abra <https://security.microsoft.com/antimalwarev2> .

2. En la **página Antimalware,** seleccione la directiva denominada **Directiva** predeterminada haciendo clic en el nombre.

3. En el control desplegable de detalles de directiva que se abre, haga clic en **Editar** configuración de protección y, a continuación, configure las siguientes opciones:
   - Seleccione **Habilitar el filtro de datos adjuntos** común para activar el filtro de datos adjuntos común. Haga **clic en Personalizar tipos de archivo** para agregar más tipos de archivo.
   - Compruebe que **habilitar la purga automática de hora cero para malware** está seleccionada.
   - Compruebe que ninguna de las opciones de configuración de la **sección Notificación** esté seleccionada.

   Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante de detalles de la directiva, haga clic en **Cerrar**.

Para obtener instrucciones detalladas para configurar directivas antimalware, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2: Protección contra la suplantación de identidad en EOP y Defender para Office 365

[La protección contra la suplantación](anti-phishing-protection.md) de identidad está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). La protección contra suplantación de identidad avanzada está disponible en [Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Para obtener más información acerca de la configuración recomendada para las directivas contra suplantación de identidad(phishing), consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

En el siguiente procedimiento se describe cómo configurar la directiva contra suplantación de identidad predeterminada. Configuración que solo están disponibles en Defender para Office 365 están claramente marcados.

1. Abra <https://security.microsoft.com/antiphishing> .

2. En la **página Anti-phishing,** seleccione la directiva denominada **Office365 AntiPhish Default (Valor predeterminado)** haciendo clic en el nombre.

3. En el menú desplegable de detalles de la directiva que aparece, configure las siguientes opciones:

   - **Sección Protección contra &** de suplantación de identidad: haga clic en Editar configuración de protección y configure las siguientes opciones en el control desplegable Editar configuración de protección que se abre:  
     - **Umbral de correo electrónico de suplantación** de identidad ( Phishing email threshold : Select <sup>\*</sup> **2 - Aggressive** (Standard) or **3 - More Aggressive** (Strict).
     - **Sección suplantación:** <sup>\*</sup> Configure los siguientes valores:
       - Seleccione Habilitar usuarios para proteger, haga clic en el vínculo Administrar **(nn) remitentes** que aparece y, a continuación, agregue remitentes internos y externos para protegerse de la suplantación, como los miembros de la junta directiva de su organización, su director general, director financiero y otros líderes sénior.
       - Seleccione **Habilitar dominios para proteger** y, a continuación, configure las siguientes opciones que aparecen:
         - Seleccione **Incluir dominios de mi propiedad** para proteger los remitentes internos en los dominios aceptados (visible haciendo clic en Ver mis **dominios**) de la suplantación.
         - Para proteger a los remitentes de otros dominios, seleccione Incluir dominios **personalizados,** haga clic en el vínculo Administrar **(nn)** dominios personalizados que aparece y, a continuación, agregue otros dominios para protegerlos de la suplantación.
     - Sección Agregar **remitentes** y dominios de confianza: haga clic en Administrar <sup>\*</sup> **(nn) remitentes** y dominios de confianza para configurar excepciones de dominio de remitente y remitente para la protección de suplantación si es necesario.
     - Configuración de inteligencia de buzones: compruebe que se han seleccionado Habilitar inteligencia de buzones y Habilitar inteligencia para la protección <sup>\*</sup> **de**  suplantación.
     - **Sección Suplantación** de identidad: compruebe que se ha seleccionado Habilitar **la inteligencia de** suplantación.

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección** Acciones: haga **clic en Editar acciones** y configure las siguientes opciones en el control desplegable **Editar** acciones que se abre:
     - **Sección Acciones de** mensaje: Configure las siguientes opciones:
       - **Si el mensaje se detecta como un usuario suplantado:** <sup>\*</sup> Seleccione Poner en cuarentena el **mensaje**.
       - **Si el mensaje se detecta como un dominio suplantado:** <sup>\*</sup> Seleccione Poner en cuarentena el **mensaje**.
       - **Si la inteligencia de buzones detecta un** usuario suplantado: seleccione Mover mensaje a las carpetas de correo no deseado (Estándar) de los destinatarios o Poner en cuarentena <sup>\*</sup> el **mensaje** (estricto). 
       - **Si el mensaje se detecta** como suplantación: seleccione Mover mensaje a las **carpetas** de correo no deseado (Estándar) de los destinatarios o Poner en cuarentena **el mensaje** (Estricto).
     - **Sugerencias de seguridad & de indicadores:** Configure las siguientes opciones:
       - **Mostrar la suplantación de consejo de seguridad:** <sup>\*</sup> Seleccione (activar).
       - **Mostrar la suplantación de dominio consejo de seguridad** <sup>\*</sup> : Seleccionar (activar).
       - **Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** <sup>\*</sup> : Seleccionar (activar).
       - **Mostrar (?) para remitentes no** autenticados para suplantación de identidad: Seleccione (activar).
       - **Mostrar etiqueta "via":** seleccione (activar) si esta configuración está disponible.

     Cuando haya terminado, haga clic en **Guardar**.

   <sup>\*</sup>Esta configuración solo está disponible en Defender para Office 365.

4. Haga **clic en Guardar** y, a continuación, en **Cerrar**

Para obtener instrucciones detalladas para configurar directivas contra suplantación de identidad, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) y [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection-in-eop"></a>Parte 3: Protección contra correo no deseado en EOP

Para obtener más información acerca de la configuración recomendada para el correo no deseado, vea Configuración de la directiva contra correo no deseado de [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

1. Abra <https://security.microsoft.com/antispam> .

2. En la **página Directivas contra correo** no deseado, seleccione la directiva denominada Directiva de entrada contra correo no deseado **(Predeterminada)** de la lista haciendo clic en el nombre.

3. En el menú desplegable de detalles de la directiva que aparece, siga estos pasos:
   - **Sección De umbral de correo & correo** no deseado masivo: Haga clic en Editar umbral de correo no deseado y **propiedades**. En el **control desplegable de propiedades** y  umbral de correo no deseado que aparece, establezca el valor de umbral de correo electrónico masivo en 5 (Estricto) o 6 (Estándar). Cuando haya terminado, haga clic en **Guardar**.
   - **Sección Remitentes y** dominios permitidos y bloqueados: Revise o edite los remitentes permitidos y los dominios permitidos.

4. Cuando haya terminado, haga clic en **Cerrar**.

Para obtener instrucciones detalladas para configurar directivas contra correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4: protección contra archivos y direcciones URL malintencionadas (Caja fuerte vínculos y Caja fuerte datos adjuntos en Defender para Office 365)

La protección con tiempo de clic frente a direcciones URL y archivos malintencionados está disponible en suscripciones que incluyen [Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se configura a través de Caja fuerte [datos adjuntos y](safe-attachments.md) [Caja fuerte de vínculos.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Caja fuerte Directivas de datos adjuntos en Microsoft Defender para Office 365

Para configurar los [Caja fuerte datos adjuntos,](safe-attachments.md)cree al menos una directiva Caja fuerte vínculos.

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija **Administración** de amenazas ATP Caja fuerte \>  \> **datos adjuntos** y, a continuación, haga clic en **Crear**.

2. En el **Asistente para nueva directiva Caja fuerte datos adjuntos** que aparece, configure las siguientes opciones:

   - En el **cuadro** Nombre, escriba `Block malware` y, a continuación, haga clic en **Siguiente**.

   - En la **Configuración,** configure las siguientes opciones:
     - En la **sección Caja fuerte datos adjuntos desconocidos** de respuesta de malware, elija **Bloquear**.
     - En la **sección Redirigir datos adjuntos,** seleccione la opción **Habilitar redireccionamiento**. Especifique la dirección de correo electrónico del administrador o operador de seguridad de la organización, que revisará los archivos detectados.

     Haga clic en **Siguiente**.

3. En  la página Aplicado **a,** haga clic en Agregar una condición, elija Aplicado **si:** El dominio de destinatario es , haga clic en Agregar **,** seleccione su dominio o dominios, haga clic en Agregar **,** haga clic en Listo y, a continuación, haga clic en **Siguiente**.

4. Revise la configuración y, a continuación, haga clic **en Finalizar**.

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Caja fuerte Vincula directivas en Microsoft Defender para Office 365

Para configurar vínculos [Caja fuerte,](safe-links.md)revise y edite la configuración global de Caja fuerte vínculos y cree al menos una directiva Caja fuerte vínculos.

1. En el [Centro de seguridad & cumplimiento,](https://protection.office.com)elija Directiva de administración de amenazas ATP Caja fuerte  \>  \> **Vínculos** y haga clic en Configuración **global** y, a continuación, configure las siguientes opciones:

   - Comprobar **Usar Caja fuerte vínculos en: Office 365 está** activada: Activar ![ ](../../media/scc-toggle-on.png) .
   - **No realizar un seguimiento cuando los usuarios hacen clic Caja fuerte vínculos:** desactive esta opción para realizar un seguimiento de los clics del usuario: ![ Desactivar ](../../media/scc-toggle-off.png) .
   - **No permitir que los usuarios hagan clic en vínculos seguros** a la dirección URL original: Compruebe que esta configuración está activada: ![ Activar ](../../media/scc-toggle-on.png) .

   Cuando haya terminado, haga clic en **Guardar**.

2. De nuevo en la página Caja fuerte vínculos principales, haga clic en **Crear**.

3. En el **Asistente para crear Caja fuerte de directivas de** vínculos que aparece, configure las siguientes opciones:

   - En el **cuadro** Nombre, escriba un nombre, como , y, a continuación, `Safe Links` haga clic en **Siguiente**.

   - En la **Configuración,** configure las siguientes opciones:
     - Seleccione la acción para direcciones URL **potencialmente malintencionadas desconocidas en mensajes**: Elija **Activar**.
     - **Seleccione la acción para las direcciones URL desconocidas** o potencialmente malintencionadas Microsoft Teams : Elija **Activar**.
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **Esperar a que se complete el examen de direcciones URL antes de entregar el mensaje**
     - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**
     - **No permitir que los usuarios hagan clic en la dirección URL original**

     Haga clic en **Siguiente**.

4. En  la página Aplicado **a,** haga clic en Agregar una condición, elija Aplicado **si:** El dominio de destinatario es , haga clic en Agregar **,** seleccione su dominio o dominios, haga clic en Agregar **,** haga clic en Listo y, a continuación, haga clic en **Siguiente**.

5. Revise la configuración y, a continuación, haga clic **en Finalizar**.

Para más información, consulte [Configurar directivas de vínculos seguros](set-up-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Parte 5: comprobar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams está activado

Las cargas de trabajo SharePoint, OneDrive y Teams se han creado para la colaboración. El uso de Defender para Office 365 ayuda a bloquear y detectar archivos que se identifican como malintencionados en sitios de grupo y bibliotecas de documentos. Puede leer más sobre cómo funciona [aquí](mdo-for-spo-odb-and-teams.md).

> [!IMPORTANT]
> **Antes de comenzar este procedimiento, asegúrese de** que el registro de auditoría ya está activado para el Microsoft 365 de auditoría. Esto lo suele hacer alguien que tenga el rol Registros de auditoría asignado en Exchange Online. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría!](../../compliance/turn-audit-log-search-on-or-off.md)

1. En el [Centro de & cumplimiento,](https://protection.office.com)elija **Administración** de amenazas ATP Caja fuerte \>  \> **datos adjuntos** y, a continuación, haga clic en **Configuración global**.

2. Compruebe que la alternancia Activar defender para Office 365 para **SharePoint, OneDrive** y Microsoft Teams está a la derecha: ![ Activar y, a continuación, haga clic en ](../../media/scc-toggle-on.png) **Guardar**.

3. Revise (y, según corresponda, edite) las directivas de datos adjuntos Caja fuerte [de](set-up-safe-attachments-policies.md) la organización y [Caja fuerte de vínculos](set-up-safe-links-policies.md).

4. (Recomendado) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro _DisallowInfectedFileDownload_ establecido en `$true` .

   - `$true` bloquea todas las acciones (excepto Eliminar) para los archivos detectados. Los usuarios no pueden abrir, mover, copiar ni compartir los archivos detectados.
   - `$false` bloquea todas las acciones excepto Eliminar y Descargar. Las personas pueden elegir aceptar el riesgo y descargar un archivo detectado.

   > [!TIP]
   > Para obtener más información acerca del uso de PowerShell con Microsoft 365, vea [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).

5. Permitir hasta 30 minutos para que los cambios se extienda a todos los Microsoft 365 centros de datos.

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
>- [Use el Centro de seguridad para administrar archivos en cuarentena en Defender para Office 365](manage-quarantined-messages-and-files.md#use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365)
>- [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Parte 6: opciones adicionales para configurar

Además de configurar la protección contra malware, direcciones URL malintencionadas y archivos, suplantación de identidad (phishing) y correo no deseado, se recomienda configurar la purga automática de cero horas.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Purga automática de hora cero para correo electrónico en EOP

[La purga automática](zero-hour-auto-purge.md) de hora cero (ZAP) está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). Esta protección está activada de forma predeterminada; sin embargo, deben cumplirse las siguientes condiciones para que la protección esté en vigor:

- Las acciones de correo no deseado se establecen **en Mover mensaje a carpeta correo no deseado** en directivas contra correo no [deseado.](anti-spam-protection.md)

- Los usuarios han mantenido su configuración predeterminada de [correo](configure-junk-email-settings-on-exo-mailboxes.md)no deseado y no han desactivado la protección de correo no deseado.

Para obtener más información, consulte [Zero-hour auto purge - protection against spam and malware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Tareas posteriores a la instalación y pasos siguientes

Después de configurar las características de protección contra amenazas, asegúrate de supervisar cómo funcionan esas características. Revise y revise las directivas para que hagan lo que necesita. Además, busque nuevas características y actualizaciones de servicio que puedan agregar valor.

****

|Qué hacer|Recursos para obtener más información|
|---|---|
|Vea cómo funcionan las características de protección contra amenazas para su organización mediante la visualización de informes|[Panel de seguridad](security-dashboard.md) <p> [Informes de seguridad de correo electrónico](view-email-security-reports.md) <p> [Informes para Microsoft Defender para Office 365](view-reports-for-mdo.md) <p> [Explorador de amenazas](threat-explorer.md)|
|Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario|[Puntuación de seguridad](../defender/microsoft-secure-score.md) <p> [Informes e información inteligentes](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 de investigación y respuesta de amenazas](./office-365-ti.md)|
|Buscar nuevas características y actualizaciones de servicio|[Opciones de versión estándar y dirigida](../../admin/manage/release-options-in-office-365.md) <p> [Centro de mensajes](../../admin/manage/message-center.md) <p> [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descripciones del servicio](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Obtenga información sobre las configuraciones de seguridad estándar y estricta recomendadas para EOP y Defender para Office 365|[Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md)|
