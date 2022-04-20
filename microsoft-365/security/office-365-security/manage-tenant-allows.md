---
title: Administrar los permitidos en la lista de permitidos o bloqueados de inquilinos
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150manage-tenant-allows.md
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a configurar los permisos en la lista de permitidos o bloqueados de inquilinos en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ad2a55d19f60bf310b62ac13dfbe2563709673d2
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64970951"
---
# <a name="add-allows-in-the-tenant-allowblock-list"></a>Agregar permisos a la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Los administradores no pueden agregar permisos directamente a la lista de permitidos o bloqueados de inquilinos. En su lugar, usa el proceso de envío del administrador para enviar el mensaje que se bloqueó, de modo que la dirección URL, el archivo o los remitentes correspondientes se agregarán a la lista de permitidos o bloqueados de inquilinos. Si no se ha producido un bloque del archivo, la dirección URL o el remitente, no se creará la opción allow. En la mayoría de los casos en los que se determinó que el mensaje era un falso positivo que se bloqueó incorrectamente, los permisos se mantienen durante el tiempo necesario para dar al sistema tiempo para permitirlos de forma natural.

> [!IMPORTANT]
> Dado que Microsoft administra el objeto permite que usted, el remitente, la dirección URL o el archivo permita que no sean necesarios o que se consideren incorrectos, se quitarán. Esto es para proteger el entorno y evitar una configuración incorrecta de allows. En los casos en los que no esté de acuerdo, es posible que se necesiten casos de soporte técnico para ayudar a determinar por qué un mensaje todavía se considera incorrecto.

## <a name="add-sender-allows-using-the-submissions-portal"></a>Agregar remitente permite usar el portal envíos

Permitir remitentes (o dominios) en la página **Envíos** de Microsoft 365 Defender.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , compruebe que la pestaña **Correos electrónicos** está seleccionada y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando el identificador de mensaje de red o cargando el archivo de correo electrónico.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active **Permitir mensajes como esta** opción.

6. En la lista desplegable **Quitar después** , especifique cuánto tiempo desea que funcione la opción permitir.

7. Cuando haya terminado, haga clic en el botón **Enviar** .

> ![Envíe malware a Microsoft para el ejemplo de análisis.](../../media/admin-submission-allow-messages.png)

## <a name="add-url-allows-using-the-submissions-portal"></a>Agregar dirección URL permite usar el portal envíos

Permitir direcciones URL en la página **Envíos** de Microsoft 365 Defender.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione la pestaña **Direcciones URL** y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando la dirección URL.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active la opción **Permitir direcciones URL como esta** .

6. En la lista desplegable **Quitar después** , especifique cuánto tiempo desea que funcione la opción permitir.

7. Cuando haya terminado, haga clic en el botón **Enviar** .

> [!div class="mx-imgBorder"]
> ![Envíe la dirección URL para su análisis.](../../media/submit-url-for-analysis.png)

## <a name="add-file-allows-using-the-submissions-portal"></a>Agregar archivo permite usar el portal envíos

Permitir archivos en la página **Envíos** de Microsoft 365 Defender.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione la pestaña **Datos adjuntos de correo electrónico** y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando el archivo o los archivos.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active la opción **Permitir archivos como esta** .

6. En la lista desplegable **Quitar después** , especifique cuánto tiempo desea que funcione la opción permitir.

7. Cuando haya terminado, haga clic en el botón **Enviar** .

> [!div class="mx-imgBorder"]
> ![Enviar correo electrónico para su análisis.](../../media/submit-email-for-analysis.png)

## <a name="create-spoofed-sender-allow-entries-using-microsoft-365-defender"></a>Creación de entradas permitidas del remitente suplantado mediante Microsoft 365 Defender

> [!NOTE]
>
> - Solo se permite o bloquea específicamente la _combinación_ del usuario suplantado _y_ la infraestructura de envío tal como se define en el par de dominio.
> - Al configurar una entrada de permitir o bloquear para un par de dominio, los mensajes de ese par de dominio ya no aparecen en la información de inteligencia de suplantación de identidad.
> - Las entradas para remitentes suplantados nunca expiran.
> - La suplantación de identidad admite permitir y bloquear. La dirección URL solo admite permitir.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Correo electrónico &** directivas de colaboración \> **& reglas Directivas** \> de **amenazas** \> Listas de **inquilinos permitidos o bloqueados** en la sección **Reglas**. O bien, para ir directamente a la página **Permitir o bloquear listas de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Suplantación** de identidad y, a continuación, haga clic en ![el icono Agregar.](../../media/m365-cc-sc-create-icon.png) **Agregar**.

3. En el control flotante **Agregar nuevos pares de dominio** que aparece, configure los siguientes valores:
   - **Agregar nuevos pares de dominio con caracteres comodín**: escriba un par de dominio por línea, hasta un máximo de 20. Para obtener más información sobre la sintaxis de las entradas de remitente suplantadas, consulte [Administrar la lista de permitidos o bloques](tenant-allow-block-list.md) de inquilinos.
   - **Tipo de suplantación**: seleccione uno de los valores siguientes:
     - **Interno**: el remitente suplantado está en un dominio que pertenece a su organización (un [dominio aceptado](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)).
     - **Externo**: el remitente suplantado está en un dominio externo.
   - **Acción**: seleccione **Permitir** o **Bloquear**.

4. Cuando haya terminado, haga clic en **Agregar**.

## <a name="add-spoofed-sender-allow-entries-using-powershell"></a>Adición de entradas permitidas del remitente suplantado mediante PowerShell

Para agregar entradas de remitente suplantadas en la lista de permitidos o bloqueados de inquilinos en [Exchange Online PowerShell](/exchange/connect-to-exchange-online-powershell), use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems).

## <a name="related-articles"></a>Artículos relacionados

- [Envíos de administradores](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)
