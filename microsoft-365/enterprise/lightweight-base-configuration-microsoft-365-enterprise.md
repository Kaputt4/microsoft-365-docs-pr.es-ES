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
ms.openlocfilehash: ff9577fb461429fd8d4628dc0eea6b8a35664fbc
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672746"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="dccf4-103">Configuración básica ligera</span><span class="sxs-lookup"><span data-stu-id="dccf4-103">The lightweight base configuration</span></span>

<span data-ttu-id="dccf4-104">*Esta guía del laboratorio de pruebas puede usarse tanto para entornos de prueba de Microsoft 365 Enterprise como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="dccf4-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="dccf4-105">En este artículo se le ofrecen instrucciones paso a paso para crear un entorno simplificado con una suscripción Microsoft 365 E5 y un equipo que ejecute Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="dccf4-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![El entorno de pruebas ligero de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="dccf4-107">Use el entorno resultante para probar las características y funciones de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="dccf4-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="dccf4-109">Haga clic [aquí](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="dccf4-109">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="dccf4-110">Fase 1: Crear la suscripción de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="dccf4-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="dccf4-111">Inicie con una suscripción de prueba de Office 365 E5, después, agregue la suscripción a Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="dccf4-112">Para iniciar la suscripción de prueba a Office 365 E5, primero necesita el nombre de una compañía ficticia y una nueva cuenta Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dccf4-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="dccf4-p101">Le recomendamos que use una variante del nombre de la compañía Contoso para el nombre de su compañía, que es una compañía ficticia usada en contenido de ejemplo de Microsoft, pero no es imprescindible. Anote aquí el nombre de la compañía ficticia: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="dccf4-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="dccf4-p102">Para registrarse para obtener una nueva cuenta Microsoft, vaya a [https://outlook.com](https://outlook.com) y cree una cuenta con una nueva cuenta y una dirección de correo electrónico. Usará esta cuenta para suscribirse a Office 365.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="dccf4-117">Anote aquí el nombre y los apellidos de la nueva cuenta: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="dccf4-117">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="dccf4-118">Anote aquí la dirección de la nueva cuenta de correo electrónico: ![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="dccf4-118">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="dccf4-119">Registrarse para una suscripción de prueba a Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="dccf4-119">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="dccf4-120">Abra el explorador de Internet en su equipo y vaya a [https://aka.ms/e5trial](https://aka.ms/e5trial).</span><span class="sxs-lookup"><span data-stu-id="dccf4-120">For the lightweight Office 365 dev/test environment, open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="dccf4-121">En la página **Bienvenido. Permítanos conocerle**, especifique:</span><span class="sxs-lookup"><span data-stu-id="dccf4-121">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="dccf4-122">Su ubicación física</span><span class="sxs-lookup"><span data-stu-id="dccf4-122">Your physical location</span></span>
    
  - <span data-ttu-id="dccf4-123">El nombre y apellidos de la nueva cuenta de Microsoft</span><span class="sxs-lookup"><span data-stu-id="dccf4-123">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="dccf4-124">La dirección de la nueva cuenta de correo</span><span class="sxs-lookup"><span data-stu-id="dccf4-124">Your new email account address</span></span>
    
  - <span data-ttu-id="dccf4-125">El número de teléfono del trabajo</span><span class="sxs-lookup"><span data-stu-id="dccf4-125">A business phone number</span></span>
    
  - <span data-ttu-id="dccf4-126">El nombre de la compañía ficticia</span><span class="sxs-lookup"><span data-stu-id="dccf4-126">Your fictional company name</span></span>
    
  - <span data-ttu-id="dccf4-127">El tamaño de la organización (250 a 999 personas)</span><span class="sxs-lookup"><span data-stu-id="dccf4-127">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="dccf4-128">Haga clic en **Un solo paso más**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-128">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="dccf4-129">En la página **Crear su id. de usuario**, escriba un nombre de usuario basado en la nueva dirección de correo, la empresa ficticia después del signo @ (quite todos los espacios en el nombre) y una contraseña (dos veces) para esta nueva cuenta de Office 365. </span><span class="sxs-lookup"><span data-stu-id="dccf4-129">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="dccf4-130">Anote en un lugar seguro la contraseña que escriba.</span><span class="sxs-lookup"><span data-stu-id="dccf4-130">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="dccf4-131">Anote aquí el nombre de la compañía ficticia, que se denominará **nombre de la organización**: ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="dccf4-131">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="dccf4-132">Haga clic en **Crear mi cuenta**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-132">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="dccf4-p103">En la página **Demuestre. Que. No. Es. Un. Robot.**, escriba el número de teléfono de su teléfono compatible con texto y, después, haga clic en **Enviarme un mensaje**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p103">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="dccf4-135">Escriba el código de verificación del mensaje de texto recibido y, después, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-135">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="dccf4-136">Anote aquí la URL de la página de inicio de sesión (seleccionar y copiar): ![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="dccf4-136">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="dccf4-137">Anote aquí el identificador de usuario (seleccionar y copiar): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dccf4-137">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="dccf4-138">Este valor se denominará **nombre de administrador global de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-138">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="dccf4-139">Cuando vea **Ya está listo**, haga clic.</span><span class="sxs-lookup"><span data-stu-id="dccf4-139">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="dccf4-140">En la página siguiente, espere hasta que Office 365 complete la configuración y estén disponibles todos los iconos.</span><span class="sxs-lookup"><span data-stu-id="dccf4-140">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="dccf4-141">Debe ver la Página principal del portal 365 de Office, desde la que puede obtener acceso a los servicios de Office y al centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dccf4-141">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="dccf4-142">Tenemos que crear una suscripción de prueba de Office 365 para que su entorno de desarrollo y prueba tenga un espacio empresarial de Azure AD separado de cualquier suscripción de pago que tenga actualmente. </span><span class="sxs-lookup"><span data-stu-id="dccf4-142">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="dccf4-143">Esta separación significa que puede agregar y quitar usuarios y grupos en el espacio empresarial de prueba sin que afecte a las suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="dccf4-143">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="dccf4-144">Fase 2: configurar la suscripción de prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="dccf4-144">Phase 3: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="dccf4-145">En esta fase, se configura la suscripción a Office 365 con usuarios adicionales y se les asignan licencias de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-145">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="dccf4-146">Siga las instrucciones que se indican en [Conectarse a PowerShell de Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) para conectarse a la suscripción a Office 365 con el módulo Azure Active Directory PowerShell para Graph desde su equipo.</span><span class="sxs-lookup"><span data-stu-id="dccf4-146">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from:</span></span>
    
<span data-ttu-id="dccf4-147">En el cuadro de diálogo Solicitud de credenciales para Windows PowerShell, escriba el nombre de administrador global de Office 365 (por ejemplo, svalladares@contosotoycompany.onmicrosoft.com) y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="dccf4-147">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="dccf4-148">Rellene el nombre de la organización (ejemplo: contosotoycompany), el código de país de dos caracteres para su ubicación, la contraseña de cuenta común y, después, ejecute los comandos siguientes desde el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="dccf4-148">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="dccf4-149">Se usa una contraseña común para automatizar y facilitar la configuración de un entorno de prueba y desarrollo.</span><span class="sxs-lookup"><span data-stu-id="dccf4-149">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="dccf4-150">Evidentemente, esto no se recomienda en el caso de suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="dccf4-150">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="dccf4-151">Guardar información clave para futuras referencias</span><span class="sxs-lookup"><span data-stu-id="dccf4-151">Record key information for future reference</span></span>

<span data-ttu-id="dccf4-152">Es recomendable que imprima este artículo para registrar la información específica que necesitará para este entorno durante los 30 días de la suscripción de prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="dccf4-152">You might want to print this article to record the specific values that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="dccf4-153">Puede extender fácilmente la suscripción de prueba otros 30 días.</span><span class="sxs-lookup"><span data-stu-id="dccf4-153">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="dccf4-154">Para un entorno de desarrollo y pruebas permanentes, cree una nueva suscripción de pago con un espacio empresarial de Azure AD distinto y un número reducido de licencias.</span><span class="sxs-lookup"><span data-stu-id="dccf4-154">For a permanent dev/test environment, create a new paid subscription with a small number of licenses.</span></span>

<span data-ttu-id="dccf4-155">Registre estos valores:</span><span class="sxs-lookup"><span data-stu-id="dccf4-155">Record these values:</span></span>
  
- <span data-ttu-id="dccf4-156">Nombre del administrador global de Office 365: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (del paso 9 de la fase 2)</span><span class="sxs-lookup"><span data-stu-id="dccf4-156">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="dccf4-157">Guarde también la contraseña de esta cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="dccf4-157">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="dccf4-158">Nombre de la organización de la suscripción de prueba: ![](./media/Common-Images/TableLine.png) (del paso 4 de la fase 2)</span><span class="sxs-lookup"><span data-stu-id="dccf4-158">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="dccf4-159">Para mostrar las cuentas de los usuarios 2, 3, 4 y 5, ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dccf4-159">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="dccf4-160">Anote aquí los nombres de las cuentas:</span><span class="sxs-lookup"><span data-stu-id="dccf4-160">Record the account names here:</span></span>
    
  - <span data-ttu-id="dccf4-161">Nombre de la cuenta de usuario 2: usuario2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dccf4-161">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="dccf4-162">Nombre de la cuenta de usuario 3: usuario3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dccf4-162">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="dccf4-163">Nombre de la cuenta de usuario 4: usuario4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dccf4-163">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="dccf4-164">Nombre de la cuenta de usuario 5: usuario5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dccf4-164">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="dccf4-165">También puede guardar la contraseña común de estas cuentas en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="dccf4-165">Also record the passwords for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-devtest-environment"></a><span data-ttu-id="dccf4-166">Usar un entorno de desarrollo y pruebas de Office 365</span><span class="sxs-lookup"><span data-stu-id="dccf4-166">Phase 1: Create an Office 365 dev/test environment</span></span>

<span data-ttu-id="dccf4-167">Si solo necesita un entorno de desarrollo y pruebas de Office 365, vea está información.</span><span class="sxs-lookup"><span data-stu-id="dccf4-167">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="dccf4-168">Consulte las [Guías del laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md) para ver otras guías del laboratorio de pruebas que se aplican a Office 365 y Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dccf4-168">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="dccf4-169">Fase 3: agregar una suscripción de prueba a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="dccf4-169">Phase 2: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="dccf4-170">En esta fase se inscribe en la suscripción de evaluación de Microsoft 365 E5 y la agrega a la misma organización de la suscripción de evaluación de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-170">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="dccf4-171">Primero agregue la suscripción de prueba de Microsoft 365 E5 y asigne una licencia de Microsoft 365 a su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="dccf4-171">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="dccf4-172">Con una instancia privada de un explorador de Internet, inicie sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) con sus credenciales de cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="dccf4-172">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="dccf4-173">En la página **Centro de administración de Microsoft 365**, en el panel de navegación izquierdo, haga clic en **Facturación > Servicios de compra**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-173">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="dccf4-174">En la página **Servicios de compra**, busque el elemento **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-174">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="dccf4-175">Mantenga el puntero del ratón sobre dicho elemento y haga clic en **Iniciar prueba gratuita**. </span><span class="sxs-lookup"><span data-stu-id="dccf4-175">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="dccf4-176">En la página de la **Versión de prueba de Microsoft 365 E5**, elija entre recibir una llamada o un mensaje de texto, escriba el número de teléfono y haga clic en **Enviarme un mensaje de texto** o **Llamarme**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-176">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="dccf4-177">En la página **Confirmar pedido**, haga clic en **Probar ahora**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-177">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="dccf4-178">En la página **Recibo del pedido**, haga clic en **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-178">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="dccf4-179">En el Centro de administración de Microsoft 365, haga clic en **Usuarios activos** y en su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="dccf4-179">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="dccf4-180">Haga clic en **Editar** para **Licencias de productos**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-180">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="dccf4-181">Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-181">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="dccf4-182">Haga clic en **Guardar > Cerrar > Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-182">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="dccf4-183">Después, repita los pasos del 8 al 11 del procedimiento anterior para todas las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).</span><span class="sxs-lookup"><span data-stu-id="dccf4-183">Next, repeat steps 8 and 9 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dccf4-184">La suscripción de prueba de Microsoft 365 E5 tiene una duración de 30 días.</span><span class="sxs-lookup"><span data-stu-id="dccf4-184">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="dccf4-185">Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con unas pocas licencias.</span><span class="sxs-lookup"><span data-stu-id="dccf4-185">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="dccf4-186">Su entorno de desarrollo y prueba ahora tiene:</span><span class="sxs-lookup"><span data-stu-id="dccf4-186">Your test environment now has:</span></span>
  
