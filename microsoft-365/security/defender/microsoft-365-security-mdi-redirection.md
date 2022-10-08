---
title: Redirigir cuentas de Microsoft Defender for Identity a Microsoft 365 Defender
description: Cómo redirigir cuentas y sesiones de Defender for Identity a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Introducción a Microsoft 365 Defender, redirección de Security Center
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security
- tier2
ms.custom: admindeeplinkDEFENDER
ms.topic: article
ms.openlocfilehash: d8c3fd2579798845c4b61222feff333b85401478
ms.sourcegitcommit: 12af9e8e3a6eaa090fda9e98ccb831dff65863a4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2022
ms.locfileid: "68060788"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-identity-to-microsoft-365-defender"></a>Redirigir cuentas de Microsoft Defender for Identity a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En esta guía se explica cómo enrutar las cuentas a Microsoft 365 Defender habilitando el redireccionamiento automático desde el portal de Microsoft Defender for Identity anterior (portal.atp.azure.com) a <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>.

## <a name="what-to-expect"></a>Qué esperar

Una vez habilitada la redirección automática, las cuentas que accedan al portal de Microsoft Defender for Identity anterior en portal.atp.azure.com se enrutarán automáticamente al portal de Microsoft 365 Defender en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">security.microsoft.com</a>.

## <a name="when-does-this-take-effect"></a>¿Cuándo surte efecto?

Una vez habilitada, esta actualización podría surtir efecto casi inmediatamente en algunas cuentas. Pero el redireccionamiento puede tardar más tiempo en propagarse a todas las cuentas de la organización. Las cuentas de sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán a Microsoft 365 Defender después de finalizar la sesión actual y volver a iniciar sesión.  

### <a name="set-up-portal-redirection"></a>Configuración del redireccionamiento del portal

Para iniciar el enrutamiento de cuentas a Microsoft 365 Defender:

1. Asegúrese de que es un administrador global o tiene permisos de administrador de seguridad en Azure Active Directory.

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>.

1. Vaya al **redireccionamiento del Portal** **general** > **de identidades** >  de **configuración** >  o [haga clic aquí](https://security.microsoft.com/preferences2/portal_redirection).

    :::image type="content" source="../../media/portal-redirection.png" alt-text="Redirección del portal."lightbox="../../media/portal-redirection.png":::

1. Cambie el valor de Redirección automática a **Activado**.

>[!IMPORTANT]
>La habilitación de esta configuración no finalizará las sesiones de usuario activas. Las cuentas que están en una sesión activa mientras se aplica esta configuración solo se dirigirán a Microsoft 365 Defender después de finalizar la sesión actual e iniciar sesión de nuevo.

>[!NOTE]
>Debe ser administrador global o tener permisos de administrador de seguridad en Azure Active Directory para habilitar o deshabilitar esta configuración.  

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?

Si algo no funciona para ti o si hay algo que no puedas completar a través de Microsoft 365 Defender, queremos oírlo. Si ha encontrado algún problema con el redireccionamiento, le recomendamos que nos lo informe mediante el formulario Enviar comentarios.

Para volver al portal de Microsoft Defender for Identity anterior:

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> como administrador global o con una cuenta y con permisos de administrador de seguridad en Azure Active Directory.

2. Vaya al **redireccionamiento del Portal** **de** > **identidades** >  de **configuración** >  o [abra la página aquí](https://security.microsoft.com/preferences2/portal_redirection).  

3. Cambie la configuración de redireccionamiento automático a **Desactivado**.

Esta configuración se puede habilitar de nuevo en cualquier momento.

Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com.

## <a name="related-information"></a>Información relacionada

- [introducción a Microsoft 365 Defender](microsoft-365-defender.md)
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender)
- [Portales de seguridad y centros de administración de Microsoft](portals.md)
