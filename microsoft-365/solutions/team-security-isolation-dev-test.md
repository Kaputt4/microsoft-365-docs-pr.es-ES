---
title: Configurar un equipo con aislamiento de seguridad en un entorno de desarrollo y pruebas
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: Configure la infraestructura y seguridad que permita a los empleados trabajar de forma remota desde cualquier lugar y en cualquier momento.
ms.openlocfilehash: c58f0849937d7a807c9969e1651c51b3a9470ba5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228608"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="6d9a0-103">Configurar un equipo con aislamiento de seguridad en un entorno de desarrollo y pruebas</span><span class="sxs-lookup"><span data-stu-id="6d9a0-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="6d9a0-104">Este artículo proporciona instrucciones paso a paso para crear un [equipo con de aislamiento de seguridad](secure-teams-security-isolation.md) en un entorno de desarrollo y prueba.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![Configuración del equipo Estrategia empresarial aislada](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="6d9a0-106">Use este entorno de desarrollo y pruebas para experimentar y adaptar la configuración a sus necesidades específicas antes de implementar este tipo de equipo en producción.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="6d9a0-107">Fase 1: Crear el entorno de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6d9a0-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="6d9a0-108">Si solamente quiere probar los equipos confidenciales y extremadamente confidenciales de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración básica ligera](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="6d9a0-109">Si quiere probar los equipos confidenciales y con un nivel de confidencialidad alto en una empresa simulada, siga las instrucciones de [Sincronización de hash de contraseñas](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6d9a0-110">Probar equipos con aislamiento de seguridad no requiere el entorno de pruebas de una empresa simulada, que incluye una intranet simulada conectada a Internet y la sincronización de directorios de un bosque de Active Directory Domain Services (AD DS).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-110">Testing a team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="6d9a0-111">Aquí se ofrece como una opción para que pueda probar un equipo con aislamiento de seguridad y experimentar con ella en un entorno que representa una organización típica.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a><span data-ttu-id="6d9a0-112">Fase 2: Crear y configurar los usuarios y grupos de Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="6d9a0-112">Phase 2: Create and configure your Azure Active Directory (Azure AD) group and users</span></span>

<span data-ttu-id="6d9a0-113">En esta fase se crea y configuran un grupo y usuarios de Azure AD para la organización ficticia.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>

<span data-ttu-id="6d9a0-114">En primer lugar, cree un grupo de seguridad con Azure Portal.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-114">First, create a security group with the Azure portal.</span></span>

1. <span data-ttu-id="6d9a0-115">Cree una pestaña aparte en el explorador y, después, vaya a Azure Portal, en [https://portal.azure.com](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="6d9a0-116">Si es necesario, inicie sesión con las credenciales de la cuenta de administrador global de la suscripción de pago o de la suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>

2. <span data-ttu-id="6d9a0-117">En Azure Portal, haga clic en **Azure Active Directory > Grupos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="6d9a0-118">En la hoja **Todos los grupos**, haga clic en **+ Nuevo grupo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="6d9a0-119">En la hoja **Grupo**:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-119">On the **Group** blade:</span></span>

  - <span data-ttu-id="6d9a0-120">Seleccione **Seguridad** en **Tipo de grupo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-120">Select **Security** in **Group type**.</span></span>

  - <span data-ttu-id="6d9a0-121">Escriba **Directivos** en **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-121">Type **C-Suite** in **Name**.</span></span>

  - <span data-ttu-id="6d9a0-122">Seleccione **Asignada** en **Tipo de pertenencia**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-122">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="6d9a0-123">Haga clic en **Crear** y, después, cierre la hoja **Grupo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-123">Click **Create**, and then close the **Group** blade.</span></span>

<span data-ttu-id="6d9a0-124">Después, configure la licencia automática para que se asigne automáticamente una licencia de Microsoft 365 E5 a los miembros del grupo **C-Suite** nuevo.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-124">Next, configure automatic licensing so that members of the new **C-Suite** group are automatically assigned a Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="6d9a0-125">En Azure Portal, haga clic en **Azure Active Directory > Licencias > Todos los productos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="6d9a0-126">En la lista, seleccione **Microsoft 365 Enterprise E5** y haga clic en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>

3. <span data-ttu-id="6d9a0-127">En la hoja **Asignar licencia**, haga clic en **Usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-127">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="6d9a0-128">En la lista de grupos, seleccione el grupo de **C-Suite**</span><span class="sxs-lookup"><span data-stu-id="6d9a0-128">In the list of groups, select the **C-Suite** group.</span></span>

5. <span data-ttu-id="6d9a0-129">Haga clic en **Seleccionar** y, después, en **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-129">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="6d9a0-130">Cierre la pestaña Azure Portal del explorador.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-130">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="6d9a0-131">Después, [conéctese al módulo de PowerShell de Azure Active Directory para Graph](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="6d9a0-132">Rellene el nombre de la organización, la ubicación y una contraseña común; después, ejecute los siguientes comandos desde el símbolo del sistema de PowerShell o el entorno de scripts integrado (ISE) para crear nuevas cuentas de usuario y agregarlas al grupo de C-Suite:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>

```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="6d9a0-p103">El uso de una contraseña común aquí es para la automatización y la facilidad de configuración para un entorno de desarrollo / prueba. Obviamente, esto está muy desaconsejado para las suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-p103">The use of a common password here is for automation and ease of configuration for a dev/test environment. Obviously, this is highly discouraged for production subscriptions.</span></span>

<span data-ttu-id="6d9a0-135">Después, siga estos pasos para comprobar que la asignación de licencias basada en grupos funcione correctamente.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-135">Use these steps to verify that group-based licensing is working correctly.</span></span>

1. <span data-ttu-id="6d9a0-136">Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

2. <span data-ttu-id="6d9a0-137">En la nueva pestaña **Centro de administración de Microsoft 365** del explorador, haga clic en **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="6d9a0-138">En la lista de usuarios, haga clic en **CEO** (Consejero delegado).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-138">In the list of users, click **CEO**.</span></span>

4. <span data-ttu-id="6d9a0-139">En el panel que muestra las propiedades de la cuenta de usuario **CEO**, compruebe que dicha cuenta tiene asignada la licencia **Microsoft 365 Enterprise E5** en **Licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>

## <a name="phase-3-create-your-team"></a><span data-ttu-id="6d9a0-140">Fase 3: Crear el equipo</span><span class="sxs-lookup"><span data-stu-id="6d9a0-140">Phase 3: Create your team</span></span>

<span data-ttu-id="6d9a0-141">En esta fase, debe crear y configurar un equipo con aislamiento de seguridad para que los miembros del equipo de directiva puedan colaborar en la estrategia de la empresa.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="6d9a0-142">Antes de proceder con los pasos de este artículo, debe habilitar [etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Office 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="6d9a0-143">Después, cree el equipo:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-143">Next, create the team:</span></span>

1. <span data-ttu-id="6d9a0-144">En Teams, haga clic en **Teams** en el lado izquierdo de la aplicación, luego haga clic en **Unirse o crear un equipo** en la parte inferior de la lista de equipos.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="6d9a0-145">Haga clic en **Crear equipo** (primera tarjeta, esquina superior izquierda).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="6d9a0-146">Elija **Crear un equipo desde cero**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="6d9a0-147">En la lista **Confidencialidad**, conserve el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="6d9a0-148">En **Privacidad**, haga clic en **Privado**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="6d9a0-149">Escriba **Estrategia de la empresa** y, después, haga clic en **Crear** > **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="6d9a0-150">A continuación, limite la creación de canales privados a los propietarios del grupo de Estrategia empresarial.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-150">Next, restrict the creation of private channels to owners of the Company Strategy group.</span></span>

1. <span data-ttu-id="6d9a0-151">En el equipo, haga clic en **Más opciones** y después en **Administrar equipo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-151">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="6d9a0-152">En la pestaña **Configuración**, expanda **Permisos de los miembros**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-152">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="6d9a0-153">Desactive la casilla de verificación **Permitir a los miembros crear canales privados**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-153">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="6d9a0-154">Después, debe configurar una etiqueta de confidencialidad aparte con la siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-154">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="6d9a0-155">El nombre es Estrategia de la empresa</span><span class="sxs-lookup"><span data-stu-id="6d9a0-155">The name is Company Strategy</span></span>
- <span data-ttu-id="6d9a0-156">El cifrado está habilitado.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-156">Encryption is enabled</span></span>
- <span data-ttu-id="6d9a0-157">El grupo Estrategia de empresa tiene permisos de coautoría.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-157">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="6d9a0-158">Siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-158">Follow these steps:</span></span>

1. <span data-ttu-id="6d9a0-159">Abra el [Centro de cumplimiento de Microsoft 365](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="6d9a0-160">En **Soluciones**, haga clic en **Protección de la información**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="6d9a0-161">Haga clic en **Crear una etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="6d9a0-162">Escriba **Estrategia de la empresa** en el nombre de la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-162">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="6d9a0-163">Escriba **Documentos de estrategia empresarial de la directiva** como información y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-163">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="6d9a0-164">En la página **Cifrado**, en el menú desplegable **Cifrado**, elija **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="6d9a0-165">Para agregar los permisos de equipo:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="6d9a0-166">a.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-166">a.</span></span> <span data-ttu-id="6d9a0-167">Haga clic en **Asignar permisos**</span><span class="sxs-lookup"><span data-stu-id="6d9a0-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="6d9a0-168">b.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-168">b.</span></span> <span data-ttu-id="6d9a0-169">Haga clic en **Agregar usuarios o grupos**, seleccione **Estrategia de la empresa** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-169">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="6d9a0-170">c.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-170">c.</span></span> <span data-ttu-id="6d9a0-171">Haga clic en **Elegir permisos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="6d9a0-172">d.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-172">d.</span></span> <span data-ttu-id="6d9a0-173">Elija **coautoría** de la lista desplegable y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="6d9a0-174">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-174">Click **Next**.</span></span>
9. <span data-ttu-id="6d9a0-175">En **Distintivo de contenido**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-175">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="6d9a0-176">En la página **Configuración de sitio y grupo**, establezca **Configuración de sitio y grupo** como **Activado**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-176">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="6d9a0-177">En el menú desplegable **Privacidad de los sitios de equipo conectados a grupos de Office 365**, elija **Privado: solo los miembros pueden acceder al sitio**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-177">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="6d9a0-178">En **Equipos no administrados**, elija **Bloquear el acceso**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-178">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="6d9a0-179">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-179">Click **Next**.</span></span>
14. <span data-ttu-id="6d9a0-180">En la página **Etiquetado automático para las aplicaciones de Office**, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-180">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="6d9a0-181">Haga clic en **Enviar** y después en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-181">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="6d9a0-182">Después, publique la nueva etiqueta con estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6d9a0-182">Next, publish the new label with these steps:</span></span>

1. <span data-ttu-id="6d9a0-183">En el Centro de cumplimiento de Microsoft 365, en la página **Protección de la información**, escoja la pestaña **Directivas de etiqueta**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-183">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="6d9a0-184">Haga clic en **Publicar etiquetas**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-184">Click **Publish labels**.</span></span>
3. <span data-ttu-id="6d9a0-185">En la página **Elegir etiquetas de confidencialidad para publicar**, haga clic en **Elija las etiquetas de confidencialidad para publicar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-185">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="6d9a0-186">Seleccione **Estrategia de la empresa** y, después, haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-186">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="6d9a0-187">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-187">Click **Next**.</span></span>
6. <span data-ttu-id="6d9a0-188">En la página **Publicar a usuarios y grupos**, haga clic en **Elija usuarios y grupos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-188">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="6d9a0-189">Haga clic en **Agregar** y, después, seleccione **Estrategia de la empresa**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-189">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="6d9a0-190">Haga clic en **Agregar** y, a continuación en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-190">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="6d9a0-191">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-191">Click **Next**.</span></span>
10. <span data-ttu-id="6d9a0-192">En la página Configuración de la directiva, active la casilla de verificación **Los usuarios deben ofrecer una justificación para quitar una etiqueta o una etiqueta de clasificación inferior** y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-192">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="6d9a0-193">Escriba **Estrategia empresarial** el nombre de la directiva y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-193">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="6d9a0-194">Haga clic en **Enviar** y después en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-194">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="6d9a0-195">La etiqueta **Estrategia empresarial** puede tardar algún tiempo en estar disponible una vez que se ha publicado.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-195">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="6d9a0-196">Después, aplique la nueva etiqueta al equipo **Estrategia empresarial** y actualice el tipo de vínculo para compartir predeterminado con el fin de reducir el riesgo de compartir por error archivos y carpetas a un público más amplio del previsto.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-196">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

1. <span data-ttu-id="6d9a0-197">Abra el [Centro de administración de SharePoint](https://admin.microsoft.com/sharepoint).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-197">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="6d9a0-198">En **Sitios**, haga clic en **Sitios activos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-198">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="6d9a0-199">Haga clic en el sitio **Estrategia empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-199">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="6d9a0-200">En **Uso compartido externo** de la pestaña **Confidencialidad**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-200">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="6d9a0-201">Seleccione la etiqueta **Estrategia empresarial** y, después, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-201">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="6d9a0-202">En **Uso compartido externo** de la pestaña **Directivas**, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-202">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="6d9a0-203">Elija **Solo personas de la organización**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-203">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="6d9a0-204">En **Tipo de vínculo de uso compartido predeterminado**, desactive la casilla de verificación **Igual que la configuración de nivel de organización** y seleccione **Usuarios con acceso existente**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-204">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="6d9a0-205">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-205">Click **Save**.</span></span>

<span data-ttu-id="6d9a0-206">Después, configure el uso compartido de los propietarios solo para el equipo de **Estrategia empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-206">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="6d9a0-207">En Teams, vaya a la pestaña **General** del equipo **Estrategia empresarial**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-207">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="6d9a0-208">En la barra de herramientas del equipo, haga clic en **Archivos**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-208">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="6d9a0-209">Haga clic en los puntos suspensivos y, luego, en **Abrir en SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-209">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="6d9a0-210">En la barra de herramientas, haga clic en el sitio de SharePoint subyacente, en el icono de configuración y, luego, en **Permisos del sitio**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-210">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="6d9a0-211">En el panel Permisos del sitio, en **Uso compartido del sitio**, haga clic en **Cambiar cómo pueden compartir los miembros**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-211">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="6d9a0-212">En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas, además del sitio** y, luego, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-212">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="6d9a0-213">Cierre los paneles **Permisos** y **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-213">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="6d9a0-214">Si inicia sesión como miembro del grupo Estrategia empresarial, verá **Estrategia empresarial** en la opción **Confidencialidad** en la barra de herramientas Inicio de Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-214">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="6d9a0-215">Seleccione la etiqueta **Estrategia empresarial** en la opción **Confidencialidad** para asignar dicha etiqueta a un archivo.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-215">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="6d9a0-216">Esta es la configuración resultante del equipo Estrategia empresarial.</span><span class="sxs-lookup"><span data-stu-id="6d9a0-216">Here is the resulting configuration for the Company Strategy team.</span></span>

![Configuración del equipo Estrategia empresarial aislada](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a><span data-ttu-id="6d9a0-218">Paso siguiente</span><span class="sxs-lookup"><span data-stu-id="6d9a0-218">Next step</span></span>

<span data-ttu-id="6d9a0-219">Cuando esté listo para la implementación de producción, vea estas [instrucciones de configuración](secure-teams-security-isolation.md).</span><span class="sxs-lookup"><span data-stu-id="6d9a0-219">When you're ready for production deployment, see these [configuration instructions](secure-teams-security-isolation.md).</span></span>
