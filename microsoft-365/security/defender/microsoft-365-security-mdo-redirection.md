---
title: Redirigir cuentas desde el Centro Office 365 seguridad y cumplimiento al nuevo Microsoft 365 Defender
description: Cómo redirigir desde defender para Office 365 a Microsoft 365 Defender.
keywords: Microsoft 365 Defender, Introducción a Microsoft 365 Defender, redirección del centro de seguridad
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842530"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a>Redirigir cuentas desde el Centro Office 365 seguridad y cumplimiento a Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender
- Defender para Office 365

En este artículo se explica cómo enrutar cuentas a Microsoft 365 Defender habilitando la redirección automática desde el antiguo Centro de seguridad y cumplimiento de Office 365 (protection.office.com), a Microsoft 365 Defender (security.microsoft.com).

## <a name="what-to-expect"></a>Qué esperar
Una vez habilitada y activa la redirección automática, los usuarios que tengan acceso a las funciones relacionadas con la seguridad en Office 365 Seguridad y cumplimiento (protection.office.com), se enruta automáticamente a Microsoft 365 Defender ( https://security.microsoft.com) .  

Obtenga más información sobre lo que ha cambiado: [Microsoft Defender para Office 365 en Microsoft 365 Defender](microsoft-365-security-center-mdo.md).

Con el redireccionamiento automático activado, los usuarios se enrutarán a Microsoft 365 Defender cuando usen funciones de seguridad en el Centro de seguridad y cumplimiento Office 365 seguridad.

Estas incluyen funcionalidades en la sección Administración de amenazas y en el panel e informes de administración de amenazas. Los elementos del Office 365 seguridad y cumplimiento que no están relacionados con la seguridad no se redirigen a Microsoft 365 Defender.

Los elementos relacionados con el cumplimiento se pueden encontrar en el centro de cumplimiento Microsoft 365 y los elementos relacionados con el flujo de correo se pueden encontrar en el centro de administración Exchange correo.

El resto de funcionalidades, ya sean relacionadas con el cumplimiento o las funcionalidades que sirven a ambos, no se ven afectadas por el redireccionamiento. Office 365 alertas de seguridad aparecen tanto en Microsoft 365 Defender como en el Centro de seguridad y cumplimiento de Office 365, sin redirección.  

### <a name="set-up-portal-redirection"></a>Configurar la redirección del portal
Para empezar a enrutar cuentas a Microsoft 365 Defender en security.microsoft.com:

1. Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory.
2. [Inicie sesión](https://security.microsoft.com/) en Microsoft 365 Defender.
3. Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**  
4. Alterna la configuración de redirección automática a **On**.
5. Haga **clic en** Habilitar para aplicar la redirección automática a Microsoft 365 Defender.

> [!NOTE]
> Una vez habilitada la redirección, las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán a Microsoft 365 Defender después de finalizar la sesión actual y volver a iniciar sesión.

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?
Si algo no funciona para ti o si hay algo que no puedes completar a través de Microsoft 365 Defender, queremos escucharlo con la opción de comentarios del portal. Si ha encontrado algún problema con el redireccionamiento, háganoslo saber.

Para volver al portal anterior:

1. [Inicie sesión](https://security.microsoft.com/) en Microsoft 365 Defender como administrador global o usar y cuenta con permisos de administrador de seguridad en Azure Active Directory.

2. Desplácese hasta **Configuración**  >  **correo & redireccionamiento del** portal de  >  **colaboración.**   

3. Alterna la opción Redirección automática a **Desactivado**.

4. Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.

Esta configuración se puede habilitar de nuevo en cualquier momento.

Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al portal anterior securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Información relacionada
- [Microsoft 365 Introducción al defensor](overview-security-center.md)
- [Microsoft Defender para endpoint en Microsoft 365 Defender](microsoft-365-security-center-mde.md)
- [Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR frente a la infografía siem](https://afrait.com/blog/xdr-versus-siem/) 
- [El nuevo defensor](https://afrait.com/blog/the-new-defender/) 
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portales de seguridad de Microsoft y centros de administración](portals.md)
