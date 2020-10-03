---
title: Activar Office 365 ATP-SharePoint, OneDrive & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Obtenga información sobre cómo activar ATP para SharePoint, OneDrive y Teams, incluido cómo establecer alertas para los archivos detectados.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0c717a89492ea1160f26f26f13be6c36f348c79c
ms.sourcegitcommit: 3a0accd616ca94d6ba7f50e502552b45e9661a95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2020
ms.locfileid: "48350660"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar ATP para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Office 365 Advanced Threat Protection (ATP) para SharePoint, OneDrive y Microsoft Teams protege su organización de archivos malintencionados que se comparten de forma inadvertida. Para obtener más información, consulte [ATP para SharePoint, OneDrive y Microsoft Teams](atp-for-spo-odb-and-teams.md).

Este artículo contiene los pasos para habilitar y configurar ATP para SharePoint, OneDrive y Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>. Para ir directamente a la página **datos adjuntos seguros de ATP** , Abra <https://protection.office.com/safeattachmentv2> .

- Para activar ATP para SharePoint, OneDrive y Microsoft Teams, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** en el centro de seguridad & cumplimiento. Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

- Para usar PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados, debe ser miembro de los roles de administrador [global](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o [Administrador de SharePoint](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) en Azure ad.

- Compruebe que el registro de auditoría está habilitado para su organización. Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría ](../../compliance/turn-audit-log-search-on-or-off.md).

- Espere hasta 30 minutos para que la configuración surta efecto.

## <a name="step-1-use-the-security--compliance-center-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Paso 1: usar el centro de seguridad & cumplimiento para activar ATP para SharePoint, OneDrive y Microsoft Teams

1. En el centro de seguridad & cumplimiento, vaya a la Directiva de **Administración de amenazas** \> **Policy** \> **datos adjuntos seguros de ATP**y haga clic en **configuración global**.

2. En la **configuración global** vuela hacia fuera que aparece, vaya a la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** . Desplace el botón de alternancia a la derecha para ![ ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) Activar ATP para SharePoint, OneDrive y Microsoft Teams.

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="use-exchange-online-powershell-to-turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Usar Exchange Online PowerShell para activar ATP para SharePoint, OneDrive y Microsoft Teams

Si prefiere usar PowerShell para activar ATP para SharePoint, OneDrive y Microsoft Teams, [Conéctese a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Paso 2: (recomendado) usar PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados

De forma predeterminada, los usuarios no pueden abrir, mover, copiar ni compartir archivos malintencionados detectados por ATP. Sin embargo, pueden eliminar y descargar archivos malintencionados.

Para evitar que los usuarios descarguen archivos malintencionados, [Conéctese a PowerShell de SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y ejecute el siguiente comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Notas**:

- Esta configuración afecta tanto a usuarios como a administradores.
- Los usuarios pueden seguir eliminando archivos malintencionados.

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-security--compliance-center-to-create-an-alert-policy-for-detected-files"></a>Paso 3 (recomendado) usar el centro de seguridad & cumplimiento para crear una directiva de alerta para los archivos detectados

Puede crear una directiva de alerta que notifique a usted y a otros administradores Cuándo ATP para SharePoint, OneDrive y Microsoft Teams detecta un archivo malintencionado. Para obtener más información acerca de las alertas, consulte [crear alertas de actividad en el centro de seguridad & cumplimiento](../../compliance/create-activity-alerts.md).

1. En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a directivas de alerta de **alertas** \> **Alert policies** o abrir <https://protection.office.com/alertpolicies> .

2. En la página **directivas de alerta** , haga clic en **nueva Directiva de alerta**.

3. El Asistente para **nueva Directiva de alerta** se abre en un vuelo hacia fuera. En la página **asigne un nombre a la alerta** , configure las siguientes opciones:

   - **Nombre**: escriba un nombre único y descriptivo. Por ejemplo, archivos malintencionados en bibliotecas.
   - **Descripción**: escriba una descripción opcional. Por ejemplo, notifica a los administradores Cuándo se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.
   - **Gravedad**: deje el valor predeterminado **bajo** seleccionado o seleccione **medio** o **alto**.
   - **Seleccione una categoría**: seleccionar la **Administración de amenazas**.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **crear configuración de alertas** , configure las siguientes opciones:

   - **¿En qué desea alertar?: Activity es**: SELECT **Detected malware in file**.
   - **¿Cómo desea que se desencadene la alerta?**: deje el valor predeterminado **cada vez que una actividad coincida con la regla** seleccionada.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **establecer los destinatarios** , configure las siguientes opciones:

   - **Enviar notificaciones por correo electrónico**: Compruebe que esta configuración está seleccionada. En el cuadro **destinatarios de correo electrónico** , seleccione uno o más administradores globales, administradores de seguridad o lectores de seguridad que deban recibir una notificación cuando se detecte un archivo malintencionado.
   - **Límite de notificaciones diarias**: deje el valor predeterminado **sin límite** seleccionado.

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revise la configuración** , revise la configuración y haga clic en **Editar** en cualquiera de las secciones para realizar cambios.

   En la sección **¿desea activar la Directiva de inmediato?** , deje el valor predeterminado **sí, actívelo** inmediatamente seleccionado.

   Cuando haya terminado, haga clic en **Finalizar**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usar seguridad & PowerShell Compliance para crear una directiva de alerta para los archivos detectados

Si prefiere usar PowerShell para crear la misma directiva de alerta que se describe en la sección anterior, [Conéctese a PowerShell del centro de cumplimiento de & de seguridad](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell) y ejecute el siguiente comando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Nota**: el valor de _gravedad_ predeterminado es bajo. Para especificar medio o alto, incluya el parámetro _Severity_ y el valor en el comando.

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [New-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

- Para comprobar si ha activado ATP para SharePoint, OneDrive y Microsoft Teams correctamente, siga uno de estos pasos:

  - En el [centro de seguridad & cumplimiento](https://protection.office.com), vaya a la Directiva de **Administración de amenazas** : \> **Policy** \> **datos adjuntos seguros de ATP**, seleccione **configuración global**y compruebe el valor de la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .

  - En Exchange Online PowerShell, ejecute el siguiente comando para comprobar la configuración de la propiedad:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).

- Para comprobar que ha bloqueado correctamente que los usuarios puedan descargar archivos malintencionados, abra PowerShell de SharePoint Online y ejecute el siguiente comando para comprobar el valor de la propiedad:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant).

- Para comprobar que ha configurado correctamente una directiva de alerta para los archivos detectados, siga uno de estos pasos:

  - En el centro de seguridad & cumplimiento, vaya a **alertas** \> **de alertas** \> y seleccione la Directiva de alerta y Compruebe la configuración.

  - En el PowerShell del centro de cumplimiento de & de seguridad, reemplace \<AlertPolicyName\> por el nombre de la Directiva de alerta, ejecute el siguiente comando y compruebe los valores de propiedad:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [Get-ActivityAlert](https://docs.microsoft.com/powershell/module/exchange/get-activityalert).

- Use el [Informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) para ver información sobre los archivos detectados en SharePoint, OneDrive y Microsoft Teams. Concretamente, puede usar la vista **ver datos por: \> malware de contenido** .
