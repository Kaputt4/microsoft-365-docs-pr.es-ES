---
title: Proteger contra amenazas en Microsoft Defender para Office 365, antimalware, anti phishing, correo no deseado, vínculos de Caja fuerte, datos adjuntos de Caja fuerte, purga automática de hora cero (ZAP), configuración de seguridad de MDO
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
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
ms.openlocfilehash: 31ca7c27e3be20e20c16004490bd2ecd5ca4ae05
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083685"
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
>
> Para omitir la configuración manual de la mayoría de las directivas de Defender para Office 365, puedes usar directivas de seguridad preestablecidas en el nivel Estándar o Estricto. Para obtener más información, vea [Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md).

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Suscripciones

Las características de protección contra amenazas se *incluyen* en todas las suscripciones Office 365 Microsoft; sin embargo, algunas suscripciones tienen características avanzadas. En la tabla siguiente se enumeran las características de protección incluidas en este artículo junto con los requisitos mínimos de suscripción.

> [!TIP]
> Observe que más allá de las instrucciones para activar la *auditoría,* los pasos inician antimalware, anti phishing y antispam, que se marcan como parte de Office 365 Exchange Online Protection (**EOP**). Esto puede parecer extraño en un artículo defender para Office 365, hasta que recuerde (**Defender para Office 365**) contiene e incluye EOP.

<br>

****

