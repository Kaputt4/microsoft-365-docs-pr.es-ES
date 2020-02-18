---
title: Restablecimiento de contraseña para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el restablecimiento de contraseña para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066146"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Restablecimiento de contraseña para el entorno de prueba de Microsoft 365

*Esta guía del laboratorio de pruebas solo se puede usar para entornos de prueba de Microsoft 365 Enterprise.*

El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas. 

En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en su entorno de prueba de Microsoft 365 en tres fases:

1.  Crear el entorno de pruebas de Microsoft 365 Enterprise.
2.  Habilitar escritura diferida de contraseñas.
3.  Configure y pruebe el restablecimiento de contraseña para la cuenta de usuario 3.
    
![Guías del laboratorio de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 u Office 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: habilitar escritura diferida de contraseñas

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: configurar y probar el restablecimiento de contraseña

En esta fase, configurará el restablecimiento de contraseña del inquilino de Azure AD mediante la pertenencia del grupo y después comprobará que funciona correctamente.

En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.

1. Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.
2. En Azure Portal, haga clic en **Azure Active Directory > Grupos > Nuevo grupo**.
3. Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**. 
4. Haga clic en **Miembros**, busque y seleccione **usuario 3**, después haga clic en **Seleccionar**y, a continuación, haga clic en **Crear**.
5. Cierre el panel **Grupos**.
6. En el panel de navegación izquierdo de Azure Active Directory, haga clic en **Restablecer contraseña**.
7. En el panel **Propiedades - Restablecer contraseña**, debajo de la opción **Habilitar autoservicio de restablecimiento de contraseña**, elija **Seleccionado**.
8. Haga clic en **Seleccionar grupo**, seleccione el grupo **PWReset** y después haga clic en **Seleccionar > Guardar**.
9. Cierre la instancia de explorador privada.

Después, pruebe el restablecimiento de contraseña de la cuenta Usuario 3.

1. Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Inicie sesión con las credenciales de la cuenta Usuario 3.
3. En **más información necesaria**, haga clic en **siguiente**. 
5. En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.
7. Cuando haya comprobados ambos, haga clic en **Parece que está bien** y cierre la instancia privada del explorador.
8. Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/sspr](https://aka.ms/sspr).
9. Escriba el nombre de la cuenta de usuario 3, escriba los caracteres de la CAPTCHA y después haga clic en **Siguiente**.
10. Para el **paso de verificación 1**, haga clic en **Enviar un correo electrónico a mi correo electrónico alternativo** y después en **Correo electrónico**. Cuando reciba el correo electrónico, escriba el código de comprobación y luego haga clic en **Siguiente**.
11. En **Volver a la cuenta**, escriba una nueva contraseña para la cuenta de usuario 3 y después haga clic en **Finalizar**. Anote la contraseña cambiada de la cuenta de usuario 3 y almacénela en un lugar seguro.
12. En una pestaña independiente del mismo explorador, vaya a [https://portal.office.com](https://portal.office.com) y después inicie sesión con el nombre de la cuenta Usuario 3 y la nueva contraseña. Debe ver la página **principal de Microsoft Office**.

Vea el paso [Simplificar el restablecimiento de contraseña](identity-secure-your-passwords.md#identity-pw-reset) en la fase Identidad para obtener información y vínculos sobre cómo configurar el restablecimiento de contraseña en un entorno de producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
