---
title: Protección contra amenazas en Microsoft Defender para Office 365, Antimalware, Anti-Phishing, Anti-spam, Vínculos seguros, Datos adjuntos seguros, Purga automática de cero horas (ZAP), configuración de seguridad de MDO
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.localizationpriority: medium
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- m365-security
- m365initiative-defender-office365
description: Los administradores pueden obtener información sobre la protección contra amenazas en Microsoft 365 y configurar cómo usarla para su organización.
ms.custom: seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: d6f832205c49d56f5b80092e115ffa79277c9e12
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68079939"
---
# <a name="protect-against-threats"></a>Protección contra amenazas

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Esta es una guía de inicio rápido que divide la configuración de Defender para Office 365 en fragmentos. Si no está familiarizado con las características de protección contra amenazas en Office 365, no esté seguro de dónde empezar o si aprende mejor *si lo hace*, use esta guía como lista de comprobación y punto de partida.

> [!IMPORTANT]
> **La configuración recomendada inicial se incluye para cada tipo de directiva; sin embargo, hay muchas opciones disponibles y puede ajustar la configuración para satisfacer las necesidades específicas de su organización**. Espere aproximadamente 30 minutos para que las directivas o los cambios funcionen a través del centro de datos.
>
> Para omitir la configuración manual de la mayoría de las directivas de Defender para Office 365, puede usar directivas de seguridad preestablecidas en el nivel Estándar o Estricto. Para obtener más información, vea [Directivas de seguridad preestablecidas en EOP y Microsoft Defender para Office 365](preset-security-policies.md).

## <a name="requirements"></a>Requisitos

### <a name="subscriptions"></a>Suscripciones

Las características de protección contra amenazas se incluyen en *todas las* suscripciones de Microsoft o Office 365; sin embargo, algunas suscripciones tienen características avanzadas. En la tabla siguiente se enumeran las características de protección incluidas en este artículo junto con los requisitos mínimos de suscripción.

> [!TIP]
> Tenga en cuenta que más allá de las instrucciones para activar la auditoría, *los pasos* inician el antimalware, la suplantación de identidad (phishing) y el correo no deseado, que se marcan como parte de Office 365 Exchange Online Protection (**EOP**). Esto puede parecer extraño en un artículo de Defender para Office 365, hasta que recuerde (**Defender para Office 365**) contiene y se basa en EOP.

