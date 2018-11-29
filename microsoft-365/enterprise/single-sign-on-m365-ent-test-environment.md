---
title: Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
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
description: 'Resumen: configure y pruebe el inicio de sesión único de conexión directa de Azure AD para su entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 10444b094e09705e93cb32c10cd0d41c19913985
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871710"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Inicio de sesión único de conexión directa de Azure AD para un entorno de prueba de Microsoft 365

El inicio de sesión único de conexión directa (SSO) de Azure AD inicia sesión automáticamente a los usuarios cuando se encuentran en sus equipos PC o dispositivos conectados a la red de la organización. El SSO de conexión directa de Azure AD proporciona a los usuarios un acceso sencillo a aplicaciones basadas en la nube, sin necesitar componentes locales adicionales.

En este artículo, se describe cómo configurar el entorno de prueba de Microsoft 365 para SSO de conexión directa de Azure AD.

Existen dos fases para configurar el entorno de prueba:

1.  Crear el entorno de prueba de la empresa ficticia de Microsoft 365 con la sincronización de hash de contraseña.
2.  Configurar Azure AD Connect en APP1 para SSO de conexión directa de Azure AD.
    
![Guías del entorno de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-create-the-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: crear la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o permanentes de Office 365 E5 y EMS E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de Windows Server AD TESTLAB con el espacio empresarial de Azure AD de sus suscripciones de Office 365 y EMS E5 de forma periódica.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: Configurar Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD

En esta fase, configurará Azure AD Connect en APP1 para el SSO de conexión directa de Azure AD y, después, comprobará que funcione.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar Azure AD Connect en APP1

1. Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2. Desde el escritorio de APP1, ejecute Azure AD Connect.

3. En la página de **Bienvenida**, haga clic en **Configurar**.

4. En la página Tareas adicionales, haga clic en **Cambiar inicio de sesión de usuario** y, después, en **Siguiente**.

5. En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, después, haga clic en **Siguiente**.

6. En la página **Inicio de sesión de usuario**, seleccione **Habilitar inicio de sesión único** y, después, haga clic en **Siguiente**.

7. En la página **Habilitar inicio de sesión único**, haga clic en **Escribir credenciales**.

8. En el cuadro de diálogo **Seguridad de Windows**, escriba **usuario1** y la contraseña de la cuenta usuario1 y, después, haga clic en **Aceptar**. Haga clic en **Siguiente**.

9. En la página **Listo para configurar**, haga clic en **Configurar**.

10. En la página **Configuración completada**, haga clic en **Salir**.

11. Desde Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Asegúrese de que la característica **Inicio de sesión único de conexión directa** esté **Habilitada**.

Después, compruebe si puede iniciar sesión en su suscripción de Office 365 con el nombre de usuario <strong>user1@testlab.</strong>\<su dominio público> de la cuenta Usuario1.

1. En Internet Explorer, en APP1, haga clic en el icono de configuración y, después, seleccione **Opciones de Internet**.
 
2. En **Opciones de Internet**, haga clic en la pestaña **Seguridad**.

3. Haga clic en **Intranet local** y, después, seleccione **Sitios**.

4. En **Intranet local**, haga clic en **Avanzadas**.

5. En **Agregar este sitio web a la zona de**, escriba **https<span>://</span>autologon.microsoftazuread-sso.com**, haga clic en **Agregar > Cerrar > Aceptar > Aceptar**.

6. Cierre la sesión de Office 365 y vuelva a iniciarla, pero esta vez especifique otra cuenta.

7. Cuando se le pida que inicie sesión, especifique el nombre <strong>user1@testlab.</strong>\<nombre de dominio público> y, después, haga clic en **Siguiente**. Iniciará sesión correctamente como Usuario1 sin que se le pida una contraseña. De esta forma, demostrará que el SSO de conexión directa funciona correctamente.

Tenga en cuenta que, aunque Usuario1 tiene permisos de administrador de dominio para el dominio de Windows Server AD de TESTLAB, no es un administrador global de Office 365. Por lo tanto, el icono de **Administrador ** no aparecerá entre las opciones.

Esta es la configuración resultante:

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Esta configuración se compone de:

- Suscripciones de prueba o permanentes a Office 365 E5 y EMS E5 con el dominio DNS TESTLAB.\<su nombre de dominio> registrado.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. 
- Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Office 365 y EMS E5 con el dominio de Windows Server AD “TESTLAB”. 
- El SSO de conexión directa de Azure AD está habilitado para que los equipos en la intranet ficticia puedan iniciar sesión en recursos de nube de Microsoft 365 sin especificar una contraseña de cuenta de usuario.

Vea el paso [Simplificar el inicio de sesión de usuario](identity-single-sign-on.md) en la fase Identidad para obtener información y vínculos sobre cómo configurar el SSO de conexión directa de Azure AD en un entorno de producción.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


