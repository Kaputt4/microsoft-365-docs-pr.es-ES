---
title: Restablecimiento de contraseña para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el restablecimiento de contraseña para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871741"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Restablecimiento de contraseña para el entorno de prueba de Microsoft 365

El restablecimiento de contraseña autoservicio de Azure AD (SSPR) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas. 

En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en su entorno de prueba de Microsoft 365 en dos fases:

1.  Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.
2.  Configurar y probar el restablecimiento de contraseña de la cuenta Usuario 2.
    
![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o permanentes de Office 365 E5 y EMS E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de Windows Server AD TESTLAB con el espacio empresarial de Azure AD de sus suscripciones de Office 365 y EMS E5.

## <a name="phase-2-configure-and-test-password-reset"></a>Fase 2: configurar y probar el restablecimiento de contraseña

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
10. En una pestaña independiente del mismo explorador, escriba [https://portal.office.com](https://portal.office.com) y después inicie sesión con el nombre de la cuenta Usuario 2 y la nueva contraseña. Debería ver la página **Inicio de Office**.

Vea el paso [Simplificar el restablecimiento de contraseña](identity-password-reset.md) en la fase Identidad para obtener información y vínculos sobre cómo configurar el restablecimiento de contraseña en un entorno de producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
