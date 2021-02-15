---
title: Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Aprenda a usar un código QR para autenticar y descargar Outlook Mobile.
ms.openlocfilehash: 1e5207a2792b557689a306fa1474a2c5fac81ed9
ms.sourcegitcommit: 78f48304f990e969a052fe6536b2e8d6856e1086
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "50242359"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook

> [!IMPORTANT]
> Esta característica solo está disponible para las organizaciones que han activado la versión dirigida en el Centro de administración de Microsoft 365. Para activar la versión dirigida y obtener más información sobre cómo funciona, consulta Configurar las opciones de versión estándar o [dirigida.](release-options-in-office-365.md) Ampliaremos a más organizaciones en las próximas semanas a través de la versión preliminar pública. La versión preliminar pública proporciona acceso anticipado a las características de Microsoft 365.

Como administrador de Microsoft 365, puede permitir que los usuarios inicien sesión en la aplicación Outlook para Android o iOS en sus dispositivos móviles sin tener que escribir su nombre de usuario y contraseña. Mediante el análisis de un código QR, los usuarios pueden autenticarse e iniciar sesión de forma segura en Outlook Mobile.

En Outlook en la Web u otras aplicaciones de escritorio de Outlook, los usuarios pueden ver notificaciones que les informan de que pueden usar Outlook en su dispositivo móvil. El administrador puede administrar estas notificaciones mediante Exchange Powershell. Si los usuarios deciden enviarse un mensaje de texto SMS para descargar la aplicación en su dispositivo móvil, aparecerá un código QR en su equipo. Podrán examinar el código QR para iniciar sesión en Outlook en su teléfono o tableta. Este código QR es un token de corta duración que solo se puede canjear una vez.

> [!NOTE]
> En algunos casos, los usuarios tendrán que volver a autenticarse en su equipo para generar el código QR.

## <a name="use-exchange-powershell"></a>Usar Exchange PowerShell

Esta característica está activada de forma predeterminada. Para deshabilitar esta característica, siga los pasos siguientes.

1. [Conéctese a Exchange PowerShell.](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)
2. Con PowerShell, puede deshabilitar las notificaciones que informan a los usuarios sobre las aplicaciones móviles de Outlook. Esto también impedirá que se muestra el flujo de inicio de sesión del código QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

Temas relacionados

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig?view=exchange-ps)