|Tipo de protección|Requisitos de suscripción|
|---|---|
|Registro de auditoría (para fines de informes)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protección antimalware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protección contra phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra correo no deseado|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra direcciones URL malintencionadas y archivos en documentos Office correo electrónico (Caja fuerte vínculos y Caja fuerte adjuntos)|[Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roles y permisos

Para configurar Defender para Office 365 directivas, se le debe asignar un rol adecuado. Echa un vistazo a la tabla siguiente para ver los roles que pueden realizar estas acciones.

<br>

****

|Rol o grupo de roles|Dónde obtener más información|
|---|---|
|administrador global|[Acerca de los roles de administración de Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Administrador de seguridad|[Permisos de roles de administrador en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Administración de la organización en Exchange Online|[Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)|
|

Para obtener más información, vea [Permissions in the Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Activar el registro de auditoría para informes e investigación

- Inicie el registro de auditoría de forma anticipada. Necesitará que la auditoría esté **on** para algunos de los pasos siguientes. El registro de auditoría está disponible en suscripciones que incluyen [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para ver los datos en los informes de protección contra [amenazas,](view-email-security-reports.md)los informes de seguridad de correo electrónico y [el Explorador,](threat-explorer.md)el registro de auditoría debe ser *On*. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1: protección antimalware en EOP

Para obtener más información acerca de la configuración recomendada para antimalware, vea [EOP anti-malware policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).

1. Abra la **página Antimalware** en el portal de Microsoft 365 Defender en <https://security.microsoft.com/antimalwarev2> .

2. En la **página Antimalware,** seleccione la directiva denominada **Default (Default)** haciendo clic en el nombre.

3. En el control desplegable de detalles de directiva que se abre, haga clic en **Editar** configuración de protección y, a continuación, configure las siguientes opciones:
   - **Sección Configuración de** protección:
     - Seleccione **Habilitar el filtro de datos adjuntos** común para activar el filtro de datos adjuntos común. Haga **clic en Personalizar tipos de archivo** para agregar más tipos de archivo.
     - **Habilitar la purga automática de hora cero para malware:** compruebe que esta configuración está seleccionada. Para obtener más información acerca de ZAP para malware, vea [Zero-hour auto purge (ZAP) for malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).
   - **Sección notificación:** compruebe que no se haya seleccionado ninguna de las opciones de configuración de notificación.

   Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante de detalles de la directiva, haga clic en **Cerrar**.

Para obtener instrucciones detalladas para configurar directivas antimalware, vea [Configure anti-malware policies in EOP](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2: Protección contra la suplantación de identidad en EOP y Defender para Office 365

[La protección contra la suplantación](anti-phishing-protection.md) de identidad está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). La protección contra suplantación de identidad avanzada está disponible en [Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Para obtener más información acerca de la configuración recomendada para las directivas contra suplantación de identidad(phishing), consulte [EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) and [Anti-phishing policy settings in Microsoft Defender for Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

En el siguiente procedimiento se describe cómo configurar la directiva contra suplantación de identidad predeterminada. Configuración que solo están disponibles en Defender para Office 365 están claramente marcados.

1. Abra la **página Anti-phishing** en el portal Microsoft 365 Defender en <https://security.microsoft.com/antiphishing> .

2. En la **página Anti-phishing,** seleccione la directiva denominada **Office365 AntiPhish Default (Valor predeterminado)** haciendo clic en el nombre.

3. En el menú desplegable de detalles de la directiva que aparece, configure las siguientes opciones:
   - **Sección Protección contra &** de suplantación de identidad: haga clic en Editar configuración de protección y configure las siguientes opciones en el control desplegable que se abre: 
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

   - **Sección** Acciones: haga **clic en Editar acciones** y configure las siguientes opciones en el control desplegable que se abre:
     - **Sección Acciones de** mensaje: Configure las siguientes opciones:
       - **Si el mensaje se detecta como un usuario suplantado:** <sup>\*</sup> Seleccione Poner en cuarentena el **mensaje**.
       - **Si el mensaje se detecta como un dominio suplantado:** <sup>\*</sup> Seleccione Poner en cuarentena el **mensaje**.
       - **Si la inteligencia de buzones detecta un** usuario suplantado: seleccione Mover mensaje a las carpetas de correo no deseado (Estándar) de los destinatarios o Poner en cuarentena <sup>\*</sup> el **mensaje** (estricto). 
       - **Si el mensaje se detecta** como suplantación: seleccione Mover mensaje a las **carpetas** de correo no deseado (Estándar) de los destinatarios o Poner en cuarentena **el mensaje** (Estricto).
     - **Sugerencias de seguridad & de indicadores:** Configure las siguientes opciones:
       - **Mostrar el primer contacto consejo de seguridad**: Seleccionar (activar).
       - **Mostrar la suplantación de consejo de seguridad:** <sup>\*</sup> Seleccione (activar).
       - **Mostrar la suplantación de dominio consejo de seguridad** <sup>\*</sup> : Seleccionar (activar).
       - **Mostrar caracteres inusuales de suplantación de usuario consejo de seguridad** <sup>\*</sup> : Seleccionar (activar).
       - **Mostrar (?) para remitentes no** autenticados para suplantación de identidad: Seleccione (activar).
       - **Mostrar etiqueta "via":** Seleccionar (activar).

     Cuando haya terminado, haga clic en **Guardar**.

   <sup>\*</sup>Esta configuración solo está disponible en Defender para Office 365.

4. Haga **clic en Guardar** y, a continuación, en **Cerrar**

Para obtener instrucciones detalladas para configurar directivas contra suplantación de identidad, vea [Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md) y [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection-in-eop"></a>Parte 3: Protección contra correo no deseado en EOP

Para obtener más información acerca de la configuración recomendada para el correo no deseado, vea Configuración de la directiva contra correo no deseado de [EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

1. Abra la **página Directivas contra correo** no deseado en el portal Microsoft 365 Defender en <https://security.microsoft.com/antispam> .

2. En la **página Directivas contra correo** no deseado, seleccione la directiva denominada Directiva de entrada contra correo no deseado **(Predeterminada)** de la lista haciendo clic en el nombre.

3. En el menú desplegable de detalles de la directiva que aparece, configure las siguientes opciones:
   - **Sección De umbral de correo & correo** no deseado masivo: Haga clic en Editar umbral de correo no deseado y **propiedades**. En el menú desplegable que aparece, configure las siguientes opciones:
     - **Umbral de correo** electrónico masivo: establezca este valor en 5 (Estricto) o 6 (Estándar).
     - Deje otras configuraciones en sus valores predeterminados (**Off** o **None**).

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección Acciones:** Haga clic **en Editar acciones**. En el menú desplegable que aparece, configure las siguientes opciones:
     - **Sección Acciones del** mensaje:
       - **Correo no** deseado: compruebe **que mover el mensaje** a la carpeta correo no deseado está seleccionado (estándar) o seleccione Mensaje de **cuarentena (estricto).**
       - **Correo no deseado de elevada** **confianza:** seleccione Mensaje en cuarentena .
       - **Suplantación de identidad**: Seleccione **Mensaje en cuarentena**.
       - **Phishing de elevada confianza:** compruebe que **los mensajes de cuarentena** están seleccionados.
       - **Masivo:** compruebe **que mover el mensaje a la** carpeta de correo no deseado está seleccionado (Estándar) o seleccione Mensaje de cuarentena **(estricto).**
     - Conservar el correo no deseado **en cuarentena durante estos días:** compruebe el valor **30** días.
     - **Habilitar sugerencias de seguridad contra correo** no deseado: compruebe que esta configuración está seleccionada (activada).
     - Habilitar la purga automática de hora **cero (ZAP):** compruebe que esta configuración está seleccionada (activada).
       - **Habilitar para mensajes de suplantación de** identidad : Compruebe que esta configuración está seleccionada (activada). Para obtener más información, vea [Zero-hour auto purge (ZAP) for phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).
       - **Habilitar para mensajes de correo no** deseado: compruebe que esta configuración está seleccionada (activada). Para obtener más información, vea [Zero-hour auto purge (ZAP) for spam](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).
     - **Sección Notificaciones:**
       - Seleccione **Habilitar notificaciones de correo no deseado del usuario final**.
         - Enviar notificaciones de correo no deseado del usuario **final cada (días):** Compruebe el valor **3** días.
         - **Idioma:** compruebe el valor **Predeterminado** o seleccione un idioma.

     Cuando haya terminado, haga clic en **Guardar**.

   - Sección Remitentes y dominios permitidos y bloqueados: Revise o edite los remitentes permitidos y los dominios permitidos como se describe en Crear listas de **remitentes bloqueados** en [EOP](create-block-sender-lists-in-office-365.md) o Crear listas de remitentes seguros [en EOP.](create-safe-sender-lists-in-office-365.md)

     Cuando haya terminado, haga clic en **Guardar**.

4. Cuando haya terminado, haga clic en **Cerrar**.

Para obtener instrucciones detalladas para configurar directivas contra correo no deseado, vea [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4: protección contra archivos y direcciones URL malintencionadas (Caja fuerte vínculos y Caja fuerte datos adjuntos en Defender para Office 365)

La protección con tiempo de clic frente a direcciones URL y archivos malintencionados está disponible en suscripciones que incluyen [Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se configura a través de Caja fuerte [datos adjuntos y](safe-attachments.md) [Caja fuerte de vínculos.](safe-links.md)

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Caja fuerte Directivas de datos adjuntos en Microsoft Defender para Office 365

Para obtener más información acerca de la configuración recomendada para Caja fuerte datos adjuntos, vea . [Caja fuerte de datos adjuntos](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

1. Abra la **página Caja fuerte datos adjuntos** en el portal Microsoft 365 Defender en <https://security.microsoft.com/safeattachmentv2> .

2. En la **página Caja fuerte datos adjuntos,** haga clic en **Configuración global** y, a continuación, configure las siguientes opciones en el menú desplegable que aparece:
   - **Activa Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams**: Activa esta opción ( ![ Activar ](../../media/scc-toggle-on.png) ).

     > [!IMPORTANT]
     > Antes de activar Caja fuerte datos adjuntos para **SharePoint, OneDrive y Microsoft Teams,** compruebe que el registro de auditoría esté activado en la organización . Normalmente, esta acción la realiza alguien que tiene el rol Registros de auditoría asignado en Exchange Online. Para obtener más información, vea Activar o desactivar la búsqueda [del registro de auditoría!](../../compliance/turn-audit-log-search-on-or-off.md)

   - **Activar documentos Caja fuerte para clientes Office**: Active esta opción ( Activar ![ ](../../media/scc-toggle-on.png) ). Tenga en cuenta que esta característica solo está disponible y es significativa Microsoft 365 E5 o Seguridad de Microsoft 365 E5 licencias.
   - **Permitir a los usuarios hacer clic** en la vista protegida incluso si Caja fuerte documentos identificaron el archivo como malintencionado : Compruebe que esta configuración está desactivada ( ![ Desactivar ](../../media/scc-toggle-off.png) ).

   Cuando haya terminado, haga clic en **Guardar**

3. En la página **Caja fuerte datos adjuntos,** haga clic ![ en Crear icono ](../../media/m365-cc-sc-create-icon.png) .

4. En el **Asistente para crear Caja fuerte de directivas de** datos adjuntos que se abre, configure las siguientes opciones:
   - **Asigne un nombre a la página de** directiva:
     - **Nombre:** escriba algo único y descriptivo.
     - **Descripción:** escriba una descripción opcional.
   - **Página Usuarios y dominios:** dado que esta es la primera directiva y es probable que quiera maximizar la cobertura, considere la posibilidad de escribir los dominios aceptados [en](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) el **cuadro** Dominios. De lo contrario, puede usar los **cuadros Usuarios** **y** Grupos para un control más detallado. Puede especificar excepciones seleccionando Excluir estos **usuarios, grupos y dominios** y especificando valores.
   - **Configuración:**
     - **Caja fuerte datos adjuntos respuesta de malware desconocido:** Seleccione **Bloquear**.
     - **Redirigir datos adjuntos con datos** adjuntos detectados: **Habilitar** redireccionamiento: Active esta opción (seleccionar) e introduzca una dirección de correo electrónico para recibir los mensajes detectados.
     - Aplicar la Caja fuerte de detección de datos adjuntos si el examen no se puede **completar (tiempo** de espera o errores): compruebe que esta configuración está seleccionada.

5. Cuando haya terminado, haga clic en **Enviar** y, a continuación, haga clic **en Listo.**

6. (Recomendado) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro _DisallowInfectedFileDownload_ establecido en `$true` en SharePoint PowerShell en línea.
   - `$true` bloquea todas las acciones (excepto Eliminar) para los archivos detectados. Las personas no pueden abrir, mover, copiar o compartir archivos detectados.
   - `$false` bloquea todas las acciones excepto Eliminar y Descargar. Las personas pueden elegir aceptar el riesgo y descargar un archivo detectado.

7. Permitir hasta 30 minutos para que los cambios se extienda a todos los Microsoft 365 centros de datos.

Para obtener instrucciones detalladas para configurar las directivas de Caja fuerte datos adjuntos y la configuración global para Caja fuerte datos adjuntos, consulte los siguientes temas:

- [Configurar directivas Caja fuerte datos adjuntos en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md)
- [Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Documentos seguros en Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Caja fuerte Vincula directivas en Microsoft Defender para Office 365

Para obtener más información acerca de la configuración recomendada para Caja fuerte links, vea [Caja fuerte links settings](recommended-settings-for-eop-and-office365.md#safe-links-settings).

1. Abra la **página Caja fuerte vínculos** en el portal Microsoft 365 Defender en <https://security.microsoft.com/safelinksv2> .

2. En la **página Caja fuerte,** haga clic en **Configuración global** y, a continuación, configure las siguientes opciones en el menú desplegable que aparece:
   - **Configuración que se aplican al contenido de la sección Office 365 aplicaciones compatibles:**
     - **Usa Caja fuerte vínculos en Office 365** aplicaciones: comprueba que esta configuración está activada ( ![ Activar ](../../media/scc-toggle-on.png) ).
     - **No realizar un seguimiento cuando los usuarios hacen clic en vínculos protegidos en Office 365** aplicaciones : Desactive esta opción ( ![ Desactivar ](../../media/scc-toggle-off.png) )
     - **No permitir que los usuarios hagan clic en la dirección URL original** en Office 365 aplicaciones : Compruebe que esta configuración está activada ( Activar ![ ](../../media/scc-toggle-on.png) ).

   Cuando haya terminado, haga clic en **Guardar**

3. En la página **Vínculos Caja fuerte,** haga clic ![ en Crear icono ](../../media/m365-cc-sc-create-icon.png) .

4. En el **Asistente para crear Caja fuerte de directivas de** vínculos que se abre, configure las siguientes opciones:
   - **Asigne un nombre a la página de** directiva:
     - **Nombre:** escriba algo único y descriptivo.
     - **Descripción:** escriba una descripción opcional.
   - **Página Usuarios y dominios:** dado que esta es la primera directiva y es probable que quiera maximizar la cobertura, considere la posibilidad de escribir los dominios aceptados [en](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) el **cuadro** Dominios. De lo contrario, puede usar los **cuadros Usuarios** **y** Grupos para un control más detallado. Puede especificar excepciones seleccionando Excluir estos **usuarios, grupos y dominios** y especificando valores.
   - **Página Configuración de** protección:
     - Seleccione la acción para direcciones URL **potencialmente malintencionadas desconocidas** en mensajes : Active esta **opción**.
     - **Seleccione la acción para las direcciones** URL desconocidas o potencialmente malintencionadas en Microsoft Teams : Active esta **configuración**. A partir de marzo de 2020, esta configuración está en Versión preliminar y solo está disponible o funcional para los miembros de la Microsoft Teams Programa de adopción de tecnología (TAP).
     - **Aplicar análisis de url en tiempo real en busca** de vínculos sospechosos y vínculos que apunten a archivos: Seleccione esta opción (activar).
       - **Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**: Seleccione esta configuración (activar).
     - **Aplicar Caja fuerte vínculos a los mensajes de correo electrónico** enviados dentro de la organización: Seleccione esta opción (activar).
     - **No realizar un seguimiento de los clics del usuario:** compruebe que esta configuración no está seleccionada (desactivada).
     - **No permitir que los usuarios hagan clic en la dirección URL original:** Compruebe que esta configuración está activada (seleccionada).
     - **Mostrar** la personalización de marca de la organización en las páginas de notificación y advertencia: seleccionar esta configuración (activarla) es significativa solo después de haber seguido las instrucciones de Personalizar el tema [Microsoft 365](../../admin/setup/customize-your-organization-theme.md) para que la organización cargue el logotipo de la empresa.
     - **No reescriba las siguientes direcciones URL:** no tenemos ninguna recomendación específica para esta configuración. Para obtener más información, vea ["Do not rewrite the following URLs" lists in Caja fuerte Links policies](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).
   - **Página de** notificación:
     - **¿Cómo le gustaría notificar a los usuarios?** sección: Opcionalmente, puede seleccionar Usar **texto de** notificación personalizado para escribir el texto de notificación personalizado que se va a usar. También puede seleccionar **Usar Traductor de Microsoft** la localización automática para traducir el texto de notificación personalizado al idioma del usuario. De lo contrario, **deje seleccionado Usar el texto de notificación predeterminado.**

5. Cuando haya terminado, haga clic en **Enviar** y, a continuación, haga clic **en Listo.**

Para obtener instrucciones detalladas para configurar Caja fuerte de vínculos y la configuración global para Caja fuerte vínculos, consulte los siguientes temas:

- [Configurar directivas Caja fuerte vínculos en Microsoft Defender para Office 365](set-up-safe-links-policies.md)
- [Configurar la configuración global para Caja fuerte vínculos en Microsoft Defender para Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Ahora configura alertas para los archivos detectados en SharePoint Online o OneDrive para la Empresa

Para recibir una notificación cuando un archivo de SharePoint Online o OneDrive para la Empresa se haya identificado como malintencionado, puede configurar una alerta como se describe en esta sección.

1. En el portal Microsoft 365 Defender en , vaya a <https://security.microsoft.com> **Correo electrónico &** \> **colaboración Directivas & reglas de** \> **alerta**.

2. En la página **Directiva de alertas,** haga clic **en Nueva directiva de alerta**.

3. Se **abrirá el Asistente para nueva directiva de** alerta. En la **página** Nombre, configure las siguientes opciones:
   - **Nombre:** escriba un nombre único y descriptivo. Por ejemplo, puede escribir Archivos malintencionados en bibliotecas.
   - **Descripción:** escriba una descripción opcional.
   - **Gravedad:** Seleccione **Bajo,** **Medio** o **Alto**.
   - **Categoría:** Seleccione **Administración de amenazas**.

   Cuando haya terminado, haga clic en **Siguiente**

4. En la **página Crear configuración de alerta,** configure las siguientes opciones:
   - **¿En qué desea alertar?** sección: **La actividad es** Malware detectado en el \> **archivo**.
   - **Sección Cómo desea que se desencadene la** alerta: Compruebe cada vez que una **actividad coincida con la regla** seleccionada.

   Cuando haya terminado, haga clic en **Siguiente**

5. En la **página Establecer los destinatarios,** configure las siguientes opciones:
   - **Enviar notificaciones por correo** electrónico: compruebe que esta configuración está secmentada.
   - **Destinatarios de correo** electrónico: seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir notificaciones cuando se detecte un archivo malintencionado.
   - **Límite de notificación diario:** compruebe **que no hay** ningún límite seleccionado.

   Cuando haya terminado, haga clic en **Siguiente**

6. En la **página Revisar la configuración,** revise la configuración, compruebe **que Sí,** activarla inmediatamente está seleccionada y, a continuación, haga clic en **Finalizar**

Para obtener más información acerca de las directivas de alerta, vea [Directivas de alerta en el Centro de cumplimiento de Microsoft 365](../../compliance/alert-policies.md).

> [!NOTE]
> Cuando haya terminado de configurar, use estos vínculos para iniciar investigaciones de carga de trabajo:
>
>- [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
>- [Use el portal Microsoft 365 Defender para administrar archivos en cuarentena en Defender para Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Administrar mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Tareas posteriores a la instalación y pasos siguientes

Después de configurar las características de protección contra amenazas, asegúrate de supervisar cómo funcionan esas características. Revise y revise las directivas para que hagan lo que necesita. Además, busque nuevas características y actualizaciones de servicio que puedan agregar valor.

<br>

****

|Qué hacer|Recursos para obtener más información|
|---|---|
|Vea cómo funcionan las características de protección contra amenazas para su organización mediante la visualización de informes|[Informes de seguridad de correo electrónico](view-email-security-reports.md) <p> [Informes para Microsoft Defender para Office 365](view-reports-for-mdo.md) <p> [Explorador de amenazas](threat-explorer.md)|
|Revisar y revisar periódicamente las directivas de protección contra amenazas según sea necesario|[Puntuación de seguridad](../defender/microsoft-secure-score.md) <p> [Microsoft 365 de investigación y respuesta de amenazas](./office-365-ti.md)|
|Buscar nuevas características y actualizaciones de servicio|[Opciones de versión estándar y dirigida](../../admin/manage/release-options-in-office-365.md) <p> [Centro de mensajes](../../admin/manage/message-center.md) <p> [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descripciones del servicio](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
