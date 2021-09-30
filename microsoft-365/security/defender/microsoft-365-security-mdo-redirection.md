---
title: Redirigir cuentas desde el Centro Office 365 seguridad y cumplimiento al nuevo Microsoft 365 Defender
description: Cómo redirigir desde defender para Office 365 a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Introducción a la Microsoft 365 Defender, redirección del centro de seguridad
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: bed6a3bfdbad66a8eb9979aea997d33a060fd134
ms.sourcegitcommit: 4ea16de333421e24b15dd1f164963bc9678653fb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "60010262"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Redirigir cuentas desde el Centro Office 365 seguridad y cumplimiento a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender
- Defender para Office 365

En este artículo se explica cómo enrutar cuentas a Microsoft 365 Defender habilitando la redirección automática desde el antiguo Centro de seguridad y cumplimiento de Office 365 (protection.office.com), a Microsoft 365 Defender (security.microsoft.com).

## <a name="what-to-expect"></a>Qué esperar
Una vez que el redireccionamiento automático está habilitado y activo, los usuarios que tengan acceso a las funciones relacionadas con la seguridad en Office 365 Seguridad y cumplimiento (protection.office.com), se enruta automáticamente a Microsoft 365 Defender ( https://security.microsoft.com) .  

Obtenga más información sobre lo que ha cambiado: [Microsoft Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md).

Con el redireccionamiento automático activado, los usuarios se enrutarán a Microsoft 365 Defender cuando usen funciones de seguridad en el Centro de seguridad y cumplimiento de Office 365 de seguridad.

Estas incluyen funcionalidades en la sección Administración de amenazas, Alertas (Ver alertas y directivas de alertas) y el panel e informes de administración de amenazas. Los elementos del Centro Office 365 seguridad y cumplimiento que no están relacionados con la seguridad no se redirigen a Microsoft 365 Defender.

Los elementos relacionados con el cumplimiento se pueden encontrar en el Centro de cumplimiento de Microsoft 365 y los elementos relacionados con el flujo de correo se pueden encontrar en el centro de administración Exchange correo.

El resto de funcionalidades, ya sean relacionadas con el cumplimiento o las funcionalidades que sirven a ambos, no se ven afectadas por el redireccionamiento.

### <a name="set-up-portal-redirection"></a>Configurar la redirección del portal

Desde principios de octubre de 2021, el redireccionamiento del portal se realiza automáticamente o de forma predeterminada. Sin embargo, si necesita deshabilitarse temporalmente, estos pasos seguirán.

<!--To start routing accounts to Microsoft 365 Defender at security.microsoft.com:

1. Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.
2. [Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.
3. Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.  
4. Toggle the Automatic redirection setting to **On**.
5. Click **Enable** to apply automatic redirection to Microsoft 365 Defender.

> [!NOTE]
> After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.-->

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?
Si algo no funciona para usted o si hay algo que no se puede completar a través de Microsoft 365 Defender, queremos escucharlo con la opción de comentarios del portal. Si ha encontrado algún problema con el redireccionamiento, háganoslo saber.

Para volver al portal anterior:

1. [Inicie sesión](https://security.microsoft.com/) en Microsoft 365 Defender como administrador global o usar y cuenta con permisos de administrador de seguridad en Azure Active Directory.

2. Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**

3. Alterna la opción Redirección automática a **Desactivado**.

4. Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.

Esta configuración se puede habilitar de nuevo en cualquier momento.

## <a name="related-information"></a>Información relacionada
- [Microsoft 365 Defender introducción](overview-security-center.md)
- [Microsoft Defender para endpoint en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR frente a la infografía siem](https://afrait.com/blog/xdr-versus-siem/) 
- [El nuevo defensor](https://afrait.com/blog/the-new-defender/) 
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portales de seguridad de Microsoft y centros de administración](portals.md)