|Tipo de protección|Requisitos de suscripción|
|---|---|
|Registro de auditoría (con fines de informes)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Protección antimalware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Protección contra phishing|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra correo no deseado|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Protección contra direcciones URL y archivos malintencionados en el correo electrónico y documentos de Office (vínculos seguros y datos adjuntos seguros)|[Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Roles y permisos

Para configurar directivas de Defender para Office 365, se le debe asignar un rol adecuado. Eche un vistazo a la tabla siguiente para ver los roles que pueden realizar estas acciones.

|Rol o grupo de roles|Dónde obtener más información|
|---|---|
|administrador global|[Acerca de los roles de administración de Microsoft 365](../../admin/add-users/about-admin-roles.md)|
|Administrador de seguridad|[Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference#security-administrator)
|Administración de la organización en Exchange Online|[Permisos de Exchange Online](/exchange/permissions-exo/permissions-exo)|

Para más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Activar el registro de auditoría para informes e investigaciones

- Inicie el registro de auditoría con antelación. Necesitará que la auditoría esté **activada** para algunos de los pasos siguientes. El registro de auditoría está disponible en suscripciones que incluyen [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description). Para ver los datos en los informes de protección contra amenazas, [los informes de seguridad de correo electrónico](view-email-security-reports.md) y [el Explorador](threat-explorer.md), el registro de auditoría debe estar *activado*. Para obtener más información, consulte [Activar o desactivar la búsqueda en el registro de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection-in-eop"></a>Parte 1: Protección contra malware en EOP

Para obtener más información sobre la configuración recomendada para el antimalware, consulte [Configuración de directivas antimalware de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings).

1. Abra la página **Antimalware** en el portal de Microsoft 365 Defender en <https://security.microsoft.com/antimalwarev2>.

2. En la página **Antimalware**, haga clic en el nombre para seleccionar la directiva denominada **Predeterminada (predeterminada).**

3. En el control flotante de detalles de la directiva que se abre, haga clic en **Editar configuración de protección** y, a continuación, configure las siguientes opciones:
   - **Sección configuración de protección** :
     - **Habilitar el filtro de datos adjuntos comunes**: seleccione (activar). Haga clic en **Personalizar tipos de archivo** para agregar más tipos de archivo.
     - **Habilitar la purga automática de cero horas para malware**: compruebe que esta configuración está seleccionada. Para obtener más información sobre ZAP para malware, consulte [Purga automática de cero horas (ZAP) para malware](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware).
   - **Directiva de cuarentena**: deje seleccionado el valor predeterminado AdminOnlyAccessPolicy. Las directivas de cuarentena definen qué pueden hacer los usuarios en los mensajes en cuarentena y si los usuarios reciben notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).
   - **Sección de notificación** : compruebe que no se ha seleccionado ninguna de las opciones de notificación.

   Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante de detalles de la directiva, haga clic en **Cerrar**.

Para obtener instrucciones detalladas para configurar directivas antimalware, consulte [Configurar directivas antimalware en EOP](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Parte 2: Protección contra suplantación de identidad en EOP y Defender para Office 365

[La protección contra suplantación de identidad](anti-phishing-protection.md) está disponible en suscripciones que incluyen [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description). La protección contra suplantación de identidad avanzada está disponible en [Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).

Para obtener más información sobre la configuración recomendada para las directivas contra suplantación de identidad (phishing), consulte [Configuración de directivas contra suplantación de identidad (EOP)](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) y [Configuración de directivas anti phishing en Microsoft Defender para Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

En el procedimiento siguiente se describe cómo configurar la directiva de anti phishing predeterminada. La configuración que solo está disponible en Defender para Office 365 está marcada claramente.

1. Abra la página **Anti-phishing** en el portal de Microsoft 365 Defender en <https://security.microsoft.com/antiphishing>.

2. En la página **Anti-phishing** , seleccione la directiva denominada **Office365 AntiPhish Default (Predeterminado)** haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, configure los siguientes valores:
   - Sección **Umbral de suplantación de identidad (phishing) & protección**: haga clic en **Editar configuración de protección** y configure las siguientes opciones en el control flotante que se abre:
     - Umbral <sup>\*</sup>de **correo electrónico de suplantación de identidad**: seleccione **2 : agresivo** (estándar) o **3: más agresivo** (estricto).
     - Sección <sup>\*</sup> **Suplantación**: Configure los valores siguientes:
       - Seleccione **Habilitar la protección de los usuarios**, haga clic en el vínculo **Administrar (nn) remitentes** que aparece y, a continuación, agregue remitentes internos y externos para protegerse de la suplantación, como los miembros del consejo de la organización, el director general, el director financiero y otros líderes sénior.
       - Seleccione **Habilitar dominios para proteger** y, a continuación, configure los siguientes valores que aparecen:
         - Seleccione **Incluir dominios de mi propiedad** para proteger a los remitentes internos de los dominios aceptados (visibles haciendo clic en **Ver mis dominios**) de la suplantación.
         - Para proteger a los remitentes en otros dominios, seleccione **Incluir dominios personalizados**, haga clic en el vínculo **Administrar (nn) dominios personalizados** que aparece y, a continuación, agregue otros dominios para protegerlos de la suplantación.
     - Sección <sup>\*</sup> **Agregar remitentes y dominios de confianza**: haga clic en **Administrar (nn) remitentes y dominios de confianza** para configurar excepciones de dominio de remitente y remitente para la protección de suplantación si es necesario.
     - Configuración de inteligencia de <sup>\*</sup> buzones de correo: compruebe que **habilitar la inteligencia de buzones** y **habilitar la inteligencia para la protección de suplantación** está seleccionado.
     - **Sección de suplantación de identidad** : compruebe que **la opción Habilitar inteligencia de suplantación** está seleccionada.

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección Acciones** : haga clic en **Editar acciones** y configure los siguientes valores en el control flotante que se abre:
     - **Sección Acciones del mensaje** : Configure las siguientes opciones:
       - **Si el mensaje se detecta como un usuario**<sup>\*</sup> suplantado: seleccione **Poner en cuarentena el mensaje**. Aparece un cuadro **Aplicar directiva de cuarentena** donde se selecciona la [directiva de cuarentena](quarantine-policies.md) que se aplica a los mensajes que están en cuarentena por la protección de suplantación de usuario.
       - **Si el mensaje se detecta como un dominio**<sup>\*</sup> suplantado: seleccione **Poner en cuarentena el mensaje**. Aparece un cuadro **Aplicar directiva de cuarentena** donde se selecciona la [directiva de cuarentena](quarantine-policies.md) que se aplica a los mensajes que están en cuarentena por la protección de suplantación de dominio.
       - **Si la inteligencia del buzón detecta un usuario**<sup>\*</sup> suplantado: seleccione **Mover mensaje a las carpetas de Email no deseados** (Estándar) de los destinatarios o **Poner en cuarentena el mensaje** (Estricto). Si selecciona **Poner en cuarentena el mensaje**, aparece un cuadro **Aplicar directiva de cuarentena** donde selecciona la [directiva de cuarentena](quarantine-policies.md) que se aplica a los mensajes que están en cuarentena por la protección de inteligencia del buzón de correo.
       - **Si el mensaje se detecta como suplantación de identidad**: seleccione **Mover mensaje a las carpetas de Email no deseados** (Estándar) de los destinatarios o **Poner en cuarentena el mensaje** (Estricto).  Si selecciona **Poner en cuarentena el mensaje**, aparece un cuadro **Aplicar directiva de cuarentena** donde selecciona la [directiva de cuarentena](quarantine-policies.md) que se aplica a los mensajes que están en cuarentena mediante la protección de inteligencia contra suplantación de identidad.
     - **Sugerencias de seguridad & sección indicadores** : Configure los siguientes valores:
       - **Mostrar la primera sugerencia de seguridad de contacto**: seleccione (activar).
       - Mostrar sugerencia <sup>\*</sup>de **seguridad de suplantación de usuario**: seleccione (activar).
       - Mostrar sugerencia <sup>\*</sup>de **seguridad de suplantación de dominio**: seleccione (activar).
       - Mostrar sugerencia <sup>\*</sup>de **seguridad de caracteres inusuales de suplantación de usuario**: seleccione (activar).
       - **Mostrar (?) para remitentes no autenticados para la suplantación de identidad**: seleccione (activar).
       - **Mostrar etiqueta "via"**: seleccione (activar).

     Cuando haya terminado, haga clic en **Guardar**.

   <sup>\*</sup>Esta configuración solo está disponible en Defender para Office 365.

4. Haga clic en **Guardar** y, a continuación, en **Cerrar.**

Para obtener instrucciones detalladas sobre cómo configurar directivas de anti phishing, consulte [Configurar directivas contra suplantación de identidad en EOP](configure-anti-phishing-policies-eop.md) y [Configurar directivas contra suplantación de identidad en Microsoft Defender para Office 365](configure-mdo-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection-in-eop"></a>Parte 3: Protección contra correo no deseado en EOP

Para obtener más información sobre la configuración recomendada para la protección contra correo no deseado, consulte [Configuración de directivas contra correo no deseado de EOP](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings).

1. Abra la página **Directivas contra correo no deseado** en el portal de Microsoft 365 Defender en <https://security.microsoft.com/antispam>.

2. En la página **Directivas contra correo no deseado** , seleccione la directiva denominada **Directiva de entrada antispam (predeterminada)** de la lista haciendo clic en el nombre.

3. En el control flotante de detalles de la directiva que aparece, configure los siguientes valores:
   - **Umbral de correo electrónico masivo & sección de propiedades de correo no deseado** : haga clic en **Editar umbral y propiedades de correo no deseado**. En el control flotante que aparece, configure los siguientes valores:
     - **Umbral de correo electrónico masivo**: establezca este valor en 5 (Estricto) o 6 (Estándar).
     - Deje otras opciones en sus valores predeterminados (**Desactivado** o **Ninguno**).

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección Acciones** : haga clic en **Editar acciones**. En el control flotante que aparece, configure los siguientes valores:
     - **Sección Acciones del mensaje** :
       - **Correo no deseado**: compruebe que **la opción Mover mensaje a la carpeta de Email no deseado** está seleccionada (Estándar) o seleccione **Mensaje de cuarentena** (Estricto).
       - **Correo no deseado de alta confianza**: seleccione **Mensaje de cuarentena**.
       - **Phishing**: seleccione **Mensaje de cuarentena**.
       - **Suplantación de identidad de alta confianza**: compruebe que los **mensajes de cuarentena** están seleccionados.
       - **Masivo**: compruebe que **la opción Mover mensaje a la carpeta Email no deseado** está seleccionada (Estándar) o seleccione **Mensaje de cuarentena** (Estricto).

       Para cada acción en la que seleccione **Mensaje de cuarentena**, aparece un cuadro **Seleccionar directiva de cuarentena** donde selecciona la directiva de [cuarentena](quarantine-policies.md) que se aplica a los mensajes que están en cuarentena por la protección contra correo no deseado.

     - **Conservar el correo no deseado en cuarentena durante estos muchos días**: compruebe el valor **30** días.
     - **Habilitar sugerencias de seguridad de correo no deseado**: compruebe que esta configuración está seleccionada (activada).
     - **Habilitar la purga automática de cero horas (ZAP):** compruebe que esta configuración está seleccionada (activada).
       - **Habilitar para mensajes de suplantación de identidad (phishing**): compruebe que esta configuración está seleccionada (activada). Para obtener más información, consulte [Purga automática de cero horas (ZAP) para phishing](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing).
       - **Habilitar para mensajes de correo no deseado**: compruebe que esta configuración está seleccionada (activada). Para obtener más información, consulte [Purga automática de cero horas (ZAP) para correo no deseado](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam).

     Cuando haya terminado, haga clic en **Guardar**.

   - **Sección De remitentes y dominios permitidos y bloqueados** : revise o edite los remitentes permitidos y los dominios permitidos, como se describe en [Creación de listas de remitentes bloqueados en EOP](create-block-sender-lists-in-office-365.md) o [Creación de listas de remitentes seguros en EOP](create-safe-sender-lists-in-office-365.md).

     Cuando haya terminado, haga clic en **Guardar**.

4. Cuando haya terminado, haga clic en **Cerrar**.

Para obtener instrucciones detalladas para configurar directivas contra correo no deseado, consulte [Configurar directivas contra correo no deseado en EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Parte 4: Protección contra direcciones URL y archivos malintencionados (vínculos seguros y datos adjuntos seguros en Defender para Office 365)

La protección con tiempo de clic frente a direcciones URL y archivos malintencionados está disponible en suscripciones que incluyen [Microsoft Defender para Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description). Se configura a través de [directivas de datos adjuntos seguros](safe-attachments.md) y [vínculos seguros](safe-links.md) .

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Directivas de datos adjuntos seguros en Microsoft Defender para Office 365

Para obtener más información sobre la configuración recomendada para datos adjuntos seguros, vea . [Configuración de datos adjuntos seguros](recommended-settings-for-eop-and-office365.md#safe-attachments-settings).

1. Abra la página **Datos adjuntos seguros** en el portal de Microsoft 365 Defender en <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Datos adjuntos seguros** , haga clic en **Configuración global** y, a continuación, configure las siguientes opciones en el control flotante que aparece:
   - **Active Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams**: active esta opción (![activar).](../../media/scc-toggle-on.png)

     > [!IMPORTANT]
     > **Antes de activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, compruebe que el registro de auditoría está activado en su organización**. Normalmente, esta acción la realiza alguien que tiene asignado el rol Registros de auditoría en Exchange Online. Para obtener más información, vea [Activar o desactivar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

   - **Activar documentos seguros para clientes de Office**: active esta opción (![activar).](../../media/scc-toggle-on.png) Tenga en cuenta que esta característica solo está disponible y es significativa con los tipos de licencia necesarios. Para obtener más información, consulte [Documentos seguros en Microsoft 365 E5](safe-docs.md).
   - **Permitir a los usuarios hacer clic en la vista protegida incluso si documentos seguros identificaron el archivo como malintencionado**: compruebe que esta configuración está desactivada (![Desactivar).](../../media/scc-toggle-off.png)

   Cuando haya terminado, haga clic en **Guardar.**

3. De nuevo en la página **Datos adjuntos seguros**, haga clic en ![el icono Crear.](../../media/m365-cc-sc-create-icon.png)

4. En el Asistente para **crear directivas de datos adjuntos seguros** que se abre, configure los siguientes valores:
   - **Asigne un nombre a la página de directiva** :
     - **Nombre**: escriba algo único y descriptivo.
     - **Descripción**: escriba una descripción opcional.
   - **Página Usuarios y dominios** : dado que esta es la primera directiva y es probable que quiera maximizar la cobertura, considere la posibilidad de escribir [los dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en el cuadro **Dominios** . De lo contrario, puede usar los cuadros **Usuarios** y **grupos** para un control más pormenorizado. Para especificar excepciones **, seleccione Excluir estos usuarios, grupos y dominios** y escriba valores.
   - **Página Configuración** :
     - **Respuesta de malware desconocida de datos adjuntos seguros**: seleccione **Bloquear**.
     - **Directiva de cuarentena**: el valor predeterminado está en blanco, lo que significa que se usa la directiva AdminOnlyAccessPolicy. Las directivas de cuarentena definen qué pueden hacer los usuarios en los mensajes en cuarentena y si los usuarios reciben notificaciones de cuarentena. Para más información, vea [Directivas de cuarentena](quarantine-policies.md).
     - **Redireccionamiento de datos adjuntos con datos adjuntos detectados** : **habilite el redireccionamiento**: active esta configuración (seleccione) y escriba una dirección de correo electrónico para recibir los mensajes detectados.
     - **Aplique la respuesta de detección de datos adjuntos seguros si el examen no se puede completar (tiempo de espera o errores):** compruebe que esta configuración está seleccionada.

5. Cuando haya terminado, haga clic en **Enviary**, a continuación, haga clic en **Listo**.

6. (Recomendado) Como administrador global o administrador de SharePoint Online, ejecute el cmdlet **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** con el parámetro _DisallowInfectedFileDownload_ establecido `$true` en en PowerShell de SharePoint Online.
   - `$true` bloquea todas las acciones (excepto Eliminar) para los archivos detectados. Personas no puede abrir, mover, copiar ni compartir los archivos detectados.
   - `$false` bloquea todas las acciones excepto Eliminar y Descargar. Personas puede optar por aceptar el riesgo y descargar un archivo detectado.

7. Espere hasta 30 minutos para que los cambios se distribuyan a todos los centros de datos de Microsoft 365.

Para obtener instrucciones detalladas sobre cómo configurar directivas de datos adjuntos seguros y opciones globales para datos adjuntos seguros, consulte los temas siguientes:

- [Configuración de directivas de datos adjuntos seguros en Microsoft Defender para Office 365](set-up-safe-attachments-policies.md)
- [Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Documentos seguros en Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Directivas de vínculos seguros en Microsoft Defender para Office 365

Para obtener más información sobre la configuración recomendada para Vínculos seguros, consulte [Configuración de vínculos seguros](recommended-settings-for-eop-and-office365.md#safe-links-settings).

1. Abra la página **Vínculos seguros** en el portal de Microsoft 365 Defender en y, a <https://security.microsoft.com/safelinksv2>continuación, haga clic en ![Crear icono.](../../media/m365-cc-sc-create-icon.png)

2. En el Asistente para **crear directivas de vínculos seguros** que se abre, configure los siguientes valores:
   - **Asigne un nombre a la página de directiva** :
     - **Nombre**: escriba algo único y descriptivo.
     - **Descripción**: escriba una descripción opcional.
   - **Página Usuarios y dominios** : dado que esta es la primera directiva y es probable que quiera maximizar la cobertura, considere la posibilidad de escribir [los dominios aceptados](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) en el cuadro **Dominios** . De lo contrario, puede usar los cuadros **Usuarios** y **grupos** para un control más pormenorizado. Para especificar excepciones **, seleccione Excluir estos usuarios, grupos y dominios** y escriba valores.
   - **Url & página configuración de protección** :
     - **Acción en direcciones URL potencialmente malintencionadas en la sección Correos electrónicos** :
       - **Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en el correo electrónico**: seleccione su configuración (activar).
       - **Aplicar vínculos seguros a los mensajes de correo electrónico enviados dentro de la organización**: seleccione esta opción (activar).
       - **Aplicar el examen de direcciones URL en tiempo real en busca de vínculos sospechosos y vínculos que apunten a archivos**: seleccione esta opción (activar).
         - **Espere a que se complete el examen de direcciones URL antes de entregar el mensaje**: seleccione esta opción (activar).
       - **No vuelva a escribir direcciones URL, realice comprobaciones solo a través de safe links API**: compruebe que esta configuración no está seleccionada (desactivar).
     - **No vuelva a escribir las siguientes direcciones URL en el correo electrónico**: no tenemos ninguna recomendación específica para esta configuración. Para obtener más información, vea ["No volver a escribir las siguientes direcciones URL" en Directivas de vínculos seguros](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies).
     - **Acción para direcciones URL potencialmente malintencionadas en la sección Microsoft Teams** :
       - ***Activado: Vínculos seguros comprueba una lista de vínculos malintencionados conocidos cuando los usuarios hacen clic en vínculos en Microsoft Teams**: seleccione esta opción (activar).
     - **Haga clic en la sección configuración de protección** :
       - **Realizar un seguimiento de los clics del usuario**: compruebe que esta configuración está seleccionada (activada).
         - **Permitir que los usuarios haga clic en la dirección URL original**: desactive esta configuración (no seleccionada).
         - **Mostrar la personalización de marca de la organización en las páginas de notificación y advertencia**: seleccionar esta configuración (activarla) solo es significativa después de haber seguido las instrucciones de [Personalización del tema de Microsoft 365 para que su organización](../../admin/setup/customize-your-organization-theme.md) cargue el logotipo de la empresa.
   - **Página de notificación** :
     - **¿Cómo desea notificar a los usuarios?** sección: opcionalmente, puede seleccionar **Usar texto de notificación personalizado** para escribir el texto de notificación personalizado que se va a usar. También puede seleccionar **Usar Microsoft Translator para la localización automática** para traducir el texto de notificación personalizado al idioma del usuario. De lo contrario, deje **seleccionado Usar el texto de notificación predeterminado** .

3. Cuando haya terminado, haga clic en **Enviary**, a continuación, haga clic en **Listo**.

Para obtener instrucciones detalladas sobre cómo configurar directivas de vínculos seguros y opciones globales para vínculos seguros, consulte [Configuración de directivas de vínculos seguros en Microsoft Defender para Office 365](set-up-safe-links-policies.md).

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Ahora configure alertas para los archivos detectados en SharePoint Online o OneDrive para la Empresa

Para recibir una notificación cuando un archivo de SharePoint Online o OneDrive para la Empresa se ha identificado como malintencionado, puede configurar una alerta como se describe en esta sección.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Email & directivas** **de & directivas de alertas de las directivas** \> de colaboración.\>

2. En la página **Directiva de alertas** , haga clic en **Nueva directiva de alerta**.

3. Se abre el Asistente para **nueva directiva de alertas** . En la página **Nombre** , configure los siguientes valores:
   - **Nombre**: escriba un nombre único y descriptivo. Por ejemplo, podría escribir Archivos malintencionados en Bibliotecas.
   - **Descripción**: escriba una descripción opcional.
   - **Gravedad**: seleccione **Baja**, **Media** o **Alta**.
   - **Categoría**: seleccione **Administración de amenazas**.

   Cuando haya terminado, haga clic en **Siguiente.**

4. En la página **Crear configuración de alerta** , configure los siguientes valores:
   - **¿En qué quiere alertar?** sección: **La actividad es** \> **Malware detectado en el archivo**.
   - **Cómo desea que se desencadene la alerta** : compruebe **cada vez que una actividad coincida con la regla** seleccionada.

   Cuando haya terminado, haga clic en **Siguiente.**

5. En la página **Establecer los destinatarios** , configure los siguientes valores:
   - **Enviar notificaciones por correo electrónico**: compruebe que esta configuración está seleccionada.
   - **Email destinatarios**: seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecte un archivo malintencionado.
   - **Límite diario de notificaciones**: compruebe que **no hay ningún límite** seleccionado.

   Cuando haya terminado, haga clic en **Siguiente.**

6. En la página **Revisar la configuración**, revise la configuración, compruebe **que sí, activarla de inmediato** está seleccionada y, a continuación, haga clic en **Finalizar**.

Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en el portal de cumplimiento Microsoft Purview](../../compliance/alert-policies.md).

> [!NOTE]
> Cuando haya terminado de configurar, use estos vínculos para iniciar investigaciones de cargas de trabajo:
>
> - [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report)
> - [Use el portal de Microsoft 365 Defender para administrar archivos en cuarentena en Defender para Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
> - [Qué hacer cuando se encuentra un archivo malintencionado en SharePoint Online, OneDrive o Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [Administración de mensajes y archivos en cuarentena como administrador en Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Tareas posteriores a la instalación y pasos siguientes

Después de configurar las características de protección contra amenazas, asegúrese de supervisar cómo funcionan esas características. Revise y revise las directivas para que hagan lo que necesita. Además, busque nuevas características y actualizaciones de servicio que puedan agregar valor.

|Qué hacer|Recursos para obtener más información|
|---|---|
|Vea cómo funcionan las características de protección contra amenazas para su organización mediante la visualización de informes|[Email informes de seguridad](view-email-security-reports.md) <p> [Informes para Microsoft Defender para Office 365](view-reports-for-mdo.md) <p> [Explorador de amenazas](threat-explorer.md)|
|Revise y revise periódicamente las directivas de protección contra amenazas según sea necesario.|[Puntuación de seguridad](../defender/microsoft-secure-score.md) <p> [Características de investigación y respuesta de amenazas de Microsoft 365](./office-365-ti.md)|
|Inspección de nuevas características y actualizaciones del servicio|[Opciones de versión estándar y de destino](../../admin/manage/release-options-in-office-365.md) <p> [Centro de mensajes](../../admin/manage/message-center.md) <p> [Plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Descripciones del servicio](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
