---
title: Autenticación de paso a través para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: autenticación de paso a través para el entorno de prueba de Microsoft 365.'
ms.openlocfilehash: c23f5cc99ca11ec19cb555541d798b8b4c74bd71
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68177666"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Autenticación de paso a través para el entorno de prueba de Microsoft 365

*Esta guía de laboratorio de pruebas se puede usar para Microsoft 365 para entornos de prueba empresariales y Office 365 Enterprise.*

Las organizaciones que quieren usar directamente su infraestructura de Active Directory Domain Services (AD DS) local para la autenticación de aplicaciones y servicios en la nube de Microsoft pueden usar la autenticación de paso a través. Este artículo describe cómo configurar el entorno de prueba de Microsoft 365 para la autenticación de paso a través, lo que resulta en la siguiente configuración:
  
![La empresa simulada con un entorno de prueba de autenticación de paso a través.](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Existen dos fases para configurar el entorno de prueba:

1.    Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.
2.    Configurar Azure AD Connect en APP1 para la autenticación de paso a través.
    
![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Haga clic [aquí](../downloads/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365

Siga las instrucciones de [sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Este es el resultado de la configuración.
  
![La empresa simulada con el entorno de prueba de sincronización de hash de contraseña.](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Esta configuración se compone de: 
  
- Microsoft 365 E5 suscripción de prueba o de pago.
- La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: configurar Azure AD Connect en APP1 para la autenticación de paso a través

En esta fase, configure Azure AD Connect en APP1 para usar la autenticación de paso a través y, después, compruebe que funciona correctamente.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurar Azure AD Connect en APP1

1.    Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.

2.    Desde el escritorio de APP1, ejecute Azure AD Connect.

3.    En la página de **Bienvenida**, haga clic en **Configurar**.

4.    En la página Tareas adicionales, haga clic en **Cambiar inicio de sesión de usuario** y, después, en **Siguiente**.

5.    En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, a continuación, haga clic en **Siguiente**.

6.    En la página **Inicio de sesión de usuario**, haga clic en **Autenticación de paso a través** y, a continuación, en **Siguiente**.

7.    En la página **Listo para configurar**, haga clic en **Configurar**.

8.    En la página **Configuración completada**, haga clic en **Salir**.

9.    From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.

10.    Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.

A continuación, pruebe la capacidad de iniciar sesión en la suscripción con el <strong>user1@testlab.</strong>\<your public domain> de la cuenta User1.

1. Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.

2. Cuando se le pida el nombre de usuario y la contraseña, especifique <strong>user1@testlab.</strong>\<your public domain> y la contraseña de User1. Debería poder iniciar sesión como User1.

Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global. Por lo tanto, no verá el icono de **administrador** como opción.

Esta es la configuración resultante:

![La empresa simulada con un entorno de prueba de autenticación de paso a través.](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Esta configuración se compone de:

- Una Microsoft 365 E5 suscripciones de prueba o de pago con el testlab de dominio DNS.\<your domain name> registrado.
- A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.

## <a name="next-step"></a>Paso siguiente

Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)