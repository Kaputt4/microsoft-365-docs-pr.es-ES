---
title: Referencia de la configuración de uso compartido de invitados de Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
f1.keywords: NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkTEAMS
- admindeeplinkSPO
ms.localizationpriority: high
recommendations: false
description: Más información sobre las opciones de configuración de uso compartido de invitados disponibles en Microsoft 365 que pueden afectar al uso compartido con personas de fuera de su organización.
ms.openlocfilehash: 4c472fb20a85c0f00f7623cc63c4d33556b511e2
ms.sourcegitcommit: 2f6a0096038d09f0e43e1231b01c19e0b40fb358
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2022
ms.locfileid: "64687266"
---
# <a name="microsoft-365-guest-sharing-settings-reference"></a>Referencia de la configuración de uso compartido de invitados de Microsoft 365

En este artículo se proporciona una referencia para las distintas opciones de configuración que pueden afectar al uso compartido de usuarios externos a la organización en las cargas de trabajo de Microsoft 365: Teams, Grupos de Microsoft 365, SharePoint y OneDrive. Esta configuración se encuentra en los centros de administración de Azure Active Directory, Microsoft 365, Teams y SharePoint.

## <a name="azure-active-directory"></a>Azure Active Directory

**Rol de administrador**: administrador global

Azure Active Directory es el servicio de directorio que usa Microsoft 365. La configuración de las relaciones de organización de Azure Active Directory afecta directamente al uso compartido en Teams, Grupos de Microsoft 365, SharePoint y OneDrive.

> [!NOTE]
> Esta configuración solo afecta a SharePoint cuando se ha configurado la [Integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview). En la tabla siguiente se presupone que esta se ha configurado.

### <a name="external-collaboration-settings"></a>Configuración de la colaboración externa

