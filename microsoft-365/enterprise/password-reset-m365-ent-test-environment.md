---
title: Restablecimiento de contraseña para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
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
ms.openlocfilehash: 30ce8517d1b0eb8967bd7cb26abba780d81eb8b0
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353163"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Restablecimiento de contraseña para el entorno de prueba de Microsoft 365

El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas. 

En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en su entorno de prueba de Microsoft 365 en tres fases:

1.  Crear el entorno de pruebas de Microsoft 365 Enterprise.
2.  Habilitar escritura diferida de contraseñas.
3.  Configurar y probar el restablecimiento de contraseña de la cuenta Usuario 2.
    
![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Office 365 E5 y EMS E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Office 365 y E5 EMS.


## <a name="phase-2-enable-password-writeback"></a>Fase 2: habilitar escritura diferida de contraseñas

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: configurar y probar el restablecimiento de contraseña

En esta fase, configurará el restablecimiento de contraseña del inquilino de Azure AD mediante la pertenencia del grupo y después comprobará que funciona correctamente.

En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.

1. Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.
2. En Azure Portal, haga clic en **Azure Active Directory > Grupos > Nuevo grupo**.
3. Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**. Haga clic en **Crear**.
5. Haga clic en el grupo **PWReset** en la lista y después haga clic en **Miembros**.
6. Haga clic en **Agregar miembros**, después en **Usuario 2** y elija **Seleccionar**. Cierre las páginas **PWReset** y **Grupo**.
7. En la página de Azure Active Directory, haga clic en **Restablecimiento de contraseña**.
8. En la página **Propiedades**, en la opción **Restablecimiento de contraseña autoservicio habilitado**, elija **Seleccionado**.
9. En **Seleccionar grupo**, escoja **PWReset** y después haga clic en **Guardar**.
10. Cierre la instancia de explorador privada.

Después, pruebe el restablecimiento de contraseña de la cuenta Usuario 2.

1. Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Inicie sesión con las credenciales de la cuenta Usuario 2.
3. En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.
4. Cuando haya comprobados ambos, haga clic en **Parece que está bien** y cierre la instancia privada del explorador.
5. Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/sspr](https://aka.ms/sspr).
6. Inicie sesión con las credenciales de la cuenta Usuario 2, escriba los caracteres de la CAPTCHA y después haga clic en **Siguiente**.
8. Para el **paso de verificación 1**, haga clic en **Enviar un correo electrónico a mi correo electrónico alternativo** y después en **Correo electrónico**. Cuando reciba el correo electrónico, escriba el código de comprobación y luego haga clic en **Siguiente**.
9. En **Volver a su cuenta**, escriba una nueva contraseña para la cuenta Usuario 2 y después haga clic en **Finalizar**. Anote la contraseña cambiada de la cuenta Usuario 2 y guárdela en una ubicación segura.
10. En una pestaña independiente del mismo explorador, escriba [https://portal.office.com](https://portal.office.com) y después inicie sesión con el nombre de la cuenta Usuario 2 y la nueva contraseña. Debe ver la página **principal de Microsoft Office**.

Vea el paso [Simplificar el restablecimiento de contraseña](identity-password-reset.md#identity-pw-reset) en la fase Identidad para obtener información y vínculos sobre cómo configurar el restablecimiento de contraseña en un entorno de producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
