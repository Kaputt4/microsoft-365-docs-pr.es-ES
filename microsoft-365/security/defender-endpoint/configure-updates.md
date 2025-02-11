---
title: Creación de un proceso de implementación gradual personalizado para Microsoft Defender actualizaciones
description: Aprenda a usar las herramientas admitidas para crear un proceso de implementación gradual personalizado para las actualizaciones.
keywords: update tools, gpo, intune, mdm, microsoft endpoint manager, policy, powershell
ms.service: microsoft-365-security
ms.subservice: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.topic: conceptual
search.appverid: met150
ms.openlocfilehash: 85dbb5458aea474757a33b93e58a1c0b00f4c683
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68174894"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Creación de un proceso de implementación gradual personalizado para Microsoft Defender actualizaciones

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> [!NOTE]
> Esta funcionalidad requiere Microsoft Defender antivirus versión 4.18.2106.X o posterior.

Para crear su propio proceso de implementación gradual personalizado para las actualizaciones de Defender, puede usar directiva de grupo, Microsoft Endpoint Manager y PowerShell.

En la tabla siguiente se enumeran las opciones de directiva de grupo disponibles para configurar canales de actualización:

|Establecer título|Descripción|Ubicación|
|---|---|---|
|Selección del canal de implementación de actualizaciones mensuales de la plataforma Microsoft Defender gradual|Habilite esta directiva para especificar cuándo reciben los dispositivos Microsoft Defender actualizaciones de la plataforma durante el lanzamiento gradual mensual. <p> Canal beta: los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones. Seleccione Canal beta para participar en la identificación y la notificación de problemas a Microsoft. Los dispositivos del Programa Windows Insider están suscritos a este canal de forma predeterminada. Solo para su uso en entornos de prueba (manuales) y un número limitado de dispositivos. <p> Canal actual (versión preliminar): a los dispositivos establecidos en este canal se les ofrecerán las actualizaciones más tempranas durante el ciclo de lanzamiento gradual mensual. Se recomienda para entornos de preproducción y validación. <p> Canal actual (preconfigurado): se ofrecerán actualizaciones a los dispositivos después del ciclo de lanzamiento gradual mensual. Se recomienda aplicar a una parte pequeña y representativa de la población de producción (~10%). <p> Canal actual (amplio): solo se ofrecerán actualizaciones a los dispositivos una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (aproximadamente entre el 10 y el 100 %). <p> Retraso crítico: se ofrecerán actualizaciones a los dispositivos con un retraso de 48 horas. Solo se sugiere para entornos críticos. <p>Si deshabilita o no configura esta directiva, el dispositivo permanecerá actualizado automáticamente durante el ciclo de versión gradual. Adecuado para la mayoría de los dispositivos.|Windows Components\Microsoft Defender Antivirus|
|Selección del canal de implementación de actualizaciones mensuales del motor Microsoft Defender gradual|Habilite esta directiva para especificar cuándo reciben los dispositivos Microsoft Defender actualizaciones del motor durante el lanzamiento gradual mensual. <p> Canal beta: los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones. Seleccione Canal beta para participar en la identificación y la notificación de problemas a Microsoft. Los dispositivos del Programa Windows Insider están suscritos a este canal de forma predeterminada. Solo para su uso en entornos de prueba (manuales) y un número limitado de dispositivos. <p> Canal actual (versión preliminar): a los dispositivos establecidos en este canal se les ofrecerán las actualizaciones más tempranas durante el ciclo de lanzamiento gradual mensual. Se recomienda para entornos de preproducción y validación. <p> Canal actual (preconfigurado): se ofrecerán actualizaciones a los dispositivos después del ciclo de lanzamiento gradual mensual. Se recomienda aplicar a una parte pequeña y representativa de la población de producción (~10%). <p> Canal actual (amplio): solo se ofrecerán actualizaciones a los dispositivos una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (aproximadamente entre el 10 y el 100 %). <p> Retraso crítico: se ofrecerán actualizaciones a los dispositivos con un retraso de 48 horas. Solo se sugiere para entornos críticos.<p> Si deshabilita o no configura esta directiva, el dispositivo permanecerá actualizado automáticamente durante el ciclo de versión gradual. Adecuado para la mayoría de los dispositivos.|Windows Components\Microsoft Defender Antivirus|
|Selección de un canal de implementación de actualizaciones de inteligencia de seguridad gradual Microsoft Defender diaria|Habilite esta directiva para especificar cuándo reciben los dispositivos Microsoft Defender actualizaciones de inteligencia de seguridad durante el lanzamiento gradual diario. <p> Canal actual (preconfigurado): se ofrecerán actualizaciones a los dispositivos después del ciclo de lanzamiento. Se recomienda aplicar a una parte pequeña y representativa de la población de producción (~10%). <p> Canal actual (amplio): solo se ofrecerán actualizaciones a los dispositivos una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (aproximadamente entre el 10 y el 100 %). <p>  Si deshabilita o no configura esta directiva, el dispositivo permanecerá actualizado automáticamente durante el ciclo de versión diario. Adecuado para la mayoría de los dispositivos.|Windows Components\Microsoft Defender Antivirus|
|Deshabilitación del lanzamiento gradual de actualizaciones de Microsoft Defender|Habilite esta directiva para deshabilitar la implementación gradual de actualizaciones de Defender. <p> Canal actual (amplio): a los dispositivos establecidos en este canal se les ofrecerá actualizaciones por última vez durante el ciclo de versión gradual. Mejor para máquinas de centro de datos que solo reciben actualizaciones limitadas. <p> Nota: Esta configuración se aplica tanto a las actualizaciones mensuales como diarias de Defender y reemplazará las selecciones de canal configuradas anteriormente para las actualizaciones de la plataforma y del motor. <p> Si deshabilita o no configura esta directiva, el dispositivo permanecerá en canal actual (predeterminado) a menos que se especifique lo contrario en canales específicos para las actualizaciones de la plataforma y del motor. Manténgase actualizado automáticamente durante el ciclo de lanzamiento gradual. Adecuado para la mayoría de los dispositivos.|Componentes de Windows\Microsoft Defender Antivirus\MpEngine|
|

