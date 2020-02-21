---
title: Documentos seguros en Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre documentos seguros en Office 365 ATP.
ms.openlocfilehash: 3980746eb2f48e77c22f5139827bead5640dad61
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170480"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Documentos seguros en Office 365 protección contra amenazas avanzada

Documentos seguros es una característica de la protección contra amenazas avanzada (ATP) de Office 365 que usa la [protección contra amenazas avanzada de Microsoft defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos y archivos que se abren en la [vista protegida](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Esta característica solo está disponible para los usuarios con la licencia de seguridad Microsoft 365 E5 o Microsoft 365 E5.

- Documentos seguros está actualmente disponible para la versión preliminar pública, disponible para los usuarios que forman parte del [programa de Office Insider](https://insider.office.com/en-us/join) en el canal mensual (dirigido), con office versión 2002 (12527,20092) o posterior. Esta característica está desactivada de forma predeterminada y el administrador de seguridad la tendrá que habilitar.

- Sólo región estadounidense admitida actualmente para el procesamiento de archivos conformes (todos los archivos se trasladarán a la región estadounidense para el análisis). La compatibilidad con la región del Reino Unido y la UE se planea en una actualización futura.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse al PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Para conectarse a PowerShell de Exchange Online Protection, vea [conectarse a PowerShell de Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Debe tener permisos asignados para poder llevar a cabo los procedimientos de este tema. Para habilitar y configurar documentos seguros, debe ser miembro de los grupos de funciones **Administración** de la organización o **Administrador de seguridad** . Para obtener más información acerca de los grupos de roles en el centro de seguridad & cumplimiento, consulte [Permissions in the Office 365 security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a>Usar el centro de cumplimiento de & de seguridad de Office 365 para configurar documentos seguros

1. Abra el centro de cumplimiento de & de seguridad <https://protection.office.com>de Office 365 en.

2. Vaya a **** \> **Directiva** \> de administración de amenazas: **datos adjuntos seguros de ATP**.

3. En la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrirse fuera de la vista protegida en las aplicaciones de Office** , configure cualquiera de las siguientes opciones:

   - **Activar documentos seguros para clientes de Office (los archivos también se enviarán a la nube de Microsoft para análisis profundos)**

   - **Permitir que los usuarios haga clic a través de la vista protegida incluso si documentos seguros identifica el archivo como malintencionado**: se recomienda no habilitar esta opción.

4. Cuando haya terminado, haga clic en **Guardar**.

![Página de datos adjuntos seguros de ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>Usar Exchange Online PowerShell o Exchange Online Protection PowerShell para configurar documentos seguros

Use la sintaxis que se muestre a continuación:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- El parámetro _EnableSafeDocs_ habilita o deshabilita los documentos seguros para toda la organización.

- El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, que abra el documento) si el documento se ha identificado como malintencionado.

En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obtener información detallada acerca de la sintaxis y los parámetros, consulte [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha habilitado y configurado documentos seguros, siga uno de estos pasos:

- En el centro de seguridad & cumplimiento, vaya a la **Directiva** \> de **Administración** \> de amenazas **datos adjuntos seguros de ATP**y compruebe que las selecciones en la sección **ayuda para que los usuarios sigan siendo seguros cuando confíen en un archivo para abrir una vista protegida externa en la sección aplicaciones de Office** .

- Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
