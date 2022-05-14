---
title: Configuración de invalidaciones locales para la configuración de Antivirus de Microsoft Defender
description: Habilite o deshabilite a los usuarios para que cambien localmente la configuración en El antivirus de Microsoft Defender.
keywords: invalidación local, directiva local, directiva de grupo, gpo, bloqueo, combinación, listas
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: 8de4450247d917f0e4d5023febf6d41c80f0688d
ms.sourcegitcommit: ebbe8713297675db5dcb3e0d9c3ae5e746b99196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2022
ms.locfileid: "65416648"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Impedir o permitir que los usuarios modifiquen localmente Antivirus de Microsoft Defender configuración de directiva


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

De forma predeterminada, Antivirus de Microsoft Defender configuración que se implementa a través de un objeto directiva de grupo en los puntos de conexión de la red impedirá que los usuarios cambien localmente la configuración. Puede cambiar esto en algunos casos.

Por ejemplo, puede ser necesario permitir que determinados grupos de usuarios (como investigadores de seguridad e investigadores de amenazas) controlen aún más la configuración individual en los puntos de conexión que usan.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Configuración de invalidaciones locales para la configuración de Antivirus de Microsoft Defender

La configuración predeterminada para estas directivas es **Deshabilitado**.

Si se establecen en **Habilitado**, los usuarios de los puntos de conexión pueden realizar cambios en la configuración asociada con la aplicación [de Seguridad de Windows](microsoft-defender-security-center-antivirus.md), la configuración de directiva de grupo local y los cmdlets de PowerShell (si procede).

En la tabla siguiente se muestra cada una de las opciones de directiva de invalidación y las instrucciones de configuración de la característica o configuración asociadas.

Para configurar estas opciones:

1. En el equipo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y haga clic en **Plantillas administrativas**.

3. Expanda el árbol para **Windows componentes** >  **Antivirus de Microsoft Defender** y, a continuación, la **ubicación** especificada en la tabla de configuración (en este artículo).

4. Haga doble clic en la **configuración de** directiva como se especifica en la tabla siguiente y establezca la opción en la configuración deseada. Haga clic en **Aceptar** y repita cualquier otra configuración.

5. Implemente el objeto directiva de grupo como de costumbre.

## <a name="table-of-settings"></a>Tabla de configuración

<br/><br/>

| Ubicación | Configuración | Artículo |
|---|---|---|---|
| MAPAS |Configuración de la invalidación de configuración local para informar a Microsoft MAPS|[Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Cuarentena|Configuración de la invalidación de configuración local para la eliminación de elementos de la carpeta Cuarentena|[Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para supervisar la actividad de archivos y programas en el equipo|[Habilitar y configurar Antivirus de Microsoft Defender protección y supervisión siempre activadas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para la supervisión de la actividad de archivo entrante y saliente | [Habilitar y configurar Antivirus de Microsoft Defender protección y supervisión siempre activadas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados|[Habilitar y configurar Antivirus de Microsoft Defender protección y supervisión siempre activadas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para activar la supervisión del comportamiento|[Habilitar y configurar Antivirus de Microsoft Defender protección y supervisión siempre activadas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para activar la protección en tiempo real|[Habilitar y configurar Antivirus de Microsoft Defender protección y supervisión siempre activadas](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Remediación|Configuración de la invalidación de configuración local para la hora del día para ejecutar un examen completo programado para completar la corrección|[Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el porcentaje máximo de uso de CPU|[Configuración y ejecución de exámenes](run-scan-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el día del examen de programación|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el tiempo de examen rápido programado|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el tiempo de examen programado|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el tipo de examen que se usará para un examen programado|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Configurar cómo se combinan las listas de exclusiones y corrección de amenazas definidas local y globalmente

También puede configurar cómo se combinan o combinan las listas definidas localmente con listas definidas globalmente. Esta configuración se aplica a [las listas de exclusión](configure-exclusions-microsoft-defender-antivirus.md), [las listas de corrección especificadas](configure-remediation-microsoft-defender-antivirus.md) y la [reducción de la superficie expuesta a ataques](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).

De forma predeterminada, las listas que se han configurado en la directiva de grupo local y la aplicación de Seguridad de Windows se combinan con listas definidas por el objeto de directiva de grupo adecuado que ha implementado en la red. Cuando hay conflictos, la lista definida globalmente tiene prioridad.

Puede deshabilitar esta configuración para asegurarse de que solo se usan listas definidas globalmente (como las de cualquier GPO implementado).

### <a name="use-group-policy-to-disable-local-list-merging"></a>Uso de directiva de grupo para deshabilitar la combinación de listas locales

1. En el equipo de administración de directiva de grupo, abra la [consola de administración de directiva de grupo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y haga clic en **Plantillas administrativas**.

3. Expanda el árbol para **Windows componentes > Antivirus de Microsoft Defender**.

4. Haga doble clic en **Configurar el comportamiento de combinación de administrador local para listas** y establezca la opción **en Deshabilitado**. Haga clic en **Aceptar**.

> [!NOTE]
> Si deshabilita la combinación de listas locales, invalidará la configuración de acceso controlado a carpetas. También invalida las carpetas protegidas o las aplicaciones permitidas establecidas por el administrador local. Para obtener más información sobre la configuración de acceso controlado a carpetas, consulte [Permitir una aplicación bloqueada en Seguridad de Windows](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configuración de la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)
