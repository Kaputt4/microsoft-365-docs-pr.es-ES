---
title: Documentos seguros en Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Obtenga información sobre Caja fuerte Documentos en Microsoft 365 E5/A5 o Microsoft 365 E5/A5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3fa1c7e07c1e1cd117ee20f4712dbbadad3c2b5c
ms.sourcegitcommit: f30616b90b382409f53a056b7a6c8be078e6866f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "65174129"
---
# <a name="safe-documents-in-microsoft-365-e5a5"></a>Caja fuerte documentos en Microsoft 365 E5/A5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Caja fuerte Documents es una característica premium que usa el back-end en la nube de [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos abiertos Office en [la vista protegida](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) o [protección de aplicaciones para Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).

Los usuarios no necesitan que Defender para punto de conexión esté instalado en sus dispositivos locales para obtener Caja fuerte protección de documentos. Los usuarios obtienen Caja fuerte protección de documentos si se cumplen todos los requisitos siguientes:

- Caja fuerte Documents está habilitado en la organización, tal como se describe en este artículo.
- Las licencias de un plan de licencias necesarias se asignan a los usuarios. Caja fuerte Documents está controlado por el plan de servicio **Office 365 SafeDocs** (o **SAFEDOCS** o **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7**) (también conocido como servicio). Este plan de servicio está disponible en los siguientes planes de licencia (también conocidos como planes de licencia, planes de Microsoft 365 o productos):
  - Microsoft 365 A5 para profesores
  - Microsoft 365 A5 para estudiantes
  - Seguridad de Microsoft 365 E5

  Caja fuerte Documentos no se incluye en los planes de licencia de Microsoft Defender para Office 365.

  Para obtener más información, consulte [Nombres de producto e identificadores de plan de servicio para licencias](/azure/active-directory/enterprise-users/licensing-service-plan-reference).

- Usan Aplicaciones Microsoft 365 para empresas (anteriormente conocida como Office 365 ProPlus) versión 2004 o posterior.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Necesita permisos en **Exchange Online** para poder realizar los procedimientos de este artículo:
  - Para configurar Caja fuerte los documentos, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad**.
  - Para obtener acceso de solo lectura a Caja fuerte configuración de documentos, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad**.

  Para obtener más información, vea los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - La adición de usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 proporciona a los usuarios los permisos necesarios _y_ los permisos para otras características de Microsoft 365. Para obtener más información, consulte [Acerca de los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

### <a name="how-does-microsoft-handle-your-data"></a>¿Cómo controla Microsoft los datos?

Para mantenerle protegido, Caja fuerte Documents envía archivos a la nube [de Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis. Puede encontrar detalles sobre cómo Microsoft Defender para punto de conexión controla los datos aquí: [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Los archivos enviados por Caja fuerte Documentos no se conservan en Defender para punto de conexión más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>Uso del portal de Microsoft 365 Defender para configurar Caja fuerte Documentos

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a **Directivas de colaboración** \> & correo electrónico **& directivas** de **amenazas** \> de reglas \> **Caja fuerte datos adjuntos** en la sección **Directivas**. Para ir directamente a la página **datos adjuntos de Caja fuerte**, use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Datos adjuntos de Caja fuerte**, haga clic en **Configuración global**.

3. En el control **flotante Configuración global** que aparece, configure los siguientes valores:
   - **Active Caja fuerte Documentos para clientes Office**: mueva el botón de alternancia a la derecha para activar la característica: ![Activar.](../../media/scc-toggle-on.png)
   - **Permitir a los usuarios hacer clic en la vista protegida incluso si Caja fuerte documentos identificaron el archivo como malintencionado**: se recomienda desactivar esta opción (deje el botón de alternancia a la izquierda: ![Desactivar).](../../media/scc-toggle-off.png)

   Cuando haya terminado, haga clic en **Guardar**.

   :::image type="content" source="../../media/safe-docs-global-settings.png" alt-text="La configuración de Caja fuerte Documentos después de seleccionar Configuración global en la página Datos adjuntos de Caja fuerte" lightbox="../../media/safe-docs-global-settings.png":::

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Uso de Exchange Online PowerShell para configurar documentos de Caja fuerte

Si prefiere usar PowerShell para configurar Caja fuerte Documents, use la siguiente sintaxis en Exchange Online PowerShell:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- El parámetro _EnableSafeDocs_ habilita o deshabilita Caja fuerte Documentos para toda la organización.
- El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios salgan de la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.

Este ejemplo habilita Caja fuerte Documentos para toda la organización e impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="configure-individual-access-to-safe-documents"></a>Configuración del acceso individual a Caja fuerte Documentos

Si desea permitir o bloquear de forma selectiva el acceso a la característica documentos Caja fuerte, siga estos pasos:

1. Active Caja fuerte Documents en el portal de Microsoft 365 Defender o Exchange Online PowerShell, como se describió anteriormente en este artículo.
2. Use Azure AD PowerShell para deshabilitar Caja fuerte Documentos para usuarios específicos, como se describe en [Deshabilitar servicios de Microsoft 365 específicos para usuarios específicos para un plan de licencias específico](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan).

  El nombre del plan de servicio que se va a deshabilitar en PowerShell es **SAFEDOCS**.

Para obtener más información, consulte los siguientes temas:

- [Visualización de licencias y servicios de Microsoft 365 con PowerShell](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [Ver Microsoft 365 detalles de licencia de cuenta y servicio con PowerShell](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Incorporación al servicio Microsoft Defender para punto de conexión para habilitar las funcionalidades de auditoría

Para habilitar las funcionalidades de auditoría, el dispositivo local debe tener instalado Microsoft Defender para punto de conexión. Para implementar Microsoft Defender para punto de conexión, debe pasar por las distintas fases de la implementación. Después de la incorporación, puede configurar las funcionalidades de auditoría en el portal de Microsoft 365 Defender.

Para más información, consulte [Incorporación al servicio de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/onboarding). Si necesita ayuda adicional, consulte Solución de [problemas de incorporación de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).

### <a name="how-do-i-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha habilitado y configurado Caja fuerte Documentos, siga estos pasos:

- En el portal de Microsoft 365 Defender, vaya a **Directivas de colaboración** \> & correo electrónico **& Directivas** de **amenazas** \> de reglas \> **Caja fuerte Datos adjuntos** en la sección \> **Directivas** **Configuración global** y compruebe la **opción Activar Caja fuerte documentos para clientes Office** y **Permitir a los usuarios hacer clic en la vista protegida incluso si Caja fuerte Documentos identifica el archivo como una configuración malintencionada**.

- Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Los siguientes archivos están disponibles para probar Caja fuerte protección de documentos. Estos archivos son similares al archivo EICAR.TXT para probar soluciones antivirus y antimalware. Los archivos no son dañinos, pero desencadenarán Caja fuerte protección de documentos.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
