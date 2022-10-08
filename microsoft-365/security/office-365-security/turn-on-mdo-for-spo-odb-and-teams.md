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
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- m365-security
- SPO_Content
description: Los administradores pueden aprender a activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, incluido cómo establecer alertas para los archivos detectados.
ms.custom:
- seo-marvel-apr2020
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 005168ba9f450b78b08714bb322f9f0cc52303b0
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68075128"
---
# <a name="turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Activar Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams protege a su organización de compartir involuntariamente archivos malintencionados. Para obtener más información, vea [Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams](mdo-for-spo-odb-and-teams.md).

Este artículo contiene los pasos para habilitar y configurar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Datos adjuntos seguros** , use <https://security.microsoft.com/safeattachmentv2>.

- Para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, debe ser miembro de los grupos de roles **Administración** de la organización o **Administrador de seguridad** en el portal de Microsoft 365 Defender. Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

- Para usar PowerShell de SharePoint Online para evitar que las personas descarguen archivos malintencionados, debe ser miembro de los roles [Administrador global](/azure/active-directory/roles/permissions-reference#global-administrator) o [Administrador de SharePoint](/azure/active-directory/roles/permissions-reference#sharepoint-administrator) en Azure AD.

- Compruebe que el registro de auditoría está habilitado para su organización. Para obtener más información, consulte [Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

- Espere hasta 30 minutos para que la configuración surta efecto.

## <a name="step-1-use-the-microsoft-365-defender-portal-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Paso 1: Usar el portal de Microsoft 365 Defender para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directivas de amenazas** \> **Datos adjuntos seguros** en la sección **Directivas**. Para ir directamente a la página **Datos adjuntos seguros** , use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Datos adjuntos seguros** , haga clic en **Configuración global**.

3. En el control **flotante Configuración global** que aparece, vaya a la sección **Proteger archivos en SharePoint, OneDrive y Microsoft Teams** .

   Mueva el botón **Activar Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams** a la derecha ![Activar alternancia.](../../media/scc-toggle-on.png) para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams.

   Cuando haya terminado, haga clic en **Guardar**.

### <a name="use-exchange-online-powershell-to-turn-on-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>Use Exchange Online PowerShell para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams

Si prefiere usar PowerShell para activar datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, [conéctese a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) y ejecute el siguiente comando:

```powershell
Set-AtpPolicyForO365 -EnableATPForSPOTeamsODB $true
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

## <a name="step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files"></a>Paso 2: (Recomendado) Usar PowerShell de SharePoint Online para evitar que los usuarios descarguen archivos malintencionados

De forma predeterminada, los usuarios no pueden abrir, mover, copiar ni compartir<sup>\*</sup> archivos malintencionados detectados por datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams. Sin embargo, pueden eliminar y descargar archivos malintencionados.

<sup>\*</sup> Si los usuarios van a **Administrar acceso**, la opción **Compartir** sigue estando disponible.

Para evitar que los usuarios descarguen archivos malintencionados, [conéctese a PowerShell de SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) y ejecute el siguiente comando:

```powershell
Set-SPOTenant -DisallowInfectedFileDownload $true
```

**Notas**:

- Esta configuración afecta tanto a los usuarios como a los administradores.
- Personas puede eliminar archivos malintencionados.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

## <a name="step-3-recommended-use-the-microsoft-365-defender-portal-to-create-an-alert-policy-for-detected-files"></a>Paso 3 (recomendado) Uso del portal de Microsoft 365 Defender para crear una directiva de alertas para los archivos detectados

Puede crear una directiva de alertas que le notifique a usted y a otros administradores cuando Datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams detecten un archivo malintencionado. Para obtener más información sobre las alertas, consulte [Directivas de alertas](../../compliance/alert-policies.md).

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas** \> **Directiva de alertas**. Para ir directamente a la página de **Directiva de alertas**, use <https://security.microsoft.com/alertpolicies>.

2. En la página **Directiva de alertas** , haga clic en **Nueva directiva de alerta**.

3. El Asistente **para nueva directiva de alertas** se abre en un control flotante. En la página **Nombre de la alerta** , configure los siguientes valores:
   - **Nombre**: escriba un nombre único y descriptivo. Por ejemplo, Archivos malintencionados en bibliotecas.
   - **Descripción**: escriba una descripción opcional. Por ejemplo, notifica a los administradores cuando se detectan archivos malintencionados en SharePoint Online, OneDrive o Microsoft Teams.
   - **Gravedad**: seleccione **Baja**, **Media** o **Alta** en la lista desplegable.
   - **Categoría**: seleccione **Administración de amenazas** en la lista desplegable.

   Cuando termine, haga clic en **Siguiente**.

4. En la página **Crear configuración de alerta** , configure los siguientes valores:
   - **¿En qué quiere alertar?** **la actividad de** la sección \> es \> Seleccionar **malware detectado en el archivo de** la lista desplegable.
   - **¿Cómo desea que se desencadene la alerta?** section: deje el valor predeterminado **Cada vez que una actividad coincida con la regla** seleccionada.

   Cuando termine, haga clic en **Siguiente**.

5. En la página **Establecer los destinatarios** , configure los siguientes valores:
   - Compruebe que **la opción Enviar notificaciones por correo electrónico** está seleccionada. En el cuadro **destinatarios de Email**, seleccione uno o varios administradores globales, administradores de seguridad o lectores de seguridad que deben recibir una notificación cuando se detecte un archivo malintencionado.
   - **Límite de notificación diario**: deje seleccionado el valor predeterminado **Sin límite** .

   Cuando termine, haga clic en **Siguiente**.

6. En la página **Revisar la configuración** , revise la configuración. Puede seleccionar **Editar** en cada sección para modificar la configuración dentro de la sección. También puede hacer clic en **Volver atrás** o seleccionar la página específica del asistente.

   En la sección **¿Desea activar la directiva inmediatamente?** deje seleccionado el valor predeterminado **Sí y actíelo de inmediato** .

   Cuando haya terminado, haga clic en **Finalizar**.

### <a name="use-security--compliance-powershell-to-create-an-alert-policy-for-detected-files"></a>Uso de PowerShell de cumplimiento de seguridad & para crear una directiva de alertas para los archivos detectados

Si prefiere usar PowerShell para crear la misma directiva de alertas que se describe en la sección anterior, [conéctese a PowerShell de cumplimiento de seguridad &](/powershell/exchange/connect-to-scc-powershell) y ejecute el siguiente comando:

```powershell
New-ActivityAlert -Name "Malicious Files in Libraries" -Description "Notifies admins when malicious files are detected in SharePoint Online, OneDrive, or Microsoft Teams" -Category ThreatManagement -Operation FileMalwareDetected -NotifyUser "admin1@contoso.com","admin2@contoso.com"
```

**Nota**: El valor _de gravedad_ predeterminado es Bajo. Para especificar Medium o High, incluya el parámetro _Severity_ y el valor en el comando.

Para obtener información detallada sobre la sintaxis y los parámetros, vea [New-ActivityAlert](/powershell/module/exchange/new-activityalert).

### <a name="how-do-you-know-these-procedures-worked"></a>¿Cómo saber si estos procedimientos han funcionado?

- Para comprobar que ha activado correctamente datos adjuntos seguros para SharePoint, OneDrive y Microsoft Teams, siga estos pasos:

  - En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas** \> **Directivas** \> de amenazas  sección \> **Datos adjuntos seguros**, seleccione **Configuración global** y compruebe el valor de la opción **Activar Defender para Office 365 para SharePoint, OneDrive y Microsoft Teams**.

  - En Exchange Online PowerShell, ejecute el siguiente comando para comprobar la configuración de la propiedad:

    ```powershell
    Get-AtpPolicyForO365 | Format-List EnableATPForSPOTeamsODB
    ```

    Para obtener información detallada sobre la sintaxis y los parámetros, consulte [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).

- Para comprobar que ha bloqueado correctamente la descarga de archivos malintencionados, abra PowerShell de SharePoint Online y ejecute el siguiente comando para comprobar el valor de la propiedad:

  ```powershell
  Get-SPOTenant | Format-List DisallowInfectedFileDownload
  ```

  Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant).

- Para comprobar que ha configurado correctamente una directiva de alerta para los archivos detectados, siga estos pasos:
  - En el portal de Microsoft 365 Defender, vaya a **Directivas & reglas** \> **Directiva de alertas** \> seleccione la directiva de alerta y compruebe la configuración.
  - En Microsoft 365 Defender portal de PowerShell, reemplace por \<AlertPolicyName\> el nombre de la directiva de alerta, ejecute el siguiente comando y compruebe los valores de propiedad:

    ```powershell
    Get-ActivityAlert -Identity "<AlertPolicyName>"
    ```

    Para obtener información detallada sobre la sintaxis y los parámetros, vea [Get-ActivityAlert](/powershell/module/exchange/get-activityalert).

- Use el [informe de estado de protección contra amenazas](view-email-security-reports.md#threat-protection-status-report) para ver información sobre los archivos detectados en SharePoint, OneDrive y Microsoft Teams. En concreto, puede usar la vista **Ver datos mediante: Malware de contenido\>**.
