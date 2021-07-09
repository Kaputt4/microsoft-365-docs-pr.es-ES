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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure y pruebe el restablecimiento de contraseña para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 13169824866e91c1a09d412a875d2f4ce4391fa8
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339387"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Restablecimiento de contraseña para el entorno de prueba de Microsoft 365

*Esta Guía del laboratorio de pruebas solo se puede usar Microsoft 365 entornos de prueba empresariales.*

El restablecimiento de contraseña de autoservicio (SSPR) de Azure Active Directory (Azure AD) permite a los usuarios restablecer o desbloquear sus contraseñas o cuentas.

En este artículo se describe cómo configurar y probar los restablecimientos de contraseña en el Microsoft 365 de prueba.

La configuración de SSPR implica tres fases:
- [Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: habilitar escritura diferida de contraseñas](#phase-2-enable-password-writeback)
- [Fase 3: configurar y probar el restablecimiento de contraseña](#phase-3-configure-and-test-password-reset)
    
![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener una asignación visual a todos los artículos de la pila Microsoft 365 guía del laboratorio de pruebas de empresa, vaya a Microsoft 365 enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

En primer lugar, siga las instrucciones de sincronización [de hash de contraseña.](password-hash-sync-m365-ent-test-environment.md) 

La configuración resultante tiene este aspecto:
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Una intranet de organización simplificada conectada a Internet, formada por las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB de Active Directory Domain Services (AD DS) con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: habilitar escritura diferida de contraseñas

Siga las instrucciones en la [Guía de laboratorio de pruebas, fase 2 de la operación de escritura diferida de contraseñas](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Debe tener la escritura diferida de contraseñas habilitada para utilizar el restablecimiento de contraseña.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: configurar y probar el restablecimiento de contraseña

En esta fase, configure el restablecimiento de contraseña en el inquilino de Azure AD a través de la pertenencia a grupos y, a continuación, compruebe que funciona.

En primer lugar, habilite el restablecimiento de contraseña de cuentas en un determinado grupo de Azure AD.

1. Desde una instancia privada del explorador, abra [https://portal.azure.com](https://portal.azure.com) y después inicie sesión con las credenciales de la cuenta de administrador global.
2. En Azure Portal, seleccione **Azure Active Directory**  >  **grupos**  >  **Nuevo grupo**.
3. Configure **Tipo de grupo** como **Seguridad**, **Nombre del grupo** como **PWReset** y **Tipo de pertenencia** como **Asignado**.
4. Seleccione **Miembros**, busque y seleccione **Usuario 3**, **Seleccione Seleccionar** y, a continuación, seleccione **Crear**.
5. Cierre el panel **Grupos**.
6. En el Azure Active Directory, seleccione **Restablecimiento de contraseña** en la navegación izquierda.
7. En el panel **Propiedades - Restablecer contraseña**, debajo de la opción **Habilitar autoservicio de restablecimiento de contraseña**, elija **Seleccionado**.
8. Seleccione **Seleccionar grupo,** seleccione el **grupo PWReset** y, a continuación, **seleccione Seleccionar**  >  **Guardar**.
9. Cierre la instancia de explorador privada.

Después, pruebe el restablecimiento de contraseña para la cuenta de usuario 3.

1. Abra una nueva instancia de explorador privada y vaya a [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Inicie sesión con las credenciales de la cuenta Usuario 3.
1. En **Más información necesaria,** seleccione **Siguiente**. 
1. En **No perder el acceso a su cuenta**, configure el teléfono de autenticación con su número de teléfono y el correo electrónico de autenticación con su cuenta de correo electrónico laboral o personal.
1. Después de comprobar ambos, seleccione **Se ve bien** y, a continuación, cierre la instancia privada del explorador.
1. En una nueva instancia del explorador privado, vaya a [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Escriba el nombre de cuenta usuario 3, escriba los caracteres del CAPTCHA y, a continuación, **seleccione Siguiente**.
1. Para **el paso de comprobación 1**, seleccione Enviar un correo electrónico alternativo **y,** a continuación, **seleccione Correo electrónico**. Cuando reciba el correo electrónico, escriba el código de verificación y, a continuación, **seleccione Siguiente**.
1. En **Volver a la cuenta,** escriba una nueva contraseña para la cuenta de usuario 3 y, a continuación, seleccione **Finalizar**. Anote la contraseña cambiada de la cuenta de usuario 3 y almacénela en un lugar seguro.
1. En una pestaña independiente del mismo explorador, vaya a [https://admin.microsoft.com](https://admin.microsoft.com) y después inicie sesión con el nombre de la cuenta Usuario 3 y la nueva contraseña. Debe ver la página **principal de Microsoft Office**.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)