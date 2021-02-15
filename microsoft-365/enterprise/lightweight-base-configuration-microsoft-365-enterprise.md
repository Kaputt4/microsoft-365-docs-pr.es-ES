---
title: Configuración básica ligera
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: Use esta Guía del entorno de pruebas para crear un entorno de prueba ligero para probar Microsoft 365 para empresas.
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487393"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="4a365-103">Configuración básica ligera</span><span class="sxs-lookup"><span data-stu-id="4a365-103">The lightweight base configuration</span></span>

<span data-ttu-id="4a365-104">*Esta Guía del entorno de pruebas se puede usar tanto para entornos de prueba de Microsoft 365 para empresas como de Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="4a365-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="4a365-105">En este artículo se describe cómo crear un entorno simplificado con una suscripción a Microsoft 365 E5 y un equipo que ejecute Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4a365-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![El entorno de pruebas ligero de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="4a365-107">La creación de un entorno de prueba ligero consta de cinco fases:</span><span class="sxs-lookup"><span data-stu-id="4a365-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="4a365-108">Fase 1: Crear la suscripción a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4a365-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="4a365-109">Fase 2: configurar la suscripción de prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a365-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="4a365-110">Fase 3: agregar una suscripción de prueba a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4a365-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="4a365-111">Fase 4: crear un equipo con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4a365-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="4a365-112">Fase 5: unir el equipo con Windows 10 a Azure AD</span><span class="sxs-lookup"><span data-stu-id="4a365-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="4a365-113">Use el entorno resultante para probar las características y la funcionalidad [de Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="4a365-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="4a365-115">Para obtener un mapa visual de todos los artículos de la pila de guía del entorno de pruebas de Microsoft 365 para empresas, vea La pila de guía del laboratorio de pruebas de [Microsoft 365 para empresas.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="4a365-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="4a365-116">Es recomendable que imprima este artículo para registrar la información específica que necesitará para este entorno durante los 30 días de la suscripción de prueba de Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a365-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="4a365-117">Puede extender fácilmente la suscripción de prueba otros 30 días.</span><span class="sxs-lookup"><span data-stu-id="4a365-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="4a365-118">Para un entorno de pruebas permanente, cree una nueva suscripción de pago con un inquilino de Azure AD distinto y un número reducido de licencias.</span><span class="sxs-lookup"><span data-stu-id="4a365-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="4a365-119">Fase 1: Crear la suscripción a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4a365-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="4a365-120">Empezamos con una suscripción de prueba de Microsoft 365 E5 y, a continuación, le agregamos la suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="4a365-121">Le recomendamos que cree una suscripción de prueba de Office 365 para que el entorno de prueba tenga un inquilino de Azure AD independiente de las suscripciones de pago que tenga actualmente.</span><span class="sxs-lookup"><span data-stu-id="4a365-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="4a365-122">Esta separación significa que puede agregar y quitar usuarios y grupos en el inquilino de prueba sin que ello afecte a las suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="4a365-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="4a365-123">Para iniciar la suscripción de prueba de Microsoft 365 E5, en primer lugar necesita un nombre de compañía ficticio y una nueva cuenta de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4a365-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="4a365-p103">Le recomendamos que use una variante del nombre de la compañía Contoso para el nombre de su compañía, que es una compañía ficticia usada en contenido de ejemplo de Microsoft, pero no es imprescindible. Anote aquí el nombre de la compañía ficticia:</span><span class="sxs-lookup"><span data-stu-id="4a365-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![Línea](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="4a365-p104">Para registrarse para obtener una nueva cuenta Microsoft, vaya a [https://outlook.com](https://outlook.com) y cree una cuenta con una nueva cuenta y una dirección de correo electrónico. Usará esta cuenta para suscribirse a Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a365-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="4a365-129">Anote aquí el nombre y los apellidos de la nueva cuenta:</span><span class="sxs-lookup"><span data-stu-id="4a365-129">Record the first and last name of your new account here:</span></span> ![Línea](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="4a365-131">Anote la dirección de la cuenta de correo electrónico nueva aquí:</span><span class="sxs-lookup"><span data-stu-id="4a365-131">Record the new email account address here:</span></span> ![Línea](../media/Common-Images/TableLine.png)<span data-ttu-id="4a365-133">Outlook.com</span><span class="sxs-lookup"><span data-stu-id="4a365-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="4a365-134">Registrarse para una suscripción de prueba de Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="4a365-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="4a365-135">En el explorador, vaya a [https://aka.ms/e5trial](https://aka.ms/e5trial) .</span><span class="sxs-lookup"><span data-stu-id="4a365-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="4a365-136">En el paso 1 de la página Gracias por **elegir Office 365 E5,** escriba su nueva dirección de cuenta de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="4a365-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="4a365-137">En el paso 2 del proceso de suscripción de prueba, escriba la información solicitada y, a continuación, realice la comprobación.</span><span class="sxs-lookup"><span data-stu-id="4a365-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="4a365-138">En el paso 3, escriba un nombre de organización y, a continuación, un nombre de cuenta que será el administrador global de la suscripción.</span><span class="sxs-lookup"><span data-stu-id="4a365-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="4a365-139">En el paso 4, registre la página de inicio de sesión aquí (seleccionar y copiar): </span><span class="sxs-lookup"><span data-stu-id="4a365-139">For step 4, record the sign-in page here (select and copy):</span></span> ![Línea](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="4a365-141">Registre aquí el identificador de usuario: ![Linea](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4a365-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="4a365-142">Registre la contraseña que escribió en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4a365-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="4a365-143">Este valor se denominará **nombre de administrador global**.</span><span class="sxs-lookup"><span data-stu-id="4a365-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="4a365-144">Seleccione **Ir a Instalación.**</span><span class="sxs-lookup"><span data-stu-id="4a365-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="4a365-145">In Office 365 E5 Setup, select **Continue using your *organization*.onmicrosoft.com for email and signing in**, and then select Exit and continue **later**.</span><span class="sxs-lookup"><span data-stu-id="4a365-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="4a365-146">Debería ver el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4a365-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="4a365-147">Fase 2: configurar la suscripción de prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a365-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="4a365-148">En esta fase, se configura la suscripción con usuarios adicionales y se les asignan licencias de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="4a365-149">Para conectarse a su suscripción con el módulo de Azure Active Directory PowerShell para Graph desde el equipo, siga las instrucciones de Conectarse a [Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="4a365-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="4a365-150">En el **Windows PowerShell de diálogo Solicitud** de credenciales, escriba el nombre del administrador global (por ejemplo, *jdoe@contosotoycompany.onmicrosoft.com)* y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="4a365-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="4a365-151">Rellene el nombre de la organización (por ejemplo, *contosotoycompany),* el código de país de dos caracteres para su ubicación, una contraseña de cuenta común y, a continuación, ejecute los siguientes comandos desde el símbolo del sistema de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="4a365-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="4a365-152">Aquí se usa una contraseña común para automatizar y facilitar la configuración de un entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="4a365-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="4a365-153">Evidentemente, esto no se recomienda en el caso de suscripciones de producción.</span><span class="sxs-lookup"><span data-stu-id="4a365-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="4a365-154">Guardar información clave para futuras referencias</span><span class="sxs-lookup"><span data-stu-id="4a365-154">Record key information for future reference</span></span>

<span data-ttu-id="4a365-155">Si aún no ha registrado estos valores, indómelos ahora:</span><span class="sxs-lookup"><span data-stu-id="4a365-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="4a365-156">Nombre del administrador global:</span><span class="sxs-lookup"><span data-stu-id="4a365-156">Global administrator name:</span></span> ![Línea](../media/Common-Images/TableLine.png)<span data-ttu-id="4a365-158">. onmicrosoft.com (del paso 6 de la fase 1)</span><span class="sxs-lookup"><span data-stu-id="4a365-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="4a365-159">Guarde también la contraseña de esta cuenta en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4a365-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="4a365-160">Nombre de la organización de la suscripción de prueba:</span><span class="sxs-lookup"><span data-stu-id="4a365-160">Your trial subscription organization name:</span></span> ![Línea](../media/Common-Images/TableLine.png) <span data-ttu-id="4a365-162">(en el paso 4 de la fase 1)</span><span class="sxs-lookup"><span data-stu-id="4a365-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="4a365-163">Para mostrar las cuentas de los usuarios 2, 3, 4 y 5, ejecute los siguientes comandos desde el símbolo del sistema del Módulo de Windows Azure Active Directory para Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a365-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="4a365-164">Anote aquí los nombres de las cuentas:</span><span class="sxs-lookup"><span data-stu-id="4a365-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="4a365-165">Nombre de la cuenta de usuario 2: usuario2 @</span><span class="sxs-lookup"><span data-stu-id="4a365-165">User 2 account name: user2@</span></span>![Línea](../media/Common-Images/TableLine.png)<span data-ttu-id="4a365-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4a365-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="4a365-168">Nombre de la cuenta de usuario 3: usuario3 @</span><span class="sxs-lookup"><span data-stu-id="4a365-168">User 3 account name: user3@</span></span>![Línea](../media/Common-Images/TableLine.png)<span data-ttu-id="4a365-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4a365-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="4a365-171">Nombre de la cuenta de usuario 4: usuario4 @</span><span class="sxs-lookup"><span data-stu-id="4a365-171">User 4 account name: user4@</span></span>![Línea](../media/Common-Images/TableLine.png)<span data-ttu-id="4a365-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4a365-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="4a365-174">Nombre de la cuenta de usuario 5: usuario5 @</span><span class="sxs-lookup"><span data-stu-id="4a365-174">User 5 account name: user5@</span></span>![Línea](../media/Common-Images/TableLine.png)<span data-ttu-id="4a365-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4a365-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="4a365-177">También puede guardar la contraseña común de estas cuentas en un lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="4a365-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="4a365-178">Usar un entorno de prueba de Office 365</span><span class="sxs-lookup"><span data-stu-id="4a365-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="4a365-179">Si solo necesita un entorno de prueba de Office 365, no es necesario que lea el resto de este artículo.</span><span class="sxs-lookup"><span data-stu-id="4a365-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="4a365-180">Para obtener guías adicionales del entorno de pruebas que se aplican a Office 365 y Microsoft 365, consulte Guías del entorno de pruebas de [Microsoft 365 para empresas.](m365-enterprise-test-lab-guides.md)</span><span class="sxs-lookup"><span data-stu-id="4a365-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="4a365-181">Fase 3: agregar una suscripción de prueba a Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="4a365-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="4a365-182">En esta fase se inscribe en la suscripción de evaluación de Microsoft 365 E5 y la agrega a la misma organización de la suscripción de evaluación de Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="4a365-183">Primero, agregue la suscripción de prueba de Microsoft 365 E5 y asigne la nueva licencia de Microsoft 365 a su cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4a365-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="4a365-184">En una ventana privada de explorador de Internet, use sus credenciales de cuenta de administrador global para iniciar sesión en el Centro de administración de Microsoft 365 en [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="4a365-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="4a365-185">En la página centro de administración de **Microsoft 365,** en el panel de navegación izquierdo, seleccione **Facturación > servicios de compra.**</span><span class="sxs-lookup"><span data-stu-id="4a365-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="4a365-186">En la **página Servicios de** compra, seleccione Microsoft **365 E5** y, a continuación, **obtenga la versión de prueba gratuita.**</span><span class="sxs-lookup"><span data-stu-id="4a365-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="4a365-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span><span class="sxs-lookup"><span data-stu-id="4a365-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="4a365-188">Realice la comprobación.</span><span class="sxs-lookup"><span data-stu-id="4a365-188">Perform the verification.</span></span>

5. <span data-ttu-id="4a365-189">En la **página Confirmar pedido,** seleccione **Probar ahora.**</span><span class="sxs-lookup"><span data-stu-id="4a365-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="4a365-190">En la **página Recibo del** pedido, seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="4a365-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="4a365-191">En el Centro de administración de Microsoft 365, seleccione **Usuarios > usuarios activos.**</span><span class="sxs-lookup"><span data-stu-id="4a365-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="4a365-192">En **Usuarios activos,** seleccione su cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="4a365-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="4a365-193">Seleccione **Licencias y aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="4a365-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="4a365-194">Desactive la licencia para Office 365 Enterprise E5 y active la licencia de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="4a365-195">Seleccione **Guardar cambios y,** a continuación, cierre el panel de información de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="4a365-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="4a365-196">Después, repita los pasos del 8 al 11 del procedimiento anterior para todas las demás cuentas (usuario 2, usuario 3, usuario 4 y usuario 5).</span><span class="sxs-lookup"><span data-stu-id="4a365-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a365-197">La duración de la suscripción de prueba de Microsoft 365 E5 es de 30 días.</span><span class="sxs-lookup"><span data-stu-id="4a365-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="4a365-198">Para tener un entorno de prueba permanente, convierta esta suscripción de prueba en una suscripción de pago con un bajo número de licencias.</span><span class="sxs-lookup"><span data-stu-id="4a365-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="4a365-199">Su entorno de desarrollo y prueba ahora tiene:</span><span class="sxs-lookup"><span data-stu-id="4a365-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="4a365-200">Una suscripción de prueba de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="4a365-201">Todas las cuentas de usuario adecuadas (ya sea solo la cuenta de administrador global o las cinco cuentas de usuario) están habilitadas para usar Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="4a365-202">La configuración resultante, que agrega Microsoft 365 E5, tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4a365-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Fase 3 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="4a365-204">Fase 4: crear un equipo con Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4a365-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="4a365-205">En esta fase se crea un equipo independiente que ejecuta Windows 10 Enterprise como equipo físico, máquina virtual o máquina virtual de Azure.</span><span class="sxs-lookup"><span data-stu-id="4a365-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="4a365-206">Equipo físico</span><span class="sxs-lookup"><span data-stu-id="4a365-206">Physical computer</span></span>

<span data-ttu-id="4a365-207">En un equipo personal, instala Windows 10 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="4a365-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="4a365-208">Puedes descargar la versión de prueba de Windows 10 Enterprise [aquí.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)</span><span class="sxs-lookup"><span data-stu-id="4a365-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="4a365-209">Máquina virtual</span><span class="sxs-lookup"><span data-stu-id="4a365-209">Virtual machine</span></span>

<span data-ttu-id="4a365-210">Usa el hipervisor que prefieras para crear una máquina virtual y, a continuación, instala Windows 10 Enterprise en ella.</span><span class="sxs-lookup"><span data-stu-id="4a365-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="4a365-211">Puedes descargar la versión de prueba de Windows 10 Enterprise [aquí.](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)</span><span class="sxs-lookup"><span data-stu-id="4a365-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="4a365-212">Máquina virtual de Azure</span><span class="sxs-lookup"><span data-stu-id="4a365-212">Virtual machine in Azure</span></span>

<span data-ttu-id="4a365-p111">Para crear una máquina virtual con Windows 10 en Microsoft Azure ***necesita tener una suscripción basada en Visual Studio***, que tiene acceso a la imagen de Windows 10 Enterprise. Otros tipos de suscripciones de Azure, como las suscripciones de prueba y suscripciones de pago, no tienen acceso a esta imagen. Para obtener la información más reciente, vea [Usar el cliente de Windows en Azure para escenarios de desarrollo y pruebas](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span><span class="sxs-lookup"><span data-stu-id="4a365-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a365-216">Los siguientes conjuntos de comandos utilizan la última versión de Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a365-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="4a365-217">Visite [Get started with Azure PowerShell cmdlets (Introducción a los cmdlets de Azure)](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span><span class="sxs-lookup"><span data-stu-id="4a365-217">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="4a365-218">Estos conjuntos de comandos crean una máquina virtual de Windows 10 Enterprise denominada WIN10 y toda su infraestructura necesaria, incluido un grupo de recursos, una cuenta de almacenamiento y una red virtual.</span><span class="sxs-lookup"><span data-stu-id="4a365-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="4a365-219">Si ya está familiarizado con los servicios de infraestructura de Azure, adapte estas instrucciones a la infraestructura implementada actualmente.</span><span class="sxs-lookup"><span data-stu-id="4a365-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="4a365-220">En primer lugar, abra un símbolo del sistema de Microsoft PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a365-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="4a365-221">Inicie sesión en su cuenta de Azure con este comando.</span><span class="sxs-lookup"><span data-stu-id="4a365-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="4a365-222">Obtenga el nombre de la suscripción con este comando.</span><span class="sxs-lookup"><span data-stu-id="4a365-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="4a365-223">Configure su suscripción de Azure.</span><span class="sxs-lookup"><span data-stu-id="4a365-223">Set your Azure subscription.</span></span> <span data-ttu-id="4a365-224">Reemplace todo el texto entre comillas, \< and > incluidos los caracteres, por el nombre correcto.</span><span class="sxs-lookup"><span data-stu-id="4a365-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="4a365-225">Después, cree un nuevo grupo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4a365-225">Next, create a new resource group.</span></span> <span data-ttu-id="4a365-226">Para determinar un nombre único de grupo de recursos, use este comando a fin de enumerar los grupos de recursos existentes.</span><span class="sxs-lookup"><span data-stu-id="4a365-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="4a365-227">Cree el nuevo grupo de recursos con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="4a365-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="4a365-228">Reemplace todo el texto entre comillas, \< and > incluidos los caracteres, por los nombres correctos.</span><span class="sxs-lookup"><span data-stu-id="4a365-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="4a365-229">A continuación, cree una nueva red virtual y la máquina virtual WIN10 con estos comandos.</span><span class="sxs-lookup"><span data-stu-id="4a365-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="4a365-230">Cuando se le solicite, proporcione el nombre y la contraseña de la cuenta de administrador local para WIN10 y guárdalo en una ubicación segura.</span><span class="sxs-lookup"><span data-stu-id="4a365-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="4a365-231">Fase 5: unir el equipo con Windows 10 a Azure AD</span><span class="sxs-lookup"><span data-stu-id="4a365-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="4a365-232">Después de crear la máquina física o virtual con Windows 10 Enterprise, inicie sesión con una cuenta de administrador local.</span><span class="sxs-lookup"><span data-stu-id="4a365-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a365-233">Para una máquina virtual en Azure, siga  [estas instrucciones](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) para conectarse a ella.</span><span class="sxs-lookup"><span data-stu-id="4a365-233">For a virtual machine in Azure, use  [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="4a365-234">Después, una el equipo WIN10 al espacio empresarial de Azure AD de la suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="4a365-235">En el escritorio del equipo WIN10, seleccione Inicio > Configuración > Cuentas > Obtener acceso al trabajo o escuela **> Conectarse.**</span><span class="sxs-lookup"><span data-stu-id="4a365-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="4a365-236">En el **cuadro de diálogo Configurar una cuenta** de trabajo o escuela, seleccione Unir este dispositivo a Azure Active **Directory.**</span><span class="sxs-lookup"><span data-stu-id="4a365-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="4a365-237">En **la cuenta de** trabajo o escuela, escriba el nombre de la cuenta de administrador global de su suscripción a Microsoft 365 E5 y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="4a365-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="4a365-238">In **Enter password**, enter the password for your global administrator account, and then select Sign **in**.</span><span class="sxs-lookup"><span data-stu-id="4a365-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="4a365-239">Cuando se le pida que se asegúrese de que se trata de su organización, seleccione **Unirse** y, a continuación, seleccione **Listo.**</span><span class="sxs-lookup"><span data-stu-id="4a365-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="4a365-240">Cierre la ventana de configuración.</span><span class="sxs-lookup"><span data-stu-id="4a365-240">Close the settings window.</span></span>
    
<span data-ttu-id="4a365-241">A continuación, instale Aplicaciones de Microsoft 365 para empresas en el equipo WIN10:</span><span class="sxs-lookup"><span data-stu-id="4a365-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="4a365-242">Abra el explorador Microsoft Edge e inicie sesión en el Centro de administración de [Microsoft 365](https://admin.microsoft.com) con sus credenciales de cuenta de administrador global.</span><span class="sxs-lookup"><span data-stu-id="4a365-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="4a365-243">En la **Microsoft Office inicio,** seleccione **Instalar Office**.</span><span class="sxs-lookup"><span data-stu-id="4a365-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="4a365-244">Cuando se le pida qué hacer, seleccione **Ejecutar** y, a continuación, seleccione **Sí para** control de cuentas **de usuario.**</span><span class="sxs-lookup"><span data-stu-id="4a365-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="4a365-245">Espere a que Office complete su instalación.</span><span class="sxs-lookup"><span data-stu-id="4a365-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="4a365-246">Cuando **veas que todo está configurado,** selecciona **Cerrar dos** veces.</span><span class="sxs-lookup"><span data-stu-id="4a365-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="4a365-247">El entorno resultante tiene este aspecto:</span><span class="sxs-lookup"><span data-stu-id="4a365-247">Your resulting environment looks like this:</span></span>

![Fase 5 del entorno de prueba de Microsoft 365 Enterprise](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="4a365-249">Esto incluye el equipo WIN10 que tiene:</span><span class="sxs-lookup"><span data-stu-id="4a365-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="4a365-250">Se unió al espacio empresarial de Azure AD de su suscripción de Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="4a365-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="4a365-251">Se inscribió como un dispositivo de Azure AD en Microsoft Intune (EMS).</span><span class="sxs-lookup"><span data-stu-id="4a365-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="4a365-252">Aplicaciones de Microsoft 365 para empresas instaladas.</span><span class="sxs-lookup"><span data-stu-id="4a365-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="4a365-253">Ya está listo para experimentar con características adicionales de [Microsoft 365 para empresas.](https://www.microsoft.com/microsoft-365/enterprise)</span><span class="sxs-lookup"><span data-stu-id="4a365-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="4a365-254">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4a365-254">Next steps</span></span>

<span data-ttu-id="4a365-255">Explore estos conjuntos adicionales de guías de laboratorio de pruebas:</span><span class="sxs-lookup"><span data-stu-id="4a365-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="4a365-256">Identidad</span><span class="sxs-lookup"><span data-stu-id="4a365-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="4a365-257">Administración de dispositivos móviles</span><span class="sxs-lookup"><span data-stu-id="4a365-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="4a365-258">Protección de la información</span><span class="sxs-lookup"><span data-stu-id="4a365-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="4a365-259">Vea también</span><span class="sxs-lookup"><span data-stu-id="4a365-259">See also</span></span>

[<span data-ttu-id="4a365-260">Guías de entornos de pruebas de Microsoft 365 para empresas</span><span class="sxs-lookup"><span data-stu-id="4a365-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4a365-261">Información general de Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4a365-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4a365-262">Documentación para Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="4a365-262">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
