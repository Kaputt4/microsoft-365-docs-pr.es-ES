---
title: Restablecimiento de contraseña para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el restablecimiento de contraseña para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 2aa2a216216895e180f9dc8af37bd4285b17e8cd
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68195795"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Restablecimiento de contraseña para el entorno de prueba de Microsoft 365

*Esta guía de laboratorio de pruebas solo se puede usar para Microsoft 365 para entornos de prueba empresariales.*

El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas.

En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en el entorno de prueba de Microsoft 365.

La configuración de SSPR implica tres fases:
- [Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: habilitar escritura diferida de contraseñas](#phase-2-enable-password-writeback)
- [Fase 3: configurar y probar el restablecimiento de contraseña](#phase-3-configure-and-test-password-reset)
    
![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para enterprise Test Lab Guide Stack (Pila de guía del laboratorio de pruebas empresariales).](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

En primer lugar, siga las instrucciones de [sincronización de hash de contraseña](password-hash-sync-m365-ent-test-environment.md). 

La configuración resultante tiene este aspecto:
  
![La empresa simulada con el entorno de prueba de sincronización de hash de contraseña.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: habilitar escritura diferida de contraseñas

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: configurar y probar el restablecimiento de contraseña

En esta fase, configure el restablecimiento de contraseña en el inquilino de Azure AD mediante la pertenencia a grupos y, a continuación, compruebe que funciona.

En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.

1. Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.
2. En el Azure Portal, seleccione **Grupos** >  **de Azure Active Directory** > **Nuevo grupo**.
3. Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**.
4. Seleccione **Miembros**, busque y seleccione **Usuario 3**, **seleccione Seleccionary**, a continuación, seleccione **Crear**.
5. Cierre el panel **Grupos**.
6. En el panel de Azure Active Directory, seleccione **Restablecimiento de contraseña** en el panel de navegación izquierdo.
7. En el panel **Propiedades - Restablecer contraseña**, debajo de la opción **Habilitar autoservicio de restablecimiento de contraseña**, elija **Seleccionado**.
8. Seleccione **Seleccionar grupo**, seleccione el grupo **PWReset** y seleccione **Seleccionar** > **guardar**.
9. Cierre la instancia de explorador privada.

A continuación, pruebe el restablecimiento de contraseña para la cuenta de usuario 3.

1. Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Inicie sesión con las credenciales de la cuenta Usuario 3.
1. En **Más información necesaria**, seleccione **Siguiente**. 
1. En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.
1. Una vez comprobados ambos, seleccione **Looks good (Aspecto correcto**) y cierre la instancia privada del explorador.
1. En una nueva instancia del explorador privado, vaya a [https://aka.ms/sspr](https://aka.ms/sspr).
1. Escriba el nombre de la cuenta de usuario 3, escriba los caracteres de CAPTCHA y, a continuación, seleccione **Siguiente**.
1. En **el paso 1 de verificación**, seleccione **Email mi correo electrónico alternativo** y, a continuación, seleccione **Email**. Cuando reciba el correo electrónico, escriba el código de verificación y, a continuación, seleccione **Siguiente**.
1. En **Volver a la cuenta**, escriba una nueva contraseña para la cuenta de usuario 3 y, a continuación, seleccione **Finalizar**. Anote la contraseña cambiada de la cuenta de usuario 3 y almacénela en un lugar seguro.
1. En una pestaña independiente del mismo explorador, vaya a [https://admin.microsoft.com](https://admin.microsoft.com) y después inicie sesión con el nombre de la cuenta Usuario 3 y la nueva contraseña. Debe ver la página **principal de Microsoft Office**.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)