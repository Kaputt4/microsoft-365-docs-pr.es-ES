---
title: Administrar sus permitidos en la lista de inquilinos permitidos/bloqueados
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar los permisos en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5870ff663f0e97d699f6e4a158f8b0b05ee0bf15
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53544330"
---
# <a name="add-allows-in-the-tenant-allowblock-list"></a>Agregar permite en la lista de inquilinos permitidos o bloqueados

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

No se puede agregar allows directamente a la lista de inquilinos permitidos o bloqueados. Use el proceso de envío de administrador para agregar la dirección URL, el archivo y/o el remitente a la lista de inquilinos permitidos o bloqueados. Microsoft no permite que los administradores agreguen permisos directamente, pero determina lo que se bloqueó y le permite. En la mayoría de los casos, se agregan los permitidos para dar al sistema algo de tiempo y permitirlo de forma natural si se garantiza. En algunos casos, Microsoft administra la opción para usted.

## <a name="add-allows-using-the-submissions-portal"></a>Agregar permite usar el portal de envíos 

Permitir archivos, direcciones URL y remitentes en la sección Envíos de Microsoft 365 Defender. 

1. En el portal Microsoft 365 Defender, vaya a **Correo electrónico &** \> **envíos de colaboración**.

2. En la **página Envíos,** compruebe que la pestaña **Enviado** para el análisis está seleccionada y, a continuación, haga clic en Icono de anuncio ![ Enviar a Microsoft para su ](../../media/m365-cc-sc-create-icon.png) **análisis.**

3. Use el menú desplegable **Enviar a Microsoft para** revisión para marcar el remitente, el archivo o la dirección URL como falso positivo. 

4. En la **sección Seleccionar un motivo para enviar a Microsoft,** seleccione No se debe haber bloqueado **(falso positivo).** 

5. Activa Permitir **mensajes como esta** opción. 

6. En la **lista** desplegable Quitar después, especifique cuánto tiempo desea que funcione la opción permitir.

7. Cuando haya terminado, haga clic en el **botón Enviar.**

> [!div class="mx-imgBorder"]
> ![Ejemplo de envío falso positivo](../../media/admin-submission-allow-messages.png)

## <a name="create-spoofed-sender-allow-entries-using-microsoft-365-defender"></a>Crear entradas de permitido de remitente suplantado mediante Microsoft 365 Defender

**Notas**:

- Solo se _permite o_ bloquea  específicamente la combinación del usuario suplantado y la infraestructura de envío definida en el par de dominio.
- Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia suplantación.
- Las entradas de remitentes suplantados nunca expiran.
- La suplantación admite permitir y bloquear. La dirección URL solo admite permitir.

1. En el portal Microsoft 365 Defender, vaya a **Directivas &** sección Reglas de directivas de amenazas sección Listas de \>  \>  \> **inquilinos permitidos o bloqueados.**

2. En la **página Lista de inquilinos permitidos o** bloqueados, seleccione la pestaña **Suplantación** y, a continuación, haga clic ![ en Bloquear icono ](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el **menú desplegable Agregar nuevos pares de** dominio que aparece, configure las siguientes opciones:
   - **Agregar nuevos pares de dominio con caracteres comodín:** escriba un par de dominio por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, vea [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).
   - **Tipo de suplantación:** seleccione uno de los siguientes valores:
     - **Interno:** el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado).](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **Externo:** el remitente suplantado está en un dominio externo.
   - **Acción:** seleccione **Permitir** o **Bloquear**.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="add-spoofed-sender-allow-entries-using-powershell"></a>Agregar entradas de permitido de remitente suplantado con PowerShell

Para agregar entradas de remitente suplantadas en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

## <a name="related-articles"></a>Artículos relacionados

- [Envíos de administrador](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)