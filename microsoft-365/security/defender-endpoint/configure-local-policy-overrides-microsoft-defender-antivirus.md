---
title: Configurar invalidaciones locales para la configuración de Antivirus de Microsoft Defender
description: Habilite o deshabilite a los usuarios para que no cambien la configuración localmente en El antivirus de Microsoft Defender.
keywords: invalidación local, directiva local, directiva de grupo, gpo, bloqueo, combinación, listas
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4a35c6717fd7a1834364df32cf5570c83a5b776e
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274525"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Impedir o permitir que los usuarios modifiquen localmente la configuración de directiva de Antivirus de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

De forma predeterminada, la configuración del Antivirus de Microsoft Defender que se implementa a través de un objeto de directiva de grupo en los puntos de conexión de la red impedirá que los usuarios cambien localmente la configuración. Puede cambiar esto en algunos casos.

Por ejemplo, puede ser necesario permitir que determinados grupos de usuarios (como investigadores de seguridad e investigadores de amenazas) controle aún más la configuración individual en los puntos de conexión que usan.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Configurar invalidaciones locales para la configuración de Antivirus de Microsoft Defender

La configuración predeterminada de estas directivas es **Disabled**.

Si se establecen en **Habilitado,** los usuarios de los puntos de conexión pueden realizar cambios en la configuración asociada con la aplicación seguridad de [Windows,](microsoft-defender-security-center-antivirus.md) la configuración de directiva de grupo local y los cmdlets de PowerShell (cuando corresponda).

En la tabla siguiente se enumeran cada una de las opciones de directiva de invalidación y las instrucciones de configuración de la característica o configuración asociada.

Para configurar estas opciones:

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a **componentes de Windows > Antivirus** de Microsoft Defender y, a continuación, la **ubicación** especificada en la tabla siguiente.

4. Haga doble clic en la configuración **de directiva** especificada en la tabla siguiente y establezca la opción en la configuración deseada. Haga **clic en** Aceptar y repita cualquier otra configuración.

5. Implemente el objeto de directiva de grupo como de costumbre.

Ubicación | Configuración | Artículo
---|---|---|---
MAPAS | Configurar la invalidación de configuración local para los informes en Microsoft MAPS | [Habilitar la protección de entrega en la nube](enable-cloud-protection-microsoft-defender-antivirus.md)
Cuarentena | Configurar la invalidación de configuración local para la eliminación de elementos de la carpeta cuarentena | [Configurar la corrección para exámenes](configure-remediation-microsoft-defender-antivirus.md)
Protección en tiempo real | Configurar la invalidación de configuración local para la actividad del programa y el archivo de supervisión en el equipo | [Habilitar y configurar la protección y supervisión siempre activas de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)
Protección en tiempo real | Configurar la invalidación de configuración local para la supervisión de la actividad de archivos entrantes y salientes | [Habilitar y configurar la protección y supervisión siempre activas de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)
Protección en tiempo real | Configurar la invalidación de configuración local para examinar todos los archivos y datos adjuntos descargados | [Habilitar y configurar la protección y supervisión siempre activas de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)
Protección en tiempo real | Configurar la invalidación de configuración local para activar la supervisión del comportamiento | [Habilitar y configurar la protección y supervisión siempre activas de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)
Protección en tiempo real | Configurar la invalidación de configuración local para activar la protección en tiempo real | [Habilitar y configurar la protección y supervisión siempre activas de Antivirus de Microsoft Defender](configure-real-time-protection-microsoft-defender-antivirus.md)
Corrección | Configurar la invalidación de configuración local para la hora del día para ejecutar un examen completo programado para completar la corrección | [Configurar la corrección para exámenes](configure-remediation-microsoft-defender-antivirus.md)
Examinar | Configurar la invalidación de configuración local para el porcentaje máximo de uso de LA CPU | [Configurar y ejecutar exámenes](run-scan-microsoft-defender-antivirus.md)
Examinar | Configurar la invalidación de configuración local para el día de examen de programación | [Configurar exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Examinar | Configurar la invalidación de configuración local para el tiempo de examen rápido programado | [Configurar exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Examinar | Configurar la invalidación de configuración local para el tiempo de examen programado | [Configurar exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Examinar | Configurar la invalidación de configuración local para el tipo de examen que se usará para un examen programado | [Configurar exámenes programados](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Configurar cómo se combinan las listas de exclusiones y corrección de amenazas definidas local y globalmente

También puede configurar cómo se combinan o combinan listas definidas localmente con listas definidas globalmente. Esta configuración se aplica a las [listas de exclusión,](configure-exclusions-microsoft-defender-antivirus.md)las listas de [corrección especificadas](configure-remediation-microsoft-defender-antivirus.md)y la [reducción de superficie de ataque.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

De forma predeterminada, las listas que se han configurado en la directiva de grupo local y la aplicación Seguridad de Windows se combinan con listas definidas por el objeto de directiva de grupo adecuado que has implementado en la red. Cuando hay conflictos, la lista definida globalmente tiene prioridad.

Puede deshabilitar esta configuración para asegurarse de que solo se usan listas definidas globalmente (como las de cualquier GPO implementado).

### <a name="use-group-policy-to-disable-local-list-merging"></a>Usar la directiva de grupo para deshabilitar la combinación de listas locales

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de [grupo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))haga clic con el botón secundario en el objeto de directiva de grupo que desea configurar y haga clic en **Editar**.

2. En el **Editor de administración de directivas de grupo,** vaya a Configuración del equipo **y** haga clic en **Plantillas administrativas.**

3. Expande el árbol a **componentes de Windows > Antivirus de Microsoft Defender**.

4. Haga doble clic en Configurar el comportamiento de combinación **de administradores locales para las** listas y establezca la opción en **Deshabilitado**. Haga clic en **Aceptar**.

> [!NOTE]
> Si deshabilita la combinación de listas locales, invalidará la configuración de acceso controlado a carpetas. También invalida las carpetas protegidas o las aplicaciones permitidas establecidas por el administrador local. Para obtener más información acerca de la configuración de acceso controlado a carpetas, consulta [Permitir una aplicación bloqueada en Seguridad de Windows](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security).

## <a name="related-topics"></a>Temas relacionados

- [Antivirus de Microsoft Defender en Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurar la interacción del usuario final con Antivirus de Microsoft Defender](configure-end-user-interaction-microsoft-defender-antivirus.md)