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
- m365-security
description: Obtenga información sobre los documentos seguros en Microsoft 365 A5 o E5 Security.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 05f337652b0cd08ac930b1439b3f2415bb697e1e
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68060436"
---
# <a name="safe-documents-in-microsoft-365-a5-or-e5-security"></a>Documentos seguros en Microsoft 365 A5 o seguridad E5

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Documentos seguros es una característica premium que usa el back-end en la nube de [Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para examinar documentos de Office abiertos en [la vista protegida](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653) o [Protección de aplicaciones para Office](https://support.microsoft.com/topic/9e0fb9c2-ffad-43bf-8ba3-78f785fdba46).

Los usuarios no necesitan que Defender para punto de conexión esté instalado en sus dispositivos locales para obtener protección de documentos seguros. Los usuarios obtienen protección de documentos seguros si se cumplen todos los requisitos siguientes:

- Documentos seguros está habilitado en la organización como se describe en este artículo.
- Las licencias de un plan de licencias necesarias se asignan a los usuarios. Los documentos seguros se controlan mediante el plan de servicio **Office 365 SafeDocs** (o **SAFEDOCS** o **bf6f5520-59e3-4f82-974b-7dbbc4fd27c7**) (también conocido como servicio). Este plan de servicio está disponible en los siguientes planes de licencia (también conocidos como planes de licencia, planes de Microsoft 365 o productos):
  - Microsoft 365 A5 para profesores
  - Microsoft 365 A5 para estudiantes
  - Seguridad de Microsoft 365 E5

  Los documentos seguros no se incluyen en los planes de licencias de Microsoft Defender para Office 365.

  Para obtener más información, consulte [Nombres de producto e identificadores de plan de servicio para licencias](/azure/active-directory/enterprise-users/licensing-service-plan-reference).

- Usan Aplicaciones Microsoft 365 para empresas (anteriormente conocida como Office 365 ProPlus) versión 2004 o posterior.

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Datos adjuntos seguros** , use <https://security.microsoft.com/safeattachmentv2>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Necesita permisos en **Exchange Online** para poder realizar los procedimientos de este artículo:
  - Para configurar la configuración de Documentos seguros, debe ser miembro de los grupos de roles **Administración de la organización** o **Administrador de seguridad** .
  - Para obtener acceso de solo lectura a la configuración de Documentos seguros, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad** .

  Para obtener más información, consulte los [permisos en Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365. For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

### <a name="how-does-microsoft-handle-your-data"></a>¿Cómo controla Microsoft los datos?

Para mantenerlo protegido, Documentos seguros envía archivos a la [nube de Microsoft Defender para punto de conexión](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) para su análisis. Puede encontrar detalles sobre cómo Microsoft Defender para punto de conexión controla los datos aquí: [Microsoft Defender para punto de conexión almacenamiento de datos y privacidad](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

Los archivos enviados por documentos seguros no se conservan en Defender para punto de conexión más allá del tiempo necesario para el análisis (normalmente, menos de 24 horas).

## <a name="use-the-microsoft-365-defender-portal-to-configure-safe-documents"></a>Uso del portal de Microsoft 365 Defender para configurar documentos seguros

1. En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas** \> **Directivas de amenazas** \> **Datos adjuntos seguros** en la sección **Directivas**. Para ir directamente a la página **Datos adjuntos seguros** , use <https://security.microsoft.com/safeattachmentv2>.

2. En la página **Datos adjuntos seguros** , haga clic en **Configuración global**.

3. En el control **flotante Configuración global** que aparece, configure los siguientes valores:
   - **Activar Documentos seguros para clientes de Office**: mueva el botón de alternancia a la derecha para activar la característica: ![Activar.](../../media/scc-toggle-on.png)
   - **Permitir a los usuarios hacer clic en la vista protegida incluso si documentos seguros identificaron el archivo como malintencionado**: se recomienda desactivar esta opción (deje el botón de alternancia a la izquierda: ![Desactivar).](../../media/scc-toggle-off.png)

   Cuando haya terminado, haga clic en **Guardar**.

   :::image type="content" source="../../media/safe-docs-global-settings.png" alt-text="La configuración de Documentos seguros después de seleccionar Configuración global en la página Datos adjuntos seguros" lightbox="../../media/safe-docs-global-settings.png":::

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Uso de Exchange Online PowerShell para configurar documentos seguros

Si prefiere usar PowerShell para configurar documentos seguros, use la siguiente sintaxis en Exchange Online PowerShell:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- El parámetro _EnableSafeDocs_ habilita o deshabilita documentos seguros para toda la organización.
- El parámetro _AllowSafeDocsOpen_ permite o impide que los usuarios salgan de la vista protegida (es decir, abrir el documento) si el documento se ha identificado como malintencionado.

En este ejemplo se habilitan los documentos seguros para toda la organización y se impide que los usuarios abran documentos que se han identificado como malintencionados desde la vista protegida.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Para obtener información detallada sobre la sintaxis y los parámetros, vea [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365).

### <a name="configure-individual-access-to-safe-documents"></a>Configuración del acceso individual a documentos seguros

Si desea permitir o bloquear de forma selectiva el acceso a la característica Documentos seguros, siga estos pasos:

1. Active Documentos seguros en el portal de Microsoft 365 Defender o Exchange Online PowerShell como se describió anteriormente en este artículo.
2. Use PowerShell de Azure AD para deshabilitar documentos seguros para usuarios específicos, como se describe en [Deshabilitar servicios específicos de Microsoft 365 para usuarios específicos para un plan de licencias específico](/microsoft-365/enterprise/disable-access-to-services-with-microsoft-365-powershell#disable-specific-microsoft-365-services-for-specific-users-for-a-specific-licensing-plan).

  El nombre del plan de servicio que se va a deshabilitar en PowerShell es **SAFEDOCS**.

Para obtener más información, consulte los siguientes temas:

- [Visualización de licencias y servicios de Microsoft 365 con PowerShell](/microsoft-365/enterprise/view-licenses-and-services-with-microsoft-365-powershell)
- [Visualización de los detalles del servicio y la licencia de la cuenta de Microsoft 365 con PowerShell](/microsoft-365/enterprise/view-account-license-and-service-details-with-microsoft-365-powershell)
- [Nombres de productos e identificadores de planes de servicio para licencias](/azure/active-directory/enterprise-users/licensing-service-plan-reference)

### <a name="onboard-to-the-microsoft-defender-for-endpoint-service-to-enable-auditing-capabilities"></a>Incorporación al servicio Microsoft Defender para punto de conexión para habilitar las funcionalidades de auditoría

Para habilitar las funcionalidades de auditoría, el dispositivo local debe tener instalado Microsoft Defender para punto de conexión. Para implementar Microsoft Defender para punto de conexión, debe pasar por las distintas fases de la implementación. Después de la incorporación, puede configurar las funcionalidades de auditoría en el portal de Microsoft 365 Defender.

Para más información, consulte [Incorporación al servicio de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/onboarding). Si necesita ayuda adicional, consulte Solución de [problemas de incorporación de Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/troubleshoot-onboarding).

### <a name="how-do-i-know-this-worked"></a>¿Cómo saber si el proceso se ha completado correctamente?

Para comprobar que ha habilitado y configurado documentos seguros, siga estos pasos:

- En el portal de Microsoft 365 Defender, vaya a **directivas de colaboración** \> **Email & & reglas** \> Directivas de **amenazas** \> **Datos adjuntos seguros** en la sección \> **Directivas** **Configuración global** y compruebe la **opción Activar documentos seguros para clientes de Office** y **Permitir a los usuarios hacer clic en la vista protegida incluso si Documentos seguros identifica el archivo como configuración malintencionada**.

- Ejecute el siguiente comando en Exchange Online PowerShell y compruebe los valores de propiedad:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- Los siguientes archivos están disponibles para probar la protección de documentos seguros. Estos archivos son similares al archivo EICAR.TXT para probar soluciones antivirus y antimalware. Los archivos no son dañinos, pero desencadenarán la protección de documentos seguros.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
