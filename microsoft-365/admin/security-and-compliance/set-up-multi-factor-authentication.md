---
title: Configurar la autenticación multifactor para los usuarios de Office 365
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
description: Aprenda a usar valores predeterminados para configurar la autenticación multifactor para los usuarios de Office 365.
monikerRange: o365-worldwide
ms.openlocfilehash: 5f468f040ca88ab4ab2bc198d0d7550bf2e7f4af
ms.sourcegitcommit: 8a88b7526e6a3a907f33a8567e0d25b74fe60d80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "43204027"
---
# <a name="set-up-multi-factor-authentication"></a>Configurar la autenticación multifactor
  
> [!IMPORTANT]
> Si compró la suscripción o la versión de prueba después del 21 de octubre de 2019 y se le solicita inesperadamente la autenticación multifactor (MFA), los [valores predeterminados de seguridad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) se han habilitado automáticamente para su suscripción.

Todas las nuevas suscripciones de Office 365 Empresa o Microsoft 365 Empresa tendrán activados automáticamente los valores predeterminados de seguridad. Esto significa que todos los usuarios tendrán que configurar MFA e instalar la aplicación Microsoft Authenticator en su dispositivo móvil. Para obtener más información, vea [Configurar la verificación en dos pasos de Office 365](https://support.office.com/article/ace1d096-61e5-449b-a875-58eb3d74de14).  

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

Se pedirá a todos los demás usuarios una autenticación adicional cuando sea necesario. Para obtener más información, vea [¿Qué son los valores predeterminados de seguridad?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

> [!NOTE]
> Debe ser un administrador global de Office 365 para configurar o modificar la MFA. <br><br>
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

Si ha configurado previamente MFA con directivas de línea base, [debe desactivarlas y activar los valores predeterminados de seguridad](#move-from-baseline-policies-to-security-defaults). Sin embargo, si tiene Microsoft 365 Business o su suscripción incluye [Azure Active Directory Premium P1 o Azure Active Directory Premium P2](https://azure.microsoft.com/pricing/details/active-directory/), también puede configurar directivas de [acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) . Para usar directivas de acceso condicional, debe asegurarse de que la [autenticación moderna](#enable-modern-authentication-for-your-organization) está habilitada.

> [!TIP]
> Para explicar a los usuarios cómo configurar la aplicación Authenticator, visite [Usar Microsoft Authenticator con Office 365](https://support.office.com/article/use-microsoft-authenticator-with-office-365-1412611f-ad8d-43ab-807c-7965e5155411?ui=en-US&rs=en-US&ad=US#ID0EAADAAA=_Step_1).

## <a name="manage-security-defaults"></a>Administrar los valores predeterminados de seguridad

1. Inicie sesión en el [Centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822) con sus credenciales de administrador global.
2. Vaya a [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).

3. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad**.
4. Elija **sí** para habilitar los valores predeterminados de seguridad o **no** para deshabilitar los valores predeterminados de seguridad y, después, elija **Guardar**.

## <a name="move-from-baseline-policies-to-security-defaults"></a>Cambie de las directivas de línea base a los valores predeterminados de seguridad.

1. En el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **Mostrar todo**y, a continuación, **Azure Active** Directory en **centros de administración**.

2. En el **centro de administración de Azure Active** Directory elija **Azure Active Directory** > **Security**.

3. En la **seguridad | **Página de introducción, elija **acceso condicional**. 

4. En la página **Directivas de acceso condicional de Azure Portal:**, elija cada directiva de línea base que esté **Activada** y establézcala como **Desactivada**.
5. Vaya a la página [Propiedades en Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).
6. En la parte inferior de la página, elija **Administrar los valores predeterminados de seguridad** y en el panel **Habilitar valores predeterminados de seguridad**, establezca **Habilitar valores predeterminados de seguridad** como **Sí**. 

## <a name="enable-modern-authentication-for-your-organization"></a>Habilitar la autenticación moderna para la organización

Todas las aplicaciones de cliente de Office 2016 admiten la MFA mediante el uso de la Biblioteca de autenticación de Active Directory (ADAL). Esto significa que las contraseñas de aplicaciones no son necesarias para los clientes de Office 2016. Sin embargo, debe asegurarse de que su suscripción a Office 365 está habilitada para ADAL, o autenticación moderna.

1. Para habilitar la autenticación moderna, en el [centro de administración](https://go.microsoft.com/fwlink/p/?linkid=834822), seleccione **Configuración** \>**Configuración **y después, en la pestaña **Servicios** elija **Autenticación moderna** en la lista.

2. Marque la casilla **habilitar autenticación moderna** en el panel de **autenticación moderna**. 

    ![En el Panel de autenticación moderna la casilla de verificación está marcada en habilitar](../../media/enablemodernauth.png)
    
> [!IMPORTANT]
> A partir de agosto de 2017, todos los nuevos inquilinos de Office 365 que incluyen Skype Empresarial online y Exchange online tienen la autenticación moderna habilitada de manera predeterminada. Para comprobar el estado de su autenticación moderna para Skype Empresarial online, puede utilizar el PowerShell de Skype Empresarial online con credenciales de Administrador Global. Ejecute Get-CsOAuthConfiguration para comprobar la salida de -ClientADALAuthOverride. Si -ClientADALAuthOverride está en la opción "Permitir", significa que la autenticación moderna está activada.
Para comprobar el estado de su MA para Exchange Online, visite [habilite la autenticación moderna en Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online).

## <a name="related-articles"></a>Artículos relacionados

[Las 10 mejores formas de proteger los planes de Office 365 y Microsoft 365 Empresa](secure-your-business-data.md)

[Habilitar la autenticación moderna para Office 2013 en dispositivos Windows](enable-modern-authentication.md)
