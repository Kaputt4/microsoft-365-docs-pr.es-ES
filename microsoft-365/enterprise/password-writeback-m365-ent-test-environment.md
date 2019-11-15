---
title: Escritura diferida de contraseña para el entorno de prueba de Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Resumen: configure la escritura diferida de contraseña para el entorno de prueba de Microsoft 365'
ms.openlocfilehash: d946aefa38884923d70d2c530d61f84861cc914e
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639760"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="36b57-103">Escritura diferida de contraseña para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36b57-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="36b57-p101">La escritura diferida de contraseña permite que los usuarios actualicen sus contraseñas a través de Azure Active Directory (Azure AD), que se replica después en la instancia local de Active Directory Domain Services (AD DS). Con la escritura diferida de contraseñas, los usuarios no necesitan actualizar sus contraseñas a través de la instancia local de AD DS donde se almacenan las cuentas de usuario originales. Esto resulta útil para los usuarios remotos o en itinerancia que no tengan una conexión de acceso remoto a la red local.</span><span class="sxs-lookup"><span data-stu-id="36b57-p101">Password writeback allows users to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don’t need to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="36b57-107">En este artículo, se describe cómo configurar el entorno de prueba de Microsoft 365 para la escritura diferida de contraseña.</span><span class="sxs-lookup"><span data-stu-id="36b57-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="36b57-108">Hay dos fases de configuración:</span><span class="sxs-lookup"><span data-stu-id="36b57-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="36b57-109">Crear el entorno de prueba de la empresa simulada de Microsoft 365 con la sincronización de hash de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="36b57-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="36b57-110">Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.</span><span class="sxs-lookup"><span data-stu-id="36b57-110">Enable password writeback for the TESTLAB AD DS domain.</span></span>
    
