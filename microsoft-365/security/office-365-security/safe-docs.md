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
description: Obtenga información sobre Caja fuerte documentos en Microsoft 365 E5 o Seguridad de Microsoft 365 E5.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1186c7856d0b979c483cf6dd1c0a010ab582e2ce
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644757"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos seguros en Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Caja fuerte Documents es una característica de Microsoft 365 E5 o Seguridad de Microsoft 365 E5 que usa [Microsoft Defender para](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) endpoint para examinar documentos y archivos que se abren en [vista](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) protegida o Protección de aplicaciones para [Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Caja fuerte Los documentos solo están disponibles para los usuarios *con Microsoft 365 E5* o *Seguridad de Microsoft 365 E5* licencias. Estas licencias no se incluyen en Microsoft Defender para Office 365 planes.

- Caja fuerte Los documentos se admiten Aplicaciones Microsoft 365 para empresas versión 2004 o posterior Office 365 ProPlus (anteriormente conocido como Office 365 ProPlus).

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>. Para ir directamente a la **página Caja fuerte datos adjuntos** de ATP, abra <https://protection.office.com/safeattachmentv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en la **Exchange Online** antes de poder realizar los procedimientos de este artículo:
  - Para configurar Caja fuerte documentos, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura a Caja fuerte documentos, debe ser miembro de los grupos de roles Lector **global** o Lector **de** seguridad.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente en el Centro de administración de Microsoft 365 la cual proporciona a los usuarios los permisos necesarios _y_ para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

### <a name="how-does-microsoft-handle-your-data"></a>¿Cómo administra Microsoft los datos?

Para mantenerte protegido, Caja fuerte documentos envía archivos a la nube de [Microsoft Defender para endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis. Los detalles sobre cómo Administra Microsoft Defender para Endpoint sus datos se pueden encontrar aquí: Microsoft Defender para el almacenamiento de datos de punto [de conexión y privacidad.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Los archivos enviados por Caja fuerte documentos no se conservan en Defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usar el Centro de seguridad & cumplimiento para configurar Caja fuerte documentos

1. En el Centro de & cumplimiento,  vaya a Directiva de administración de amenazas \>  \> **ATP Caja fuerte datos adjuntos** y, a continuación, haga clic en **Configuración global**.

2. En el **menú desplegable Configuración global** que aparece, configure las siguientes opciones:

   - **Activar documentos Caja fuerte para clientes Office**: Mueva el botón de alternancia a la derecha para activar la característica: Activar ![ ](../../media/scc-toggle-on.png) .

   - **Permitir que** los usuarios haga clic en vista protegida incluso si Caja fuerte Documents identifica el archivo como malintencionado : Se recomienda dejar esta opción desactivada (dejar el botón de alternancia a la izquierda: ![ Desactivar ](../../media/scc-toggle-off.png) ).

   Cuando haya terminado, haga clic en **Guardar**.

   ![Caja fuerte Configuración de documentos después de seleccionar Configuración global en la Caja fuerte datos adjuntos.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar Exchange Online PowerShell para configurar Caja fuerte documentos

Utilice la siguiente sintaxis:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- El _parámetro EnableSafeDocs habilita_ o deshabilita Caja fuerte documentos para toda la organización.
- El _parámetro AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.

En este ejemplo se Caja fuerte documentos para toda la organización e impide que los usuarios abran documentos que se hayan identificado como malintencionados desde la vista protegida.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obtener información detallada sobre la sintaxis y los parámetros, [vea Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Incorporación al Servicio de extremo de Microsoft Defender para habilitar las capacidades de auditoría

Para implementar Microsoft Defender para endpoint, debe pasar por las distintas fases de implementación. Después de la incorporación, puede configurar las capacidades de auditoría en el Centro de seguridad & cumplimiento.

Para obtener más información, [vea Onboard to the Microsoft Defender for Endpoint service](/microsoft-365/security/defender-endpoint/onboarding). Si necesita ayuda adicional, consulte [Troubleshoot Microsoft Defender for Endpoint onboarding issues](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).

### <a name="how-do-i-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha habilitado y configurado documentos Caja fuerte documentos, siga estos pasos:

- En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> **Datos** **adjuntos** de ATP Caja fuerte , haga clic en Configuración global y compruebe la opción Activar documentos de **Caja fuerte** para clientes de Office y Permitir que los usuarios haga clic en la vista protegida incluso si Caja fuerte Documents identifica el archivo como una configuración malintencionada.

- Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de la propiedad:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Los siguientes archivos están disponibles para probar la protección Caja fuerte documentos. Estos documentos son similares al archivo EICAR.TXT para probar soluciones antimalware y antivirus. Los archivos no son dañinos, pero desencadenarán la protección Caja fuerte documentos.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
