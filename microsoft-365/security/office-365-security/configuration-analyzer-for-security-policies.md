---
title: Analizador de configuración para directivas de seguridad
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar el analizador de configuración para buscar y corregir directivas de seguridad que están por debajo de las directivas de seguridad predeterminadas protección estándar y Protección estricta.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd0cf4f3194a7a8eec39f2d0c447dca2dae5948b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537936"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El analizador de configuración del Centro de seguridad y cumplimiento de & proporciona una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración protección estándar y la configuración de perfil de protección estricta en directivas de seguridad [preestablecidas.](preset-security-policies.md)

El analizador de configuración analiza los siguientes tipos de directivas:

- **Exchange Online Protection (EOP):** esto incluye organizaciones Microsoft 365 con buzones de correo Exchange Online y organizaciones independientes de EOP sin Exchange Online buzones de correo:

  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md).
  - [Directivas antimalware](configure-anti-malware-policies.md).
  - [Directivas contra suplantación de identidad de EOP](set-up-anti-phishing-policies.md#spoof-settings).

- **Directivas de Microsoft Defender para Office 365:** esto incluye organizaciones con Microsoft 365 E5 o Defender para Office 365 de complementos:

  - Las directivas contra suplantación de identidad en Microsoft Defender para Office 365, que incluyen:

    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra suplantación de identidad de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales de suplantación de identidad avanzada](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Caja fuerte de vínculos](set-up-safe-links-policies.md).

  - [Caja fuerte de datos adjuntos](set-up-safe-attachments-policies.md).

Los **valores de** configuración **de** directiva Estándar y Estricto que se usan como líneas base se describen en Configuración recomendada para EOP y Microsoft Defender para Office 365 [seguridad.](recommended-settings-for-eop-and-office365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la **página Analizador de configuración,** use <https://protection.office.com/configurationAnalyzer> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Necesita que se le asignen permisos en el Centro de seguridad y cumplimiento para poder realizar los procedimientos de este artículo:
  - Para usar el analizador de configuración **y** realizar actualizaciones de directivas de seguridad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles **Lector global** o **Lector de** seguridad.

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  > [!NOTE]
  >  
  > - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  >
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Usar el analizador de configuración en el Centro de seguridad & cumplimiento

En el Centro de & cumplimiento, vaya al Analizador **de** configuración de directivas \>  \> **de administración de amenazas**.

![Widget analizador de configuración en la página Directiva de administración \> de amenazas](../../media/configuration-analyzer-widget.png)

El analizador de configuración tiene dos pestañas principales:

- **Configuración recomendaciones:** elija Estándar o Estricto y compare dicha configuración con las directivas de seguridad existentes. En los resultados, puede ajustar los valores de la configuración para que suban al mismo nivel que Standard o Strict.

- **Historial y análisis de deriva de configuración:** esta vista le permite realizar un seguimiento de los cambios de directiva con el tiempo.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Ficha Configuración y recomendaciones en el analizador de configuración

De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar. Puede cambiar a la comparación del perfil de protección estricta haciendo clic en **Ver recomendaciones estrictas**. Para volver atrás, seleccione **Ver recomendaciones estándar**.

![Configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

De forma predeterminada, la columna Nombre de configuración **o** grupo de directivas contiene una vista contraida de los distintos tipos de directivas de seguridad y el número de configuraciones que necesitan mejoras (si las hay). Los tipos de directivas son:

- **Contra correo no deseado**
- **Anti-phishing**
- **Antimalware**
- **Datos adjuntos Caja fuerte ATP** (si la suscripción incluye Microsoft Defender para Office 365)
- **Vínculos Caja fuerte ATP** (si la suscripción incluye Microsoft Defender para Office 365)

En la vista predeterminada, todo está contraído. Junto a cada directiva, hay un resumen de los resultados de comparación de las directivas (que puede modificar) y la configuración de las directivas correspondientes para los perfiles de protección estándar o estricto (que no puede modificar). Verá la siguiente información para el perfil de protección con el que está comparando:

- **Verde:** todas las configuraciones de todas las directivas existentes son al menos tan seguras como el perfil de protección.
- **Ámbar:** un pequeño número de configuraciones en las directivas existentes no son tan seguras como el perfil de protección.
- **Rojo:** un número significativo de configuraciones en las directivas existentes no son tan seguras como el perfil de protección. Esta puede ser una configuración en muchas directivas o en muchas configuraciones de una directiva.

Para las comparaciones favorables, verá el texto: **Todas las opciones de configuración siguen las** \<**Standard** or **Strict**\> **recomendaciones**. De lo contrario, verá el número de opciones recomendadas para cambiar.

Si expande **Grupo de directivas o nombre de** configuración, se revelan todas las directivas y la configuración asociada en cada directiva específica que requiera atención. O bien, puede expandir un tipo específico de directiva (por ejemplo, **Contra** correo no deseado) para ver solo esa configuración en esos tipos de directivas que requieren su atención.

Si la comparación no tiene recomendaciones de mejora (verde), expandir la directiva no revela nada. Si hay un número de recomendaciones para mejorar (ámbar o rojo), se revelan las configuraciones que requieren atención y la información correspondiente se muestra en las siguientes columnas:

- El nombre de la configuración que requiere su atención. Por ejemplo, en la captura de pantalla anterior, es el umbral **de correo electrónico** masivo en una directiva contra correo no deseado.

- **Directiva:** nombre de la directiva afectada que contiene la configuración.

- **Se aplica a**: el número de usuarios a los que se aplican las directivas afectadas.

- **Configuración actual:** el valor actual de la configuración.

- **Last modified**: The date that the policy was last modified.

- **Recomendaciones:** el valor de la configuración en el perfil de protección estándar o estricto. Para cambiar el valor de la configuración de la directiva para que coincida con el valor recomendado en el perfil de protección, haga clic en **Adoptar**. Si el cambio se realiza correctamente, verá el mensaje: Recomendaciones **se adoptó correctamente**. Haga **clic en** Actualizar para ver el número reducido de recomendaciones y la eliminación de la fila de configuración o directiva específica de los resultados.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Ficha Historial y análisis de deriva de configuración en el analizador de configuración

Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas. De forma predeterminada, se muestra la siguiente información:

- **Última modificación**
- **Modificado por**
- **Nombre de configuración**
- **Directiva**
- **Tipo**

Para filtrar los resultados, haga clic en **Filtrar**. En el **menú** desplegable Filtros que aparece, puede seleccionar entre los filtros siguientes:

- **Hora de inicio** y **hora de finalización** (fecha)
- **Protección estándar o** **protección estricta**

Para exportar los resultados a un .csv, haga clic en **Exportar**.

![Análisis de deriva de configuración y vista de historial en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)