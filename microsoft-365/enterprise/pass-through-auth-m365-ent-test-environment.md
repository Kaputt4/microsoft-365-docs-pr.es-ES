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
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: autenticación de paso a través para el entorno de prueba de Microsoft 365.'
ms.openlocfilehash: 4f9941b017f00b40a6ae7e893211131cae51c611
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42066432"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ada18-103">Autenticación de paso a través para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ada18-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ada18-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="ada18-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ada18-105">Las organizaciones que quieren usar directamente su infraestructura de Active Directory Domain Services (AD DS) local para la autenticación de aplicaciones y servicios en la nube de Microsoft pueden usar la autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="ada18-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="ada18-106">Este artículo describe cómo configurar el entorno de prueba de Microsoft 365 para la autenticación de paso a través, lo que resulta en la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="ada18-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="ada18-108">Existen dos fases para configurar el entorno de prueba:</span><span class="sxs-lookup"><span data-stu-id="ada18-108">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="ada18-109">Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="ada18-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="ada18-110">Configurar Azure AD Connect en APP1 para la autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="ada18-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="ada18-112">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="ada18-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="ada18-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ada18-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="ada18-p102">Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="ada18-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="ada18-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="ada18-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="ada18-118">Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="ada18-118">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="ada18-119">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="ada18-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="ada18-120">Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="ada18-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 or Office 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="ada18-121">Fase 2: configurar Azure AD Connect en APP1 para la autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="ada18-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="ada18-122">En esta fase, configure Azure AD Connect en APP1 para usar la autenticación de paso a través y, después, compruebe que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="ada18-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="ada18-123">Configurar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="ada18-123">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="ada18-124">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="ada18-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="ada18-125">Desde el escritorio de APP1, ejecute Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="ada18-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="ada18-126">En la página de **Bienvenida**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="ada18-126">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="ada18-127">En la página Tareas adicionales, haga clic en **Cambiar inicio de sesión de usuario** y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ada18-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="ada18-128">En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ada18-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="ada18-129">En la página **Inicio de sesión de usuario**, haga clic en **Autenticación de paso a través**y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ada18-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="ada18-130">En la página **Listo para configurar**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="ada18-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="ada18-131">En la página **Configuración completada**, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="ada18-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="ada18-p104">Desde el Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Compruebe que la característica **Autenticación de paso a través** aparece como **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="ada18-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="ada18-p105">Haga clic en **Autenticación de paso a través**. El panel **Autenticación de paso a través** enumera los servidores donde se instalan los agentes de autenticación. Verá APP1 en la lista. Cerrar el panel **Autenticación de paso a través**.</span><span class="sxs-lookup"><span data-stu-id="ada18-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="ada18-138">Después, compruebe si puede iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<su nombre de usuario de dominio público> de la cuenta Usuario1.</span><span class="sxs-lookup"><span data-stu-id="ada18-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="ada18-139">Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="ada18-139">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="ada18-140">Cuando se le solicite un nombre de usuario y contraseña, especifique <strong>user1@testlab.</strong>\<su dominio público > y la contraseña de User1.</span><span class="sxs-lookup"><span data-stu-id="ada18-140">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="ada18-141">Debería poder iniciar sesión como User1.</span><span class="sxs-lookup"><span data-stu-id="ada18-141">You should successfully sign in as User1.</span></span>

<span data-ttu-id="ada18-142">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="ada18-142">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="ada18-143">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="ada18-143">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="ada18-144">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="ada18-144">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="ada18-146">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="ada18-146">This configuration consists of:</span></span>

- <span data-ttu-id="ada18-147">Suscripciones de prueba o de pago de Microsoft 365 E5 u Office 365 E5 con el dominio DNS testlab. \<su nombre de dominio > registrado.</span><span class="sxs-lookup"><span data-stu-id="ada18-147">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="ada18-p108">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Un Agente de autenticación se ejecuta en APP1 para administrar las solicitudes de autenticación de paso a través desde el inquilino de Azure AD de las suscripciones de Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="ada18-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 or Office 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="ada18-150">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="ada18-150">Next step</span></span>

<span data-ttu-id="ada18-151">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="ada18-151">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ada18-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="ada18-152">See also</span></span>

[<span data-ttu-id="ada18-153">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ada18-153">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ada18-154">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ada18-154">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ada18-155">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ada18-155">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
