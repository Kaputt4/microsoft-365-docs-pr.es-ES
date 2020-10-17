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

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

La Sign-On única transparente (SSO sin problemas) de Azure AD inicia sesión de forma automática en los usuarios cuando están en sus equipos o dispositivos que están conectados a la red de su organización. SSO transparente de Azure AD proporciona a los usuarios acceso sencillo a las aplicaciones basadas en la nube sin necesidad de componentes locales adicionales.

En este artículo se describe cómo configurar el entorno de prueba de Microsoft 365 para el SSO sin problemas de Azure AD.

La configuración de un SSO sin problemas de Azure AD implica dos fases:
- [Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [sincronización de hash de contraseña para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

La configuración resultante tiene el siguiente aspecto:
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de:
  
- Una suscripción de prueba o de pago de Microsoft 365 E5.
- Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y cliente1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio de servicios de dominio de Active Directory (AD DS) TESTLAB con el inquilino de Azure AD de su suscripción a Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD

En esta fase, configure Azure AD Connect en APP1 para el SSO sin problemas de Azure AD y, a continuación, compruebe que funciona.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar Azure AD Connect en APP1

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2. Desde el escritorio de APP1, ejecute Azure AD Connect.

3. En la **Página principal**, seleccione **configurar**.

4. En la página **tareas adicionales** , seleccione **cambiar inicio de sesión de usuario**y, a continuación, seleccione **siguiente**.

5. En la página **conectar con Azure ad** , escriba las credenciales de la cuenta de administrador global y, a continuación, seleccione **siguiente**.

6. En la página **Inicio de sesión de usuario** , seleccione **Habilitar el inicio de sesión único**y, a continuación, seleccione **siguiente**.

7. En la página **Habilitar el inicio de sesión único** , seleccione **escribir credenciales**.

8. En el cuadro de diálogo **seguridad de Windows** , escriba **usuario1** y la contraseña de la cuenta usuario1, seleccione **Aceptar**y, a continuación, seleccione **siguiente**.

9. En la página **listo para configurar** , seleccione **configurar**.

10. En la página **configuración completada** , seleccione **salir**.

11. En Azure portal, en el panel izquierdo, seleccione Azure **Active Directory**  >  **Azure ad Connect**. Compruebe que la característica de **Inicio de sesión único** de forma transparente aparece como **habilitada**.

A continuación, pruebe la capacidad de iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<*your public domain*> de la cuenta User1.

1. En Internet Explorer en APP1, seleccione el icono de configuración y, a continuación, seleccione **Opciones de Internet**.
 
2. En **Opciones de Internet**, seleccione la pestaña **seguridad** .

3. Seleccione **Intranet local**y, a continuación, seleccione **sitios**.

4. En **Intranet local**, seleccione **avanzadas**.

5. En **Agregar este sitio web a la zona**, escriba **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**, seleccione **Agregar**  >  **cierre**  >  **Aceptar**aceptar  >  **OK**.

6. Cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

7. Cuando se le pida que inicie sesión, especifique <strong>user1@testlab.</strong>\<*your public domain*> nombre y, a continuación, seleccione **siguiente**. Debería iniciar sesión correctamente como User1 sin que se le pide una contraseña. Esto demuestra que el SSO de inicio de sesión directa de Azure AD está funcionando.

Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global de Azure AD. Por lo tanto, no verá el icono de **administrador** como opción.

Esta es la configuración resultante:

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Esta configuración se compone de:

- Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS testlab.\<*your domain name*> registrado.
- Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y cliente1 en una subred de una red virtual de Azure.
- Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.
- El SSO transparente de Azure AD está habilitado para que los equipos de la intranet simulada puedan iniciar sesión en los recursos de nube de Microsoft 365 sin especificar la contraseña de la cuenta de usuario.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
