---
title: Configuración básica ligera
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Utilice esta guía de laboratorio de pruebas para crear un entorno de prueba ligero a con objeto de probar Microsoft 365 Enterprise.
ms.openlocfilehash: 6f49982fe71196f3c147c1638b402ee63bb861c1
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202311"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="c9798-103">Configuración básica ligera</span><span class="sxs-lookup"><span data-stu-id="c9798-103">The lightweight base configuration</span></span>

<span data-ttu-id="c9798-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="c9798-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="c9798-105">En este artículo se le ofrecen instrucciones paso a paso para crear un entorno simplificado con una suscripción Microsoft 365 E5 y un equipo que ejecute Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c9798-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![El entorno de pruebas ligero de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="c9798-107">Use el entorno resultante para probar las características y funciones de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="c9798-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="c9798-109">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="c9798-109">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="c9798-110">Fase 1: Crear la suscripción de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c9798-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="c9798-111">Inicie con una suscripción de prueba de Office 365 E5, después, agregue la suscripción a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="c9798-112">Para iniciar la suscripción de prueba a Office 365 E5, primero necesita el nombre de una compañía ficticia y una nueva cuenta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c9798-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="c9798-p101">Le recomendamos que use una variante del nombre de la compañía Contoso para el nombre de su compañía, que es una compañía ficticia usada en contenido de ejemplo de Microsoft, pero no es imprescindible. Anote aquí el nombre de la compañía ficticia: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="c9798-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="c9798-p102">Para registrarse para obtener una nueva cuenta Microsoft, vaya a [https://outlook.com](https://outlook.com) y cree una cuenta con una nueva cuenta y una dirección de correo electrónico. Usará esta cuenta para suscribirse a Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9798-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="c9798-117">Anote aquí el nombre y los apellidos de la nueva cuenta: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="c9798-117">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="c9798-118">Anote aquí la dirección de la nueva cuenta de correo electrónico: ![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="c9798-118">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="c9798-119">Registrarse para una suscripción de prueba a Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="c9798-119">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="c9798-120">Abra el explorador de Internet en su equipo y vaya a [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="c9798-120">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="c9798-121">En la página **Gracias por elegir Office 365 E5**, especifique la dirección de su nueva cuenta de correo electrónico en el paso 1.</span><span class="sxs-lookup"><span data-stu-id="c9798-121">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="c9798-122">En el paso 2 del proceso de suscripción de prueba, escriba la información solicitada y, después, lleve a cabo la comprobación.</span><span class="sxs-lookup"><span data-stu-id="c9798-122">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="c9798-123">En el paso 3, escriba el nombre de la organización y después el nombre de la cuenta que será el administrador global de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="c9798-123">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="c9798-124">En el paso 4, registre la página de inicio de sesión aquí (seleccionar y copiar): ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="c9798-124">For step 4, record the sign-in page here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span> 
6. <span data-ttu-id="c9798-125">Registre aquí el identificador de usuario: ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c9798-125">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="c9798-126">Anote en un lugar seguro la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="c9798-126">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="c9798-127">Este valor se denominará **nombre de administrador global de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="c9798-127">This value will be referred to as the **Office 365 global administrator name**.</span></span>
8. <span data-ttu-id="c9798-128">Haga clic en **Ir a Configuración**.</span><span class="sxs-lookup"><span data-stu-id="c9798-128">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="c9798-129">En el programa de instalación de Office 365 E5, haga clic en **Continuar usando *su organización*.onmicrosoft.com para el correo electrónico e inicio de sesión** y, a continuación, haga clic en **Salir y continuar más tarde**.</span><span class="sxs-lookup"><span data-stu-id="c9798-129">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="c9798-130">Debería ver el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9798-130">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="c9798-131">Tenemos que crear una suscripción de prueba de Office 365 para que su entorno de prueba tenga un inquilino de Azure AD separado de cualquier suscripción de pago que tenga actualmente.</span><span class="sxs-lookup"><span data-stu-id="c9798-131">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="c9798-132">Esta separación significa que puede agregar y quitar usuarios y grupos en el espacio empresarial de prueba sin que afecte a las suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="c9798-132">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="c9798-133">Fase 2: configurar la suscripción de prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="c9798-133">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="c9798-134">En esta fase, se configura la suscripción a Office 365 con usuarios adicionales y se les asignan licencias de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-134">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="c9798-135">Siga las instrucciones que se indican en [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) para conectarse a la suscripción a Office 365 con el módulo Azure Active Directory PowerShell para Graph desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="c9798-135">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="c9798-136">En el cuadro de diálogo **Solicitud de credenciales para Windows PowerShell**, escriba el nombre de administrador global de Office 365 (por ejemplo, svalladares@contosotoycompany.onmicrosoft.com) y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="c9798-136">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="c9798-137">Rellene el nombre de la organización (ejemplo: contosotoycompany), el código de país de dos caracteres para su ubicación, la contraseña de cuenta común y, después, ejecute los comandos siguientes desde el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c9798-137">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="c9798-138">Aquí se usa una contraseña común para automatizar y facilitar la configuración de un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="c9798-138">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="c9798-139">Evidentemente, esto no se recomienda en el caso de suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="c9798-139">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="c9798-140">Guardar información clave para futuras referencias</span><span class="sxs-lookup"><span data-stu-id="c9798-140">Record key information for future reference</span></span>

<span data-ttu-id="c9798-141">Es recomendable que imprima este artículo para registrar la información específica que necesitará para este entorno durante los 30 días de la suscripción de prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="c9798-141">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="c9798-142">Puede extender fácilmente la suscripción de prueba otros 30 días.</span><span class="sxs-lookup"><span data-stu-id="c9798-142">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="c9798-143">Para un entorno de pruebas permanente, cree una nueva suscripción de pago con un inquilino de Azure AD distinto y un número reducido de licencias.</span><span class="sxs-lookup"><span data-stu-id="c9798-143">For a permanent dev/test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="c9798-144">Registre estos valores:</span><span class="sxs-lookup"><span data-stu-id="c9798-144">Record these values:</span></span>
  
- <span data-ttu-id="c9798-145">Nombre del administrador global de Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (del paso 6 de la fase 1)</span><span class="sxs-lookup"><span data-stu-id="c9798-145">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="c9798-146">Guarde también la contraseña de esta cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="c9798-146">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="c9798-147">Nombre de la organización de la suscripción de prueba: ![](./media/Common-Images/TableLine.png) (del paso 4 de la fase 1)</span><span class="sxs-lookup"><span data-stu-id="c9798-147">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="c9798-148">Para mostrar las cuentas de los usuarios 2, 3, 4 y 5, ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9798-148">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="c9798-149">Anote aquí los nombres de las cuentas:</span><span class="sxs-lookup"><span data-stu-id="c9798-149">Record the account names here:</span></span>
    
  - <span data-ttu-id="c9798-150">Nombre de la cuenta de usuario 2: usuario2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c9798-150">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="c9798-151">Nombre de la cuenta de usuario 3: usuario3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c9798-151">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="c9798-152">Nombre de la cuenta de usuario 4: usuario4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c9798-152">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="c9798-153">Nombre de la cuenta de usuario 5: usuario5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="c9798-153">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="c9798-154">También puede guardar la contraseña común de estas cuentas en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="c9798-154">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="c9798-155">Usar un entorno de prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="c9798-155">Using an Office 365 dev/test environment</span></span>

<span data-ttu-id="c9798-156">Si todo lo que necesita es un entorno de prueba de Office 365, puede detenerse aquí.</span><span class="sxs-lookup"><span data-stu-id="c9798-156">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="c9798-157">Consulte las [Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para ver otras guías del laboratorio de pruebas que se aplican a Office 365 y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9798-157">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="c9798-158">Fase 3: agregar una suscripción de prueba a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c9798-158">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="c9798-159">En esta fase se inscribe en la suscripción de evaluación de Microsoft 365 E5 y la agrega a la misma organización de la suscripción de evaluación de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-159">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="c9798-160">Primero, agregue la suscripción de prueba de Microsoft 365 E5 y asigne la nueva licencia de Microsoft 365 a su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c9798-160">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="c9798-161">Con una instancia privada de un explorador de Internet, inicie sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) con sus credenciales de cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c9798-161">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="c9798-162">En la página **Centro de administración de Microsoft 365**, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="c9798-162">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="c9798-163">En la página **Servicios de compra**, haga clic en \*\*Microsoft 365 E5 \*\*y, después, haga clic en **Obtener la versión de prueba gratuita**.</span><span class="sxs-lookup"><span data-stu-id="c9798-163">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="c9798-164">En la página de la **Versión de prueba de Microsoft 365 E5**, elija entre recibir una llamada o un mensaje de texto, escriba el número de teléfono y haga clic en **Enviarme un mensaje de texto** o **Llamarme**.</span><span class="sxs-lookup"><span data-stu-id="c9798-164">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="c9798-165">Realice la comprobación.</span><span class="sxs-lookup"><span data-stu-id="c9798-165">Perform the verification.</span></span>

5. <span data-ttu-id="c9798-166">En la página **Confirmar pedido**, haga clic en **Probar ahora**.</span><span class="sxs-lookup"><span data-stu-id="c9798-166">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="c9798-167">En la página **Recibo del pedido**, haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="c9798-167">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="c9798-168">En el Centro de administración de Microsoft 365, haga clic en **Usuarios > Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="c9798-168">On the Microsoft 365 admin center tab, click **Users > Active users**.</span></span>

8. <span data-ttu-id="c9798-169">En **Usuarios activos**, haga clic en su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="c9798-169">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="c9798-170">Seleccione **Licencias y aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="c9798-170">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="c9798-171">Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-171">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="c9798-172">Haga clic en **Guardar cambios** y, después, cierre el panel de información de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="c9798-172">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="c9798-173">Después, repita los pasos del 8 al 11 del procedimiento anterior para todas las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).</span><span class="sxs-lookup"><span data-stu-id="c9798-173">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9798-174">La suscripción de prueba de Microsoft 365 E5 tiene una duración de 30 días.</span><span class="sxs-lookup"><span data-stu-id="c9798-174">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="c9798-175">Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con un bajo número de licencias.</span><span class="sxs-lookup"><span data-stu-id="c9798-175">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="c9798-176">Su entorno de desarrollo y prueba ahora tiene:</span><span class="sxs-lookup"><span data-stu-id="c9798-176">Your test environment now has:</span></span>
  
- <span data-ttu-id="c9798-177">Una suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-177">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="c9798-178">Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-178">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="c9798-179">Esta es la configuración resultante, que agrega Microsoft 365 E5, que incluye Office 365 y Enterprise Security + administración (EMS).</span><span class="sxs-lookup"><span data-stu-id="c9798-179">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Fase 3 del entorno de prueba de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="c9798-181">Fase 4: crear un equipo con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9798-181">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="c9798-182">En esta fase se crea un equipo independiente que ejecuta Windows 10 Enterprise como equipo físico, máquina virtual o máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="c9798-182">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="c9798-183">Equipo físico</span><span class="sxs-lookup"><span data-stu-id="c9798-183">Physical computer</span></span>

<span data-ttu-id="c9798-p109">Obtenga un equipo personal e instale Windows 10 Enterprise en él. Puede descargar la versión de evaluación de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="c9798-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="c9798-186">Máquina virtual</span><span class="sxs-lookup"><span data-stu-id="c9798-186">Virtual machine</span></span>

<span data-ttu-id="c9798-p110">Cree una máquina virtual con el hipervisor que prefiera e instale Windows 10 Enterprise en ella. Puede descargar la versión de evaluación de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="c9798-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="c9798-189">Máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="c9798-189">Virtual machine in Azure</span></span>

<span data-ttu-id="c9798-p111">Para crear una máquina virtual con Windows 10 en Microsoft Azure ***necesita tener una suscripción basada en Visual Studio***, que tiene acceso a la imagen de Windows 10 Enterprise. Otros tipos de suscripciones de Azure, como las suscripciones de prueba y suscripciones de pago, no tienen acceso a esta imagen. Para obtener la información más reciente, vea [Usar el cliente de Windows en Azure para escenarios de desarrollo y pruebas](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="c9798-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9798-p112">Los siguientes conjuntos de comandos usan la versión más reciente de Azure PowerShell. Vea [Introducción a los cmdlets de Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Estos conjuntos de comandos compilan una máquina virtual con Windows 10 Enterprise llamada WIN10 y toda la infraestructura necesaria, que incluye un grupo de recursos, una cuenta de almacenamiento y una red virtual. Si ya está familiarizado con los servicios de infraestructura de Azure, adapte estas instrucciones para que se ajusten a la infraestructura implementada actualmente.</span><span class="sxs-lookup"><span data-stu-id="c9798-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="c9798-197">En primer lugar, abra un símbolo del sistema de Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9798-197">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="c9798-198">Inicie sesión en su cuenta de Azure con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="c9798-198">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="c9798-199">Obtenga su nombre de suscripción mediante el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="c9798-199">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="c9798-p113">Configure su suscripción de Azure. Cambie todo el contenido entrecomillado, incluidos los caracteres \< y >, por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="c9798-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="c9798-p114">Después, cree un nuevo grupo de recursos. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.</span><span class="sxs-lookup"><span data-stu-id="c9798-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="c9798-p115">Cree el nuevo grupo de recursos con estos comandos. Reemplace todo el contenido entrecomillado, incluidos los caracteres \< y > , por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="c9798-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="c9798-p116">Después, cree una red virtual y la máquina virtual WIN10 con estos comandos. Cuando se le pida, indique el nombre y contraseña de la cuenta de administrador local para WIN10 y guárdelos en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="c9798-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="c9798-208">Fase 5: unir el equipo con Windows 10 a Azure AD</span><span class="sxs-lookup"><span data-stu-id="c9798-208">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="c9798-209">Después de crear la máquina física o virtual con Windows 10 Enterprise, inicie sesión con una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="c9798-209">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c9798-210">En el caso de una máquina virtual de Azure, conéctela siguiendo [estas instrucciones](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="c9798-210">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="c9798-211">Después, una el equipo WIN10 al espacio empresarial de Azure AD de la suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-211">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="c9798-212">En el escritorio del equipo WIN10, haga clic en **Inicio > Configuración > Cuentas > Obtener acceso a trabajo o escuela > Conectarse**.</span><span class="sxs-lookup"><span data-stu-id="c9798-212">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="c9798-213">En el cuadro de diálogo **Set up a work or school account** (Configurar una cuenta profesional o educativa), haga clic en **Join this device to Azure Active Directory** (Unir este dispositivo a Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="c9798-213">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="c9798-214">En **Cuenta profesional o educativa**, escriba el nombre de la cuenta de administrador global de la suscripción de Microsoft 365 E5 y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="c9798-214">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="c9798-215">En **Escribir contraseña**, escriba la contraseña de la cuenta de administrador global y luego haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="c9798-215">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="c9798-216">Cuando se le pida que confirme que es su organización, haga clic en **Unir** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="c9798-216">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="c9798-217">Cierre la ventana de configuración.</span><span class="sxs-lookup"><span data-stu-id="c9798-217">Close the settings window.</span></span>
    
<span data-ttu-id="c9798-218">Después, instale Office 365 ProPlus en el equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="c9798-218">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="c9798-219">Abra el explorador Microsoft Edge e inicie sesión en el portal de Office con las credenciales de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="c9798-219">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="c9798-220">Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="c9798-220">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="c9798-221">En la pestaña **Inicio de Microsoft Office**, haga clic en **Instalar Office**.</span><span class="sxs-lookup"><span data-stu-id="c9798-221">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="c9798-222">Cuando se le pregunte qué hacer, haga clic en **Ejecutar** y luego en **Sí** para **Control de cuentas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="c9798-222">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="c9798-p118">Espere hasta que se complete la instalación de Office. Cuando vea **Ya está listo**, haga clic en **Cerrar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="c9798-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="c9798-225">Este es el entorno resultante.</span><span class="sxs-lookup"><span data-stu-id="c9798-225">Here is your resulting environment.</span></span>

![Fase 5 del entorno de prueba de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="c9798-227">Esto incluye el equipo WIN10 que tiene:</span><span class="sxs-lookup"><span data-stu-id="c9798-227">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="c9798-228">Se unió al espacio empresarial de Azure AD de su suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="c9798-228">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="c9798-229">Se inscribió como un dispositivo de Azure AD en Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="c9798-229">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="c9798-230">Tiene instalado Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="c9798-230">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="c9798-231">Ahora está preparado para experimentar con otras características de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="c9798-231">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="c9798-232">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c9798-232">Next steps</span></span>

<span data-ttu-id="c9798-233">Explore estos conjuntos adicionales de guías de laboratorio de pruebas:</span><span class="sxs-lookup"><span data-stu-id="c9798-233">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="c9798-234">Identidad</span><span class="sxs-lookup"><span data-stu-id="c9798-234">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="c9798-235">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="c9798-235">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="c9798-236">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="c9798-236">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="c9798-237">Vea también</span><span class="sxs-lookup"><span data-stu-id="c9798-237">See also</span></span>

[<span data-ttu-id="c9798-238">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9798-238">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c9798-239">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9798-239">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c9798-240">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c9798-240">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
