---
title: Usar etiquetas de confidencialidad con Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Usar etiquetas de confidencialidad para proteger el contenido en los sitios de SharePoint y Microsoft Teams, y los grupos de Microsoft 365.
ms.openlocfilehash: b9168320b5764a3d7ed4e1570c32f0f35ccbc44d
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199630"
---
# <a name="use-sensitivity-labels-to-protect-content-in-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint

>*[Instrucciones de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

Además de usar [etiquetas de confidencialidad](sensitivity-labels.md) para clasificar y proteger documentos y mensajes de correo electrónico, también puede usarlas para proteger el contenido en los siguientes contenedores: sitios de Microsoft Teams, grupos de Microsoft 365 ([anteriormente grupos de Office 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)), y sitios de SharePoint. Para esta clasificación y protección de nivel de contenedor, utilice la siguiente configuración de etiquetas:

- Privacidad (pública o privada) de los sitios de equipos conectados a grupos de Microsoft 365
- Acceso de usuarios externos
- Acceso desde dispositivos no administrados 

Cuando aplica esta etiqueta de confidencialidad a un contenedor compatible, la etiqueta aplica automáticamente la configuración de protección y clasificación al grupo o sitio conectado.

Sin embargo, el contenido de estos contenedores no hereda las etiquetas para la clasificación y configuración, como las marcas visuales o el cifrado. Para que los usuarios puedan etiquetar sus documentos en los sitios de SharePoint o de grupos, asegúrese de [habilitar las etiquetas de confidencialidad para archivos de Office en SharePoint y OneDrive](sensitivity-labels-sharepoint-onedrive-files.md).

> [!NOTE]
> Las etiquetas de sensibilidad para contenedores no son compatibles con las Redes de entrega de contenido (CDNs) de Office 365.

## <a name="using-sensitivity-labels-for-microsoft-teams-microsoft-365-groups-and-sharepoint-sites"></a>Uso de etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint

Antes de habilitar etiquetas de confidencialidad para contenedores y establecerlas para la nueva configuración, los usuarios pueden ver y aplicar etiquetas de confidencialidad en sus aplicaciones. Por ejemplo, en Word:

![Una etiqueta de sensibilidad que se muestra en la aplicación de escritorio de Word](../media/sensitivity-label-word.png)

Después de habilitar y configurar etiquetas de confidencialidad para contenedores, los usuarios también pueden ver y aplicar etiquetas de confidencialidad en sitios de equipos de Microsoft, grupos de Microsoft 365 y sitios de SharePoint. Por ejemplo, al crear un sitio de grupo de SharePoint:

![Una etiqueta de sensibilidad al crear un sitio de equipo desde SharePoint](../media/sensitivity-labels-new-team-site.png)

## <a name="how-to-enable-sensitivity-labels-for-containers-and-synchronize-labels"></a>Cómo habilitar etiquetas de confidencialidad para contenedores y sincronizarlas

1. Dado que esta característica usa la funcionalidad de Azure AD, siga las instrucciones de la documentación de Azure AD para habilitar la compatibilidad con etiquetas de confidencialidad: [Asignar etiquetas de confidencialidad a grupos de Microsoft 365 en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels).

2. Ahora tiene que sincronizar sus etiquetas de confidencialidad en Azure AD. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
    
    Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

3. Después, ejecute el siguiente comando para asegurarse de que sus etiquetas de confidencialidad se pueden usar con los grupos de Microsoft 365:
    
    ```powershell
    Execute-AzureAdLabelSync
    ```

## <a name="how-to-configure-site-and-group-settings"></a>Cómo establecer la configuración de sitio y grupo

Ya está listo para crear o editar las etiquetas de confidencialidad que quiera y que estén disponibles para sitios y grupos. Al habilitar etiquetas de confidencialidad para contenedores, se hace visible una nueva página en los asistentes de etiquetas de confidencialidad: **Configuración de sitio y grupo**

Si necesita ayuda para crear o editar una etiquetas de confidencialidad, vea las instrucciones en [Crear y configurar etiquetas de confidencialidad](create-sensitivity-labels.md#create-and-configure-sensitivity-labels).

En la nueva página **Configuración de sitio y grupo**, configure las opciones:

- **Privacidad de los sitios de equipos conectados a grupos de Office 365**: mantenga el valor predeterminado de **Público: cualquier persona de la organización puede acceder al sitio ** si quiere que todos en su organización accedan al sitio de grupo o grupo donde se aplica esta etiqueta.
    
    Seleccione **Privado** si quiere que el acceso esté restringido solo a miembros aprobados de su organización.
    
    Seleccione **Ninguno: permitir al usuario elegir quién puede acceder al sitio** cuando quiera proteger el contenido del contenedor mediante el uso de la etiqueta de confidencialidad, pero permitir que los usuarios configuren la configuración de privacidad ellos mismos.
    
    Las opciones **Pública** o **Privada** para establecen y bloquean la configuración de privacidad cuando aplica esta etiqueta al contenedor. La configuración elegida reemplaza cualquier configuración de privacidad anterior establecida para el equipo o grupo, y bloquea el valor de privacidad para que solo se pueda cambiar quitando primero la etiqueta de confidencialidad del contenedor. Después de quitar la etiqueta de confidencialidad, la configuración de privacidad de la etiqueta permanece y los usuarios ya pueden cambiarla de nuevo.

- **Acceso de usuarios externos**: controla si el propietario del grupo puede [agregar invitados al grupo](/office365/admin/create-groups/manage-guest-access-in-groups).

- **Dispositivos no administrados**: para [dispositivos sin administrar](/sharepoint/control-access-from-unmanaged-devices), permite acceso total, acceso de solo Web, o bloquear el acceso completamente. Si ha configurado este parámetro a nivel de espacio empresarial o para sitio específico, la configuración que especifique aquí solo se aplicará si es más restrictiva.

![La pestaña de configuración del sitio y del grupo](../media/edit-sensitivity-label-site-group2.png)

> [!IMPORTANT]
> La configuración de sitio y grupo solo surte efecto al aplicar la etiqueta a un equipo, grupo o sitio. El resto de opciones de configuración de etiqueta, como el cifrado y la marcación de contenido, no se aplican a todo el contenido del equipo, grupo o sitio.
> 
> Implementación gradual en espacios empresariales: solo las etiquetas con la configuración de sitio y de grupo estarán disponibles para seleccionarlas cuando los usuarios creen equipos, grupos y sitios. Si actualmente puede aplicar una etiqueta a un contenedor cuando la etiqueta no tiene habilitadas las configuraciones de sitio y grupo, solo se aplica el nombre de la etiqueta al contenedor.

Si la etiqueta de confidencialidad aún no se ha publicado, publíquela [agregándola a una directiva de etiqueta de confidencialidad](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy). Los usuarios que tienen asignada una directiva de etiqueta de confidencialidad que incluye esta etiqueta podrán seleccionarla para sitios y grupos.

En la Directiva de etiqueta, solo la configuración de directiva **aplicar esta etiqueta de forma predeterminada a los documentos y el correo electrónico** es aplicable cuando se aplica esta etiqueta a contenedores. No se aplican otras opciones de configuración de Directiva, como la etiqueta obligatoria, que requiere la justificación del usuario y un vínculo a la página de ayuda personalizada.

## <a name="sensitivity-label-management"></a>Administración de etiquetas de confidencialidad

Use las siguientes instrucciones para crear, modificar o eliminar las etiquetas de confidencialidad configuradas para sitios y grupos.

### <a name="creating-and-publishing-labels-that-are-configured-for-sites-and-groups"></a>Crear y publicar etiquetas configuradas para sitios y grupos

Cuando se crea y se publica una nueva etiqueta de confidencialidad, los usuarios en los equipos, grupos y sitios pueden verla en un plazo de una hora. Sin embargo, si modifica una etiqueta existente, permita que pasen hasta 24 horas. Use las siguientes instrucciones para publicar una etiqueta para los usuarios establecida para la configuración de sitio y grupo:

1. Después de crear y configurar la etiqueta de confidencialidad, agréguela a una directiva de etiqueta que solo se aplique a algunos usuarios de prueba.

2. Espere a que se replique el cambio:
    - Nueva etiqueta: espere una hora.
    - Etiqueta existente: espere 24 horas.

3. Después de este período, utilice una de las cuentas de usuario de prueba para crear un equipo, un grupo de Microsoft 365 o un sitio de SharePoint con la etiqueta creada en el paso 1.

4. Si no se producen errores durante el proceso de creación, significa que es seguro publicar la etiqueta en todos los usuarios de su inquilino.

### <a name="modifying-published-labels-that-are-configured-for-sites-and-groups"></a>Modificar las etiquetas publicadas que están configuradas para sitios y grupos

Como práctica recomendada, no cambie la configuración de sitio y grupo para una etiqueta de confidencialidad cuando se haya aplicado a equipos, grupos o sitios. Si lo hace, espere hasta 24 horas para que los cambios se repliquen en todos los contenedores que tienen la etiqueta aplicada. 

Además, si los cambios incluyen la configuración **Acceso de usuarios externos**:

- La nueva configuración se aplica a los usuarios nuevos, pero no a los usuarios existentes. Por ejemplo, si esta configuración se seleccionó previamente y, como resultado, los usuarios invitados entraron el sitio, estos aún podrán tener acceso al sitio después de que la opción esté desactivada en la configuración de la etiqueta.

- La configuración de privacidad de las propiedades de grupo hiddenMembership y roleEnabled no se actualiza.


### <a name="deleting-published-labels-that-are-configured-for-sites-and-groups"></a>Eliminar etiquetas publicadas que están configuradas para sitios y grupos

Si elimina una etiqueta de confidencialidad con la configuración de sitio y grupo habilitada, y esa etiqueta se incluye en una o más directivas de etiquetas, esta acción pueden provocar fallas de creación para nuevos equipos, grupos y sitios. Para evitarlo, siga las instrucciones que se indican a continuación:

1. Elimine la etiqueta de confidencialidad de todas las directivas de etiqueta que la incluyan.

2. Espere una hora.

3. Después de este período, pruebe a crear un equipo, grupo o sitio y compruebe que la etiqueta ya no es visible.

4. Si la etiqueta de confidencialidad no es visible, ya puede eliminarla de forma segura.

## <a name="how-to-apply-sensitivity-labels-to-containers"></a>Cómo aplicar etiquetas de confidencialidad a contenedores

Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los siguientes contenedores:

- [Grupo de Microsoft 365 en Azure AD](#apply-sensitivity-labels-to-microsoft-365-groups)
- [Sitio de grupo de Microsoft Teams](#apply-a-sensitivity-label-to-a-new-team)
- [Grupo de Microsoft 365 en Outlook en la Web](#apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web)
- [Sitio de SharePoint](#apply-a-sensitivity-label-to-a-new-site)

Puede usar PowerShell si necesita [aplicar una etiqueta de sensibilidad a varios sitios](#use-powershell-to-apply-a-sensitivity-label-to-multiple-sites).

### <a name="apply-sensitivity-labels-to-microsoft-365-groups"></a>Aplicar etiquetas de confidencialidad a grupos de Microsoft 365

Ya está listo para aplicar la etiqueta o las etiquetas de confidencialidad a los grupos de Microsoft 365. Regrese a la documentación de Azure AD para obtener instrucciones:

- [Asignar una etiqueta a un grupo nuevo en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-a-new-group-in-azure-portal)

-  [Asignar una etiqueta a un grupo existente en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#assign-a-label-to-an-existing-group-in-azure-portal)

-  [Quitar una etiqueta a un grupo existente en Azure Portal](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#remove-a-label-from-an-existing-group-in-azure-portal)

### <a name="apply-a-sensitivity-label-to-a-new-team"></a>Aplicar una etiqueta de confidencialidad a un nuevo equipo

Los usuarios pueden seleccionar etiquetas de confidencialidad al crear nuevos equipos en Microsoft Teams. Al seleccionar la etiqueta en la lista desplegable **confidencialidad**, es posible que la configuración de privacidad cambie para reflejar la configuración de la etiqueta. En función de la configuración de acceso de usuarios externos que haya seleccionado para la etiqueta, los usuarios pueden o no, agregar al equipo personas de fuera de la organización.

[Más información sobre las etiquetas de confidencialidad para Teams](https://docs.microsoft.com/microsoftteams/sensitivity-labels)

![La configuración de privacidad al crear un nuevo equipo](../media/privacy-setting-new-team.png)

Después de crear el equipo, se muestra la etiqueta de confidencialidad en la esquina superior derecha de todos los canales.

![La etiqueta de confidencialidad se muestra en el equipo](../media/privacy-setting-teams.png)

El servicio aplica automáticamente la misma etiqueta de confidencialidad al grupo de Microsoft 365 y al sitio de grupo de SharePoint conectado.

### <a name="apply-a-sensitivity-label-to-a-new-group-in-outlook-on-the-web"></a>Aplicar una etiqueta de confidencialidad a un nuevo grupo en Outlook en la Web

En Outlook en la Web, al crear un grupo, puede seleccionar o cambiar la opción **confidencialidad** para las etiquetas publicadas:

![Crear un grupo y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-group.png)

### <a name="apply-a-sensitivity-label-to-a-new-site"></a>Aplicar una etiqueta de confidencialidad a un nuevo sitio

Los administradores y los usuarios finales pueden seleccionar las etiquetas de confidencialidad cuando [crean sitios de grupo y de comunicación modernos](/sharepoint/create-site-collection) y expandir la **configuración avanzada**:

![Crear un sitio y seleccionar una opción en Confidencialidad](../media/sensitivity-label-new-communication-site.png)

En el cuadro desplegable se mostrarán los nombres de etiqueta de la selección, y en el icono de ayuda se mostrarán todos los nombres de etiqueta con la información sobre herramientas, que puede ayudar a los usuarios a determinar la etiqueta correcta que debe aplicar.

Cuando los usuarios exploren el sitio, podrán ver el nombre de la etiqueta y las directivas aplicadas. Por ejemplo, este sitio se ha etiquetado como **confidencial** y la configuración de privacidad se ha establecido en **privada**:

![Un sitio en el que se ha aplicado una etiqueta de confidencialidad](../media/sensitivity-label-site.png)

### <a name="use-powershell-to-apply-a-sensitivity-label-to-multiple-sites"></a>Usar PowerShell para aplicar una etiqueta de confidencialidad a varios sitios

Puede usar los cmdlet [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite?view=sharepoint-ps) y [Set-SPOTenant](/powershell/module/sharepoint-online/set-spotenant?view=sharepoint-ps) con el parámetro *SensitivityLabel* desde el actual Shell de administración de SharePoint Online para aplicar una etiqueta de sensibilidad a muchos sitios. Los sitios pueden ser cualquiera de los pertenecientes a la colección de sitios de SharePoint o un sitio de OneDrive.

Asegúrese de que tiene la versión 16.0.19418.12000 o posterior del Shell de administración de SharePoint Online.

1. Abra una sesión de PowerShell con la opción **Ejecutar como administrador**.

2. Si no conoce su etiqueta GUID, vaya a: [Conectarse al PowerShell del Centro de seguridad y cumplimiento de Office 365](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) y obtenga la lista de etiquetas de confidencialidad y sus GUID.
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. Ahora, vaya a [conectarse a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) y almacene su GUID de etiqueta como una variable. Por ejemplo: 
    
    ```powershell
    $Id = [GUID]("e48058ea-98e8-4940-8db0-ba1310fd955e")
    ```

4. Cree una nueva variable que identifique varios sitios con una cadena de identificación en común en su URL. Por ejemplo:
    
    ```powershell
    $sites = Get-SPOSite -IncludePersonalSite $true -Limit all -Filter "Url -like 'documents" 
    ```

5. Ejecute el siguiente comando para aplicar la etiqueta a estos sitios. Utilice nuestros ejemplos:
    
    ```powershell
    $sites | ForEach-Object {Set-SpoTenant $_.url -SensitivityLabel $Id}
    ```

Para aplicar distintas etiquetas a otros sitios, repita el siguiente comando para cada sitio: `Set-SPOSite -Identity <URL> -SensitivityLabel "<labelguid>"`

## <a name="view-and-manage-sensitivity-labels-in-the-sharepoint-admin-center"></a>Ver y administrar etiquetas de confidencialidad en el centro de administración de SharePoint

Para ver, ordenar y buscar las etiquetas de confidencialidad aplicadas, use la página **Sitios activos** en el nuevo Centro de administración de SharePoint. Es posible que primero tenga que agregar la columna **confidencialidad**:

![La columna Confidencialidad en la página Sitios activos](../media/manage-site-sensitivity-labels.png)

Para obtener más información sobre la administración de sitios desde la página Sitios activos, incluido cómo agregar una columna, vea [Administrar sitios en el nuevo centro de administración de SharePoint](/sharepoint/manage-sites-in-new-admin-center).

También puede cambiar y aplicar una etiqueta desde esta página:

1. Seleccione el nombre del sitio para abrir el panel de detalles.

2. Seleccione la pestaña **Directivas** y después, elija **Editar** para la configuración **Confidencialidad**.

3. En el panel **Editar configuración de confidencialidad**, seleccione la etiqueta de confidencialidad que desea aplicar al sitio y, a continuación, elija **Guardar**.

## <a name="support-for-sensitivity-labels"></a>Compatibilidad con etiquetas de confidencialidad.

Las siguientes aplicaciones y servicios son compatibles con etiquetas de confidencialidad establecidas para la configuración de sitio y grupo:

- Centros de administración:
    - Centro de administración de SharePoint
    - Portal de Azure Active Directory
    - Centro de cumplimiento de Microsoft 365, centro de seguridad de 365 Microsoft, y Centro de seguridad y cumplimiento de Office 365

- Servicios y aplicaciones de usuario:
    - SharePoint
    - Teams
    - Outlook en la Web y para Windows, Mac OS, iOS y Android
    - Forms
    - Stream

Las siguientes aplicaciones y servicios actualmente no son compatibles con las etiquetas de confidencialidad establecidas para la configuración de sitios y grupos:

- Centros de administración:
    - Centro de administración de Microsoft 365
    - Centro de administración de Teams
    - Centro de administración de Exchange

- Servicios y aplicaciones de usuario:
    - Dynamics 365
    - Yammer
    - Planner
    - Proyecto
    - PowerBI

## <a name="classic-azure-ad-group-classification"></a>Clasificación de grupos de Azure AD clásica

Microsoft 365 ya no admitirá las antiguas clasificaciones para los nuevos grupos de Microsoft 365 y sitios de SharePoint después de que habilite etiquetas de confidencialidad para contenedores. Sin embargo, los grupos y sitios existentes que son compatibles con etiquetas de confidencialidad aún mostrarán los valores de clasificación antiguos hasta que los convierta para usar etiquetas de confidencialidad.

Como ejemplo de cómo podría haber utilizado la antigua clasificación de grupos para SharePoint, consulte [Clasificación de sitios "modernos" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification).

Estas clasificaciones se configuraron con Azure AD PowerShell o la biblioteca principal de PnP y definiendo valores para la configuración de `ClassificationList`. Si su espacio empresarial tiene valores de clasificación definidos, se muestran al ejecutar el siguiente comando desde el módulo de [PowerShell de AzureADPreview](https://www.powershellgallery.com/packages/AzureADPreview):

```powershell
   ($setting["ClassificationList"])
```

Para convertir las clasificaciones antiguas en etiquetas de confidencialidad, siga uno de estos procedimientos:

- Usar etiquetas existentes: especifique la configuración de la etiqueta que desee para los sitios y grupos al editar las etiquetas de confidencialidad existentes que ya están publicadas.

- Crear etiquetas nuevas: especifique la configuración de la etiqueta que desee para los sitios y grupos creando y publicando nuevas etiquetas de confidencialidad que tengan los mismos nombres que las de las clasificaciones existentes.

Luego: 

1. Use PowerShell para aplicar las etiquetas de confidencialidad a los grupos de Microsoft 365 y a los sitios de SharePoint mediante la asignación de nombres. Vea la siguiente sección para obtener instrucciones.

2. Quitar las clasificaciones antiguas de los grupos y sitios existentes.

Aunque no se puede impedir que los usuarios creen grupos nuevos en aplicaciones y servicios que aún no admiten las etiquetas de confidencialidad, puede ejecutar un script de PowerShell periódico para buscar grupos nuevos que los usuarios han creado con las clasificaciones anteriores y convertirlos para usar etiquetas de confidencialidad. 

Para ayudarle a administrar la coexistencia de etiquetas de confidencialidad y clasificaciones de Azure AD para sitios y grupos, consulte [Clasificación y etiquetas de confidencialidad de Azure Active Directory para grupos de Microsoft 365](migrate-aad-classification-sensitivity-labels.md).

#### <a name="use-powershell-to-convert-classifications-for-microsoft-365-groups-to-sensitivity-labels"></a>Usar PowerShell para convertir clasificaciones de grupos de Microsoft 365 a etiquetas de confidencialidad

1. En primer lugar, [conéctese a PowerShell del Centro de seguridad y cumplimiento de Office 365](/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell). 
    
    Por ejemplo, en una sesión de PowerShell que se ejecuta como administrador, inicie sesión con una cuenta de administrador global:
    
    ```powershell
    Set-ExecutionPolicy RemoteSigned
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.compliance.protection.outlook.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session -DisableNameChecking
    ```

2. Consiga la lista de etiquetas de sensibilidad y sus GUIDs usando el cmdlet[Get-Label](https://docs.microsoft.com/powershell/module/exchange/get-label?view=exchange-ps):
    
    ```powershell
    Get-Label |ft Name, Guid
    ```

3. Tome nota de los GUID para las etiquetas de confidencialidad que quiere aplicar a los grupos de Microsoft 365.

4. Ahora[Conexión al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).
    
    Por ejemplo:
    
    ```powershell
    $UserCredential = Get-Credential
    $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $UserCredential -Authentication Basic -AllowRedirection
    Import-PSSession $Session
    ```

5. Use el comando siguiente como ejemplo para obtener la lista de grupos que actualmente tienen la clasificación de "general":

   ```PowerShell
   $Groups= Get-UnifiedGroup | Where {$_.classification -eq "General"}
   ```

6. Para cada grupo, agregue la nueva etiqueta de sensibilidad GUID. Por ejemplo:

    ```PowerShell
    foreach ($g in $groups)
    {Set-UnifiedGroup -Identity $g.Identity -SensitivityLabelId "457fa763-7c59-461c-b402-ad1ac6b703cc"}
    ```

7. Repita los pasos 5 y 6 para el resto de sus clasificaciones de grupo.

## <a name="auditing-sensitivity-label-activities"></a>Auditar actividades de etiqueta de confidencialidad

Si alguien carga un documento en un sitio protegido con una etiqueta de confidencialidad y el documento tiene una etiqueta de confidencialidad de [mayor prioridad](sensitivity-labels.md#label-priority-order-matters) que la etiqueta de confidencialidad que se aplica al sitio, esta acción no está bloqueada. Por ejemplo, aplicó la etiqueta **general** a un sitio de SharePoint y alguien carga en este sitio un documento etiquetado como **confidencial**. Debido a que una etiqueta de confidencialidad con mayor prioridad identifica el contenido que es más confidencial que el contenido que tiene un orden de menor prioridad, esta situación podría ser un problema de seguridad.

Aunque la acción no está bloqueada, se audita y genera automáticamente un correo electrónico a la persona que cargó el documento y el administrador del sitio. Como resultado, tanto el usuario como los administradores pueden identificar los documentos que no están alineados con la prioridad de las etiquetas y tomar las medidas necesarias. Por ejemplo, eliminar o mover el documento cargado del sitio. 

No sería un problema de seguridad si el documento tiene una etiqueta de confidencialidad de menor prioridad que la etiqueta de confidencialidad aplicada al sitio. Por ejemplo, un documento con la etiqueta **general** se carga en un sitio con la etiqueta **confidencial**. En este escenario, no se generarán ni un evento de auditoría, ni un correo electrónico.

Para buscar el registro de auditoría para este evento, busque **Desfase detectado de la confidencialidad del documento** en la categoría de las **actividades de archivos y páginas**. 

El correo electrónico generado automáticamente tiene el asunto **Etiqueta de confidencialidad no compatible detectado** y el mensaje de correo electrónico explica que la etiqueta no coincide con un vínculo al documento cargado y al sitio. También contiene un vínculo a la documentación en el que se explica cómo los usuarios pueden cambiar la etiqueta de confidencialidad. Actualmente, estos correos electrónicos automatizados no se pueden deshabilitar o personalizar.

Cuando alguien agrega o quita una etiqueta de confidencialidad a un sitio o grupo, estas actividades también se auditan, pero sin generar un correo electrónico automáticamente. 

Todos estos eventos de auditoría se pueden encontrar en la categoría [Actividades de etiqueta de confidencialidad](search-the-audit-log-in-security-and-compliance.md#sensitivity-label-activities). Para obtener instrucciones sobre cómo buscar el registro de auditoría, vea [buscar el registro de auditoría en el Centro de seguridad y cumplimiento](search-the-audit-log-in-security-and-compliance.md).

## <a name="how-to-disable-sensitivity-labels-for-containers"></a>Cómo deshabilitar etiquetas de confidencialidad para contenedores

Puede desactivar las etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint siguiendo las mismas instrucciones que se indican en [Habilitar la compatibilidad con etiquetas de confidencialidad en PowerShell](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-assign-sensitivity-labels#enable-sensitivity-label-support-in-powershell). Sin embargo, para deshabilitar la característica, en el paso 5, especifique `$setting["EnableMIPLabels"] = "False"`.

Además de ocultar la página **Configuración de sitios y grupos** cuando cree o edite etiquetas de confidencialidad, esta acción revierte la propiedad que usan los contenedores para su configuración. Al habilitar las etiquetas de confidencialidad para Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint se cambia la propiedad **Clasificación** (usada para la [clasificación de grupos de Azure AD](#classic-azure-ad-group-classification)) a **Confidencialidad**. Cuando deshabilita las etiquetas de confidencialidad para contenedores, estos ignoran la propiedad Confidencialidad y vuelven a usar la propiedad Clasificación.

Esto quiere decir que no se exigirá la configuración de etiquetas para sitios y grupos que se aplicó previamente a los contenedores, y los contenedores ya no mostrarán las etiquetas.

Si dichos contenedores tienen valores de clasificación de Azure AD aplicados, estos volverán a usar las clasificaciones. Tenga en cuenta que cualquier nuevo sitio o grupo creado después de habilitar la característica no mostrará una etiqueta ni tendrá una clasificación. Ahora puede aplicar valores de clasificación tanto a estos como a los nuevos contenedores. Para obtener más información, consulte [Clasificación de sitios "moderna" de SharePoint](https://docs.microsoft.com/sharepoint/dev/solution-guidance/modern-experience-site-classification) y [Crear clasificaciones para grupos de Office en su organización](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell).

## <a name="additional-resources"></a>Recursos adicionales

Consulte la grabación y las preguntas contestadas sobre el [Uso de etiquetas de sensibilidad con Microsoft Teams, grupos de O365 y sitios de SharePoint Online](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/using-sensitivity-labels-with-microsoft-teams-o365-groups-and/ba-p/1221885#M1380).

Este seminario web se grabó cuando la característica aún estaba en la versión preliminar, por lo que es posible que observe algunas discrepancias en la interfaz de usuario. Sin embargo, la información de esta característica aún es precisa, con las nuevas funciones que se documentan en esta página.
