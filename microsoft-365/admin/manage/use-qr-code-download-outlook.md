---
title: Usar un código QR para iniciar sesión en las aplicaciones Outlook móviles
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
description: Aprende a usar un código QR para autenticar y descargar Outlook móvil.
ms.openlocfilehash: 2c1853a6ea1dd1a5d2ad30b975d1dbd23b942040
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636003"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a>Usar un código QR para iniciar sesión en las aplicaciones Outlook móviles

> [!IMPORTANT]
> Esta característica solo está disponible para las organizaciones que han activado La versión dirigida en el centro Microsoft 365 administración. Para activar la versión dirigida y obtener más información sobre cómo funciona, vea Configurar las opciones de versión estándar o [dirigida.](release-options-in-office-365.md) Nos expandiremos a más organizaciones en las próximas semanas a través de la versión preliminar pública. La vista previa pública proporciona acceso anticipado a Microsoft 365 características.

Como administrador de Microsoft 365, puedes permitir que los usuarios inicien sesión en Outlook para la aplicación de Android o iOS en sus dispositivos móviles sin tener que escribir su nombre de usuario y contraseña. Al examinar un código QR, los usuarios pueden autenticarse e iniciar sesión de forma segura en Outlook móvil.

En Outlook web u otras aplicaciones de escritorio Outlook escritorio, es posible que los usuarios vean notificaciones que les informen de que pueden usar Outlook en su dispositivo móvil. El administrador puede administrar estas notificaciones mediante Exchange Powershell. Si los usuarios deciden enviarse un SMS de texto para descargar la aplicación en su dispositivo móvil, aparecerá un código QR en su equipo. Podrán examinar el código QR para iniciar sesión en Outlook en su teléfono o tableta. Este código QR es un token de corta duración que solo se puede canjear una vez.

> [!NOTE]
> En algunos casos, los usuarios deben volver a autenticarse en su equipo para generar el código QR.

## <a name="use-exchange-powershell"></a>Usar Exchange PowerShell

Esta característica está activada de forma predeterminada. Para deshabilitar esta característica, siga los pasos siguientes.

1. [Conectar a Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).
2. Con PowerShell, puede deshabilitar las notificaciones que informan a los usuarios sobre el Outlook aplicaciones móviles. Esto también impide que se muestra el flujo de inicio de sesión de código QR.

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

## <a name="related-content"></a>Contenido relacionado

[Configurar las opciones de versión estándar o dirigida](release-options-in-office-365.md) (artículo)\
[Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig?view=exchange-ps) (artículo)