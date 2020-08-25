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
ms.openlocfilehash: 39bec980ac95681ec2c2300914582d5e8786c884
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867168"
---
# <a name="configuration-analyzer-for-protection-policies-in-eop-and-office-365-atp"></a>Analizador de configuración para directivas de protección en EOP y Office 365 ATP

> [!NOTE]
> Las características descritas en este tema están en versión preliminar, no están disponibles en todas las organizaciones y están sujetas a cambios.

El analizador de configuración del centro de seguridad & cumplimiento ofrece una ubicación central para buscar y corregir directivas de seguridad en las que la configuración está por debajo de la configuración de Perfil de protección estándar y protección estricta en [directivas de seguridad predeterminadas](preset-security-policies.md).

El analizador de configuración analiza los siguientes tipos de directivas:

- **Directivas de Exchange Online Protection (EOP)**: Esto incluye a Microsoft 365 organizaciones con buzones de Exchange Online y organizaciones independientes de EOP sin buzones de Exchange Online:
  
  - [Directivas contra correo no deseado](configure-your-spam-filter-policies.md).
  - [Directivas antimalware](configure-anti-malware-policies.md).
  - [Directivas de protección contra suplantación de EOP](set-up-anti-phishing-policies.md#spoof-settings).

- **Directivas de protección contra amenazas avanzada (ATP) de Office 365**: Esto incluye a las organizaciones con suscripciones de complementos de ATP de Microsoft 365 E5 u Office 365:

  - Directivas antiphishing de ATP, que incluyen:

    - La misma [configuración de suplantación](set-up-anti-phishing-policies.md#spoof-settings) de identidad que están disponibles en las directivas de protección contra suplantación de EOP.
    - [Configuración de suplantación](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)
    - [Umbrales de suplantación de identidad avanzada](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies)

  - [Directivas de vínculos a prueba](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings-in-custom-policies-for-specific-users)de errores.

  - [Directivas de datos adjuntos seguros](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-policy-settings-in-custom-policies-for-specific-users).

Los valores de configuración **estándar** y **estricta** de la Directiva que se usan como líneas de base se describen en [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>¿Qué necesita saber antes de comenzar?

- Abra el Centro de seguridad y cumplimiento en <https://protection.office.com/>. Para ir directamente a la página del **analizador de configuración** , use <https://protection.office.com/configurationAnalyzer> .

- Para conectarse al PowerShell de Exchange Online, consulte [Conexión a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Debe tener permisos asignados para poder realizar los procedimientos descritos en este artículo:

  - Para usar el analizador de configuración **y** realizar actualizaciones en las directivas de seguridad, debe pertenecer a uno de los siguientes grupos de roles:

    - **Administración de la organización** o **Administrador de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización** o **Administración de higiene** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

  - Para obtener acceso de solo lectura al analizador de configuración, debe ser miembro de uno de los siguientes grupos de roles:

    - **Lector de seguridad** en el [Centro de seguridad y cumplimiento](permissions-in-the-security-and-compliance-center.md).
    - **Administración de la organización de solo visualización** en [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

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
- **Antimalware**
- **Datos adjuntos seguros de ATP** (si la suscripción incluye ATP)
- **Vínculos seguros ATP** (si la suscripción incluye ATP)

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
