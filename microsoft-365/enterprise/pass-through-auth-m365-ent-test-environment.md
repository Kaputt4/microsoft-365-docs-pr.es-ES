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
ms.openlocfilehash: 1b5540f2e16ac0267bf33faf42defe6bca6d25cd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695199"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="26c81-103">Autenticación de paso a través para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26c81-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="26c81-104">*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*</span><span class="sxs-lookup"><span data-stu-id="26c81-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="26c81-105">Las organizaciones que quieren usar directamente su infraestructura de Active Directory Domain Services (AD DS) local para la autenticación de aplicaciones y servicios en la nube de Microsoft pueden usar la autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="26c81-105">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="26c81-106">Este artículo describe cómo configurar el entorno de prueba de Microsoft 365 para la autenticación de paso a través, lo que resulta en la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="26c81-106">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="26c81-108">Existen dos fases para configurar el entorno de prueba:</span><span class="sxs-lookup"><span data-stu-id="26c81-108">There are two phases to setting up this test environment:</span></span>

1.    <span data-ttu-id="26c81-109">Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="26c81-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="26c81-110">Configurar Azure AD Connect en APP1 para la autenticación de paso a través.</span><span class="sxs-lookup"><span data-stu-id="26c81-110">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Guías del entorno de pruebas para la nube de Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="26c81-112">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="26c81-112">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="26c81-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="26c81-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="26c81-p102">Siga las instrucciones de [Sincronización de hash de contraseñas para Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="26c81-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="26c81-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="26c81-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="26c81-118">Suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="26c81-118">Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="26c81-119">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="26c81-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="26c81-120">Azure AD Connect se ejecuta en APP1 para sincronizar periódicamente el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26c81-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="26c81-121">Fase 2: configurar Azure AD Connect en APP1 para la autenticación de paso a través</span><span class="sxs-lookup"><span data-stu-id="26c81-121">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="26c81-122">En esta fase, configure Azure AD Connect en APP1 para usar la autenticación de paso a través y, después, compruebe que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="26c81-122">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="26c81-123">Configurar Azure AD Connect en APP1</span><span class="sxs-lookup"><span data-stu-id="26c81-123">Configure Azure AD Connect on APP1</span></span>

1.    <span data-ttu-id="26c81-124">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="26c81-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.    <span data-ttu-id="26c81-125">Desde el escritorio de APP1, ejecute Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="26c81-125">From the desktop of APP1, run Azure AD Connect.</span></span>

3.    <span data-ttu-id="26c81-126">En la página de **Bienvenida**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="26c81-126">On the **Welcome page**, click **Configure**.</span></span>

4.    <span data-ttu-id="26c81-127">En la página Tareas adicionales, haga clic en **Cambiar inicio de sesión de usuario** y, después, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="26c81-127">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.    <span data-ttu-id="26c81-128">En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="26c81-128">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.    <span data-ttu-id="26c81-129">En la página **Inicio de sesión de usuario**, haga clic en **Autenticación de paso a través**y, a continuación, en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="26c81-129">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.    <span data-ttu-id="26c81-130">En la página **Listo para configurar**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="26c81-130">On the **Ready to configure** page, click **Configure**.</span></span>

8.    <span data-ttu-id="26c81-131">En la página **Configuración completada**, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="26c81-131">On the **Configuration complete** page, click **Exit**.</span></span>

9.    <span data-ttu-id="26c81-p104">Desde el Azure Portal, en el panel izquierdo, haga clic en **Azure Active Directory > Azure AD Connect**. Compruebe que la característica **Autenticación de paso a través** aparece como **Habilitada**.</span><span class="sxs-lookup"><span data-stu-id="26c81-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10.    <span data-ttu-id="26c81-p105">Haga clic en **Autenticación de paso a través**. El panel **Autenticación de paso a través** enumera los servidores donde se instalan los agentes de autenticación. Verá APP1 en la lista. Cerrar el panel **Autenticación de paso a través**.</span><span class="sxs-lookup"><span data-stu-id="26c81-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="26c81-138">A continuación, pruebe la capacidad de iniciar sesión en su suscripción con el <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="26c81-138">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="26c81-139">de la cuenta User1.</span><span class="sxs-lookup"><span data-stu-id="26c81-139">user name of the User1 account.</span></span>

1. <span data-ttu-id="26c81-140">Desde APP1, cierre la sesión y vuelva a iniciarla, pero esta vez especifique una cuenta diferente.</span><span class="sxs-lookup"><span data-stu-id="26c81-140">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="26c81-141">Cuando se le pida el nombre de usuario y la contraseña, especifique <strong>user1@testlab.</strong>\<your public domain></span><span class="sxs-lookup"><span data-stu-id="26c81-141">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain></span></span> <span data-ttu-id="26c81-142">y la contraseña de User1.</span><span class="sxs-lookup"><span data-stu-id="26c81-142">and the User1 password.</span></span> <span data-ttu-id="26c81-143">Debería poder iniciar sesión como User1.</span><span class="sxs-lookup"><span data-stu-id="26c81-143">You should successfully sign in as User1.</span></span>

<span data-ttu-id="26c81-144">Tenga en cuenta que, aunque User1 tiene permisos de administrador de dominio para el dominio TESTLAB AD DS, no es un administrador global.</span><span class="sxs-lookup"><span data-stu-id="26c81-144">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="26c81-145">Por lo tanto, no verá el icono de **administrador** como opción.</span><span class="sxs-lookup"><span data-stu-id="26c81-145">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="26c81-146">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="26c81-146">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="26c81-148">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="26c81-148">This configuration consists of:</span></span>

- <span data-ttu-id="26c81-149">Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS testlab.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="26c81-149">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name></span></span> <span data-ttu-id="26c81-150">registrado.</span><span class="sxs-lookup"><span data-stu-id="26c81-150">registered.</span></span>
- <span data-ttu-id="26c81-p110">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure. Un Agente de autenticación se ejecuta en APP1 para administrar las solicitudes de autenticación de paso a través desde el inquilino de Azure AD de las suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="26c81-p110">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="next-step"></a><span data-ttu-id="26c81-153">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="26c81-153">Next step</span></span>

<span data-ttu-id="26c81-154">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="26c81-154">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="26c81-155">Vea también</span><span class="sxs-lookup"><span data-stu-id="26c81-155">See also</span></span>

[<span data-ttu-id="26c81-156">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="26c81-156">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="26c81-157">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="26c81-157">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="26c81-158">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="26c81-158">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
