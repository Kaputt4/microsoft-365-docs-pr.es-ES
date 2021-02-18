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
ms.openlocfilehash: a3f4ed3535c7e53774b9b567b50f7c06e99cef9d
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288590"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documentos seguros en Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Documentos seguros es una característica de Microsoft 365 E5 o Microsoft 365 E5 Security que usa [Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para endpoint para examinar documentos y archivos que se abren en la vista [protegida.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de empezar?

- Documentos seguros solo está disponible para los usuarios con licencias de Seguridad de *Microsoft 365 E5* o *Microsoft 365 E5.* Estas licencias no se incluyen en los planes de Microsoft Defender para Office 365.

- Documentos seguros es compatible con Aplicaciones de Microsoft 365 para empresas (anteriormente conocido como Office 365 ProPlus) versión 2004 o posterior.

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com>. Para ir directamente a la página **Datos adjuntos seguros** de ATP, abra <https://protection.office.com/safeattachmentv2> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para configurar la configuración de documentos seguros,  debe ser miembro de los grupos de roles Administración de la organización o **Administrador de** seguridad.
  - Para obtener acceso de solo lectura a la configuración de documentos seguros, debe ser miembro de los grupos de roles Lector **global** o **Lector de** seguridad.

  Para más información, consulte [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >
  > - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

### <a name="how-does-microsoft-handle-your-data"></a>¿Cómo controla Microsoft los datos?

Para mantenerte protegido, Documentos seguros envía archivos a la nube [de Microsoft Defender para endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis. Los detalles sobre cómo Microsoft Defender para puntos de conexión controla los datos se pueden encontrar aquí: Microsoft Defender para el almacenamiento de datos y la privacidad de los [puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

Los archivos enviados por documentos seguros no se conservan en Defender más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usar el Centro de seguridad & cumplimiento para configurar documentos seguros

1. En el Centro de & cumplimiento, vaya a Directiva de administración de amenazas Datos adjuntos seguros de  \>  \> **ATP** y, a continuación, haga clic **en Configuración global.**

2. En el **menú emergente Configuración** global que aparece, configure las siguientes opciones:

   - **Activar Documentos seguros para clientes de Office:** mueva el botón de alternancia a la derecha para activar la característica: ![ ](../../media/scc-toggle-on.png) Activar.

   - **Permitir a** los usuarios hacer clic a través de la vista protegida incluso si Documentos seguros identifica el archivo como malintencionado : Se recomienda dejar esta opción desactivada (deje el botón de alternancia a la izquierda: Desactivar ![ ](../../media/scc-toggle-off.png) ).

   Cuando haya terminado, haga clic en **Guardar**.

   ![Configuración de documentos seguros después de seleccionar la configuración global en la página Datos adjuntos seguros.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Usar Exchange Online PowerShell para configurar documentos seguros

Utilice la sintaxis siguiente:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- El _parámetro EnableSafeDocs habilita_ o deshabilita documentos seguros para toda la organización.
- El _parámetro AllowSafeDocsOpen_ permite o impide que los usuarios abandonen la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.

En este ejemplo se habilitan documentos seguros para toda la organización y se impide que los usuarios abran documentos identificados como malintencionados desde la vista protegida.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obtener información detallada acerca de la sintaxis y los parámetros, [consulte Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha habilitado y configurado Documentos seguros, siga uno de estos pasos:

- En el Centro de seguridad y  cumplimiento de &, vaya a Directiva de administración de amenazas \>  \> Datos **adjuntos** seguros de **ATP,** haga clic en Configuración global y compruebe la opción Activar documentos seguros para clientes de **Office** y Permitir a los usuarios hacer clic en vista protegida incluso si Documentos seguros identifica el archivo como configuración malintencionada.

- Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Los siguientes archivos están disponibles para probar la protección de documentos seguros. Estos documentos son similares al archivo EICAR.TXT para probar soluciones antimalware y antivirus. Los archivos no son perjudiciales, pero activarán la protección de documentos seguros.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
