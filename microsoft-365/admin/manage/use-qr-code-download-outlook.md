---
title: Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: high
ms.collection:
- scotvorg
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
description: Obtenga información sobre cómo usar un código QR para autenticar y descargar Outlook Mobile.
ms.openlocfilehash: 0816c88ca302e442999d84da094094c058c80025
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68203209"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usar un código QR para iniciar sesión en las aplicaciones móviles de Outlook

Como administrador de Microsoft 365, puede permitir que los usuarios inicien sesión en Outlook para Android o la aplicación iOS en sus dispositivos móviles sin tener que escribir su nombre de usuario y contraseña. Al digitalizar un código QR, los usuarios pueden autenticarse e iniciar sesión de forma segura en Outlook Mobile.

En Outlook en la Web u otras aplicaciones de escritorio de Outlook, los usuarios pueden ver notificaciones que les informan de que pueden usar Outlook en su dispositivo móvil. El administrador puede administrar estas notificaciones mediante Exchange PowerShell. Si los usuarios deciden enviarse un mensaje de texto SMS para descargar la aplicación en su dispositivo móvil, aparecerá un código QR en su equipo. Podrán digitalizar el código QR para iniciar sesión en Outlook en su teléfono o tableta. Este código QR es un token de corta duración que solo se puede canjear una vez.

La notificación solo se genera si se cumplen las condiciones siguientes:

1. La experiencia de código QR está habilitada para el inquilino (esta experiencia está habilitada de forma predeterminada).

2. El usuario aún no usa Outlook para iOS y Android.

3. El usuario tiene un estado vacío en el panel de lectura (no selecciona la opción de abrir automáticamente el primer correo electrónico).

4. El usuario no descartó la notificación.

> [!NOTE]
> En algunos casos, los usuarios deben volver a autenticarse en su equipo para generar el código QR.

## <a name="use-exchange-powershell"></a>Usar Exchange PowerShell

Esta característica está activada de forma predeterminada. Para deshabilitar esta característica, siga los pasos que se indican a continuación.

1. [Conectarse a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)
2. Con PowerShell, puede deshabilitar las notificaciones que informan a los usuarios sobre las aplicaciones móviles de Outlook. Esto también impide que se muestre el flujo de inicio de sesión del código QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

> [!NOTE]
> Al usar el comando de Exchange PowerShell, los cambios pueden tardar hasta 8 horas en propagarse.

## <a name="related-content"></a>Contenido relacionado

[Configurar las opciones de las versiones estándar o dirigida](release-options-in-office-365.md) (artículo)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) (artículo)
