---
title: Autenticación de paso a través para el entorno de prueba de Microsoft 365
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: autenticación de paso a través para el entorno de prueba de Microsoft 365.'
ms.openlocfilehash: d83de4ece4d1eaeddac882cf46a4fe85b8ba7cd4
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487451"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Autenticación de paso a través para el entorno de prueba de Microsoft 365

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

Las organizaciones que quieren usar directamente su infraestructura de Active Directory Domain Services (AD DS) local para la autenticación de aplicaciones y servicios en la nube de Microsoft pueden usar la autenticación de paso a través. Este artículo describe cómo configurar el entorno de prueba de Microsoft 365 para la autenticación de paso a través, lo que resulta en la siguiente configuración:
  
![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Existen dos fases para configurar el entorno de prueba:

1.    Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.
2.    Configurar Azure AD Connect en APP1 para la autenticación de paso a través.
    
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Suscripción de prueba o de pago de Microsoft 365 E5.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: configurar Azure AD Connect en APP1 para la autenticación de paso a través

En esta fase, configure Azure AD Connect en APP1 para usar la autenticación de paso a través y, después, compruebe que funciona correctamente.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar Azure AD Connect en APP1

1.    Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2.    Desde el escritorio de APP1, ejecute Azure AD Connect.

3.    En la página de **Bienvenida**, haga clic en **Configurar**.

4.    En la página Tareas adicionales, haga clic en **Cambiar inicio de sesión de usuario** y, después, en **Siguiente**.

5.    En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, a continuación, haga clic en **Siguiente**.

6.    En la página **Inicio de sesión de usuario**, haga clic en **Autenticación de paso a través**y, a continuación, en **Siguiente**.

7.    En la página **Listo para configurar**, haga clic en **Configurar**.

8.    En la página **Configuración completada**, haga clic en **Salir**.

9.    Desde el Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Compruebe que la característica **Autenticación de paso a través** aparece como **Habilitada**.

10.    Haga clic en **Autenticación de paso a través**. El panel **Autenticación de paso a través** enumera los servidores donde se instalan los agentes de autenticación. Verá APP1 en la lista. Cerrar el panel **Autenticación de paso a través**.

A continuación, pruebe la capacidad de iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<your public domain> de la cuenta User1.

1. Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

2. Cuando se le pida el nombre de usuario y la contraseña, especifique <strong>user1@testlab.</strong>\<your public domain> y la contraseña de User1. Debería poder iniciar sesión como User1.

Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global. Por lo tanto, no verá el icono de **administrador** como opción.

Esta es la configuración resultante:

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Esta configuración se compone de:

- Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS testlab.\<your domain name> registrado.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Un Agente de autenticación se ejecuta en APP1 para administrar las solicitudes de autenticación de paso a través desde el inquilino de Azure AD de las suscripciones de Microsoft 365.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
