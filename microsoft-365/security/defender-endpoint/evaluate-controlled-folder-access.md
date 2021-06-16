---
title: Evaluar acceso controlado a carpetas
description: Vea cómo el acceso controlado a carpetas puede ayudar a proteger los archivos de que las aplicaciones malintencionadas cambien.
keywords: Protección contra vulnerabilidades, windows 10, Windows Defender, ransomware, proteger, evaluar, probar, probar, probar
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 4254c5ea24d8c901ac5f6337b0c626afe02747e2
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926648"
---
# <a name="evaluate-controlled-folder-access"></a>Evaluar acceso controlado a carpetas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[El acceso controlado](controlled-folders.md) a carpetas es una característica que ayuda a proteger los documentos y archivos contra modificaciones de aplicaciones sospechosas o malintencionadas. El acceso controlado a carpetas se admite Windows Server 2019 y Windows 10 cliente.

Es especialmente útil para ayudar a proteger contra [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) que intenta cifrar los archivos y retenerlos como rehenes.

Este artículo le ayuda a evaluar el acceso controlado a carpetas. Explica cómo habilitar el modo de auditoría para que pueda probar la característica directamente en su organización.

> [!TIP]
> También puede visitar el sitio web de escenario de demostración de Microsoft Defender para endpoint en [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) para confirmar que la característica funciona y ver cómo funciona.

## <a name="use-audit-mode-to-measure-impact"></a>Usar el modo de auditoría para medir el impacto

Habilite el acceso controlado a carpetas en  modo auditoría para ver un registro de lo que hubiera ocurrido si se hubiera habilitado completamente. Pruebe cómo funcionará la característica en su organización para asegurarse de que no afecta a las aplicaciones de línea de negocio. También puede obtener una idea de cuántos intentos de modificación de archivos sospechosos suelen producirse durante un período de tiempo determinado.

Para habilitar el modo de auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Si quieres auditar completamente cómo funcionará el acceso controlado a carpetas en tu organización, tendrás que usar una herramienta de administración para implementar esta configuración en dispositivos de tus redes.
También puedes usar la directiva de grupo, Intune, la administración de dispositivos móviles (MDM) o Microsoft Endpoint Manager para configurar e implementar la configuración, como se describe en el tema principal de acceso controlado a [carpetas](controlled-folders.md).

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Revisar los eventos de acceso controlado a carpetas Windows visor de eventos

Los siguientes eventos de acceso controlado a carpetas aparecen en Windows visor de eventos en la carpeta Microsoft/Windows/Windows Defender/Operational.

Id. de evento | Descripción
-|-
 5007 | Evento cuando se cambia la configuración
 1124 | Evento de acceso a carpetas controladas auditada
 1123 | Evento de acceso controlado a carpetas bloqueadas

> [!TIP]
> Puede configurar una suscripción Windows [de reenvío](/windows/win32/wec/setting-up-a-source-initiated-subscription) de eventos para recopilar los registros de forma centralizada. 

## <a name="customize-protected-folders-and-apps"></a>Personalizar aplicaciones y carpetas protegidas

Durante la evaluación, es posible que quieras agregar a la lista de carpetas protegidas o permitir que determinadas aplicaciones modifiquen archivos.

Vea [Proteger carpetas](controlled-folders.md) importantes con acceso controlado a carpetas para configurar la característica con herramientas de administración, como la directiva de grupo, PowerShell y los proveedores de servicios de configuración mdm (CSP).

## <a name="see-also"></a>Ver también

* [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md)
* [Microsoft Defender para punto de conexión](evaluate-mde.md)
* [Usar modo de auditoría](audit-windows-defender.md)
