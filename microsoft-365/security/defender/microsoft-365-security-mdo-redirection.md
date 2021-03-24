---
title: Redirigir cuentas de Microsoft Defender para Office 365 al nuevo centro de seguridad de Microsoft 365
description: Cómo redirigir desde Defender para Office 365 al Centro de seguridad de Microsoft 365.
keywords: Centro de seguridad de Microsoft 365, Introducción al centro de seguridad de Microsoft 365, redirección del centro de seguridad
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072680"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a>Redirigir cuentas de Microsoft Defender para Office 365 al Centro de seguridad de Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Se aplica a:**

- Microsoft 365 Defender
- Defender para Office 365

En este artículo se explica cómo enrutar cuentas al Centro de seguridad de Microsoft 365 habilitando la redirección automática desde el antiguo Centro de seguridad y cumplimiento de Microsoft (protection.office.com o securitycenter.microsoft.com), al Centro de seguridad de Microsoft 365 (security.microsoft.com).

>[!NOTE]
> La funcionalidad de redirección del portal está disponible solo para clientes de Office 365 E5 y Microsoft Defender para office P2

## <a name="what-to-expect"></a>Qué esperar
Una vez habilitada y activa la redirección automática, los usuarios que tengan acceso a las funciones relacionadas con la seguridad en Office 365 Seguridad y cumplimiento (protection.office.com), se enruta automáticamente al Centro de seguridad de Microsoft 365 ( https://security.microsoft.com) .  

Obtenga más información sobre los cambios: [Microsoft Defender para Office 365 en el](microsoft-365-security-center-mdo.md)Centro de seguridad de Microsoft 365 .

Con el redireccionamiento automático activado, los usuarios se enrutarán al Centro de seguridad de Microsoft 365 cuando usen funciones de seguridad en el Centro de seguridad y cumplimiento de Office 365.

Estas incluyen funcionalidades en la sección Administración de amenazas y en el panel e informes de administración de amenazas. Los elementos del Centro de seguridad y cumplimiento de Office 365 que no están relacionados con la seguridad no se redirigen al Centro de seguridad de Microsoft 365.

Los elementos relacionados con el cumplimiento se pueden encontrar en el Centro de cumplimiento de Microsoft 365 y los elementos relacionados con el flujo de correo se pueden encontrar en el Centro de administración de Exchange.

El resto de funcionalidades, ya sean relacionadas con el cumplimiento o las funcionalidades que sirven a ambos, no se ven afectadas por el redireccionamiento. Las alertas de seguridad de Office 365 aparecen en el Centro de seguridad de Microsoft 365 y en el Centro de seguridad y cumplimiento de Office 365, sin redirección.  

### <a name="set-up-portal-redirection"></a>Configurar la redirección del portal
Para iniciar el enrutamiento de cuentas al Centro de seguridad de Microsoft 365 en security.microsoft.com:

1. Asegúrese de que es un administrador global o que tiene permisos de administrador de seguridad en Azure Active Directory.
2. [Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365.
3. Vaya a **Configuración Correo**  >  **& redireccionamiento del** portal de  >  **colaboración.**  
4. Alterna la configuración de redirección automática a **On**.
5. Haga **clic en** Habilitar para aplicar el redireccionamiento automático al portal del centro de seguridad de Microsoft 365.

> [!NOTE]
> Una vez habilitada la redirección, las cuentas en sesiones activas mientras se aplica esta configuración no se expulsarán de su sesión y solo se enrutarán al centro de seguridad de Microsoft 365 después de finalizar la sesión actual y volver a iniciar sesión.

## <a name="can-i-go-back-to-using-the-former-portal"></a>¿Puedo volver a usar el portal anterior?
Si algo no funciona para usted o si hay algo que no se puede completar a través del portal del centro de seguridad de Microsoft 365, queremos escucharlo con la opción de comentarios del portal. Si ha encontrado algún problema con el redireccionamiento, le recomendamos que se ponga en contacto con su compañero de pm directamente a través de la vista previa privada o háganoslo saber a través del formulario Enviar comentarios.

Para volver al portal anterior:

1. [Inicie sesión](https://security.microsoft.com/) en el Centro de seguridad de Microsoft 365 como administrador global o use y tenga una cuenta con permisos de administrador de seguridad en Azure Active Directory.

2. Vaya a **Configuración**  >  **Desdireccionamiento del** Portal  >  **general**  >  **de extremos**.  

3. Alterna la opción Redirección automática a **Desactivado**.

4. Haga **clic en** Deshabilitar & compartir comentarios cuando se le pida.

Esta configuración se puede habilitar de nuevo en cualquier momento.

Una vez deshabilitadas, las cuentas ya no se enrutarán a security.microsoft.com y volverás a tener acceso al antiguo portal: securitycenter.windows.com o securitycenter.microsoft.com.

## <a name="related-information"></a>Información relacionada
- [Vista general del Centro de seguridad de Microsoft 365](overview-security-center.md)
- [Microsoft Defender para endpoint en el Centro de seguridad de Microsoft 365](microsoft-365-security-center-mde.md)
- [Microsoft ofrece SIEM y XDR unificados para modernizar las operaciones de seguridad](https://www.microsoft.com/security/blog/?p=91813) 
- [XDR frente a la infografía siem](https://afrait.com/blog/xdr-versus-siem/) 
- [El nuevo defensor](https://afrait.com/blog/the-new-defender/) 
- [Acerca de Microsoft 365 Defender](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [Portales de seguridad de Microsoft y centros de administración](portals.md)