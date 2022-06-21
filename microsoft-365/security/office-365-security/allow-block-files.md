---
title: Permitir o bloquear archivos mediante la lista de bloqueados y permitidos del espacio empresarial
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
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a permitir o bloquear archivos en la lista de inquilinos permitidos o bloqueados en el portal de seguridad.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a85af4beda791fb9cc2382a48a701406941d0325
ms.sourcegitcommit: 7df8adc9e67ab65e413d7ea7bb0dcb9fd2da1a11
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2022
ms.locfileid: "66185805"
---
# <a name="allow-or-block-files-using-the-tenant-allowblock-list"></a>Permitir o bloquear archivos mediante la lista de bloqueados y permitidos del espacio empresarial

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Puede usar el portal de Microsoft 365 Defender o PowerShell para permitir o bloquear archivos en la lista de permitidos o bloqueados de inquilinos.

## <a name="create-block-file-entries"></a>Creación de entradas de archivo de bloque 

### <a name="use-microsoft-365-defender"></a>Uso de Microsoft 365 Defender

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas & reglas De directivas** \> de amenazas sección \> **Reglas de directivas** de **amenazas** \> **Listas de permitidos o bloques de inquilinos**. O bien, para ir directamente a la página **Permitir o bloquear lista de inquilinos** , use <https://security.microsoft.com/tenantAllowBlockList>.

2. En la página **Lista de permitidos o bloqueados de inquilinos** , seleccione la pestaña **Archivos** y, a continuación, haga clic en ![el icono Bloquear.](../../media/m365-cc-sc-create-icon.png) **Bloquear**.

3. En el control flotante **Bloquear archivos** que aparece, configure los siguientes valores:
   - **Agregar hash de archivo**: escriba un valor hash SHA256 por línea, hasta un máximo de 20.
   - **Nunca expire**: realice uno de los pasos siguientes:
     - Compruebe que la configuración está desactivada (![desactivar)](../../media/scc-toggle-off.png) y use el cuadro **Quitar activado** para especificar la fecha de expiración de las entradas.

     o

     - Mueva el botón de alternancia a la derecha para configurar las entradas para que nunca expiren: ![Activar.](../../media/scc-toggle-on.png).
   - **Nota opcional**: escriba texto descriptivo para las entradas.

4. Cuando haya terminado, haga clic en **Agregar**.

> [!NOTE]
> Los correos electrónicos que contienen estos archivos se bloquearán como _malware_.

### <a name="use-powershell"></a>Usar PowerShell

Para agregar entradas de archivo de bloque en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
New-TenantAllowBlockListItems -ListType <FileHash> -Block -Entries "Value1","Value2",..."ValueN" <-ExpirationDate Date | -NoExpiration> [-Notes <String>]
```

En este ejemplo se agrega una entrada de archivo de bloque para los archivos especificados que nunca expiran.

```powershell
New-TenantAllowBlockListItems -ListType FileHash -Block -Entries "768a813668695ef2483b2bde7cf5d1b2db0423a0d3e63e498f3ab6f2eb13ea3","2c0a35409ff0873cfa28b70b8224e9aca2362241c1f0ed6f622fef8d4722fd9a" -NoExpiration
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems).

## <a name="create-allow-file-entries"></a>Creación de entradas de archivo allow

### <a name="use-microsoft-365-defender"></a>Uso de Microsoft 365 Defender

Permitir archivos en la página **Envíos** de Microsoft 365 Defender.

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Acciones & envíos envíos**\>. O bien, para ir directamente a la página **Envíos** , use <https://security.microsoft.com/reportsubmission>.

2. En la página **Envíos** , seleccione la pestaña **Datos adjuntos de correo electrónico** y, a continuación, haga clic en ![el icono Enviar a Microsoft para análisis.](../../media/m365-cc-sc-create-icon.png) **Envíe a Microsoft para su análisis**.

3. Use el control flotante **Enviar a Microsoft para revisar** para enviar un mensaje agregando el archivo o los archivos.

4. En la sección **Seleccionar un motivo para enviar a Microsoft**, seleccione **No debería haberse bloqueado (falso positivo).**

5. Active la opción **Permitir archivos como esta** .

6. En la lista desplegable **Quitar después**, especifique cuánto tiempo desea que funcione la opción Permitir.

7. Agregue por qué va a agregar allow mediante la **nota opcional**. 

8. Cuando haya terminado, haga clic en el botón **Enviar** .

  :::image type="content" source="../../media/submit-email-for-analysis.png" alt-text="Enviar correo electrónico para su análisis." lightbox="../../media/submit-email-for-analysis.png":::

> [!NOTE]
>
> Cuando se vuelve a encontrar el archivo, no se envía para las comprobaciones de detonación o reputación, y se omiten todos los demás filtros basados en archivos. Durante el flujo de correo, si el resto de los filtros encuentran el correo electrónico que contiene el archivo que se va a limpiar, se entregará el correo electrónico.

## <a name="view-file-entries"></a>Visualización de entradas de archivo 

Para ver las entradas de archivo de bloque en la lista de inquilinos permitidos o bloqueados, use la sintaxis siguiente:

```powershell
Get-TenantAllowBlockListItems -ListType <FileHash> [-Entry <SenderValue | FileHashValue | URLValue>] [<-ExpirationDate Date | -NoExpiration>]
```

En este ejemplo se devuelve información del valor hash de archivo especificado.

```powershell
Get-TenantAllowBlockListItems -ListType FileHash -Entry "9f86d081884c7d659a2feaa0c55ad015a3bf4f1b2b0b822cd15d6c15b0f00a08"
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems).

## <a name="modify-file-entries"></a>Modificar entradas de archivo

Para modificar las entradas de archivo allow o block en la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Set-TenantAllowBlockListItems -ListType <FileHash> -Ids <"Id1","Id2",..."IdN"> [<-ExpirationDate Date | -NoExpiration>] [-Notes <String>]
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems).

## <a name="remove-file-entries"></a>Quitar entradas de archivo 

Para quitar las entradas de archivo allow o block de la lista de permitidos o bloqueados de inquilinos, use la sintaxis siguiente:

```powershell
Remove-TenantAllowBlockListItems -ListType <FileHash> -Ids <"Id1","Id2",..."IdN">
```

Para obtener información detallada sobre la sintaxis y los [parámetros, vea Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems).

## <a name="related-articles"></a>Artículos relacionados

- [Envíos de administradores](admin-submission.md)
- [Notificar falsos positivos y falsos negativos](report-false-positives-and-false-negatives.md)
- [Administrar los bloques y los permitidos en la lista de permitidos o bloqueados de inquilinos](manage-tenant-allow-block-list.md)
- [Permitir o bloquear correos electrónicos en la lista de permitidos o bloqueados de inquilinos](allow-block-email-spoof.md)
- [Permitir o bloquear direcciones URL en la lista de permitidos o bloqueados de inquilinos](allow-block-urls.md)
