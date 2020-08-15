---
title: Escritura diferida de contraseña para el entorno de prueba de Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Resumen: configure la escritura diferida de contraseña para el entorno de prueba de Microsoft 365'
ms.openlocfilehash: b8c89ca7ef967c423b89db4559ef04f715a5f869
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686231"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="07f9a-103">Escritura diferida de contraseña para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07f9a-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="07f9a-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="07f9a-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="07f9a-p101">La escritura diferida de contraseña permite que los usuarios actualicen sus contraseñas a través de Azure Active Directory (Azure AD), que se replica después en la instancia local de Active Directory Domain Services (AD DS). Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar sus contraseñas a través de la instancia local de AD DS donde se almacenan las cuentas de usuario originales. Esto resulta útil para los usuarios remotos o en itinerancia que no tengan una conexión de acceso remoto a la red local.</span><span class="sxs-lookup"><span data-stu-id="07f9a-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't need to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="07f9a-108">En este artículo, se describe cómo configurar el entorno de prueba de Microsoft 365 para la escritura diferida de contraseña.</span><span class="sxs-lookup"><span data-stu-id="07f9a-108">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="07f9a-109">Hay dos fases de configuración:</span><span class="sxs-lookup"><span data-stu-id="07f9a-109">There are two phases to setting this up:</span></span>

1.    <span data-ttu-id="07f9a-110">Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="07f9a-110">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.    <span data-ttu-id="07f9a-111">Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.</span><span class="sxs-lookup"><span data-stu-id="07f9a-111">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="07f9a-113">Haga clic [aquí](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual con todos los artículos en la pila de la guías de laboratorio para pruebas de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="07f9a-113">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="07f9a-114">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07f9a-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="07f9a-p102">Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="07f9a-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="07f9a-118">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="07f9a-118">This configuration consists of:</span></span> 
  
- <span data-ttu-id="07f9a-119">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="07f9a-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="07f9a-120">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="07f9a-120">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="07f9a-121">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="07f9a-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="07f9a-122">Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.</span><span class="sxs-lookup"><span data-stu-id="07f9a-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="07f9a-123">En primer lugar, configure la cuenta del Usuario 1 con el rol de administrador global.</span><span class="sxs-lookup"><span data-stu-id="07f9a-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="07f9a-124">Desde el [Centro de administración de Microsoft 365](https://portal.microsoft.com), inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="07f9a-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="07f9a-125">Haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-125">Click **Active users**.</span></span>
 
3. <span data-ttu-id="07f9a-126">En la página **Usuarios activos**, haga clic en la cuenta **usuario1**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="07f9a-127">En el panel **usuario1**, haga clic en **Editar** junto a **Roles**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="07f9a-p103">En el panel **Editar roles de usuario** de usuario1, haga clic en **Administrador global**. Haga clic en **Guardar** y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-p103">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="07f9a-130">A continuación, configure la cuenta de Usuario 1 con la configuración de seguridad que le permite cambiar las contraseñas en nombre de otros usuarios en el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="07f9a-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="07f9a-131">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="07f9a-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="07f9a-132">Desde el escritorio de APP1, haga clic en **Inicio**, escriba **active** y, después, haga clic en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="07f9a-p104">Haga clic en **Vista** en la barra de menús. Si **Características avanzadas** no está habilitado, haga clic para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="07f9a-p104">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="07f9a-135">En el panel de árbol, haga clic derecho en su dominio, haga clic en **Propiedades** y, a continuación, haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="07f9a-136">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="07f9a-137">En la pestaña **Permisos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="07f9a-138">Haga clic en **Seleccionar una entidad de seguridad**, escriba **Usuario1** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="07f9a-139">En **Se aplica a**, seleccione **Objetos de usuario descendiente**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="07f9a-140">En **Permisos**, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07f9a-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="07f9a-141">Cambiar contraseña</span><span class="sxs-lookup"><span data-stu-id="07f9a-141">Change password</span></span>
    - <span data-ttu-id="07f9a-142">Restablecer contraseña</span><span class="sxs-lookup"><span data-stu-id="07f9a-142">Reset password</span></span>

10. <span data-ttu-id="07f9a-143">En **Propiedades**, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="07f9a-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="07f9a-144">Escribir lockoutTime</span><span class="sxs-lookup"><span data-stu-id="07f9a-144">Write lockoutTime</span></span>
    - <span data-ttu-id="07f9a-145">Escribir pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="07f9a-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="07f9a-146">Haga clic tres veces en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="07f9a-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="07f9a-147">Cierre **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="07f9a-148">A continuación, configure Azure AD Connect en APP1 para la escritura diferida de contraseña.</span><span class="sxs-lookup"><span data-stu-id="07f9a-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="07f9a-149">Si es necesario, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="07f9a-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="07f9a-150">Desde el escritorio de APP1, haga doble clic en **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="07f9a-151">En la página de **Bienvenida**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="07f9a-152">En la página **Tareas adicionales**, haga clic en **Personalizar las opciones de sincronización** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="07f9a-153">En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-153">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="07f9a-154">En las páginas **Conectar directorios** y **Filtrado de dominios y unidades organizativas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="07f9a-155">En la página **Características opcionales**, seleccione **Contraseña con escritura diferida** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-155">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="07f9a-156">En la página **Preparado para configurar**, haga clic en **Configurar** y espere a que finalice el proceso.</span><span class="sxs-lookup"><span data-stu-id="07f9a-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="07f9a-157">Cuando vea finalizar la configuración, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="07f9a-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="07f9a-158">Ya está listo para probar la escritura diferida de contraseñas para los usuarios de equipos que no estén conectados a la red virtual de la intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="07f9a-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="07f9a-159">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="07f9a-159">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="07f9a-161">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="07f9a-161">This configuration consists of:</span></span>

- <span data-ttu-id="07f9a-162">Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS TESTLAB.\<your domain name></span><span class="sxs-lookup"><span data-stu-id="07f9a-162">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name></span></span> <span data-ttu-id="07f9a-163">registrado.</span><span class="sxs-lookup"><span data-stu-id="07f9a-163">registered.</span></span>
- <span data-ttu-id="07f9a-164">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="07f9a-164">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="07f9a-165">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="07f9a-165">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="07f9a-166">La escritura diferida de contraseña está habilitada para que los usuarios puedan cambiar sus contraseñas a través de Azure AD sin tener que estar conectados a la intranet simplificada.</span><span class="sxs-lookup"><span data-stu-id="07f9a-166">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="07f9a-167">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="07f9a-167">Next step</span></span>

<span data-ttu-id="07f9a-168">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="07f9a-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="07f9a-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="07f9a-169">See also</span></span>

[<span data-ttu-id="07f9a-170">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="07f9a-170">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="07f9a-171">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="07f9a-171">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="07f9a-172">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="07f9a-172">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


