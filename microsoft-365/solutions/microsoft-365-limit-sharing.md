---
title: Limitar el uso compartido en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom:
- admindeeplinkMAC
- admindeeplinkTEAMS
- admindeeplinkSPO
ms.localizationpriority: high
recommendations: false
description: Obtenga más información sobre las opciones para limitar o deshabilitar el uso compartido de Microsoft 365.
ms.openlocfilehash: f9833e1c033644e117a4009720a627d783e4e946
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985617"
---
# <a name="limit-sharing-in-microsoft-365"></a>Limitar el uso compartido en Microsoft 365

Aunque no puede deshabilitar el uso compartido interno por completo ni quitar el botón Compartir de los sitios, hay varias maneras en las que puede limitar el uso compartido de Microsoft 365 para satisfacer las necesidades de la organización.

Los métodos para compartir archivos se muestran en la tabla siguiente. Haga clic en el vínculo de la columna **Método de uso compartido** para obtener información detallada.

|Método de uso compartido|Descripción|Opciones de limitación|
|:-------------|:----------|:-------------|
|[Grupo o equipo de Microsoft 365](#microsoft-365-group-or-team)|Los usuarios a los que se les ha concedido acceso a un equipo de Microsoft Teams o a un grupo de Microsoft 365 pueden editar el acceso a los archivos del sitio de SharePoint asociado.|Si el grupo o equipo es privado, las invitaciones de uso compartido para unirse al equipo se envían al propietario del sitio para su aprobación. Los administradores pueden deshabilitar el acceso de invitados o usar etiquetas de confidencialidad para impedir el acceso a personas externas a la organización.|
|[Sitio de SharePoint](#sharepoint-site)|A los usuarios se pueden conceder el acceso de propietario, miembro o visitante a un sitio de SharePoint y tendrán ese nivel de acceso a los archivos del sitio.|Los permisos del sitio se pueden restringir para que solo sus propietarios puedan compartirlo. Los administradores pueden configurar un sitio para que sea de solo lectura o bloquear el acceso por completo.|
|[Compartir con usuarios específicos](#sharing-with-specific-people)|Los miembros del sitio y los usuarios con permisos de edición pueden conceder permisos directos a archivos y carpetas, o compartirlos con vínculos de *Usuarios específicos*.|Los permisos del sitio se pueden restringir para que solo los propietarios del sitio puedan compartir archivos y carpetas. En este caso, el acceso directo y el uso compartido del vínculo de *Usuarios específicos* por miembros del sitio se envían al propietario para su aprobación.|
|[Compartir invitados de SharePoint y OneDrive](#sharepoint-guest-sharing)|Los propietarios y miembros de sitios de SharePoint y los propietarios de OneDrive pueden compartir archivos y carpetas con personas ajenas a la organización.|El uso compartido de invitados se puede deshabilitar para toda la organización o para sitios individuales.|
|[Vínculos de uso compartido de *Personas de su organización*](#people-in-your-organization-sharing-links)|Los propietarios y miembros del sitio de SharePoint pueden compartir archivos con vínculos de *Personas de su organización*, que funcionarán para cualquier persona dentro de la organización.|Los vínculos de *Personas de su organización* se pueden deshabilitar en el nivel de sitio.|
|[Crear sitios, grupos y equipos](#create-sites-groups-and-teams)|De forma predeterminada, los usuarios pueden crear nuevos sitios, grupos y equipos desde los que pueden compartir contenido.|Los administradores pueden restringir quién puede crear sitios, grupos y equipos.|
|[Correo electrónico](#email)|Los usuarios que tengan acceso a un archivo pueden enviárselo a otros usuarios por correo electrónico.|Los administradores pueden cifrar archivos con las etiquetas de confidencialidad para evitar que se compartan con usuarios no autorizados.|
|[Descargar o copiar archivos](#download-or-file-copy)|Los usuarios que tienen acceso a un archivo pueden descargarlo o copiarlo y compartirlo con otros usuarios externos al ámbito de Microsoft 365.|Los administradores pueden cifrar archivos con las etiquetas de confidencialidad para evitar que se compartan con usuarios no autorizados.|

También puede restringir las condiciones en las que los usuarios acceden al contenido compartido. Vea el [acceso condicional](#conditional-access) más adelante en este artículo para más información.

While you can use the admin controls described in this article to limit sharing in your organization, we highly recommend that you consider using the security and compliance features available in Microsoft 365 to create a secure sharing environment. See [File collaboration in SharePoint with Microsoft 365](/sharepoint/deploy-file-collaboration) and [Configure a team with security isolation](secure-teams-security-isolation.md) for information.

Para comprender cómo se usa el uso compartido en su organización, [ejecute un informe sobre el uso compartido de archivos y carpetas](/sharepoint/sharing-reports).

## <a name="microsoft-365-group-or-team"></a>Grupo o equipo de Microsoft 365

Si quiere limitar el uso compartido en un grupo de Microsoft 365 o un equipo de Microsoft Teams, es importante que el grupo o equipo sea privado. Los usuarios dentro de su organización pueden unirse a un equipo o grupo público en cualquier momento. Si el grupo o equipo no es privado, no hay ninguna forma de limitar el uso compartido del equipo o de sus archivos en la organización.

### <a name="guest-sharing"></a>Uso compartido de invitados

Si quiere evitar el acceso de invitados en Teams, puede desactivar el uso compartido de invitados en el centro de administración de Teams.

Para desactivar el uso compartido de invitados en Teams
1. En el Centro de administración de Teams, expanda la pestaña **Configuración de toda la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2173122" target="_blank">**** Acceso de invitados</a>.
2. Desactive **Permitir el acceso de invitado en Teams**.
3. Haga clic en **Guardar**.

Si quiere evitar el acceso de invitado en los Grupos de Microsoft 365, puede desactivar la configuración del acceso de invitado de los grupos en el Centro de administración de Microsoft 365.

Para desactivar el uso compartido de invitados en los grupos de Microsoft 365
1. En el Centro de administración de Microsoft 365, haga clic en la pestaña **Configuración** > **Configuración de la organización** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">**Servicios**</a>.
2. Haga clic en **Grupos de Microsoft 365**
3. Desactive las casillas **Permitir que los miembros del grupo de fuera de la organización tengan acceso al contenido del grupo** y **Permitir que los propietarios de grupos agreguen a usuarios ajenos a la organización a los grupos**.
4. Haga clic en **Guardar cambios**.

    ![Captura de pantalla de la configuración de uso compartido de grupos de Microsoft 365 en el Centro de administración de Microsoft 365.](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> Si quiere evitar que los invitados compartan información para un grupo o equipo en particular, puede hacerlo usando [Microsoft PowerShell](per-group-guest-access.md) o [etiquetas de confidencialidad](../compliance/sensitivity-labels-teams-groups-sites.md).

Puede limitar el uso compartido de invitados a usuarios de dominios específicos al permitir o bloquear dominios en Azure Active Directory. Esto también afecta al uso compartido de invitados en SharePoint si ha habilitado la [integración de SharePoint y OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview).

Para permitir las invitaciones de uso compartido solo de dominios específicos
1. En la página Información general de Azure Active Directory, haga clic en **Relaciones de la organización**.
2. Haga clic en **Configuración**.
3. En **Restricciones de colaboración**, seleccione **Denegar las invitaciones a los dominios especificados** o **Permitir solo invitaciones a los dominios especificados** y, después, escriba los dominios que quiera usar.
4. Haga clic en **Guardar**.

    ![Captura de pantalla de la configuración de restricciones de colaboración en Azure Active Directory.](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a>Sitio de SharePoint

Puede limitar el uso compartido de sitios de SharePoint solo a los propietarios del sitio. Esto impide que los miembros del sitio lo compartan. Tenga en cuenta que si el sitio está conectado a un grupo de Microsoft 365, sus miembros pueden invitar a otros usuarios al grupo, lo que les dará acceso al sitio.

Para limitar el uso compartido de sitios a los propietarios
1. En el sitio, haga clic en el icono de engranaje y, después, haga clic en **Permisos del sitio**.
2. En **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
3. Seleccione **Los propietarios y miembros del sitio, y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios de sitios pueden compartir el sitio**.
4. Haga clic en **Guardar**.

    ![Captura de pantalla de la configuración de permisos de uso compartido en un sitio de SharePoint.](../media/sharepoint-site-sharing-permissions-level-two.png)

Puede desactivar las solicitudes de acceso para impedir que los usuarios que no sean miembros del sitio lo soliciten.

Para desactivar las solicitudes de acceso
1. En el sitio, haga clic en el icono de engranaje y, después, haga clic en **Permisos del sitio**.
2. En **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
3. Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.

Puede limitar el uso compartido de sitios a dominios específicos al permitirlos o bloquearlos.

Para limitar el uso compartido del sitio por dominio

1. En el Centro de administración de SharePoint en **Sitios**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a>.
2. Seleccione el sitio que quiere configurar.
3. En la pestaña **Directivas**, en **Uso compartido externo**, seleccione **Editar**.
4. En **Configuración avanzada para uso compartido externo**, seleccione **Limitar uso compartido por dominio**.
5. Agregue los dominios que desea permitir o bloquear y, a continuación, seleccione **Guardar**.
6. Seleccione **Guardar**.

    ![Captura de pantalla de la configuración en el nivel de sitio de dominios permitidos.](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a>Bloquear el acceso a un sitio

You can block access to a site or make a site read-only by changing the lock state of the site. For details, see [Lock and unlock sites](/sharepoint/manage-lock-status).

### <a name="permissions-inheritance"></a>Herencia de permisos

Aunque no se recomienda, puede usar [Herencia de permisos de SharePoint](/sharepoint/what-is-permissions-inheritance) para personalizar los niveles de acceso a los sitios y subsitios.

## <a name="sharing-with-specific-people"></a>Compartir con usuarios específicos

Si quiere limitar el uso compartido de un sitio o de su contenido, puede configurarlo para que solo los propietarios puedan compartir archivos, carpetas y el sitio. Cuando se configura, los intentos de los miembros del sitio para compartir archivos o carpetas con vínculos de *Usuarios específicos* se envían al propietario del sitio para su aprobación.

Para limitar el uso compartido de sitios, archivos y carpetas a los propietarios
1. En el sitio, haga clic en el icono de engranaje y, después, haga clic en **Permisos del sitio**.
2. En **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
3. Seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.
4. Haga clic en **Guardar**.

    ![Captura de pantalla de la configuración de permisos de uso compartido en un sitio de SharePoint configurado como Solo propietarios.](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a>Uso compartido de invitados de SharePoint

Si quiere evitar el uso compartido de archivos y carpetas de SharePoint o OneDrive con usuarios externos a la organización, puede desactivar el uso compartido de invitados para toda la organización o para un sitio individual.

Para desactivar el uso compartido de invitados de SharePoint en su organización

1. En el Centro de administración de SharePoint en **Directivas**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Uso compartido**</a>.
2. En **Uso compartido externo**, arrastre el control deslizante de SharePoint hacia abajo hasta **Solo los usuarios de la organización**.
3. Seleccione **Guardar**.

    ![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint configurado como Cualquier usuario.](../media/sharepoint-tenant-sharing-off.png)


Para desactivar el uso compartido de invitados en un sitio
1. En el Centro de administración de SharePoint en **Sitios**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a>.
2. Seleccione el sitio que quiere configurar.
3. En la pestaña **Directivas**, en **Uso compartido externo**, seleccione **Editar**.
4. En **Uso compartido externo**, elija **Solo los usuarios de su organización** y, después, seleccione **Guardar**.

    ![Captura de pantalla de la configuración de compartición a nivel de sitio de SharePoint establecida en Sólo personas de su organización.](../media/sharepoint-site-external-sharing-settings-off.png)

Puede desactivar el uso compartido de invitados para un OneDrive individual haciendo clic en el usuario en el Centro de administración de Microsoft 365 y seleccionando **Gestionar el uso compartido externo en la** pestaña e **OneDrive**.

Si quiere permitir el uso compartido con personas externas a la organización, pero quiere asegurarse de que todos los usuarios se autentican, puede deshabilitar los vínculos de tipo *Cualquiera* (uso compartido anónimo) para toda la organización o para un sitio individual.

Para desactivar los vínculos de tipo *Cualquiera* en el nivel de organización

1. En el Centro de administración de SharePoint en **Directivas**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185222" target="_blank">**Uso compartido**</a>.
2. En **Uso compartido externo**, arrastre el control deslizante de SharePoint hacia abajo hasta **Invitados nuevos y existentes**.
3. Seleccione **Guardar**.

    ![Captura de pantalla de la configuración de uso compartido en el nivel de organización de SharePoint configurado como Invitados nuevos y existentes.](../media/sharepoint-guest-sharing-new-existing-guests.png)

Desactivar los vínculos de tipo *Cualquiera*

1. En el Centro de administración de SharePoint en **Sitios**, seleccione <a href="https://go.microsoft.com/fwlink/?linkid=2185220" target="_blank">**Sitios activos**</a>.
2. Seleccione el sitio que quiere configurar.
3. En la pestaña **Directivas**, en **Uso compartido externo**, seleccione **Editar**.
4. En **Uso compartido externo**, elija **Invitados nuevos y existentes** y, después, seleccione **Guardar**.

    ![Captura de pantalla de la configuración de uso compartido de nivel de sitio de SharePoint establecida en Configuración nueva y existente.](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a>Vínculos de uso compartido de *Personas de su organización*

By default, members of a site can share files and folders with other people in your organization by using a *People in your organization* link. You can disable *People in your organization* links by using PowerShell:

```powershell
Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks Disabled
```

Por ejemplo:

```powershell
Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks Disabled
```

## <a name="create-sites-groups-and-teams"></a>Crear sitios, grupos y equipos

De forma predeterminada, los usuarios pueden crear nuevos sitios, grupos y equipos desde los que pueden compartir contenido (según su configuración de uso compartido). Puede limitar quién puede crear sitios, grupos y equipos. Vea las referencias siguientes:

- [Administrar la creación de un sitio de SharePoint](/sharepoint/manage-site-creation)
- [Administrar quién puede crear grupos de Microsoft 365](./manage-creation-of-groups.md)

> [!NOTE]
> Restringir la creación de grupos restringe la creación de equipos.

## <a name="email"></a>Correo electrónico

Puede evitar el uso compartido no deseado de mensajes de correo electrónico mediante el cifrado. Esto impide que los mensajes de correo electrónico se reenvíen o se compartan de algún modo con usuarios no autorizados. El cifrado de correo electrónico se puede habilitar mediante etiquetas de confidencialidad. Para más detalles, vea [Restringir el acceso al contenido mediante el cifrado en las etiquetas de confidencialidad](../compliance/encryption-sensitivity-labels.md).

## <a name="download-or-file-copy"></a>Descargar o copiar archivos

Los usuarios que tienen acceso a los archivos y carpetas de Microsoft 365 pueden descargar archivos y copiarlos en medios externos. Para reducir el riesgo del uso compartido de archivos no deseados, puede cifrar el contenido con las etiquetas de confidencialidad.

## <a name="conditional-access"></a>Acceso condicional

Azure Active Directory conditional access provides options to limit or prevent sharing with people based on network location, device health, sign-in risk, and other factors. See [What is Conditional Access?](/azure/active-directory/conditional-access/overview).

SharePoint provides direct integration with Azure AD conditional access for both unmanaged devices and network location. See the following references for details:

- [Control de acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices)
- [Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a>Consulte también

[Referencia de la configuración de uso compartido de invitados de Microsoft 365](microsoft-365-guest-settings.md)
