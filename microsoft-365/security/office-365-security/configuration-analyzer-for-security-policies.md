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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Los administradores pueden aprender a usar el analizador de configuración para encontrar y corregir directivas de seguridad que están por debajo de las directivas de seguridad estándar protección estándar y protección estricta.
ms.openlocfilehash: 5a57e16dcac6afee910ce546d3a40c2c9c669f2d
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616157"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-microsoft-defender-for-office-365"></a>Analizador de configuración para directivas de protección en EOP y Microsoft defender para Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Las características descritas en este tema están en versión preliminar, no están disponibles en todas las organizaciones y están sujetas a cambios. Para obtener información sobre la programación de versiones, consulte el [plan de desarrollo de Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=config%2Canalyzer).

El analizador de configuración del centro de seguridad & cumplimiento ofrece una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración de Perfil de protección estándar y protección estricta en [directivas de seguridad predeterminadas](preset-security-policies.md).

El analizador de configuración analiza los siguientes tipos de directivas:

- **Directivas de Exchange Online Protection (EOP)**: Esto incluye a Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de EOP sin buzones de Exchange Online:

  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md).
  - [Directivas antimalware](configure-anti-malware-policies.md).
  - [Directivas de protección contra suplantación de EOP](set-up-anti-phishing-policies.md#spoof-settings).

- **Directivas de Microsoft defender para office 365**: Esto incluye a las organizaciones con las suscripciones complementarias de Microsoft 365 E5 o defender para Office 365:

  - Directivas antiphishing en Microsoft defender para Office 365, que incluyen:

    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas de protección contra suplantación de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)
    - [Umbrales de suplantación de identidad avanzada](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

  - [Directivas de vínculos a prueba](set-up-atp-safe-links-policies.md)de errores.

  - [Directivas de datos adjuntos seguros](set-up-atp-safe-attachments-policies.md).

Los valores de configuración **estándar** y **estricta** de la Directiva que se usan como líneas de base se describen en [configuración recomendada para EOP y Microsoft defender para Office 365 Security](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página del **analizador de configuración** , use <https://protection.office.com/configurationAnalyzer> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conectarse a PowerShell de Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener asignados permisos en el centro de seguridad & cumplimiento antes de poder llevar a cabo los procedimientos de este artículo:
  - Para usar el analizador de configuración **y** realizar actualizaciones en las directivas de seguridad, debe ser miembro de los grupos de roles administración de la **organización** o **Administrador de seguridad** .
  - Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de los grupos de roles **lector global** o **lector de seguridad** .

  Para obtener más información, vea [Permisos en el Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).

  **Notas**:

  - Agregar usuarios al rol correspondiente de Azure Active Directory en el Centro de administración de Microsoft 365 otorga a los usuarios los permisos necesarios en el Centro de seguridad y cumplimiento _y_ permisos para otras características de Microsoft 365. Para obtener más información, vea [Sobre los roles de administrador](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - El grupo de roles **Administración de organización de solo lectura** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) también proporciona acceso de solo lectura a la característica.

## <a name="use-the-configuration-analyzer-in-the-security--compliance-center"></a>Uso del analizador de configuración en el centro de seguridad & cumplimiento

En el centro de seguridad & cumplimiento, vaya a **Threat Management** \> **Policy** \> **Configuration Analyzer**.

![Widget analizador de configuración en la página Directiva de administración de amenazas \>](../../media/configuration-analyzer-widget.png)

El analizador de configuración tiene dos pestañas principales:

- **Configuración y recomendaciones**: elige estándar o estricto y compara esa configuración con las directivas de seguridad existentes. En los resultados, puede ajustar los valores de la configuración para que aparezcan en el mismo nivel que el estándar o estricto.

- **Análisis e historial de la fase de configuración**: esta vista permite realizar un seguimiento de los cambios de directiva con el tiempo.

### <a name="setting-and-recommendations-tab-in-the-configuration-analyzer"></a>Configuración y ficha recomendaciones en el analizador de configuración

De forma predeterminada, la pestaña se abre en la comparación con el perfil de protección estándar. Puede cambiar a la comparación de un perfil de protección estricto haciendo clic en **Ver recomendaciones estrictas**. Para cambiar de nuevo, seleccione **Ver recomendaciones estándar**.

![Vista de configuración y recomendaciones en el analizador de configuración](../../media/configuration-analyzer-settings-and-recommendations-view.png)

De forma predeterminada, la columna **grupo de directivas/nombre de configuración** contiene una vista contraída de los distintos tipos de directivas de seguridad y el número de opciones de configuración que necesitan mejorar (si las hay). Los tipos de directivas son los siguientes:

- **Contra correo electrónico no deseado**
- **Contra la suplantación de identidad**
- **Anti-malware**
- **Datos adjuntos seguros de ATP** (si su suscripción incluye a Microsoft defender para Office 365)
- **Vínculos seguros ATP** (si la suscripción incluye Microsoft defender para Office 365)

En la vista predeterminada, todo se contrae. Junto a cada Directiva, hay un resumen de los resultados de la comparación de las directivas (que puede modificar) y la configuración de las directivas correspondientes para los perfiles de protección estándar o estricto (que no se pueden modificar). Verá la siguiente información del perfil de protección que está comparando con:

- **Verde**: todas las opciones de configuración de todas las directivas existentes son al menos tan seguras como el perfil de protección.
- **Ámbar**: un número reducido de configuraciones en las directivas existentes no es tan seguro como el perfil de protección.
- **Red**: un número significativo de configuraciones en las directivas existentes no es tan seguro como el perfil de protección. Esto puede deberse a algunas configuraciones en muchas directivas o muchas opciones de configuración en una directiva.

Para comparaciones favorables, verá el texto: **todas las opciones siguen** \<**Standard** or **Strict**\> **recomendaciones**. De lo contrario, verá el número de opciones de configuración recomendadas que se deben cambiar.

Si amplía el **nombre del grupo o la configuración de directivas**, se muestran todas las directivas y la configuración asociada en cada Directiva específica que requieran atención. O bien, puede expandir un tipo específico de directiva (por ejemplo, **contra el correo no deseado**) para ver sólo la configuración en los tipos de directivas que requieren su atención.

Si la comparación no tiene recomendaciones para la mejora (verde), la expansión de la Directiva no revela nada. Si hay algún número de recomendaciones para la mejora (ámbar o rojo), se revela la configuración que requiere atención y se revela la información correspondiente en las siguientes columnas:

- El nombre de la configuración que requiere su atención. Por ejemplo, en la captura de pantalla anterior, se trata del **umbral de correo electrónico masivo** en una directiva contra correo no deseado.

- **Directiva**: el nombre de la Directiva afectada que contiene la configuración.

- Se **aplica a**: el número de usuarios a los que se aplican las directivas afectadas.

- **Configuración actual**: el valor actual de la configuración.

- **Última modificación**: la fecha en la que la Directiva se modificó por última vez.

- **Recomendaciones**: el valor de la configuración en el perfil de protección estándar o estricta. Para cambiar el valor de la configuración de la Directiva de manera que se ajuste al valor recomendado en el perfil de protección, haga clic en **adoptar**. Si el cambio se realiza correctamente, verá el mensaje: **recomendaciones adoptadas correctamente**. Haga clic en **Actualizar** para ver el menor número de recomendaciones y para quitar la configuración específica o la fila de la Directiva de los resultados.

### <a name="configuration-drift-analysis-and-history-tab-in-the-configuration-analyzer"></a>Ficha historial y análisis de derivación de configuración del analizador de configuración

Esta pestaña le permite realizar un seguimiento de los cambios realizados en las directivas de seguridad personalizadas. De forma predeterminada, se muestra la siguiente información:

- **Última modificación**
- **Modificado por**
- **Nombre de la configuración**
- **Directiva**
- **Tipo**

Para filtrar los resultados, haga clic en **Filtrar**. En el control flotante **filtros** que aparece, puede seleccionar entre los filtros siguientes:

- **Hora de inicio** y **hora de finalización** (fecha)
- **Protección estándar** o **protección estricta**

Para exportar los resultados a un archivo. csv, haga clic en **exportar**.

![Vista de historial y análisis de derivación de configuración en el analizador de configuración](../../media/configuration-analyzer-configuration-drift-analysis-view.png)
