---
title: Crear un proceso de implementación gradual personalizado para actualizaciones de Microsoft Defender
description: Obtenga información sobre cómo usar herramientas compatibles para crear un proceso de implementación gradual personalizado para actualizaciones
keywords: herramientas de actualización, gpo, intune, mdm, microsoft endpoint manager, policy, powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: a506f4913369e53fd2ed4943bb2557935f1d62e5
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105565"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Crear un proceso de implementación gradual personalizado para actualizaciones de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Esta funcionalidad requiere Antivirus de Microsoft Defender versión 4.18.2106.X o posterior.

Para crear su propio proceso de implementación gradual personalizado para actualizaciones de Defender, puede usar la directiva de grupo, Microsoft Endpoint Manager y PowerShell.

En la tabla siguiente se enumeran las opciones de directiva de grupo disponibles para configurar canales de actualización:

| Título de configuración  | Description  | Ubicación  |
|-|-|-|
| Seleccionar el canal de lanzamiento de actualización mensual de la plataforma gradual de Microsoft Defender  | Habilite esta directiva para especificar cuándo los dispositivos reciben actualizaciones de la plataforma de Microsoft Defender durante el lanzamiento gradual mensual. Canal beta: los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones. Seleccione Canal beta para participar en la identificación y la presentación de informes de problemas a Microsoft. Los dispositivos del Windows Insider Program se suscriben a este canal de forma predeterminada. Solo para su uso en entornos de prueba (manuales) y un número limitado de dispositivos.  <br><br>  Canal actual (versión preliminar): los dispositivos establecidos en este canal recibirán actualizaciones lo antes posible durante el ciclo de lanzamiento gradual mensual. Sugerido para entornos de preproducción/validación.  <br><br>  Canal actual (por fases): se ofrecerán actualizaciones a los dispositivos después del ciclo de lanzamiento gradual mensual. Se sugiere aplicar a una parte pequeña y representativa de la población de producción (~10%).  <br><br>  Canal actual (amplio): los dispositivos solo se ofrecerán actualizaciones una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (~10-100%).  <br><br>   Si deshabilitas o no configuras esta directiva, el dispositivo se mantendrá actualizado automáticamente durante el ciclo de lanzamiento gradual. Adecuado para la mayoría de los dispositivos.  | Windows Componentes\Antivirus de Microsoft Defender  |
| Seleccionar el canal de lanzamiento de actualización mensual del motor de Microsoft Defender gradual  | Habilite esta directiva para especificar cuándo los dispositivos reciben actualizaciones del motor de Microsoft Defender durante el lanzamiento gradual mensual.  <br><br>  Canal beta: los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones. Seleccione Canal beta para participar en la identificación y la presentación de informes de problemas a Microsoft. Los dispositivos del Windows Insider Program se suscriben a este canal de forma predeterminada. Solo para su uso en entornos de prueba (manuales) y un número limitado de dispositivos.  <br><br>  Canal actual (versión preliminar): los dispositivos establecidos en este canal recibirán actualizaciones lo antes posible durante el ciclo de lanzamiento gradual mensual. Sugerido para entornos de preproducción/validación.  <br><br>  Canal actual (por fases): se ofrecerán actualizaciones a los dispositivos después del ciclo de lanzamiento gradual mensual. Se sugiere aplicar a una parte pequeña y representativa de la población de producción (~10%).  <br><br>  Canal actual (amplio): los dispositivos solo se ofrecerán actualizaciones una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (~10-100%).  <br><br>  Si deshabilitas o no configuras esta directiva, el dispositivo se mantendrá actualizado automáticamente durante el ciclo de lanzamiento gradual. Adecuado para la mayoría de los dispositivos.  | Windows Componentes\Antivirus de Microsoft Defender  |
| Seleccionar canal de lanzamiento gradual de actualizaciones de definiciones diarias de Microsoft Defender  | Habilite esta directiva para especificar cuándo los dispositivos reciben actualizaciones de definiciones de Microsoft Defender durante el lanzamiento gradual diario. <br><br> Canal actual (por fases): se ofrecerán actualizaciones a los dispositivos después del ciclo de lanzamiento. Se sugiere aplicar a una parte pequeña y representativa de la población de producción (~10%). <br><br>   Canal actual (amplio): los dispositivos solo se ofrecerán actualizaciones una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (~10-100%). <br><br>   Si deshabilitas o no configuras esta directiva, el dispositivo se mantendrá actualizado automáticamente durante el ciclo de lanzamiento diario. Adecuado para la mayoría de los dispositivos.  | Windows Componentes\Antivirus de Microsoft Defender  |
| Deshabilitar la implementación gradual de actualizaciones de Microsoft Defender  | Habilite esta directiva para deshabilitar la implementación gradual de actualizaciones de Defender. <br><br> Canal actual (amplio): los dispositivos establecidos en este canal recibirán actualizaciones en último lugar durante el ciclo de lanzamiento gradual. Ideal para máquinas de centros de datos que solo reciben actualizaciones limitadas. <br><br> Nota: Esta configuración se aplica tanto a las actualizaciones mensuales como diarias de Defender y invalidará las selecciones de canal configuradas anteriormente para las actualizaciones de la plataforma y el motor. <br><br> Si deshabilitas o no configuras esta directiva, el dispositivo permanecerá en Canal actual (predeterminado) a menos que se especifique lo contrario en canales específicos para actualizaciones de plataforma y motor. Mantenerse actualizado automáticamente durante el ciclo de lanzamiento gradual. Adecuado para la mayoría de los dispositivos.  | Windows Componentes\Antivirus de Microsoft Defender  |

## <a name="group-policy"></a>Directiva de grupo

> [!NOTE]
> Se publicará una plantilla ADMX de Defender actualizada junto con la versión 21H2 de Windows 10. Una versión no localizada está disponible para su descarga en https://github.com/microsoft/defender-updatecontrols .

Puede usar la [directiva de grupo](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)para configurar y administrar Antivirus de Microsoft Defender en los puntos de   conexión.

En general, puede usar el siguiente procedimiento para configurar o cambiar la configuración Antivirus de Microsoft Defender de directiva de grupo:

1. En el equipo de administración de directivas de grupo, abra la Consola de administración de directivas de **grupo,** haga clic con el botón secundario en el objeto de directiva de grupo  (GPO) que desea configurar y haga clic en **Editar**.

2. Con el Editor de administración de directivas de grupo, vaya a **Configuración del equipo**.

3. Haga clic **en Plantillas administrativas**.

4. Expanda el árbol para **Windows componentes > Antivirus de Microsoft Defender**.

5. Expanda la sección (denominada **** Ubicación en la tabla de este tema) que contiene la configuración que desea configurar, haga doble clic en la configuración para abrirlo y realice cambios en la   configuración.

6. [Implemente el GPO actualizado como lo hace normalmente](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx).

## <a name="intune"></a>Intune

Siga las instrucciones del siguiente vínculo para crear una directiva personalizada en Intune:

[Agregar configuración personalizada para Windows 10 dispositivos en Microsoft Intune: Azure \| Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

## <a name="powershell"></a>PowerShell

Use el `Set-MpPreference` cmdlet para configurar la implementación de las actualizaciones graduales.

Usa los siguientes parámetros:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Ejemplo:

Se `Set-MpPreference -PlatformUpdatesChannel Beta` usa para configurar las actualizaciones de la plataforma para que lleguen desde el canal beta.

Para obtener más información sobre los parámetros y cómo configurarlos, vea [Set-MpPreference (Defender) | Microsoft Docs](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps&preserve-view=true).
