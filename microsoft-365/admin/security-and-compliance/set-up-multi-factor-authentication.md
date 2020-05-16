---
title: Configuración de autenticación multifactor para usuarios
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: Obtenga información sobre cómo usar los valores predeterminados de seguridad para configurar la autenticación multifactor para los usuarios.
monikerRange: o365-worldwide
ms.openlocfilehash: c4ea6037b34d29f2d1e05e248e03e49ee6b06f56
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262380"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor
  
> [!IMPORTANT]
> Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la autenticación multifactor (MFA), los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.

Todas las nuevas suscripciones de Microsoft 365 tendrán habilitada la [seguridad predeterminada](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) . Esto significa que todos los usuarios tendrán que configurar la autenticación multifactor (MFA) e instalar la aplicación Microsoft Authenticator en su dispositivo móvil. Para obtener más información, consulte [configurar la MFA para una cuenta de Microsoft 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).

Los nueve roles de administrador que se indican a continuación serán necesarios para realizar una autenticación adicional cada vez que inicien sesión:

- Administrador global
- Administrador de SharePoint
- Administrador de Exchange
- Administrador de acceso condicional
- Administrador de seguridad
- Administrador de contraseñas o administrador del departamento de soporte técnico
- Administrador de facturación
- Administrador de usuarios
- Administrador de autenticación

Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario.

> [!NOTE]
> Debe ser un administrador global para configurar o modificar la MFA <br><br>
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

Si ha configurado previamente MFA con directivas de línea base, debe desactivarlas [para activar los valores predeterminados de seguridad](#move-from-baseline-policies-to-security-defaults). Sin embargo, si tiene Microsoft 365 Business o su suscripción incluye [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), también puede configurar directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) . Para usar directivas de acceso condicional, debe asegurarse de que los valores predeterminados de seguridad están deshabilitados y la [autenticación moderna](#enable-modern-authentication-for-your-organization) está habilitada.

> [!TIP]
> Para explicar a los usuarios cómo configurar la aplicación Microsoft Authenticator, vea [usar Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411).

## <a name="manage-security-defaults"></a>Administrar los valores predeterminados de seguridad

1. Inicie sesión en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822) con credenciales de administrador global.
2. Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
3. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
4. Elija **sí** para habilitar los valores predeterminados de seguridad y **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Cambie de las directivas de línea base a los valores predeterminados de seguridad.

1. Vaya a la [Página acceso condicional-directivas](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies).
2. Elija cada directiva de línea base que esté **activada** y establezca la **Directiva de habilitación** en **desactivada**.
3. Vaya a la [Página de propiedades de Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
4. En la parte inferior de la página, **Elija administrar los valores predeterminados de seguridad**y, en el panel **Habilitar valores** predeterminados de seguridad, establezca la alternancia **Habilitar valores predeterminados de seguridad** en **sí**y, después, elija **Guardar**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Habilitar la autenticación moderna para la organización

Todas las aplicaciones de cliente de Office 2016 admiten la MFA mediante el uso de la Biblioteca de autenticación de Active Directory (ADAL). Esto significa que las contraseñas de aplicaciones no son necesarias para los clientes de Office 2016. Consulte [este artículo](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings#app-passwords) para obtener más información.

Sin embargo, debe asegurarse de que la suscripción a Microsoft 365 está habilitada para ADAL o para la autenticación moderna.

1. Para habilitar la autenticación moderna, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **configuración** de la \> **organización** y, a continuación, en la pestaña **servicios** , elija **autenticación moderna** en la lista.

2. Active la casilla **Habilitar autenticación moderna (recomendada)** en el panel de **autenticación moderna** y, a continuación, elija **Guardar cambios**. 

    ![En el Panel de autenticación moderna la casilla de verificación está marcada en habilitar](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> A partir de agosto de 2017, todas las suscripciones de Microsoft 365 nuevas que incluyen Skype empresarial online y Exchange Online tienen habilitada de forma predeterminada la autenticación moderna. Para comprobar el estado de su autenticación moderna para Skype Empresarial online, puede utilizar el PowerShell de Skype Empresarial online con credenciales de Administrador Global. Ejecute Get-CsOAuthConfiguration para comprobar la salida de -ClientADALAuthOverride. Si -ClientADALAuthOverride está en la opción "Permitir", significa que la autenticación moderna está activada.
Para comprobar el estado de su MA para Exchange Online, visite [habilite la autenticación moderna en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Artículos relacionados

[Las diez formas principales de proteger los planes de Microsoft 365 para empresas](secure-your-business-data.md)

[Habilitar la autenticación moderna para Office 2013 en dispositivos Windows](enable-modern-authentication.md)
