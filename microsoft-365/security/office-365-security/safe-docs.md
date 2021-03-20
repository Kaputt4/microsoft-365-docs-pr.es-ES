---
title: Documentos seguros en Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre documentos seguros en Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f67dd21c4cea62012af4713bceddc2eebae33c7d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908812"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos seguros en Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Documentos seguros es una característica de Microsoft 365 E5 o Microsoft 365 E5 Security que usa [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para endpoint para examinar documentos y archivos abiertos en la [vista protegida.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Documentos seguros solo está disponible para los usuarios con licencias de Seguridad de *Microsoft 365 E5* o *Microsoft 365 E5.* Estas licencias no se incluyen en los planes de Microsoft Defender para Office 365.

- Documentos seguros se admite en Aplicaciones de Microsoft 365 para empresas (anteriormente conocida como Office 365 ProPlus) versión 2004 o posterior.

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>. Para ir directamente a la **página Datos adjuntos seguros** de ATP, abra <https://protection.office.com/safeattachmentv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar la configuración de documentos seguros, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a la configuración de documentos seguros, debe ser miembro de los grupos de roles **Lector global** o Lector **de** seguridad.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

### <a name="how-does-microsoft-handle-your-data"></a>¿Cómo administra Microsoft los datos?

Para mantenerte protegido, Documentos seguros envía archivos a la nube de [Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis. Los detalles sobre cómo Administra Microsoft Defender para Endpoint sus datos se pueden encontrar aquí: Microsoft Defender para el almacenamiento de datos de punto [de conexión y privacidad.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Los archivos enviados por Documentos seguros no se conservan en Defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usar el Centro de seguridad & cumplimiento para configurar documentos seguros

1. En el Centro de seguridad & cumplimiento, vaya a **Directiva** de administración de amenazas Datos adjuntos seguros de \>  \> **ATP** y, a continuación, haga clic **en Configuración global**.

2. En el **menú desplegable Configuración global** que aparece, configure las siguientes opciones:

   - **Activar Documentos seguros para clientes de Office:** mueva el botón de alternancia a la derecha para activar la característica: ![ Activar ](../../media/scc-toggle-on.png) .

   - **Permitir que** los usuarios haga clic en vista protegida incluso si Documentos seguros identifica el archivo como malintencionado : Se recomienda que deje esta opción desactivada (deje el botón de alternancia a la izquierda: ![ Desactivar ](../../media/scc-toggle-off.png) ).

   Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración de documentos seguros después de seleccionar Configuración global en la página Datos adjuntos seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar Exchange Online PowerShell para configurar documentos seguros

Utilice la siguiente sintaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- El _parámetro EnableSafeDocs_ habilita o deshabilita documentos seguros para toda la organización.
- El _parámetro AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.

En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos que se hayan identificado como malintencionados desde la vista protegida.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha habilitado y configurado Documentos seguros, siga estos pasos:

- En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> Datos **adjuntos** seguros de **ATP,** haga clic en Configuración global y compruebe la opción Activar documentos seguros para clientes de **Office** y Permitir que los usuarios haga clic en vista protegida incluso si Documentos seguros identifica el archivo como una configuración malintencionada.

- Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de la propiedad:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Los siguientes archivos están disponibles para probar la protección de documentos seguros. Estos documentos son similares al archivo EICAR.TXT para probar soluciones antimalware y antivirus. Los archivos no son dañinos, pero activarán la protección de documentos seguros.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)