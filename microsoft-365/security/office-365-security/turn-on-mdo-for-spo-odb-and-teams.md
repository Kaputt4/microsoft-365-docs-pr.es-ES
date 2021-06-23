---
title: Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Los administradores pueden aprender a activar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, incluido cómo establecer alertas para los archivos detectados.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b64b3cfb29b3be999c9e26804e35dc4d02e48fbb
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083097"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege a su organización de compartir accidentalmente archivos malintencionados. Para obtener más información, [vea Caja fuerte attachments for SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Este artículo contiene los pasos para habilitar y configurar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la **página Caja fuerte datos adjuntos,** abra <https://security.microsoft.com/safeattachmentv2> .

- Para activar Caja fuerte datos adjuntos de SharePoint, OneDrive y Microsoft Teams, debe ser miembro de los  grupos  de roles Administración de la organización o Administrador de seguridad en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Para usar SharePoint PowerShell en línea para evitar que los usuarios descarguen archivos [](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#sharepoint-administrator) malintencionados, debe ser miembro de los roles administrador [global](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#global-administrator--company-administrator) o administrador SharePoint en Azure AD.

- Compruebe que el registro de auditoría está habilitado para su organización. Para obtener más información, consulte [Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

- Espere hasta 30 minutos para que la configuración suba a efecto.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Paso 1: Usar el portal Microsoft 365 Defender para activar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams

1. En el portal Microsoft 365 Defender, vaya **a Directivas &** de directivas de amenazas sección Directivas de amenazas Caja fuerte Datos \>  \>  \> **adjuntos**.

2. En la **página Caja fuerte datos adjuntos,** haga clic en **Configuración global**.

3. En el **menú desplegable Configuración global** que aparece, vaya a la sección Proteger archivos de **SharePoint, OneDrive y Microsoft Teams.**

   Mueva la palanca Activar defender para Office 365 para **SharePoint, OneDrive** y Microsoft Teams a la derecha Activar para activar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y ![ ](../../media/scc-toggle-on.png) Microsoft Teams.

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Use Exchange Online PowerShell para activar Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams

Si prefiere usar PowerShell para activar los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, conéctese [a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Paso 2: (recomendado) Usar SharePoint PowerShell en línea para evitar que los usuarios descarguen archivos malintencionados

De forma predeterminada, los usuarios no pueden abrir, mover, copiar o compartir archivos malintencionados detectados por los datos adjuntos de Caja fuerte para SharePoint, OneDrive y <sup>\*</sup> Microsoft Teams. Sin embargo, pueden eliminar y descargar archivos malintencionados.

<sup>\*</sup> Si los usuarios van a **Administrar acceso,** la **opción** Compartir aún está disponible.

Para evitar que los usuarios descarguen archivos malintencionados, conéctese [a SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) en línea y ejecute el siguiente comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Notas**:

- Esta configuración afecta tanto a usuarios como a administradores.
- Los usuarios aún pueden eliminar archivos malintencionados.

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Paso 3 (recomendado) Use el portal de Microsoft 365 Defender para crear una directiva de alerta para los archivos detectados

Puede crear una directiva de alerta que le informe a usted y a otros administradores cuando Caja fuerte datos adjuntos para SharePoint, OneDrive y Microsoft Teams detecte un archivo malintencionado. Para obtener más información sobre las alertas, vea [Create activity alerts in the Microsoft 365 Defender portal](../../compliance/create-activity-alerts.md).

1. En el portal Microsoft 365 Defender, vaya **a Directivas & reglas de** alerta o abra \>  <https://security.microsoft.com/alertpolicies> .

2. En la página **Directiva de alertas,** haga clic **en Nueva directiva de alerta**.

3. El **Asistente para nueva directiva de** alertas se abre en un desplegable. En la **página Nombre de la alerta,** configure las siguientes opciones:
   - **Nombre:** escriba un nombre único y descriptivo. Por ejemplo, Archivos malintencionados en bibliotecas.
   - **Descripción:** escriba una descripción opcional. Por ejemplo, notifica a los administradores cuándo se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.
   - **Gravedad:** seleccione **Bajo,** **Medio** o **Alto** en la lista desplegable.
   - **Categoría:** seleccione **Administración de amenazas** en la lista desplegable.

   Cuando termine, haga clic en **Siguiente**.

4. En la **página Crear configuración de alerta,** configure las siguientes opciones:
   - **¿En qué desea alertar?** sección \> **Actividad es** \> Seleccionar malware detectado en **el** archivo de la lista desplegable.
   - **¿Cómo desea que se desencadene la alerta?** sección: Deje el valor predeterminado **Cada vez que una actividad coincida con la regla** seleccionada.

   Cuando termine, haga clic en **Siguiente**.

5. En la **página Establecer los destinatarios,** configure las siguientes opciones:
   - Compruebe **que enviar notificaciones por correo electrónico** está seleccionado. En el **cuadro Destinatarios de correo** electrónico, seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir notificaciones cuando se detecte un archivo malintencionado.
   - **Límite de notificación diario:** deje el valor predeterminado **Sin límite** seleccionado.

   Cuando termine, haga clic en **Siguiente**.

6. En la **página Revisar la configuración,** revisa la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   En la sección ¿Desea activar la directiva **inmediatamente?,** deje seleccionado el valor predeterminado **Sí, encórzcala inmediatamente.**

   Cuando haya terminado, haga clic en **Finalizar**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Usar PowerShell de & seguridad para crear una directiva de alerta para los archivos detectados

Si prefiere usar PowerShell para crear la misma directiva de alerta que se describe en la sección anterior, conéctese [a PowerShell](/powershell/exchange/connect-to-scc-powershell) del Centro de seguridad & cumplimiento y ejecute el siguiente comando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Nota:** El valor _predeterminado de gravedad_ es Low. Para especificar Medium o High, incluya el _parámetro Severity_ y el valor en el comando.

Para obtener información detallada acerca de la sintaxis y los parámetros, [vea New-ActivityAlert](/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

- Para comprobar que ha activado correctamente los datos adjuntos de Caja fuerte para SharePoint, OneDrive y Microsoft Teams, siga uno de los pasos siguientes:

  - En el portal de Microsoft 365 Defender, vaya **a** Directivas & reglas Directivas de amenazas sección Directivas de amenazas Caja fuerte Datos adjuntos, seleccione Configuración global y compruebe el valor de la configuración Activar defender para Office 365 para SharePoint, OneDrive y \>  \>  \>  **Microsoft Teams.** 

  - En Exchange Online PowerShell, ejecute el siguiente comando para comprobar la configuración de la propiedad:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).

- Para comprobar que ha bloqueado correctamente la descarga de archivos malintencionados, abra SharePoint PowerShell en línea y ejecute el siguiente comando para comprobar el valor de la propiedad:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

- Para comprobar que ha configurado correctamente una directiva de alerta para los archivos detectados, siga estos pasos:
  - En el portal Microsoft 365 Defender, vaya a **Directivas & reglas** de alerta Seleccione la directiva de alerta y compruebe la \>  \> configuración.
  - En Microsoft 365 Defender powerShell del portal, reemplace por el nombre de la directiva de alerta, ejecute el siguiente comando y \<AlertPolicyName\> compruebe los valores de la propiedad:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para obtener información detallada sobre la sintaxis y los parámetros, [vea Get-ActivityAlert](/powershell/module/exchange/get-activityalert).

- Use el [informe de estado de](view-email-security-reports.md#threat-protection-status-report) protección contra amenazas para ver información sobre los archivos detectados en SharePoint, OneDrive y Microsoft Teams. En concreto, puede usar la **vista Ver datos mediante: Vista malware \> de** contenido.
