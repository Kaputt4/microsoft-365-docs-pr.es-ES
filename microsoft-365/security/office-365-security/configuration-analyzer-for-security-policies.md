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
description: Los administradores pueden aprender a usar el analizador de configuración para buscar y corregir directivas de seguridad que están por debajo de la configuración de Protección estándar y Protección estricta en directivas de seguridad preestablecidas.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: b5f33bb7b30f63ad5d6705b7a9cbffb38f280a2c
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479167"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Analizador de configuración para directivas de protección en EOP y Microsoft Defender para Office 365

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

El analizador de configuración del portal de Microsoft 365 Defender proporciona una ubicación central para buscar y corregir directivas de seguridad en las que la configuración se encuentra por debajo de la configuración protección estándar y perfil de protección estricta en [las directivas de seguridad preestablecidas](preset-security-policies.md).

El analizador de configuración analiza los siguientes tipos de directivas:

- **directivas de Exchange Online Protection (EOP):** esto incluye organizaciones de Microsoft 365 con buzones de Exchange Online y organizaciones EOP independientes sin Exchange Online buzones:
  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md).
  - [Directivas antimalware](configure-anti-malware-policies.md).
  - [Directivas contra phishing de EOP](set-up-anti-phishing-policies.md#spoof-settings).

- **directivas de Microsoft Defender para Office 365**: esto incluye organizaciones con suscripciones de complemento de Microsoft 365 E5 o Defender para Office 365:
  - Directivas contra suplantación de identidad en Microsoft Defender para Office 365, que incluyen:
    - La misma [configuración de suplantación de identidad](set-up-anti-phishing-policies.md#spoof-settings) que está disponible en las directivas de protección contra suplantación de identidad (EOP).
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales avanzados de phishing](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
  - [Directivas de vínculos seguros](set-up-safe-links-policies.md).
  - [Directivas de datos adjuntos seguros](set-up-safe-attachments-policies.md).

Los valores de configuración de directiva estándar y estricto que se usan como líneas base se describen en [Configuración recomendada para EOP y Microsoft Defender para Office 365 seguridad](recommended-settings-for-eop-and-office365.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el portal de Microsoft 365 Defender en <https://security.microsoft.com>. Para ir directamente a la página **Analizador de configuración** , use <https://security.microsoft.com/configurationAnalyzer>.

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados en el portal de Microsoft 365 Defender para poder realizar los procedimientos de este artículo:
  - Para usar el analizador de configuración **y** realizar actualizaciones en las directivas de seguridad, debe ser miembro de los grupos de roles Administración de la **organización** o **Administrador de seguridad** .
  - Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles **Lector global** o **Lector de seguridad**.

  Para obtener más información, consulte [Permisos en el portal de Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

  > [!NOTE]
  >
  > - Agregar usuarios al rol de Azure Active Directory correspondiente proporciona a los usuarios los permisos necesarios en el portal de Microsoft 365 Defender _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](../../admin/add-users/about-admin-roles.md).
  > - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-configuration-analyzer-in-the-microsoft-365-defender-portal"></a>Uso del analizador de configuración en el portal de Microsoft 365 Defender

En el portal de Microsoft 365 Defender en <https://security.microsoft.com>, vaya a Email & Directivas de **colaboración** \> **& Reglas**\>: **Analizador de configuración** de **directivas** \> de amenazas en la sección **Directivas con plantilla**. Para ir directamente a la página **Analizador de configuración** , use <https://security.microsoft.com/configurationAnalyzer>.

La página **Analizador de configuración** tiene tres pestañas principales:

- **Recomendaciones estándar**: compare las directivas de seguridad existentes con las recomendaciones estándar. Puede ajustar los valores de configuración para que suban al mismo nivel que Estándar.
- **Recomendaciones estrictas**: compare las directivas de seguridad existentes con las recomendaciones estrictas. Puede ajustar los valores de configuración para que suban al mismo nivel que Strict.
- **Análisis e historial de desfase de configuración**: audite y realice un seguimiento de los cambios de directiva a lo largo del tiempo.

### <a name="standard-recommendations-and-strict-recommendations-tabs-in-the-configuration-analyzer"></a>Pestañas Recomendaciones estándar y Recomendaciones estrictas en el analizador de configuración

De forma predeterminada, el analizador de configuración se abre en la pestaña **Recomendaciones estándar** . Puede cambiar a la pestaña **Recomendaciones estrictas** . La configuración, el diseño y las acciones son los mismos en ambas pestañas.

:::image type="content" source="../../media/configuration-analyzer-settings-and-recommendations-view.png" alt-text="Vista Configuración y recomendaciones en el Analizador de configuración" lightbox="../../media/configuration-analyzer-settings-and-recommendations-view.png":::

En la primera sección de la pestaña se muestra el número de opciones de configuración de cada tipo de directiva que necesitan mejoras en comparación con protección estándar o estricta. Los tipos de directivas son:

- **Antispam**
- **Anti-phishing**
- **Antimalware**
- **Datos adjuntos seguros** (si la suscripción incluye Microsoft Defender para Office 365)
- **Vínculos seguros** (si la suscripción incluye Microsoft Defender para Office 365)

Si no se muestra un tipo y un número de directiva, todas las directivas de ese tipo cumplen la configuración recomendada de Protección estándar o estricta.

El resto de la pestaña es la tabla de configuraciones que deben subirse al nivel Protección estándar o estricta. La tabla contiene las columnas siguientes:

- **Recomendaciones:** el valor de la configuración en el perfil de protección Estándar o Estricta.
- **Directiva:** nombre de la directiva afectada que contiene la configuración.
- **Nombre de configuración o grupo de directivas:** el nombre de la configuración que requiere su atención.
- **Tipo de directiva**: Antispam, Anti-phishing, Antimalware, Vínculos seguros o Datos adjuntos seguros.
- **Configuración actual**: valor actual de la configuración.
- **Última modificación**: la fecha en que se modificó por última vez la directiva.
- **Estado**: normalmente, este valor no se **inicia**.

### <a name="change-a-policy-setting-to-the-recommended-value"></a>Cambiar una configuración de directiva al valor recomendado

En la pestaña **Protección estándar** o **Protección estricta** del analizador de configuración, seleccione la fila de la tabla. Aparecen los siguientes botones:

- **Aplicar recomendación**
- **Ver directiva**
- **Actualizar**:

Si selecciona una fila y hace clic en **Aplicar recomendación**, aparece un cuadro de diálogo de confirmación (con la opción de no volver a mostrar el cuadro de diálogo). Si hace clic en **Aceptar**, ocurre lo siguiente:

- La configuración se actualiza al valor recomendado.
- La **directiva Aplicar recomendación** y **Ver** desaparece (solo queda el botón **Actualizar** ).
- El valor **De estado** de la fila cambia a **Completo**.

Si selecciona una fila y hace clic en **Ver directiva**, se le llevará al control flotante de detalles de la directiva afectada en el portal de Microsoft 365 Defender, donde puede actualizar manualmente la configuración.

Después de actualizar automáticamente o manualmente la configuración, haga clic en **Actualizar** para ver el número reducido de recomendaciones y la eliminación de la fila actualizada de los resultados.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Pestaña análisis e historial de la deriva de configuración en el analizador de configuración

Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad y cómo se comparan con la configuración estándar o estricta. De forma predeterminada, se muestra la siguiente información:

- **Última modificación**
- **Modificado por**
- **Establecer nombre**
- **Directiva**: nombre de la directiva afectada.
- **Tipo**: Anti-spam, Anti-phishing, Anti-malware, Vínculos seguros o Datos adjuntos seguros.
- **Cambio de configuración**: el valor antiguo y el nuevo valor de la configuración
- **Desfase de configuración**: el valor **Aumentar** o **Disminuir** que indica que la configuración aumentó o disminuyó la seguridad en comparación con la configuración estándar o estricta recomendada.

Para filtrar los resultados, haga clic en **Filtrar**. En el menú desplegable **Filtros** que aparece, puede seleccionar entre los filtros siguientes:

- **Hora de inicio** y **hora de finalización** (fecha): puede volver hasta 90 días a partir de hoy.
- **Protección estándar** o **protección estricta**

Cuando haya terminado, haga clic en **Aplicar**.

Para exportar los resultados a un archivo .csv, haga clic en **Exportar**.

Para filtrar los resultados por un valor **específico Modificado por**, **Nombre de configuración** o **Tipo** , use el cuadro **Buscar** .

:::image type="content" source="../../media/configuration-analyzer-configuration-drift-analysis-view.png" alt-text="La vista Historial y análisis de desfase de configuración en el analizador de configuración" lightbox="../../media/configuration-analyzer-configuration-drift-analysis-view.png":::