## <a name="group-policy"></a>Directiva de grupo

> [!NOTE]
> Se publicará una plantilla ADMX de Defender actualizada junto con la versión 21H2 de Windows 10. Hay disponible una versión no localizada para su descarga en https://github.com/microsoft/defender-updatecontrols.

Puede usar [directiva de grupo](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN) para configurar y administrar Microsoft Defender Antivirus en los puntos de conexión.

En general, puede usar el procedimiento siguiente para configurar o cambiar Microsoft Defender configuración de directiva de grupo antivirus:

1. En la máquina de administración de directiva de grupo, abra la **consola de administración de directiva de grupo**, haga clic con el botón derecho en el **objeto de directiva de grupo** (GPO) que desea configurar y haga clic en **Editar**.

2. Con el Editor de administración de directiva de grupo vaya a **Configuración del equipo**.

3. Haga clic en **Plantillas administrativas**.

4. Expanda el árbol a **componentes de Windows > Microsoft Defender Antivirus**.

5. Expanda la sección (denominada **Ubicación** en la tabla de este tema) que contiene la configuración que desea configurar, haga doble clic en la configuración para abrirla y realice cambios en la configuración.

6. [Implemente el GPO actualizado como lo hace normalmente](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx).

## <a name="intune"></a>Intune

Siga las instrucciones del vínculo siguiente para crear una directiva personalizada en Intune:

[Adición de la configuración personalizada para dispositivos Windows 10 en Microsoft Intune: Azure \|Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

Para obtener más información sobre el CSP de Defender usado para el proceso de implementación gradual, consulte [CSP de Defender](/windows/client-management/mdm/defender-csp).

## <a name="powershell"></a>PowerShell

Use el cmdlet para configurar la `Set-MpPreference` implementación de las actualizaciones graduales.

Usa los siguientes parámetros:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease 1|0
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Ejemplo:

Use `Set-MpPreference -PlatformUpdatesChannel Beta` para configurar las actualizaciones de la plataforma para que lleguen desde el canal beta.

Para obtener más información sobre los parámetros y cómo configurarlos, consulte [Set-MpPreference](/powershell/module/defender/set-mppreference) (Microsoft Defender Antivirus).

> [!TIP]
> Si busca información relacionada con el antivirus para otras plataformas, consulte:
> - [Establecer las preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de las directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configurar Defender para punto de conexión en características de Android](android-configure.md)
> - [Configurar Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)
