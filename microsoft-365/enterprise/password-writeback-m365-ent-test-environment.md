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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487133"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e7a74-103">Escritura diferida de contraseña para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7a74-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e7a74-104">*Esta guía del entorno de pruebas solo puede usarse para entornos de prueba de empresa de Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="e7a74-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e7a74-p101">Los usuarios pueden usar la escritura diferida de contraseñas para actualizar sus contraseñas a través de Azure Active Directory (Azure AD), que se replican en los servicios de dominio de Active Directory (AD DS) locales. Con la escritura diferida de contraseña, los usuarios no tienen que actualizar sus contraseñas a través del AD DS local en el que se almacenan sus cuentas de usuario originales. Esto ayuda a los usuarios móviles o remotos que no tienen una conexión de acceso remoto a su red local.</span><span class="sxs-lookup"><span data-stu-id="e7a74-p101">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="e7a74-108">En este artículo se describe cómo configurar el entorno de prueba de Microsoft 365 para la escritura diferida de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="e7a74-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="e7a74-109">La configuración del entorno de prueba para la escritura diferida de contraseñas implica dos fases:</span><span class="sxs-lookup"><span data-stu-id="e7a74-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="e7a74-110">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7a74-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="e7a74-111">Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.</span><span class="sxs-lookup"><span data-stu-id="e7a74-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e7a74-113">Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="e7a74-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e7a74-114">Fase 1: configurar la sincronización de hash de contraseñas para el entorno de prueba de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7a74-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e7a74-p102">En primer lugar, siga las instrucciones de [sincronización de hash de contraseña](password-hash-sync-m365-ent-test-environment.md). La configuración resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e7a74-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Your resulting configuration looks like this:</span></span>
  
