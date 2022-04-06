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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Los administradores pueden aprender a usar el analizador de configuración para buscar y corregir directivas de seguridad que se encuentran por debajo de la configuración en Protección estándar y Protección estricta en directivas de seguridad preestablecidas.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 459f44f29b89b2bbca6aa0f6847d0b4636647be6
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64477069"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El analizador de configuración del portal de Microsoft 365 Defender proporciona una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración protección estándar y la configuración de perfil de protección estricta en directivas de seguridad [preestablecidas](preset-security-policies.md).

El analizador de configuración analiza los siguientes tipos de directivas:

- **Exchange Online Protection de correo electrónico (EOP**): esto incluye Microsoft 365 con buzones de correo Exchange Online y organizaciones EOP independientes sin Exchange Online buzones de correo:
  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md).
  - [Directivas antimalware](configure-anti-malware-policies.md).
  - [Directivas contra suplantación de identidad de EOP](set-up-anti-phishing-policies.md#spoof-settings).

- **Directivas de Microsoft Defender Office 365**: esto incluye organizaciones con Microsoft 365 E5 o Defender para Office 365 suscripciones de complementos:
  - Las directivas contra suplantación de identidad en Microsoft Defender para Office 365, que incluyen:
    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas contra suplantación de identidad de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales avanzados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Directivas de vínculos seguros](set-up-safe-links-policies.md).
  - [Directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md).

Los valores de configuración de directiva Estándar y Estricto que se usan como líneas base se describen en Configuración recomendada para [EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la **página Analizador de configuración** , use <https://security.microsoft.com/configurationAnalyzer>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos en el portal de Microsoft 365 Defender para poder realizar los procedimientos descritos en este artículo:
  - Para usar el analizador de configuración **y** realizar actualizaciones de directivas de seguridad, debe ser miembro de los grupos de roles **Administración** de la organización o Administrador **de** seguridad.
  - Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad**.

  Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente proporciona a los usuarios los permisos necesarios en _el portal de_ Microsoft 365 Defender y permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a>Usar el analizador de configuración en el portal Microsoft 365 Defender configuración

En el portal Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email **& Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Configuration analyzer** en la **sección Directivas con** plantilla. Para ir directamente a la **página Analizador de configuración** , use <https://security.microsoft.com/configurationAnalyzer>.

La **página Analizador de** configuración tiene tres pestañas principales:

- **Recomendaciones estándar**: compare las directivas de seguridad existentes con las recomendaciones estándar. Puede ajustar los valores de configuración para que suban al mismo nivel que Standard.
- **Recomendaciones estrictas**: compare las directivas de seguridad existentes con las recomendaciones estrictas. Puede ajustar los valores de configuración para que suban al mismo nivel que Strict.
- **Historial y análisis de deriva de configuración**: auditar y realizar un seguimiento de los cambios de directiva con el tiempo.

### <a name="standard-recommendations-and-strict-recommendations-tabs-in-the-configuration-analyzer"></a>Recomendaciones estándar y pestañas de recomendaciones estrictas en el analizador de configuración

De forma predeterminada, el analizador de configuración se abre en la **pestaña Recomendaciones estándar** . Puede cambiar a la pestaña **Recomendaciones estrictas** . La configuración, el diseño y las acciones son iguales en ambas pestañas.

:::image type="content" source="../../media/configuration-analyzer-settings-and-recommendations-view.png" alt-text="Vista Configuración recomendaciones en el analizador de configuración" lightbox="../../media/configuration-analyzer-settings-and-recommendations-view.png":::

La primera sección de la pestaña muestra el número de configuraciones de cada tipo de directiva que necesitan mejoras en comparación con la protección estándar o estricta. Los tipos de directivas son:

- **Contra correo no deseado**
- **Anti-phishing**
- **Antimalware**
- **Caja fuerte datos adjuntos** (si la suscripción incluye Microsoft Defender para Office 365)
- **Caja fuerte (** si la suscripción incluye Microsoft Defender para Office 365)

Si no se muestra un tipo y un número de directiva, todas las directivas de ese tipo cumplen la configuración recomendada de protección estándar o estricta.

El resto de la pestaña es la tabla de opciones de configuración que deben subirse al nivel Protección estándar o estricta. La tabla contiene las siguientes columnas:

- **Recomendaciones:** el valor de la configuración en el perfil de protección Estándar o Estricta.
- **Directiva:** nombre de la directiva afectada que contiene la configuración.
- **Nombre de configuración o grupo de directivas:** el nombre de la configuración que requiere su atención.
- **Tipo de directiva**: Anti-spam, Anti-phishing, Anti-malware, Caja fuerte Links o Caja fuerte Attachments.
- **Configuración actual**: el valor actual de la configuración.
- **Última modificación**: la fecha en que se modificó por última vez la directiva.
- **Estado**: normalmente, este valor **no se inicia**.

### <a name="change-a-policy-setting-to-the-recommended-value"></a>Cambiar una configuración de directiva al valor recomendado

En la **ficha Protección estándar** o **Protección estricta** del analizador de configuración, seleccione la fila de la tabla. Aparecen los botones siguientes:

- **Aplicar recomendación**
- **Ver directiva**
- **Actualizar**:

Si selecciona una fila y hace clic en **Aplicar** recomendación, aparecerá un cuadro de diálogo de confirmación (con la opción de no volver a mostrar el cuadro de diálogo). Si hace clic en **Aceptar**, suceden las siguientes cosas:

- La configuración se actualiza al valor recomendado.
- La **directiva Aplicar recomendación** y **Ver** desaparecen (solo permanece **el botón** Actualizar).
- El **valor Status** de la fila cambia a **Complete**.

Si selecciona una fila y hace clic  en Ver directiva, verá los detalles de la directiva afectada en el portal de Microsoft 365 Defender donde puede actualizar manualmente la configuración.

Después de actualizar la configuración automáticamente o manualmente, haga clic en  Actualizar para ver el número reducido de recomendaciones y la eliminación de la fila actualizada de los resultados.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Pestaña análisis e historial de la deriva de configuración en el analizador de configuración

Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad y cómo estos cambios se comparan con la configuración estándar o estricta. De forma predeterminada, se muestra la siguiente información:

- **Última modificación**
- **Modificado por**
- **Nombre de la configuración**
- **Directiva**: el nombre de la directiva afectada.
- **Tipo**: Anti-spam, Anti-phishing, Anti-malware, Caja fuerte Links o Caja fuerte Attachments.
- **Cambio de configuración**: el valor antiguo y el nuevo valor de la configuración
- **Deriva de** configuración: el valor **Aumentar** **o disminuir** que indica que la configuración aumentó o disminuyó la seguridad en comparación con la configuración estándar o estricta recomendada.

Para filtrar los resultados, haga clic en **Filtrar**. En el menú desplegable **Filtros** que aparece, puede seleccionar entre los filtros siguientes:

- **Hora de** inicio y **hora de finalización** (fecha): puede volver hasta 90 días a partir de hoy.
- **Protección estándar o** **protección estricta**

Cuando haya terminado, haga clic en **Aplicar**.

Para exportar los resultados a un archivo .csv, haga clic en **Exportar**.

Para filtrar los resultados por un valor **específico Modificado por**, **Nombre de** **configuración o Tipo** , use el **cuadro** Buscar.

:::image type="content" source="../../media/configuration-analyzer-configuration-drift-analysis-view.png" alt-text="La vista Historial y análisis de deriva de configuración en el analizador de configuración" lightbox="../../media/configuration-analyzer-configuration-drift-analysis-view.png":::