![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="36b57-112">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="36b57-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="36b57-113">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="36b57-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="36b57-p102">Primero, siga las instrucciones de [Sincronización de hash de contraseñas](password-hash-sync-m365-ent-test-environment.md). Esta es la configuración resultante.</span><span class="sxs-lookup"><span data-stu-id="36b57-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="36b57-117">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="36b57-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="36b57-118">Suscripciones de prueba o de pago de Office 365 E5 y EMS E5.</span><span class="sxs-lookup"><span data-stu-id="36b57-118">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="36b57-119">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="36b57-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="36b57-120">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio de TESTLAB AD DS con el espacio empresarial de Azure AD de sus suscripciones de Office 365 y EMS E5.</span><span class="sxs-lookup"><span data-stu-id="36b57-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="36b57-121">Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.</span><span class="sxs-lookup"><span data-stu-id="36b57-121">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="36b57-122">En primer lugar, configure la cuenta del Usuario 1 con el rol de administrador global.</span><span class="sxs-lookup"><span data-stu-id="36b57-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="36b57-123">Desde el [Centro de administración de Microsoft 365](https://portal.microsoft.com), inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="36b57-123">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="36b57-124">Haga clic en **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="36b57-124">Click **Active users**.</span></span>
 
3. <span data-ttu-id="36b57-125">En la página **Usuarios activos**, haga clic en la cuenta **usuario1**.</span><span class="sxs-lookup"><span data-stu-id="36b57-125">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="36b57-126">En el panel **usuario1**, haga clic en **Editar** junto a **Roles**.</span><span class="sxs-lookup"><span data-stu-id="36b57-126">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="36b57-p103">En el panel **Editar roles de usuario** de usuario1, haga clic en **Administrador global**. Haga clic en **Guardar** y, a continuación, haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="36b57-p103">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="36b57-129">A continuación, configure la cuenta de Usuario 1 con la configuración de seguridad que le permite cambiar las contraseñas en nombre de otros usuarios en el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="36b57-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="36b57-130">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="36b57-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="36b57-131">Desde el escritorio de APP1, haga clic en **Inicio**, escriba **active** y, después, haga clic en **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="36b57-131">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="36b57-p104">Haga clic en **Vista** en la barra de menús. Si **Características avanzadas** no está habilitado, haga clic para habilitarlo.</span><span class="sxs-lookup"><span data-stu-id="36b57-p104">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="36b57-134">En el panel de árbol, haga clic derecho en su dominio, haga clic en **Propiedades** y, a continuación, haga clic en la pestaña **Seguridad**.</span><span class="sxs-lookup"><span data-stu-id="36b57-134">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="36b57-135">Haga clic en **Avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="36b57-135">Click **Advanced**.</span></span>

6. <span data-ttu-id="36b57-136">En la pestaña **Permisos**, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="36b57-136">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="36b57-137">Haga clic en **Seleccionar una entidad de seguridad**, escriba **Usuario1** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="36b57-137">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="36b57-138">En **Se aplica a**, seleccione **Objetos de usuario descendiente**.</span><span class="sxs-lookup"><span data-stu-id="36b57-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="36b57-139">En **Permisos**, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36b57-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="36b57-140">Cambiar contraseña</span><span class="sxs-lookup"><span data-stu-id="36b57-140">Change password</span></span>
    - <span data-ttu-id="36b57-141">Restablecer contraseña</span><span class="sxs-lookup"><span data-stu-id="36b57-141">Reset password</span></span>

10. <span data-ttu-id="36b57-142">En **Propiedades**, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="36b57-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="36b57-143">Escribir lockoutTime</span><span class="sxs-lookup"><span data-stu-id="36b57-143">Write lockoutTime</span></span>
    - <span data-ttu-id="36b57-144">Escribir pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="36b57-144">Write pwdLastSet</span></span>

11. <span data-ttu-id="36b57-145">Haga clic tres veces en **Aceptar** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="36b57-145">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="36b57-146">Cierre **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="36b57-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="36b57-147">A continuación, configure Azure AD Connect en APP1 para la escritura diferida de contraseña.</span><span class="sxs-lookup"><span data-stu-id="36b57-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="36b57-148">Si es necesario, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="36b57-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="36b57-149">Desde el escritorio de APP1, haga doble clic en **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="36b57-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="36b57-150">En la página de **Bienvenida**, haga clic en **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="36b57-150">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="36b57-151">En la página **Tareas adicionales**, haga clic en **Personalizar las opciones de sincronización** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36b57-151">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="36b57-152">En la página **Conectar a Azure AD**, escriba las credenciales de la cuenta de administrador global y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36b57-152">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="36b57-153">En las páginas **Conectar directorios** y **Filtrado de dominios y unidades organizativas**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36b57-153">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="36b57-154">En la página **Características opcionales**, seleccione **Contraseña con escritura diferida** y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="36b57-154">On the **Optional features** page, select **Password writeback** and click **Next**.</span></span> 

8. <span data-ttu-id="36b57-155">En la página **Preparado para configurar**, haga clic en **Configurar** y espere a que finalice el proceso.</span><span class="sxs-lookup"><span data-stu-id="36b57-155">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="36b57-156">Cuando vea finalizar la configuración, haga clic en **Salir**.</span><span class="sxs-lookup"><span data-stu-id="36b57-156">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="36b57-157">Ya está listo para probar la escritura diferida de contraseñas para los usuarios de equipos que no estén conectados a la red virtual de la intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="36b57-157">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="36b57-158">Esta es la configuración resultante:</span><span class="sxs-lookup"><span data-stu-id="36b57-158">Here is your resulting configuration:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="36b57-160">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="36b57-160">This configuration consists of:</span></span>

- <span data-ttu-id="36b57-161">Suscripciones de prueba o de pago a Office 365 E5 y EMS E5 con el dominio DNS TESTLAB.\<su nombre de dominio> registrado.</span><span class="sxs-lookup"><span data-stu-id="36b57-161">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="36b57-162">La intranet de una organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y CLIENTE1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="36b57-162">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="36b57-163">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Office 365 y EMS E5 con el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="36b57-163">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB AD DS domain.</span></span> 
- <span data-ttu-id="36b57-164">La escritura diferida de contraseña está habilitada para que los usuarios puedan cambiar sus contraseñas a través de Azure AD sin tener que estar conectados a la intranet simplificada.</span><span class="sxs-lookup"><span data-stu-id="36b57-164">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="36b57-165">Vea el paso [Simplificar las actualizaciones de contraseña](identity-add-user-accounts.md#identity-pw-writeback) en la fase Identidad para obtener información y vínculos sobre cómo configurar la escritura diferida de contraseña en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="36b57-165">See the [Simplify password updates](identity-add-user-accounts.md#identity-pw-writeback) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="36b57-166">Siguiente paso</span><span class="sxs-lookup"><span data-stu-id="36b57-166">Next step</span></span>

<span data-ttu-id="36b57-167">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="36b57-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="36b57-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="36b57-168">See also</span></span>

[<span data-ttu-id="36b57-169">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36b57-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="36b57-170">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36b57-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="36b57-171">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="36b57-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


