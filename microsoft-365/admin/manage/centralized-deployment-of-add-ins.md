---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine si el inquilino y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar complementos de Office.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519370"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="590dc-103">Determinar si la implementación centralizada de complementos funciona para su organización</span><span class="sxs-lookup"><span data-stu-id="590dc-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="590dc-104">La implementación centralizada es la forma recomendada y con más características para la mayoría de los clientes de implementar complementos de Office para usuarios y grupos de su organización.</span><span class="sxs-lookup"><span data-stu-id="590dc-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="590dc-105">Si es administrador, use esta guía para determinar si su organización y los usuarios cumplen los requisitos para poder usar la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="590dc-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="590dc-106">Implementación centralizada proporciona las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="590dc-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="590dc-107">Un administrador global puede asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="590dc-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="590dc-108">Cuando se inicia la aplicación de Office correspondiente, el complemento se descarga automáticamente.</span><span class="sxs-lookup"><span data-stu-id="590dc-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="590dc-109">Si el complemento admite comandos de complemento, el complemento aparece automáticamente en la cinta de opciones dentro de la aplicación de Office.</span><span class="sxs-lookup"><span data-stu-id="590dc-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="590dc-110">Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento.</span><span class="sxs-lookup"><span data-stu-id="590dc-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="590dc-111">La implementación centralizada admite tres plataformas de escritorio, aplicaciones de Windows, Mac y Office en línea.</span><span class="sxs-lookup"><span data-stu-id="590dc-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="590dc-112">La implementación centralizada también admite iOS y Android (solo complementos de Outlook Mobile).</span><span class="sxs-lookup"><span data-stu-id="590dc-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="590dc-113">Un complemento puede tardar hasta 24 horas en mostrarse para el cliente de todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="590dc-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="590dc-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="590dc-114">Requirements</span></span>