**Navegación:** [Centro de administración de Azure Active Directory](https://aad.portal.azure.com) > Azure Active Directory > Identidades externas > Configuración de colaboración externa

![Captura de pantalla de la página de configuración de relaciones de organización de Azure Active Directory.](../media/azure-ad-organizational-relationships-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Acceso de usuario invitado|Los usuarios invitados tienen acceso limitado a propiedades y pertenencia a objetos de directorio|Determina los [permisos que tienen los invitados en Azure Active Directory](/azure/active-directory/fundamentals/users-default-permissions).|
|Configuración de invitaciones para usuarios invitados|Cualquier persona de la organización puede invitar a usuarios invitados, incluidos los invitados y los no administradores|Determina si los invitados, miembros y administradores pueden invitar a usuarios invitados a la organización. <p> Esta configuración afecta a las experiencias de uso compartido de Microsoft 365 como Teams y SharePoint.|
|Habilitar el registro de autoservicio de invitados a través de los flujos de usuario|No|Determina si puede crear flujos de usuario que permitan a alguien registrarse en una aplicación que ha creado y crear una cuenta de invitado.|
|Restricciones de colaboración|Permitir el envío de invitaciones a cualquier dominio|Esta configuración le permite especificar una lista de dominios permitidos o bloqueados para el uso compartido. Si se especifican dominios permitidos, las invitaciones de uso compartido solo se pueden enviar a estos dominios. Si se especifican dominios denegados, las invitaciones de uso compartido no se pueden enviar a estos dominios. <p> Esta configuración afecta a las experiencias de uso compartido de Microsoft 365 como Teams y SharePoint. Puede permitir o bloquear dominios en un nivel más granular con el filtrado de dominios de SharePoint o Teams.|

Esta configuración afecta al modo en que se invitan a los usuarios al directorio. No afecta al uso compartido de invitados que ya están en el directorio.

### <a name="cross-tenant-access-settings"></a>Configuración de acceso entre inquilinos

**Navegación:** [Azure Active Directory centro de administración](https://aad.portal.azure.com) > Azure Active Directory > identidades externas > configuración de acceso entre inquilinos > pestaña Configuración predeterminada

La configuración predeterminada se aplica a todas las organizaciones Azure AD externas, excepto a aquellas con configuración específica de la organización. Configuración para una organización específica se puede configurar en la pestaña **Configuración de la organización**. Hay configuraciones independientes para los invitados (colaboración B2B) y Azure AD usuarios de [conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview).

![Captura de pantalla de Azure Active Directory página configuración de acceso entre inquilinos.](../media/azure-ad-cross-tenant-default-settings.png)

**Configuración de acceso entrante**

La configuración de acceso entrante controla si los usuarios de organizaciones Azure AD externas pueden acceder a los recursos de la organización.

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Colaboración B2B: usuarios y grupos externos|Todos los permitidos|Determina a qué personas de otras organizaciones Azure AD se les puede conceder acceso a los recursos de su organización como invitados.|
|Colaboración B2B: aplicaciones|Todos los permitidos|Determina a qué aplicaciones de la organización se puede conceder acceso a los invitados.|
|Conexión directa B2B: usuarios y grupos externos|Todos bloqueados|Determina si a las personas de otras organizaciones Azure AD se les puede conceder acceso a los recursos de su organización a través de la conexión directa B2B.|
|Conexión directa B2B: aplicaciones|Todos bloqueados|Determina a qué aplicaciones de la organización se puede conceder acceso a los usuarios de conexión directa B2B.|
|Configuración de confianza|Deshabilitado|Determina si las directivas de acceso condicional aceptarán notificaciones de otras organizaciones de Azure AD cuando personas de esas organizaciones accedan a los recursos.|

**Configuración de acceso saliente**

La configuración de acceso saliente controla si los usuarios pueden acceder a los recursos de una organización externa.

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Colaboración B2B: usuarios y grupos externos|Todos los permitidos|Determina qué usuarios de su organización pueden tener acceso a los recursos de otras organizaciones Azure AD como invitados.|
|Colaboración B2B: aplicaciones|Todos los permitidos|Determina a qué aplicaciones de otras organizaciones Azure AD se puede conceder acceso a los usuarios como invitados.|
|Conexión directa B2B: usuarios y grupos externos|Todos bloqueados|Determina qué usuarios de su organización pueden tener acceso a los recursos de otras organizaciones Azure AD a través de la conexión directa B2B.|
|Conexión directa B2B: aplicaciones|Todos bloqueados|Determina a qué aplicaciones de otras organizaciones Azure AD se puede conceder acceso a los usuarios a través de la conexión directa B2B.|

## <a name="microsoft-365"></a>Microsoft 365

**Rol de administrador**: administrador global

El Centro de administración de Microsoft 365 tiene configuración a nivel de organización para el uso compartido y los Grupos de Microsoft 365.

### <a name="sharing"></a>Compartir

**Navegación:** [Centro de administración de Microsoft 365](https://admin.microsoft.com) > **Configuración** > **Configuración de la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**pestaña** seguridad y privacidad</a> > **Compartir**.

![Captura de pantalla de la configuración de uso compartido de invitados de seguridad y privacidad en el Centro de administración de Microsoft 365.](../media/sharepoint-security-privacy-sharing-setting.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Permitir que los usuarios agreguen nuevos invitados a la organización|Activado|Si se establece en **Sí**, los miembros de Azure AD pueden invitar a través de Azure AD; si se establece en **No**, no pueden hacerlo. Cuando se establece en **Sí**, los miembros de grupos de Microsoft 365 pueden invitar a invitados con la aprobación del propietario; cuando se establece en **No**, los miembros de grupos de Microsoft 365 pueden invitar a invitados con aprobación de propietario, pero los propietarios deben ser administradores globales para aprobar. <p> Tenga en cuenta que la opción **Los miembros pueden invitar** hace referencia a los miembros de Azure AD (frente a los invitados) y no a los miembros del sitio o grupo de Microsoft 365. <p> Esto es idéntico a la opción de configuración **Los miembros pueden invitar** en las relaciones de organización de Azure Active Directory.|

### <a name="microsoft-365-groups"></a>Grupos de Microsoft 365

**Navegación:** [Centro de administración de Microsoft 365](https://admin.microsoft.com) > **Configuración** > **Configuración de la organización** > Grupos de Microsoft 365

![Captura de pantalla de la configuración de invitados de Grupos de Microsoft 365 en el Centro de administración de Microsoft 365.](../media/office-365-groups-guest-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Permitir que los miembros del grupo de fuera de la organización tengan acceso al contenido del grupo|Activado|Si se establece en **Activado**, los invitados pueden acceder al contenido de los grupos; si se establece en **Desactivado**, no pueden hacerlo. Esta configuración debe establecerse en **Activado** para cualquier escenario en el que los invitados interactúen con grupos de Microsoft 365 o Teams.|
|Permitir que los propietarios de grupos agreguen a usuarios ajenos a la organización a los grupos|Activado|Si está **activado**, los propietarios de los grupos de Microsoft 365 o Teams pueden invitar a nuevos invitados al grupo. Si está **desactivado**, no pueden hacerlo. Esta configuración debe estar **activada** para cualquier escenario en el que los invitados se vayan a agregar a los grupos.|

Esta configuración se encuentra en el nivel de organización. Consulte [Crear configuración para un grupo específico](/azure/active-directory/users-groups-roles/groups-settings-cmdlets#create-settings-for-a-specific-group) para obtener información sobre cómo cambiar esta configuración en el nivel de grupo mediante PowerShell.

## <a name="teams"></a>Teams

El conmutador principal de acceso de invitado de Teams, **Permitir el acceso de invitados en Teams**, debe estar **Activado** para que las demás opciones de configuración de invitados estén disponibles.

**Rol de administrador**: administrador de servicios de Teams

### <a name="guest-access"></a>Acceso de invitados

**Navegación:** [centro de administración de Teams](https://admin.teams.microsoft.com) > **Configuración de toda la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Acceso de invitados**</a>

![Captura de pantalla de la opción de acceso de invitados de Teams.](../media/teams-guest-access-toggle.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Permitir el acceso de invitados en Teams|Activado|Activa o desactiva el acceso de invitados a Teams en general. Esta configuración puede tardar 24 horas en aplicarse una vez cambiada.|

### <a name="guest-calling"></a>Llamadas de invitado

**Navegación:** [centro de administración de Teams](https://admin.teams.microsoft.com) > **Configuración de toda la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Acceso de invitados**</a>

![Captura de pantalla de las opciones de llamada de invitados de Teams.](../media/teams-guest-calling-setting.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Realizar llamadas privadas|Activado|Si está **Activado**, los invitados pueden realizar llamadas de punto a punto en Teams; si está **Desactivado**, no pueden hacerlo.|

### <a name="guest-meeting"></a>Reunión de invitados

**Navegación:** [centro de administración de Teams](https://admin.teams.microsoft.com) > **Configuración de toda la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Acceso de invitados**</a>

![Captura de pantalla de la configuración de reunión de invitado de Teams.](../media/teams-guest-meeting-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Permitir vídeo IP|Activado|Si está **Activado**, los invitados pueden usar el vídeo en sus llamadas y reuniones; si está **Desactivado**, no pueden hacerlo.|
|Modo de uso compartido de la pantalla|Toda la pantalla|Si está **Deshabilitado**, los invitados no pueden compartir su pantalla en Teams. Si se establece en **Una sola aplicación**, los invitados solo pueden compartir una única aplicación en su pantalla. Si se establece en **Pantalla completa**, los invitados pueden elegir entre compartir una aplicación o toda la pantalla.|
|Permitir Reunirse ahora|Activado|Si está **Activado**, los invitados pueden usar la característica Reunirse ahora en Teams; si está **Desactivado**, no pueden hacerlo.|

### <a name="guest-messaging"></a>Mensajería de invitado

**Navegación:** [centro de administración de Teams](https://admin.teams.microsoft.com) > **Configuración de toda la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**Acceso de invitados**</a>

![Captura de pantalla de la configuración de mensajería de invitados de Teams.](../media/teams-guest-messaging-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Editar los mensajes enviados|Activado|Si está **Activado**, los invitados pueden editar los mensajes que se enviaron previamente; si está **Desactivado**, no pueden hacerlo.|
|Eliminar mensajes enviados|Activado|Si está **Activado**, los invitados pueden eliminar los mensajes que se enviaron previamente; si está **Desactivado**, no pueden hacerlo.|
|Chat|Activado|Si está **Activado**, los invitados pueden usar chat en Teams; si está **Desactivado**, no pueden hacerlo.|
|Usar Giphys en las conversaciones|Activado|Si está **Activado**, los invitados pueden usar Giphys en las conversaciones; si está **Desactivado**, no pueden hacerlo.|
|Clasificación del contenido de Giphy|Moderado|Cuando se establece en **Permitir todo el contenido**, los invitados pueden insertar todos los Giphys en los chats, independientemente de la clasificación del contenido. Si se establece en **Moderado**, los invitados pueden insertar Giphys en los chats, pero se les restringirá de forma moderada el contenido para adultos. Si se establece en **Estricto**, los invitados pueden insertar Giphys en los chats, pero se les restringirá insertar contenido para adultos.|
|Usar Memes en las conversaciones|Activado|Si está **Activado**, los invitados pueden usar memes en las conversaciones; si está **Desactivado**, no pueden hacerlo.|
|Usar adhesivos en las conversaciones|Activado|Si está **Activado**, los invitados pueden usar adhesivos en las conversaciones; si está **Desactivado**, no pueden hacerlo.|
|Permitir el lector inmersivo para ver mensajes|Activado|Si está **Activado**, los invitados pueden ver los mensajes en el lector inmersivo; si está **Desactivado**, no pueden hacerlo.|

## <a name="sharepoint-and-onedrive-organization-level"></a>SharePoint y OneDrive (nivel de la organización)

**Rol de administrador**: Administrador del servicio SharePoint

Esta configuración afecta a todos los sitios de la organización. No afecta directamente a los grupos de Microsoft 365 o Teams, pero le recomendamos que alinee esta configuración con la de los grupos de Microsoft 365 y Teams para evitar problemas de experiencia de usuario. (Por ejemplo, si se permite el uso compartido de invitados en Teams, pero no en SharePoint, los invitados en Teams no tendrán acceso a la pestaña Archivos, ya que los archivos de Teams se almacenan en SharePoint).

### <a name="sharepoint-and-onedrive-sharing-settings"></a>Configuración de uso compartido de SharePoint y OneDrive

Como OneDrive es una jerarquía de sitios dentro de SharePoint, la configuración de uso compartido en el nivel de la organización afecta directamente a OneDrive al igual que otros sitios de SharePoint.

**Navegación:** Centro de administración de SharePoint > **Directivas** > <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Compartir**</a>

![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint.](../media/external-sharing.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|SharePoint|Cualquiera|Especifica los permisos de uso compartido más permisivos permitidos para los sitios de SharePoint.|
|OneDrive|Cualquiera|Especifica los permisos de uso compartido más permisivos permitidos para los sitios de OneDrive. Esta configuración no puede ser más permisiva que la configuración de SharePoint.|

### <a name="sharepoint-and-onedrive-advanced-sharing-settings"></a>Configuración de uso compartido avanzado de SharePoint y OneDrive

**Navegación:** Centro de administración de SharePoint > **Directivas** > <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Compartir**</a>

![Captura de pantalla de la configuración de uso compartido adicional en el nivel de organización de SharePoint.](../media/external-sharing.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Limitar el uso compartido externo por dominio|Desactivado|Esta configuración le permite especificar una lista de dominios permitidos o bloqueados para el uso compartido. Si se especifican dominios permitidos, las invitaciones de uso compartido solo se pueden enviar a estos dominios. Si se especifican dominios denegados, las invitaciones de uso compartido no se pueden enviar a estos dominios. <p> Esta configuración afecta a todos los sitios de SharePoint y OneDrive de la organización.|
|Permitir que solo los usuarios en grupos de seguridad específicos compartan externamente|Desactivado|Si quiere limitar quién puede compartir con los invitados en SharePoint y OneDrive, puede hacerlo limitando el uso compartido a los usuarios de los grupos de seguridad especificados. Esta configuración no afecta al uso compartido a través de los grupos de Microsoft 365 o Teams. Los invitados a través de un grupo o un equipo también tendrían acceso al sitio asociado, aunque el uso compartido de documentos y carpetas lo puedan realizar solo los usuarios de los grupos de seguridad especificados. <p> Para cada grupo especificado, puede elegir qué usuarios pueden compartir vínculos con Cualquiera.|
|Los invitados deben iniciar sesión con la misma cuenta a la que se enviaron las invitaciones para el uso compartido|Desactivado|Impide que los invitados canjeen las invitaciones de uso compartido de sitios con una dirección de correo electrónico distinta a la que se envió la invitación. <p> [La Integración de SharePoint y OneDrive con Azure AD B2B (versión preliminar)](/sharepoint/sharepoint-azureb2b-integration-preview) no usa esta opción, ya que todos los invitados se agregan al directorio basándose en la dirección de correo electrónico a la que se envió la invitación.|
|Permitir que los invitados compartan elementos que no poseen|Activado|Si está **Activado**, los invitados pueden compartir elementos que no poseen con otros usuarios o invitados; si está **Desactivado**, no pueden hacerlo. Los invitados siempre podrán compartir elementos sobre los que tengan control total.|
|Las personas que usan un código de verificación deben volver a autenticarse después de estos días|Desactivado|Este valor permite requerir que los usuarios que se autentiquen con un código de acceso de un solo uso tengan que volver a autenticarse después de un determinado número de días.|
|El acceso de invitado a un sitio o a OneDrive expirará automáticamente después de este número de días|Activado|Si su administrador ha establecido un tiempo de vencimiento para el acceso de invitados, cada invitado que invite al sitio o con quien comparta archivos y carpetas individuales tendrá acceso durante un cierto número de días. Para obtener más información, visite [Administrar la caducidad de invitado para un sitio](https://support.microsoft.com/en-us/office/manage-guest-expiration-for-a-site-25bee24f-42ad-4ee8-8402-4186eed74dea)

### <a name="sharepoint-and-onedrive-file-and-folder-link-settings"></a>Configuración de vínculos a archivos y carpetas de SharePoint y OneDrive

Cuando se comparten archivos y carpetas en SharePoint y OneDrive, los destinatarios con los que se comparte reciben un vínculo con los permisos para el archivo o la carpeta en lugar de obtener acceso directo a ellos. Existen varios tipos de vínculos disponibles y puede elegir el tipo de vínculo predeterminado que se muestra a los usuarios cuando comparten un archivo o una carpeta. También puede establecer permisos y opciones de expiración para vínculos de *Cualquiera*.

**Navegación:** Centro de administración de SharePoint > **Directivas** > <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Compartir**</a>

![Captura de pantalla de la configuración de uso compartido de los archivos y carpetas de nivel de organización de SharePoint.](../media/sharepoint-organization-files-folders-sharing-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Vínculos de archivos y carpetas|Cualquiera con el vínculo|Especifica el vínculo para compartir que se muestra de manera predeterminada cuando un usuario comparte un archivo o una carpeta. Si quieren, los usuarios pueden cambiar la opción antes de compartir. Si el valor predeterminado está establecido en **Cualquiera con el vínculo** y no se permite el uso compartido de *Cualquiera* para un sitio determinado, se mostrará como valor predeterminado para ese sitio **Solo los miembros de su organización**.|
|Los vínculos deben expirar dentro de este número de días:|Desactivado (sin expiración)|Especifica el número de días que transcurren después de que se cree un vínculo de *Cualquiera* para que expire. Los vínculos expirados no se pueden renovar. Si necesita seguir compartiendo después de la fecha de expiración, cree un nuevo vínculo.|
|Permisos de archivos|Ver y editar|Especifica los niveles de permisos de archivo disponibles para los usuarios al crear un vínculo de *Cualquiera*. Si se selecciona **Ver**, los usuarios solo pueden crear vínculos de archivo de *Cualquiera* con permisos de visualización. Si se selecciona **Ver y editar**, los usuarios pueden elegir entre ver y ver y editar los permisos al crear el vínculo.|
|Permisos de carpeta|Ver, editar y cargar|Especifica los niveles de permisos de carpeta disponibles para los usuarios al crear un vínculo de *Cualquiera*. Si se selecciona **Ver**, los usuarios solo pueden crear vínculos de carpeta de *Cualquiera* con permisos de visualización. Si se selecciona **Ver, editar y cargar**, los usuarios pueden elegir entre ver y ver, editar y cargar permisos al crear el vínculo.|

## <a name="sharepoint-site-level"></a>SharePoint (nivel de sitio)

**Rol de administrador**: Administrador del servicio SharePoint

Como estas opciones están sujetas a la configuración de toda la organización de SharePoint, puede cambiar la configuración de uso compartido efectiva del sitio si cambia la configuración de nivel de la organización. Si elige una configuración aquí y el nivel de organización se establece posteriormente en un valor más restrictivo, este sitio funcionará con ese valor más restrictivo. Por ejemplo, si elige **Cualquiera** y la configuración de nivel de organización se establece posteriormente en **Invitados nuevos y existentes**, este sitio solo permitirá invitados nuevos y existentes. Si la configuración del nivel de organización se vuelve a establecer en **Cualquiera**, este sitio volverá a permitir el vínculo de *Cualquiera*.

### <a name="site-sharing"></a>Uso compartido de sitios

Puede establecer permisos para el uso compartido de invitados para cada sitio de SharePoint. Esta configuración se aplica al uso compartido de sitios y al uso compartido de archivos y carpetas. (El uso compartido de *Cualquiera* no está disponible para compartir sitios. Si elige **Cualquiera**, los usuarios podrán compartir archivos y carpetas mediante vínculos de *Cualquiera*, y el mismo sitio con invitados nuevos y existentes).

Si en el sitio se ha aplicado una etiqueta de confidencialidad, puede que dicha etiqueta controle la configuración de uso compartido externo. Para obtener más información, consulte [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).

> [!NOTE]
> La configuración de uso compartido de sitios de canal solo se puede cambiar mediante el cmdlet de PowerShell [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite).

**Navegación:** Centro de administración de SharePoint > <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a> > seleccionar el sitio > pestaña **Directivas** > **Editar uso compartido externo**

![Captura de pantalla de la configuración de uso compartido externo del sitio de SharePoint.](../media/sharepoint-site-external-sharing-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Puede compartir contenido con|Varía por tipo de sitio (consulte la tabla siguiente)|Indica el tipo de uso compartido externo permitido para este sitio. Las opciones disponibles en esta sección están sujetas a la configuración de uso compartido en el nivel de la organización de SharePoint.|

### <a name="site-file-and-folder-link-settings"></a>Configuración de vínculos a archivos y carpetas del sitio

Puede establecer valores predeterminados para los tipos de vínculos y permisos, y la configuración de expiración para *Cualquiera* para cada sitio. Cuando se establece en el nivel de sitio, esta configuración reemplaza la configuración de nivel de organización. Tenga en cuenta que, si se deshabilitan los vínculos *Cualquiera* en el nivel de la organización, *Cualquiera* no será un tipo de vínculo disponible en el nivel de sitio.

**Navegación:** Centro de administración de SharePoint > <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a> > seleccionar el sitio > pestaña **Directivas** > **Editar uso compartido externo**

![Captura de pantalla de la configuración de vínculos para compartir en el nivel de sitio de SharePoint.](../media/sharepoint-site-link-sharing-settings.png)

| Valor | Predeterminado | Descripción |
|:-----|:-----|:-----|
|Limitar el uso compartido por dominio|Desactivado|Esta configuración le permite especificar una lista de dominios permitidos o bloqueados para el uso compartido. Si se especifican dominios permitidos, las invitaciones de uso compartido solo se pueden enviar a estos dominios. Si se especifican dominios denegados, las invitaciones de uso compartido no se pueden enviar a estos dominios. <p> Esta configuración no se puede usar para reemplazar las restricciones de dominio establecidas en el nivel de la organización o de Azure AD.|
|Tipo de vínculo para compartir predeterminado|Igual que la configuración de nivel de organización|Esta configuración le permite especificar el vínculo para compartir predeterminado que se muestra a los usuarios en este sitio. La opción *Igual que la configuración de nivel de organización* se define mediante una combinación de la configuración de uso compartido de la organización y el sitio.|
|Configuración avanzada de vínculos para "Cualquiera"|Igual que la configuración de nivel de organización|Especifica el número de días transcurridos desde que se ha creado un vínculo *Cualquiera* para un archivo de este sitio que expira. Los vínculos expirados no se pueden renovar. Si necesita seguir compartiendo después de la fecha de expiración, cree un nuevo vínculo.|
|Permiso de vínculo predeterminado|Igual que la configuración de nivel de organización|Esta configuración le permite especificar el permiso predeterminado (Ver o Editar) para compartir vínculos creados para archivos en este sitio.|

### <a name="default-site-sharing-settings"></a>Configuración de uso compartido de sitio predeterminada

En la tabla siguiente se muestra la configuración de uso compartido predeterminada para cada tipo de sitio.

| Tipo de sitio | Valor de uso compartido predeterminado |
|:-----|:-----|
|Clásico|**Solo personas de la organización**|
|OneDrive|**Cualquiera**|
|Sitios conectados a un grupo (incluyendo Teams)|Los **Invitados nuevos y existentes**, si la configuración de los grupos de Microsoft 365 **Permitir que los propietarios de grupos agreguen a usuarios ajenos a la organización a grupos** está **Activada**; en caso contrario, **Solo los invitados existentes**.|
|Comunicación|**Solo personas de la organización**|
|Sitios modernos sin grupo (sitio de grupo #STS3)|**Solo personas de la organización**|

> [!NOTE]
> El sitio de comunicación raíz (tenant-name.sharepoint.com) tiene de forma predeterminada la configuración de uso compartido **Cualquiera**.

## <a name="see-also"></a>Vea también

[Información general sobre el uso compartido externo de SharePoint y OneDrive](/sharepoint/external-sharing-overview)

[Acceso de invitado en Microsoft Teams](/MicrosoftTeams/guest-access)

[Agregar invitados a los grupos de Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6)
