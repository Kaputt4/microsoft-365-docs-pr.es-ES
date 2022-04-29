---
title: Quitar conectores bloqueados del portal de entidades restringidas en Microsoft 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Obtenga información sobre cómo quitar conectores bloqueados en Microsoft 365 Defender.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7d248129c7dec83541c4b340fdac7e881344bbf0
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2022
ms.locfileid: "65131468"
---
# <a name="remove-blocked-connectors-from-the-restricted-entities-portal"></a>Eliminación de conectores bloqueados del portal de entidades restringidas

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**

- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Si se detecta que un conector de entrada está potencialmente en peligro, se le restringe el envío de cualquier correo electrónico de retransmisión. A continuación, el conector se agrega a la página **Entidades restringidas** del portal de Microsoft 365 Defender. Cuando se usa el conector para enviar correo electrónico, el mensaje se devuelve en un informe de no entrega (también conocido como NDR o mensaje devuelto) con el código de error 550;5.7.711 y el texto siguiente: 

> No se pudo entregar el mensaje. La razón más común para esto es que el conector de correo electrónico de su organización es sospechoso de enviar correo no deseado o phish y ya no tiene permiso para enviar correo electrónico. Póngase en contacto con el administrador de correo electrónico para obtener ayuda. 
> Servidor remoto devolvió '550;5.7.711 Acceso denegado, conector de entrada incorrecto. AS(2204).' 

Los administradores pueden quitar conectores de la página Entidades restringidas en Microsoft 365 Defender o en Exchange Online PowerShell. 

## <a name="learn-more-on-restricted-entities"></a>Más información sobre las entidades restringidas

Una entidad restringida es una entidad que se ha bloqueado para enviar correo electrónico porque se ha visto potencialmente comprometida o ha superado el límite de envío.

Hay dos tipos de entidades restringidas: 

- **Usuario restringido**: para obtener más información sobre por qué se puede restringir un usuario y cómo controlar usuarios restringidos, consulte [Eliminación de usuarios bloqueados del portal de entidades restringidas](removing-user-from-restricted-users-portal-after-spam.md). 

- **Conector restringido**: obtenga información sobre por qué se puede restringir un conector y cómo controlar conectores restringidos (en este artículo).  

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Entidades restringidas** , use <https://security.microsoft.com/restrictedentities>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos en **Exchange Online** para poder seguir los procedimientos mencionados en este artículo:
  - Para quitar conectores del portal de entidades restringidas, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** .
  - Para el acceso de solo lectura al portal de entidades restringidas, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

- Antes de quitar el conector del portal de entidades restringidas, asegúrese de seguir los pasos necesarios para recuperar el control del conector. Para obtener más información, vea [Responder a un conector en peligro](respond-compromised-connector.md).

## <a name="use-the-microsoft-365-defender-portal-to-remove-a-connector-from-the-restricted-entities-list"></a>Use el portal de Microsoft 365 Defender para quitar un conector de la lista entidades restringidas

1. En el [portal de Microsoft 365 Defender](https://security.microsoft.com), vaya a **Correo electrónico & entidades** **restringidas** **de revisión de** \> colaboración\>. Para ir directamente a la página **Entidades restringidas** , use <https://security.microsoft.com/restrictedentities>.

2. En la página **Entidades restringidas** , busque y seleccione el conector que desea desbloquear haciendo clic en el conector.

3. Haga clic en la acción **Desbloquear** que aparece.

4. En el control flotante **Desbloquear entidad** que aparece, lea los detalles sobre el conector restringido. Debe seguir las recomendaciones para asegurarse de que está realizando las acciones adecuadas en caso de que el conector esté en peligro.

5. Cuando haya terminado, haga clic en **Desbloquear**.

   > [!NOTE]
   > Todas las restricciones pueden tardar hasta 1 hora en quitarse del conector.

## <a name="verify-the-alert-settings-for-restricted-connectors"></a>Comprobación de la configuración de alertas para conectores restringidos

La directiva de alertas predeterminada denominada **Actividad de conector sospechosa** notificará automáticamente a los administradores cuando se bloquee la transmisión de correo electrónico a los conectores. Para obtener más información sobre las directivas de alerta, consulte [Directivas de alerta en Microsoft 365](../../compliance/alert-policies.md).

> [!IMPORTANT]
> Para que las alertas funcionen, debe activarse la búsqueda de registros de auditoría. Para obtener más información, consulte [ Desactivar o activar la búsqueda de registros de auditoría](../../compliance/turn-audit-log-search-on-or-off.md).

1. En el portal de Microsoft 365 Defender, vaya a **Correo electrónico y colaboración** \> **Directivas y reglas** \> **directiva de alertas**.

2. En la página **Directiva de alertas** , busque y seleccione la alerta denominada **Actividad de conector sospechosa**. Puede ordenar las directivas por nombre o usar el **Cuadro de búsqueda** para buscar la directiva.

3. En el control flotante **Actividad sospechosa del conector** que aparece, compruebe o configure los siguientes valores:
   - **Estado**: compruebe que la alerta está activada ![Activación](../../media/scc-toggle-on.png).
   - **Destinatarios de correo electrónico**: Haga clic en **Editar** y compruebe o configure las siguientes opciones en el control flotante **Editar destinatarios** que aparece:
     - **Enviar notificaciones por correo electrónico**: compruebe que está seleccionado (**Activado**).
     - **Destinatarios de correo electrónico**: El valor predeterminado es **TenantAdmins** (lo que significa miembros de **Administrador global**). Para agregar más destinatarios, haga clic en un área en blanco del cuadro. Se mostrará una lista de destinatarios y puede empezar a escribir un nombre para filtrar y seleccionar un destinatario. Para quitar un destinatario existente del cuadro, haga clic en el ![Icono Quitar](../../media/m365-cc-sc-remove-selection-icon.png) junto a su nombre.
     - **Límite diario de notificaciones**: el límite no es superior a 3 notificaciones por conector al día.

     Cuando haya terminado, haga clic en **Guardar**.

4. De nuevo en el control flotante **Actividad sospechosa del conector** , haga clic en **Cerrar**.

## <a name="use-exchange-online-powershell-to-view-and-remove-connectors-from-the-restricted-entities-list"></a>Use Exchange Online PowerShell para ver y quitar conectores de la lista entidades restringidas

Para ver la lista de conectores que tienen restringido el envío de correo electrónico, ejecute el siguiente comando:

```powershell
Get-BlockedConnector
```

Para ver detalles sobre un conector específico, reemplace \<connectorId\> y ejecute el siguiente comando:

```powershell
Get-BlockedConnector -ConnectorId <connectorId>
```

Para quitar un conector de la lista de entidades restringidas, reemplace \<connectorId\> y ejecute el siguiente comando:

```powershell
Remove-BlockedConnector -ConnectorId <connectorId>
```

## <a name="more-information"></a>Más información

- [Respuesta a un conector en peligro](respond-compromised-connector.md)
- [Eliminación de usuarios bloqueados](removing-user-from-restricted-users-portal-after-spam.md)