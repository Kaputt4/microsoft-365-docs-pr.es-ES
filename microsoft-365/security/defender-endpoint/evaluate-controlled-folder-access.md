---
title: Evaluar acceso controlado a carpetas
description: Vea cómo el acceso controlado a carpetas puede ayudar a proteger los archivos de que las aplicaciones malintencionadas cambien.
keywords: Protección contra vulnerabilidades de seguridad, windows 10, windows 11, windows defender, ransomware, protect, evaluate, test, demo, try
ms.service: microsoft-365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
audience: ITPro
ms.topic: conceptual
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.subservice: mde
ms.collection:
- m365-security
- tier2
search.appverid: met150
ms.openlocfilehash: 4a6d0d1be1e26023b93164861a6d3533fda94220
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68173839"
---
# <a name="evaluate-controlled-folder-access"></a>Evaluar acceso controlado a carpetas

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)


[El acceso controlado a carpetas](controlled-folders.md) es una característica que ayuda a proteger los documentos y archivos frente a modificaciones por parte de aplicaciones sospechosas o malintencionadas. El acceso controlado a carpetas se admite en clientes de Windows Server 2019, Windows Server 2022, Windows 10 y Windows 11.

Es especialmente útil para ayudar a proteger contra [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) que intenta cifrar sus archivos y mantenerlos como rehenes.

Este artículo le ayuda a evaluar el acceso controlado a carpetas. Explica cómo habilitar el modo de auditoría para que pueda probar la característica directamente en su organización.

## <a name="use-audit-mode-to-measure-impact"></a>Uso del modo de auditoría para medir el impacto

Habilite el acceso controlado a carpetas en modo de auditoría para ver un registro de lo que *habría* ocurrido si estuviera totalmente habilitado. Pruebe cómo funcionará la característica en su organización para asegurarse de que no afecta a las aplicaciones de línea de negocio. También puede hacerse una idea de cuántos intentos de modificación de archivos sospechosos suelen producirse durante un período de tiempo determinado.

Para habilitar el modo de auditoría, use el siguiente cmdlet de PowerShell:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Si desea auditar completamente cómo funcionará el acceso controlado a carpetas en su organización, deberá usar una herramienta de administración para implementar esta configuración en los dispositivos de las redes.
También puede usar directiva de grupo, Intune, administración de dispositivos móviles (MDM) o Microsoft Endpoint Manager para configurar e implementar la configuración, como se describe en el tema principal de [acceso controlado a carpetas](controlled-folders.md).

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Revisar eventos de acceso controlado a carpetas en Windows Visor de eventos

Los siguientes eventos de acceso controlado a carpetas aparecen en Windows Visor de eventos en la carpeta Microsoft/Windows/Windows Defender/Operational.

Id. de evento | Descripción
-|-
 5007 | Evento cuando se cambia la configuración
 1124 | Evento de acceso a carpetas controladas auditadas
 1123 | Evento de acceso a carpetas controladas bloqueadas

> [!TIP]
> Puede configurar una [suscripción de reenvío de eventos de Windows](/windows/win32/wec/setting-up-a-source-initiated-subscription) para recopilar los registros de forma centralizada. 

## <a name="customize-protected-folders-and-apps"></a>Personalización de carpetas y aplicaciones protegidas

Durante la evaluación, es posible que desee agregar a la lista de carpetas protegidas o permitir que ciertas aplicaciones modifiquen archivos.

Consulte [Protección de carpetas importantes con acceso controlado a carpetas](controlled-folders.md) para configurar la característica con herramientas de administración, incluidos directiva de grupo, PowerShell y proveedores de servicios de configuración de MDM (CSP).

## <a name="see-also"></a>Vea también

* [Proteger carpetas importantes con acceso controlado a carpetas](controlled-folders.md)
* [Microsoft Defender para punto de conexión](evaluate-mde.md)
* [Usar modo de auditoría](audit-windows-defender.md)
