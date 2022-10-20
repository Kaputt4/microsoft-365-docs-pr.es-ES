---
title: Configuración de invalidaciones locales para Microsoft Defender configuración del Antivirus
description: Habilite o deshabilite a los usuarios para que cambien localmente la configuración en Microsoft Defender Antivirus.
keywords: invalidación local, directiva local, directiva de grupo, gpo, bloqueo, combinación, listas
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: conceptual
ms.custom: nextgen
ms.date: 08/02/2022
ms.reviewer: ''
manager: dansimp
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 6d74a3798db01495af2786519f06ec1d8f58afe2
ms.sourcegitcommit: 0d8fb571024f134d7480fe14cffc5e31a687d356
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68631994"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Impedir o permitir que los usuarios modifiquen localmente Microsoft Defender configuración de directivas antivirus


**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

De forma predeterminada, Microsoft Defender configuración del Antivirus que se implementa a través de un objeto समूह नीति en los puntos de conexión de la red impedirá que los usuarios cambien localmente la configuración. Puede cambiar esta configuración en algunos casos. Por ejemplo, podría ser necesario permitir que determinados grupos de usuarios, como investigadores de seguridad e investigadores de amenazas, tengan un mayor control sobre la configuración individual en los puntos de conexión que usan.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Configuración de invalidaciones locales para Microsoft Defender configuración del Antivirus

La configuración predeterminada para estas directivas de invalidación local es **Deshabilitado**.

Si las directivas están establecidas en **Habilitado**, los usuarios pueden realizar cambios en la configuración asociada en sus dispositivos mediante la aplicación [de Seguridad de Windows](microsoft-defender-security-center-antivirus.md), la configuración de समूह नीति local o los cmdlets de PowerShell (si procede).

En [la sección Tabla de configuración](#table-of-settings) se enumeran las opciones de directiva de invalidación y las instrucciones de configuración.

Para configurar estas opciones:

1. En el equipo de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto समूह नीति que desea configurar y, a continuación, seleccione **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes** >  de Windows **Microsoft Defender Antivirus** y, a continuación, la **ubicación** especificada en la [sección tabla de configuración](#table-of-settings) (en este artículo).

4. Haga doble clic en la **configuración de** directiva como se especifica en la tabla siguiente y establezca la opción en la configuración deseada. Seleccione **Aceptar** y repita para cualquier otra configuración.

5. Implemente el objeto समूह नीति como de costumbre.

## <a name="table-of-settings"></a>Tabla de configuración

| Ubicación | Setting | Artículo |
|---|---|---|---|
| MAPAS |Configuración de la invalidación de configuración local para informar a Microsoft MAPS|[Habilitar la protección proporcionada en la nube](enable-cloud-protection-microsoft-defender-antivirus.md) |
| Quarantine|Configuración de la invalidación de configuración local para la eliminación de elementos de la carpeta Cuarentena|[Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para supervisar la actividad de archivos y programas en el equipo|[Habilitación y configuración de Microsoft Defender protección y supervisión always-on del Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para la supervisión de la actividad de archivo entrante y saliente | [Habilitación y configuración de Microsoft Defender protección y supervisión always-on del Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados|[Habilitación y configuración de Microsoft Defender protección y supervisión always-on del Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para activar la supervisión del comportamiento|[Habilitación y configuración de Microsoft Defender protección y supervisión always-on del Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Protección en tiempo real|Configuración de la invalidación de configuración local para activar la protección en tiempo real|[Habilitación y configuración de Microsoft Defender protección y supervisión always-on del Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md) |
| Remediación|Configuración de la invalidación de configuración local para la hora del día para ejecutar un examen completo programado para completar la corrección|[Configuración de la corrección de exámenes](configure-remediation-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el porcentaje máximo de uso de CPU|[Configuración y ejecución de exámenes](run-scan-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el día del examen de programación|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el tiempo de examen rápido programado|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el tiempo de examen programado|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |
| Examinar|Configuración de la invalidación de configuración local para el tipo de examen que se usará para un examen programado|[Configuración de exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md) |

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Configurar cómo se combinan las listas de exclusiones y corrección de amenazas definidas local y globalmente

También puede configurar cómo se combinan o combinan las listas definidas localmente con listas definidas globalmente. Esta configuración se aplica a [las listas de exclusión](configure-exclusions-microsoft-defender-antivirus.md), [las listas de corrección especificadas](configure-remediation-microsoft-defender-antivirus.md) y la [reducción de la superficie expuesta a ataques](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).

De forma predeterminada, las listas que se han configurado en la directiva de grupo local y la aplicación de Seguridad de Windows se combinan con listas definidas por el objeto de समूह नीति adecuado que ha implementado en la red. Cuando hay conflictos, la lista definida globalmente tiene prioridad. Puede deshabilitar esta configuración para asegurarse de que solo se usan listas definidas globalmente (como las de cualquier GPO implementado).

### <a name="use-group-policy-to-disable-local-list-merging"></a>Uso de समूह नीति para deshabilitar la combinación de listas locales

1. En el equipo de administración de समूह नीति, abra la [consola de administración de समूह नीति](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), haga clic con el botón derecho en el objeto समूह नीति que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directiva de grupo**, vaya a **Configuración del equipo** y seleccione **Plantillas administrativas**.

3. Expanda el árbol a **componentes** >  **de Windows Microsoft Defender Antivirus**.

4. Haga doble clic en **Configurar el comportamiento de combinación de administrador local para listas** y establezca la opción **en Deshabilitado**. A continuación, seleccione **Aceptar**.

### <a name="use-microsoft-endpoint-manager-to-disable-local-list-merging"></a>Uso de Microsoft Endpoint Manager para deshabilitar la combinación de listas locales

1. En el [Centro de administración de Microsoft Endpoint Manager](https://endpoint.microsoft.com), seleccione **Antivirus** **de seguridad** >  de puntos de conexión.

2. Elija **Crear directiva** o modifique una directiva de antivirus de Microsoft Defender existente.

3. En **Configuración**, seleccione la lista desplegable situada junto a **Deshabilitar combinación de Administración local** y seleccione **Deshabilitar combinación local Administración**.

> [!NOTE]
> Si deshabilita la combinación de listas locales, invalidará la configuración de acceso controlado a carpetas. También invalida las carpetas protegidas o las aplicaciones permitidas establecidas por el administrador local. Para obtener más información sobre la configuración de acceso controlado a carpetas, consulte [Permitir una aplicación bloqueada en Seguridad de Windows](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)

## <a name="related-topics"></a>Temas relacionados

- [Microsoft Endpoint Manager](/mem/endpoint-manager-overview)
- [Antivirus de Microsoft Defender en Windows](microsoft-defender-antivirus-in-windows-10.md)
- [Configuración de la interacción del usuario final con Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)