- <span data-ttu-id="dccf4-187">Una suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-187">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="dccf4-188">Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-188">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="dccf4-189">Esta es la configuración resultante, que agrega Microsoft 365 E5, que incluye Office 365 y Enterprise Security + administración (EMS).</span><span class="sxs-lookup"><span data-stu-id="dccf4-189">Figure 1 shows your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Fase 2 del entorno de prueba de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="dccf4-191">Fase 4: crear un equipo con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dccf4-191">Phase 3: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="dccf4-192">En esta fase se crea un equipo independiente que ejecuta Windows 10 Enterprise como equipo físico, máquina virtual o máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="dccf4-192">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="dccf4-193">Equipo físico</span><span class="sxs-lookup"><span data-stu-id="dccf4-193">Physical computer</span></span>

<span data-ttu-id="dccf4-p109">Obtenga un equipo personal e instale Windows 10 Enterprise en él. Puede descargar la versión de evaluación de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="dccf4-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="dccf4-196">Máquina virtual</span><span class="sxs-lookup"><span data-stu-id="dccf4-196">Virtual machine</span></span>

<span data-ttu-id="dccf4-p110">Cree una máquina virtual con el hipervisor que prefiera e instale Windows 10 Enterprise en ella. Puede descargar la versión de evaluación de Windows 10 Enterprise [aquí](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span><span class="sxs-lookup"><span data-stu-id="dccf4-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="dccf4-199">Máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="dccf4-199">Virtual machine in Azure</span></span>

<span data-ttu-id="dccf4-p111">Para crear una máquina virtual con Windows 10 en Microsoft Azure ***necesita tener una suscripción basada en Visual Studio***, que tiene acceso a la imagen de Windows 10 Enterprise. Otros tipos de suscripciones de Azure, como las suscripciones de prueba y suscripciones de pago, no tienen acceso a esta imagen. Para obtener la información más reciente, vea [Usar el cliente de Windows en Azure para escenarios de desarrollo y pruebas](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="dccf4-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dccf4-p112">Los siguientes conjuntos de comandos usan la versión más reciente de Azure PowerShell. Vea [Introducción a los cmdlets de Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). Estos conjuntos de comandos compilan una máquina virtual con Windows 10 Enterprise llamada WIN10 y toda la infraestructura necesaria, que incluye un grupo de recursos, una cuenta de almacenamiento y una red virtual. Si ya está familiarizado con los servicios de infraestructura de Azure, adapte estas instrucciones para que se ajusten a la infraestructura implementada actualmente.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="dccf4-207">En primer lugar, abra un símbolo del sistema de Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dccf4-207">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="dccf4-208">Inicie sesión en su cuenta de Azure con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="dccf4-208">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="dccf4-209">Obtenga su nombre de suscripción mediante el comando siguiente.</span><span class="sxs-lookup"><span data-stu-id="dccf4-209">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="dccf4-p113">Configure su suscripción de Azure. Cambie todo el contenido entrecomillado, incluidos los caracteres \< y >, por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="dccf4-p114">Después, cree un nuevo grupo de recursos. Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="dccf4-p115">Cree el nuevo grupo de recursos con estos comandos. Reemplace todo el contenido entrecomillado, incluidos los caracteres \< y > , por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="dccf4-p116">Después, cree una red virtual y la máquina virtual WIN10 con estos comandos. Cuando se le pida, indique el nombre y contraseña de la cuenta de administrador local para WIN10 y guárdelos en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_D1_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="dccf4-218">Fase 5: unir el equipo con Windows 10 a Azure AD</span><span class="sxs-lookup"><span data-stu-id="dccf4-218">Phase 4: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="dccf4-219">Después de crear la máquina física o virtual con Windows 10 Enterprise, inicie sesión con una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="dccf4-219">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dccf4-220">En el caso de una máquina virtual de Azure, conéctela siguiendo [estas instrucciones](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span><span class="sxs-lookup"><span data-stu-id="dccf4-220">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="dccf4-221">Después, una el equipo WIN10 al espacio empresarial de Azure AD de la suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-221">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="dccf4-222">En el escritorio del equipo WIN10, haga clic en **Inicio > Configuración > Cuentas > Obtener acceso a trabajo o escuela > Conectarse**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-222">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="dccf4-223">En el cuadro de diálogo **Set up a work or school account** (Configurar una cuenta profesional o educativa), haga clic en **Join this device to Azure Active Directory** (Unir este dispositivo a Azure Active Directory).</span><span class="sxs-lookup"><span data-stu-id="dccf4-223">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="dccf4-224">En **Cuenta profesional o educativa**, escriba el nombre de la cuenta de administrador global de la suscripción de Microsoft 365 E5 y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-224">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="dccf4-225">En **Escribir contraseña**, escriba la contraseña de la cuenta de administrador global y luego haga clic en **Iniciar sesión**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-225">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="dccf4-226">Cuando se le pida que confirme que es su organización, haga clic en **Unir** y luego en **Listo**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-226">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="dccf4-227">Cierre la ventana de configuración.</span><span class="sxs-lookup"><span data-stu-id="dccf4-227">Close the settings window.</span></span>
    
<span data-ttu-id="dccf4-228">Después, instale Office 365 ProPlus en el equipo con Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dccf4-228">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="dccf4-229">Abra el explorador Microsoft Edge e inicie sesión en el portal de Office con las credenciales de la cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="dccf4-229">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="dccf4-230">Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).</span><span class="sxs-lookup"><span data-stu-id="dccf4-230">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="dccf4-231">En la pestaña **Inicio de Microsoft Office**, haga clic en **Instalar Office**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-231">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="dccf4-232">Cuando se le pregunte qué hacer, haga clic en **Ejecutar** y luego en **Sí** para **Control de cuentas de usuario**.</span><span class="sxs-lookup"><span data-stu-id="dccf4-232">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="dccf4-p118">Espere hasta que se complete la instalación de Office. Cuando vea **Ya está listo**, haga clic en **Cerrar** dos veces.</span><span class="sxs-lookup"><span data-stu-id="dccf4-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="dccf4-235">Este es el entorno resultante.</span><span class="sxs-lookup"><span data-stu-id="dccf4-235">Here is your resulting configuration:</span></span>

![Fase 5 del entorno de prueba de Microsoft 365 Enterprise](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="dccf4-237">Esto incluye el equipo WIN10 que tiene:</span><span class="sxs-lookup"><span data-stu-id="dccf4-237">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="dccf4-238">Se unió al espacio empresarial de Azure AD de su suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="dccf4-238">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="dccf4-239">Se inscribió como un dispositivo de Azure AD en Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="dccf4-239">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="dccf4-240">Tiene instalado Office 365 ProPlus.</span><span class="sxs-lookup"><span data-stu-id="dccf4-240">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="dccf4-241">Ahora está preparado para experimentar con otras características de [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span><span class="sxs-lookup"><span data-stu-id="dccf4-241">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="dccf4-242">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="dccf4-242">Next steps</span></span>

<span data-ttu-id="dccf4-243">Explore estos conjuntos adicionales de guías de laboratorio de pruebas:</span><span class="sxs-lookup"><span data-stu-id="dccf4-243">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="dccf4-244">Identidad</span><span class="sxs-lookup"><span data-stu-id="dccf4-244">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="dccf4-245">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="dccf4-245">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="dccf4-246">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="dccf4-246">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="dccf4-247">Vea también</span><span class="sxs-lookup"><span data-stu-id="dccf4-247">See also</span></span>

[<span data-ttu-id="dccf4-248">Guías de laboratorio de pruebas de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dccf4-248">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="dccf4-249">Implementar Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dccf4-249">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="dccf4-250">Documentación y recursos de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dccf4-250">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
