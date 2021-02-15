---
title: Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: 'Resumen: configure y pruebe el inicio de sesión único de conexión directa de Azure AD para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487611"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365

*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*

Azure AD Seamless Single Sign-On (SSO de conexión directa) inicia sesión automáticamente en los usuarios cuando se encuentran en sus equipos o dispositivos que están conectados a la red de su organización. El SSO de conexión directa de Azure AD proporciona a los usuarios un fácil acceso a las aplicaciones basadas en la nube sin necesidad de componentes locales adicionales.

En este artículo se describe cómo configurar el entorno de prueba de Microsoft 365 para sso de conexión directa de Azure AD.

La configuración del SSO de conexión directa de Azure AD consta de dos fases:
- [Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vaya a La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [sincronización de hash de contraseña para Microsoft 365.](password-hash-sync-m365-ent-test-environment.md) 

La configuración resultante tiene este aspecto:
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de Active Directory Domain Services (AD DS) con el inquilino de Azure AD de su suscripción de Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD

En esta fase, configure Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD y, a continuación, compruebe que funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar Azure AD Connect en APP1

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2. Desde el escritorio de APP1, ejecute Azure AD Connect.

3. En la **página principal,** seleccione **Configurar**.

4. En la **página Tareas adicionales,** seleccione Cambiar **inicio de sesión** de usuario y, a continuación, **seleccione Siguiente**.

5. En la **página Conectarse a Azure AD,** escriba las credenciales de la cuenta de administrador global y, a continuación, seleccione **Siguiente.**

6. En la **página Inicio de sesión del usuario,** seleccione Habilitar inicio de sesión **único** y, a continuación, **seleccione Siguiente.**

7. En la **página Habilitar inicio de sesión único,** seleccione Escribir **credenciales.**

8. En el cuadro de diálogo Seguridad de **Windows,** escriba usuario1 y la contraseña de la cuenta **usuario1,** seleccione Aceptar **y,** a continuación, **seleccione Siguiente**.

9. En la **página Listo para configurar,** seleccione **Configurar**.

10. En la **página Configuración completada,** seleccione **Salir**.

11. En Azure Portal, en el panel izquierdo, seleccione **Azure Active Directory** Azure AD  >  **Connect.** Compruebe que la **característica de inicio de sesión único de conexión** sencilla aparece como **Habilitada.**

A continuación, pruebe la capacidad de iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<*your public domain*> de la cuenta User1.

1. En Internet Explorer en APP1, seleccione el icono de configuración y, a continuación, **seleccione Opciones de Internet.**
 
2. En **Opciones de Internet,** seleccione la **pestaña** Seguridad.

3. Seleccione **Intranet local y,** a continuación, **Sitios.**

4. En **intranet local,** seleccione **Opciones avanzadas.**

5. En **Agregar este sitio web a la zona,** escriba https **<span>://</span>autologon.microsoftazuread-sso.com**, **seleccione Agregar**  >  **cerrar**  >    >  **aceptar.**

6. Cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

7. Cuando se le pida que inicie sesión, especifique <strong>user1@testlab.</strong>\<*your public domain*> y, a continuación, **seleccione Siguiente**. Debería iniciar sesión correctamente como User1 sin que se le pide una contraseña. Esto demuestra que el SSO de inicio de sesión directa de Azure AD está funcionando.

Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global de Azure AD. Por lo tanto, no verá el icono de **administrador** como opción.

Esta es la configuración resultante:

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuración se compone de:

- Una suscripción de prueba o de pago de Microsoft 365 E5 con el dominio DNS testlab.\<*your domain name*> registrado.
- Intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENT1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.
- El SSO de conexión directa de Azure AD está habilitado para que los equipos de la intranet simulada puedan iniciar sesión en los recursos en la nube de Microsoft 365 sin especificar una contraseña de cuenta de usuario.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