<span data-ttu-id="590dc-115">La implementación centralizada de complementos requiere que los usuarios usen SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium (y que se haya iniciado sesión en Office con su identificador de organización) y que tengan buzones de Exchange Online y Exchange Online activos.</span><span class="sxs-lookup"><span data-stu-id="590dc-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="590dc-116">El directorio de suscripción debe estar en Azure Active Directory o federado.</span><span class="sxs-lookup"><span data-stu-id="590dc-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="590dc-117">Puede ver los requisitos específicos de Office y Exchange a continuación, o usar el Herramienta de comprobación de compatibilidad [de implementación centralizada.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="590dc-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="590dc-118">La implementación centralizada no es compatible con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="590dc-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="590dc-119">Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013</span><span class="sxs-lookup"><span data-stu-id="590dc-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="590dc-120">Un servicio de directorio local</span><span class="sxs-lookup"><span data-stu-id="590dc-120">An on-premises directory service</span></span>
- <span data-ttu-id="590dc-121">Implementación de complementos en un buzón local de Exchange</span><span class="sxs-lookup"><span data-stu-id="590dc-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="590dc-122">Implementación de complemento a SharePoint</span><span class="sxs-lookup"><span data-stu-id="590dc-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="590dc-123">Aplicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="590dc-123">Teams apps</span></span>
- <span data-ttu-id="590dc-124">Implementación de complementos del modelo de objetos componentes (COM) o Visual Studio Tools for Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="590dc-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="590dc-125">Implementaciones de Microsoft 365 que no incluyen Exchange Online, como SKU: Aplicaciones de Microsoft 365 para empresas y Aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="590dc-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="590dc-126">Requisitos de Office</span><span class="sxs-lookup"><span data-stu-id="590dc-126">Office Requirements</span></span>

- <span data-ttu-id="590dc-127">Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="590dc-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="590dc-128">En un dispositivo Windows, versión 1704 o posterior de las SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU de empresa: Business Basic, Business Standard, Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="590dc-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="590dc-129">En mac, versión 15.34 o posterior.</span><span class="sxs-lookup"><span data-stu-id="590dc-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="590dc-130">Para Outlook, los usuarios deben usar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="590dc-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="590dc-131">Versión 1701 o posterior de las SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Empresa Premium.</span><span class="sxs-lookup"><span data-stu-id="590dc-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="590dc-132">Versión 1808 o posterior de Office Professional Plus 2019 u Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="590dc-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="590dc-133">Versión 16.0.4494.1000 o posterior de Office Professional Plus 2016 (MSI) u Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="590dc-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="590dc-134">Versión 15.0.4937.1000 o posterior de Office Professional Plus 2013 (MSI) u Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="590dc-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="590dc-135">Versión 16.0.9318.1000 o posterior de Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="590dc-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="590dc-136">Versión 2.75.0 o posterior de Outlook Mobile para iOS</span><span class="sxs-lookup"><span data-stu-id="590dc-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="590dc-137">Versión 2.2.145 o posterior de Outlook Mobile para Android</span><span class="sxs-lookup"><span data-stu-id="590dc-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="590dc-138">\*Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de Outlook adecuada, no en la sección "Mis complementos".</span><span class="sxs-lookup"><span data-stu-id="590dc-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="590dc-139">Requisitos de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="590dc-139">Exchange Online requirements</span></span>

<span data-ttu-id="590dc-140">Microsoft Exchange almacena los manifiestos del complemento en el inquilino de su organización.</span><span class="sxs-lookup"><span data-stu-id="590dc-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="590dc-141">El administrador que implementa complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="590dc-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="590dc-p106">Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="590dc-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="590dc-144">Comprobación de compatibilidad de implementación centralizada</span><span class="sxs-lookup"><span data-stu-id="590dc-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="590dc-145">Con el Checker de compatibilidad de implementación centralizada, puede comprobar si los usuarios de su espacio empresarial están configurados para usar la implementación centralizada para Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="590dc-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="590dc-146">El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook.</span><span class="sxs-lookup"><span data-stu-id="590dc-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="590dc-147">Descargue el Comprobador de compatibilidad [aquí](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="590dc-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="590dc-148">Ejecutar el checker de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="590dc-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="590dc-149">Inicie una ventana de PowerShell.exe elevada.</span><span class="sxs-lookup"><span data-stu-id="590dc-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="590dc-150">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="590dc-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="590dc-151">Ejecute el **comando Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="590dc-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="590dc-152">Este comando le solicita  *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated.onmicrosoft. </span> com)* y  *_las credenciales de TenantAdmin_* (use sus credenciales de administrador global) y, a continuación, solicita su consentimiento.</span><span class="sxs-lookup"><span data-stu-id="590dc-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="590dc-153">Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación.</span><span class="sxs-lookup"><span data-stu-id="590dc-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="590dc-154">Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv).</span><span class="sxs-lookup"><span data-stu-id="590dc-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="590dc-155">El archivo se guarda en **C:\windows\system32** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="590dc-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="590dc-156">El archivo de salida contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="590dc-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="590dc-157">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="590dc-157">User Name</span></span>
    
- <span data-ttu-id="590dc-158">Id. de usuario (dirección de correo electrónico del usuario)</span><span class="sxs-lookup"><span data-stu-id="590dc-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="590dc-159">Preparado para la Implementación centralizada: si los elementos restantes son ciertos</span><span class="sxs-lookup"><span data-stu-id="590dc-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="590dc-160">Plan de Office: el plan de Office para el que tienen licencia</span><span class="sxs-lookup"><span data-stu-id="590dc-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="590dc-161">Office activado: si Office está activado</span><span class="sxs-lookup"><span data-stu-id="590dc-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="590dc-162">Buzón compatible: si están en un buzón habilitado para OAuth</span><span class="sxs-lookup"><span data-stu-id="590dc-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="590dc-163">No se admite la autenticación multifactor al usar el módulo de PowerShell de implementación central.</span><span class="sxs-lookup"><span data-stu-id="590dc-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="590dc-164">Asignaciones de usuario y de grupo</span><span class="sxs-lookup"><span data-stu-id="590dc-164">User and group assignments</span></span>

<span data-ttu-id="590dc-165">La característica implementación centralizada admite actualmente la mayoría de los grupos admitidos por Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución y los grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="590dc-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="590dc-166">Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos.</span><span class="sxs-lookup"><span data-stu-id="590dc-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="590dc-167">La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="590dc-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="590dc-168">La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.</span><span class="sxs-lookup"><span data-stu-id="590dc-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="590dc-p110">Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.</span><span class="sxs-lookup"><span data-stu-id="590dc-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagrama del departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="590dc-172">Averiguar si un grupo contiene grupos anidados</span><span class="sxs-lookup"><span data-stu-id="590dc-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="590dc-173">La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook.</span><span class="sxs-lookup"><span data-stu-id="590dc-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="590dc-174">Si escribe el nombre  del grupo en el campo Para de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="590dc-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="590dc-175">En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos.</span><span class="sxs-lookup"><span data-stu-id="590dc-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Pestaña Miembros de la tarjeta de contacto de Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="590dc-p112">Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="590dc-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Pestaña Pertenencia de la tarjeta de contacto de Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="590dc-p113">De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="590dc-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="590dc-182">Ponerse en contacto con Microsoft para obtener soporte técnico</span><span class="sxs-lookup"><span data-stu-id="590dc-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="590dc-183">Si usted o sus usuarios tienen problemas para cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft (obtenga información[sobre](../contact-support-for-business-products.md)cómo).</span><span class="sxs-lookup"><span data-stu-id="590dc-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="590dc-184">Proporcione la siguiente información sobre su entorno de Microsoft 365 en el vale de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="590dc-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="590dc-185">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="590dc-185">**Platform**</span></span>|<span data-ttu-id="590dc-186">**Información de depuración**</span><span class="sxs-lookup"><span data-stu-id="590dc-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="590dc-187">Office</span><span class="sxs-lookup"><span data-stu-id="590dc-187">Office</span></span>  <br/> | <span data-ttu-id="590dc-188">Registros Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="590dc-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="590dc-189">Id. del espacio empresarial ( [más información](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))    </span><span class="sxs-lookup"><span data-stu-id="590dc-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="590dc-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="590dc-190">CorrelationID.</span></span> <span data-ttu-id="590dc-191">Vea el origen de una de las páginas de Office y busque el valor del identificador de correlación y envíelo a soporte técnico:</span><span class="sxs-lookup"><span data-stu-id="590dc-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="590dc-192">Clientes enriquecidos (Windows y Mac)</span><span class="sxs-lookup"><span data-stu-id="590dc-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="590dc-193">Registros Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="590dc-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="590dc-194">Crear números de la aplicación cliente (preferiblemente como captura de pantalla de **Archivo/Cuenta)**</span><span class="sxs-lookup"><span data-stu-id="590dc-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