![La empresa simulada con el entorno de prueba con la sincronización de hash de contraseñas](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="e7a74-118">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="e7a74-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="e7a74-119">Una suscripción de prueba o de pago de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="e7a74-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e7a74-120">Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y cliente1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="e7a74-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e7a74-121">Azure AD Connect se ejecuta en APP1 para sincronizar el dominio TESTLAB de AD DS con el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7a74-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="e7a74-122">Fase 2: Habilitar la escritura diferida de contraseña para el dominio TESTLAB de AD DS.</span><span class="sxs-lookup"><span data-stu-id="e7a74-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="e7a74-123">En primer lugar, configure la cuenta del Usuario 1 con el rol de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7a74-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="e7a74-124">Desde el [Centro de administración de Microsoft 365](https://portal.microsoft.com), inicie sesión con su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="e7a74-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="e7a74-125">Seleccione **usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="e7a74-126">En la página **usuarios activos** , seleccione la cuenta **user1** .</span><span class="sxs-lookup"><span data-stu-id="e7a74-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="e7a74-127">En el panel **user1** , seleccione **Editar** junto a **roles**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="e7a74-128">En el panel **Editar roles de usuario** para Usuario1, seleccione **administrador global**, **Guardar**y, a continuación, haga clic en **cerrar**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="e7a74-129">A continuación, configure la cuenta de Usuario 1 con la configuración de seguridad que le permite cambiar las contraseñas en nombre de otros usuarios en el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="e7a74-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="e7a74-130">Desde el [Azure Portal](https://portal.azure.com), inicie sesión con su cuenta de administrador global y, a continuación, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="e7a74-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="e7a74-131">En el escritorio de APP1, seleccione **Inicio**, escriba **activo**y, a continuación, seleccione **usuarios y equipos de Active**Directory.</span><span class="sxs-lookup"><span data-stu-id="e7a74-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="e7a74-132">En la barra de menús, seleccione **Ver**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="e7a74-133">Si **las características avanzadas** no están habilitadas, selecciónela para habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="e7a74-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="e7a74-134">En el panel de árbol, seleccione y mantenga presionado (o haga clic con el botón derecho) en su dominio, seleccione **propiedades**y, a continuación, seleccione la pestaña **seguridad** .</span><span class="sxs-lookup"><span data-stu-id="e7a74-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="e7a74-135">Seleccione **Opciones avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="e7a74-136">En la pestaña **permisos** , seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="e7a74-137">Seleccione **seleccionar una entidad de identidad**, escriba **usuario1**y, después, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="e7a74-138">En **Se aplica a**, seleccione **Objetos de usuario descendiente**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="e7a74-139">En **Permisos**, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7a74-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="e7a74-140">**Cambiar contraseña**</span><span class="sxs-lookup"><span data-stu-id="e7a74-140">**Change password**</span></span>
    - <span data-ttu-id="e7a74-141">**Restablecer contraseña**</span><span class="sxs-lookup"><span data-stu-id="e7a74-141">**Reset password**</span></span>

10. <span data-ttu-id="e7a74-142">En **Propiedades**, seleccione lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e7a74-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="e7a74-143">**Escribir lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="e7a74-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="e7a74-144">**Escribir pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="e7a74-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="e7a74-145">Seleccione **Aceptar** tres veces para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="e7a74-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="e7a74-146">Cierre **Usuarios y equipos de Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="e7a74-147">A continuación, configure Azure AD Connect en APP1 para la escritura diferida de contraseña.</span><span class="sxs-lookup"><span data-stu-id="e7a74-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="e7a74-148">Si es necesario, conéctese a APP1 con la cuenta TESTLAB\Usuario1.</span><span class="sxs-lookup"><span data-stu-id="e7a74-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="e7a74-149">Desde el escritorio de APP1, haga doble clic en **Azure AD Connect**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="e7a74-150">En la **Página principal**, seleccione **configurar**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="e7a74-151">En la página **tareas adicionales** , seleccione **personalizar opciones de sincronización**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="e7a74-152">En la página **conectar con Azure ad** , escriba las credenciales de la cuenta de administrador global y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="e7a74-153">En las páginas **conectar directorios** y el **filtrado de dominio/unidad organizativa** , seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="e7a74-154">En la página **características opcionales** , seleccione **escritura diferida de contraseñas**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="e7a74-155">En la página **listo para configurar** , seleccione **configurar** y espere a que finalice el proceso.</span><span class="sxs-lookup"><span data-stu-id="e7a74-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="e7a74-156">Cuando vea el finalizar la configuración, seleccione **salir**.</span><span class="sxs-lookup"><span data-stu-id="e7a74-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="e7a74-157">Ya está listo para probar la escritura diferida de contraseñas para los usuarios de equipos que no están conectados a la red virtual de la intranet simulada.</span><span class="sxs-lookup"><span data-stu-id="e7a74-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="e7a74-158">La configuración resultante tiene el siguiente aspecto:</span><span class="sxs-lookup"><span data-stu-id="e7a74-158">Your resulting configuration looks like this:</span></span>

![La empresa simulada con el entorno de prueba con la autenticación de paso a través](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="e7a74-160">Esta configuración se compone de:</span><span class="sxs-lookup"><span data-stu-id="e7a74-160">This configuration consists of:</span></span>

- <span data-ttu-id="e7a74-161">Una suscripción de prueba de Microsoft 365 E5 o de pago con el dominio DNS TESTLAB.\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="e7a74-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="e7a74-162">registrado.</span><span class="sxs-lookup"><span data-stu-id="e7a74-162">registered.</span></span>
- <span data-ttu-id="e7a74-163">Una intranet de organización simplificada conectada a Internet, que consta de las máquinas virtuales DC1, APP1 y cliente1 en una subred de una red virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="e7a74-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e7a74-164">Azure AD Connect se ejecuta en APP1 para sincronizar la lista de cuentas y grupos desde el espacio empresarial de Azure AD de sus suscripciones de Microsoft 365 con el dominio de TESTLAB AD DS.</span><span class="sxs-lookup"><span data-stu-id="e7a74-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="e7a74-165">La escritura diferida de contraseña está habilitada para que los usuarios puedan cambiar sus contraseñas a través de Azure AD sin tener que estar conectados a la intranet simplificada.</span><span class="sxs-lookup"><span data-stu-id="e7a74-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="e7a74-166">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="e7a74-166">Next step</span></span>

<span data-ttu-id="e7a74-167">Explorar características de [identidad](m365-enterprise-test-lab-guides.md#identity) adicionales y funcionalidades en su entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="e7a74-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7a74-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7a74-168">See also</span></span>

[<span data-ttu-id="e7a74-169">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e7a74-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e7a74-170">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e7a74-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e7a74-171">Documentación de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="e7a74-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


