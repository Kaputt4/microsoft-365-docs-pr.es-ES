---
title: Autenticación de paso a través para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: autenticación de paso a través para el entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 98e0ad4b216fdc3940c0077cb308d6271ffed678
ms.sourcegitcommit: 7ae0389cf06e2f481ee646556720ab3f3e93ea32
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "38757727"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Autenticación de paso a través para el entorno de prueba de Microsoft 365

*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*

Las organizaciones que quieren usar directamente su infraestructura de Active Directory Domain Services (AD DS) local para la autenticación de aplicaciones y servicios en la nube de Microsoft pueden usar la autenticación de paso a través. Este artículo describe cómo configurar el entorno de prueba de Microsoft 365 para la autenticación de paso a través, lo que resulta en la siguiente configuración:
  
![La empresa simulada con el entorno de prueba con la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Existen dos fases para configurar el entorno de prueba:

1.  Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.
2.  Configurar Azure AD Connect en APP1 para la autenticación de paso a través.
    
![Guías del entorno de pruebas para la nube de Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 u Office 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: configurar Azure AD Connect en APP1 para la autenticación de paso a través

En esta fase, configure Azure AD Connect en APP1 para usar la autenticación de paso a través y, después, compruebe que funciona correctamente.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar Azure AD Connect en APP1

1.  Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2.  Desde el escritorio de APP1, ejecute Azure AD Connect.

3.  En la página de **Bienvenida**, haga clic en **Configurar**.

4.  En la página Tareas adicionales, haga clic en **Cambiar inicio de sesión de usuario** y, después, en **Siguiente**.

5.  En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, a continuación, haga clic en **Siguiente**.

6.  En la página **Inicio de sesión de usuario**, haga clic en **Autenticación de paso a través**y, a continuación, en **Siguiente**.

7.  En la página **Listo para configurar**, haga clic en **Configurar**.

8.  En la página **Configuración completada**, haga clic en **Salir**.

9.  Desde el Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Compruebe que la característica **Autenticación de paso a través** aparece como **Habilitada**.

10. Haga clic en **Autenticación de paso a través**. El panel **Autenticación de paso a través** enumera los servidores donde se instalan los agentes de autenticación. Verá APP1 en la lista. Cerrar el panel **Autenticación de paso a través**.

Después, compruebe si puede iniciar sesión en su suscripción de Office 365 con el nombre de usuario <strong>user1@testlab.</strong>\<su dominio público> de la cuenta Usuario1.

1. Desde APP1, cierre sesión en Office 365 y vuelva a iniciar sesión, esta vez especificando una cuenta diferente.

2. Cuando se le solicite un nombre de usuario y contraseña, especifique <strong>user1@testlab.</strong>\<su dominio público > y la contraseña de User1. Debería poder iniciar sesión como User1.

Tenga en cuenta que aunque User1 tiene permisos de administrador de dominio para el dominio de AD DS de práctica de prueba, no es un administrador global de Office 365. Por lo tanto, no verá el icono de **administrador** como opción.

Esta es la configuración resultante:

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Esta configuración se compone de:

- Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5 con el dominio DNS testlab. \<su nombre de dominio > registrado.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Un Agente de autenticación se ejecuta en APP1 para administrar las solicitudes de autenticación de paso a través desde el inquilino de Azure AD de las suscripciones de Microsoft 365 u Office 365.

## <a name="next-step"></a>Siguiente paso

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


