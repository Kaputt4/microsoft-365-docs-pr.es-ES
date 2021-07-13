---
title: Determinar si la implementación centralizada de complementos funciona para su organización
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determine si el inquilino y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar Office complementos.
ms.openlocfilehash: cb1cc019cfd87ee05112ea0ac1f0f1675316c6d3
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393708"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="80ca6-103">Determinar si la implementación centralizada de complementos funciona para su organización</span><span class="sxs-lookup"><span data-stu-id="80ca6-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="80ca6-104">La implementación centralizada es la forma recomendada y más enriquecte de características para que la mayoría de los clientes implemente Office complementos para usuarios y grupos dentro de su organización.</span><span class="sxs-lookup"><span data-stu-id="80ca6-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="80ca6-105">Si es administrador, use esta guía para determinar si su organización y los usuarios cumplen los requisitos para poder usar la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="80ca6-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="80ca6-106">Implementación centralizada proporciona las siguientes ventajas:</span><span class="sxs-lookup"><span data-stu-id="80ca6-106">Centralized Deployment provides the following benefits:</span></span>

- <span data-ttu-id="80ca6-107">Un administrador global puede asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios de la organización.</span><span class="sxs-lookup"><span data-stu-id="80ca6-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>

- <span data-ttu-id="80ca6-108">Cuando se inicia Office aplicación, el complemento se descarga automáticamente.</span><span class="sxs-lookup"><span data-stu-id="80ca6-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="80ca6-109">Si el complemento admite comandos de complemento, el complemento aparecerá automáticamente en la cinta de opciones dentro de la Office aplicación.</span><span class="sxs-lookup"><span data-stu-id="80ca6-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>

- <span data-ttu-id="80ca6-110">Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento.</span><span class="sxs-lookup"><span data-stu-id="80ca6-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="80ca6-111">La implementación centralizada admite tres plataformas de escritorio Windows, Mac y Aplicaciones Office línea.</span><span class="sxs-lookup"><span data-stu-id="80ca6-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="80ca6-112">La implementación centralizada también admite iOS y Android (solo Outlook complementos móviles).</span><span class="sxs-lookup"><span data-stu-id="80ca6-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="80ca6-113">Un complemento puede tardar hasta 24 horas en aparecer para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="80ca6-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="80ca6-114">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="80ca6-114">Before you begin</span></span>

<span data-ttu-id="80ca6-115">La implementación centralizada de complementos requiere que los usuarios usen SKU de Microsoft 365 Enterprise: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium (y han iniciado sesión en Office con su identificador de organización) y tienen buzones de Exchange Online y Exchange Online activos.</span><span class="sxs-lookup"><span data-stu-id="80ca6-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="80ca6-116">El directorio de suscripción debe estar en o federado para Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80ca6-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="80ca6-117">Puede ver requisitos específicos para Office y Exchange a continuación, o usar el Control de compatibilidad de implementación [centralizada](#centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="80ca6-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="80ca6-118">La implementación centralizada no es compatible con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80ca6-118">Centralized Deployment doesn't support the following:</span></span>

- <span data-ttu-id="80ca6-119">Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013</span><span class="sxs-lookup"><span data-stu-id="80ca6-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
- <span data-ttu-id="80ca6-120">Un servicio de directorio local</span><span class="sxs-lookup"><span data-stu-id="80ca6-120">An on-premises directory service</span></span>
- <span data-ttu-id="80ca6-121">Implementación de complementos en un buzón Exchange local</span><span class="sxs-lookup"><span data-stu-id="80ca6-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="80ca6-122">Implementación de complemento a SharePoint</span><span class="sxs-lookup"><span data-stu-id="80ca6-122">Add-in deployment to SharePoint</span></span>
- <span data-ttu-id="80ca6-123">Teams aplicaciones</span><span class="sxs-lookup"><span data-stu-id="80ca6-123">Teams apps</span></span>
- <span data-ttu-id="80ca6-124">Implementación de complementos de modelo de objetos componentes (COM) o Visual Studio Tools para Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="80ca6-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="80ca6-125">Implementaciones de Microsoft 365 que no incluyen Exchange Online como SKU: Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para Enterprise.</span><span class="sxs-lookup"><span data-stu-id="80ca6-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="80ca6-126">Office Requisitos</span><span class="sxs-lookup"><span data-stu-id="80ca6-126">Office Requirements</span></span>

- <span data-ttu-id="80ca6-127">Para word, Excel y PowerPoint complementos, los usuarios deben usar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="80ca6-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="80ca6-128">En un dispositivo Windows, versión 1704 o posterior de Microsoft 365 Enterprise SKU: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="80ca6-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="80ca6-129">En mac, versión 15.34 o posterior.</span><span class="sxs-lookup"><span data-stu-id="80ca6-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="80ca6-130">Por Outlook, los usuarios deben usar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="80ca6-130">For Outlook, your users must be using one of the following:</span></span>
  - <span data-ttu-id="80ca6-131">Versión 1701 o posterior de Microsoft 365 Enterprise SKU: E3/E5/F3 o SKU empresariales: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="80ca6-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="80ca6-132">Versión 1808 o posterior de Office Profesional Plus 2019 o Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="80ca6-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="80ca6-133">Versión 16.0.4494.1000 o posterior de Office Profesional Plus 2016 (MSI) o Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="80ca6-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="80ca6-134">Versión 15.0.4937.1000 o posterior de Office Profesional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="80ca6-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="80ca6-135">Versión 16.0.9318.1000 o posterior de Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="80ca6-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span>
- <span data-ttu-id="80ca6-136">Versión 2.75.0 o posterior de Outlook móvil para iOS</span><span class="sxs-lookup"><span data-stu-id="80ca6-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span>
- <span data-ttu-id="80ca6-137">Versión 2.2.145 o posterior de Outlook móvil para Android</span><span class="sxs-lookup"><span data-stu-id="80ca6-137">Version 2.2.145 or later of Outlook mobile for Android</span></span>

    <span data-ttu-id="80ca6-138">\*Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de opciones Outlook, no en la sección "Mis complementos".</span><span class="sxs-lookup"><span data-stu-id="80ca6-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="80ca6-139">Exchange Online requisitos</span><span class="sxs-lookup"><span data-stu-id="80ca6-139">Exchange Online requirements</span></span>

<span data-ttu-id="80ca6-140">Microsoft Exchange los manifiestos del complemento en el inquilino de la organización.</span><span class="sxs-lookup"><span data-stu-id="80ca6-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="80ca6-141">El administrador que implementa complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="80ca6-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>

<span data-ttu-id="80ca6-p106">Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity).</span><span class="sxs-lookup"><span data-stu-id="80ca6-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span>


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="80ca6-144">Comprobación de compatibilidad de implementación centralizada</span><span class="sxs-lookup"><span data-stu-id="80ca6-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="80ca6-145">Con el control de compatibilidad de implementación centralizada, puede comprobar si los usuarios del espacio empresarial están configurados para usar la implementación centralizada para Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="80ca6-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="80ca6-146">El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook.</span><span class="sxs-lookup"><span data-stu-id="80ca6-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="80ca6-147">Descargue el [control de compatibilidad](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="80ca6-147">Download the [compatibility checker](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>

#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="80ca6-148">Ejecutar el control de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="80ca6-148">Run the compatibility checker</span></span>

1. <span data-ttu-id="80ca6-149">Inicie una ventana PowerShell.exe con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="80ca6-149">Start an elevated PowerShell.exe window.</span></span>

2. <span data-ttu-id="80ca6-150">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="80ca6-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```

3. <span data-ttu-id="80ca6-151">Ejecute el **comando Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="80ca6-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="80ca6-152">Este comando le solicita  *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated.onmicrosoft. </span> com*) y  *_las credenciales de TenantAdmin_* (use sus credenciales de administrador global) y, a continuación, solicite el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="80ca6-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>

   > [!NOTE]
   > <span data-ttu-id="80ca6-153">Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación.</span><span class="sxs-lookup"><span data-stu-id="80ca6-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span>

<span data-ttu-id="80ca6-154">Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv).</span><span class="sxs-lookup"><span data-stu-id="80ca6-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="80ca6-155">El archivo se guarda en **C:\windows\system32** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="80ca6-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="80ca6-156">El archivo de salida contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="80ca6-156">The output file contains the following information:</span></span>

- <span data-ttu-id="80ca6-157">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="80ca6-157">User Name</span></span>

- <span data-ttu-id="80ca6-158">Id. de usuario (dirección de correo electrónico del usuario)</span><span class="sxs-lookup"><span data-stu-id="80ca6-158">User ID (User's email address)</span></span>

- <span data-ttu-id="80ca6-159">Preparado para la Implementación centralizada: si los elementos restantes son ciertos</span><span class="sxs-lookup"><span data-stu-id="80ca6-159">Centralized Deployment ready - If the remaining items are true</span></span>

- <span data-ttu-id="80ca6-160">Office plan: el plan de Office para el que tienen licencia</span><span class="sxs-lookup"><span data-stu-id="80ca6-160">Office plan - The plan of Office they are licensed for</span></span>

- <span data-ttu-id="80ca6-161">Office activado: si Office está activado</span><span class="sxs-lookup"><span data-stu-id="80ca6-161">Office Activated - If they have activated Office</span></span>

- <span data-ttu-id="80ca6-162">Buzón compatible: si están en un buzón habilitado para OAuth</span><span class="sxs-lookup"><span data-stu-id="80ca6-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="80ca6-163">La autenticación multifactor no se admite al usar el módulo PowerShell de implementación central.</span><span class="sxs-lookup"><span data-stu-id="80ca6-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span> <span data-ttu-id="80ca6-164">El módulo solo funciona con autenticación básica.</span><span class="sxs-lookup"><span data-stu-id="80ca6-164">The module only works with Basic authentication.</span></span>

## <a name="user-and-group-assignments"></a><span data-ttu-id="80ca6-165">Asignaciones de usuario y de grupo</span><span class="sxs-lookup"><span data-stu-id="80ca6-165">User and group assignments</span></span>

<span data-ttu-id="80ca6-166">La característica Implementación centralizada actualmente admite la mayoría de los grupos admitidos por Azure Active Directory, incluidos Microsoft 365, listas de distribución y grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="80ca6-166">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>

> [!NOTE]
> <span data-ttu-id="80ca6-167">Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos.</span><span class="sxs-lookup"><span data-stu-id="80ca6-167">Non-mail enabled security groups are not currently supported.</span></span>

<span data-ttu-id="80ca6-168">La implementación centralizada admite asignaciones a usuarios individuales, grupos y todos los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="80ca6-168">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="80ca6-169">La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.</span><span class="sxs-lookup"><span data-stu-id="80ca6-169">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>

<span data-ttu-id="80ca6-p111">Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.</span><span class="sxs-lookup"><span data-stu-id="80ca6-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>

![Diagrama del departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)


### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="80ca6-173">Averiguar si un grupo contiene grupos anidados</span><span class="sxs-lookup"><span data-stu-id="80ca6-173">Find out if a group contains nested groups</span></span>

<span data-ttu-id="80ca6-174">La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook.</span><span class="sxs-lookup"><span data-stu-id="80ca6-174">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="80ca6-175">Si escribe el nombre del grupo en el campo **Para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="80ca6-175">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="80ca6-176">En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos.</span><span class="sxs-lookup"><span data-stu-id="80ca6-176">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span>

![Ficha Miembros de Outlook de contacto](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

<span data-ttu-id="80ca6-p113">Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="80ca6-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span>

![Ficha Pertenencia de la Outlook de contacto](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

<span data-ttu-id="80ca6-p114">De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](/previous-versions/azure/ad/graph/api/groups-operations).</span><span class="sxs-lookup"><span data-stu-id="80ca6-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>

### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="80ca6-183">Ponerse en contacto con Microsoft para obtener soporte técnico</span><span class="sxs-lookup"><span data-stu-id="80ca6-183">Contacting Microsoft for support</span></span>

<span data-ttu-id="80ca6-184">Si usted o sus usuarios tienen problemas para cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft[(](../../business-video/get-help-support.md)obtenga información sobre cómo ).</span><span class="sxs-lookup"><span data-stu-id="80ca6-184">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="80ca6-185">Proporcione la siguiente información sobre su entorno Microsoft 365 en el vale de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="80ca6-185">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>

|<span data-ttu-id="80ca6-186">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="80ca6-186">**Platform**</span></span>|<span data-ttu-id="80ca6-187">**Información de depuración**</span><span class="sxs-lookup"><span data-stu-id="80ca6-187">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80ca6-188">Office</span><span class="sxs-lookup"><span data-stu-id="80ca6-188">Office</span></span>  <br/> | <span data-ttu-id="80ca6-189">Registros Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="80ca6-189">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="80ca6-190">Identificador de inquilino ([obtenga información sobre cómo](/onedrive/find-your-office-365-tenant-id))</span><span class="sxs-lookup"><span data-stu-id="80ca6-190">Tenant ID ([learn how](/onedrive/find-your-office-365-tenant-id))</span></span>  <br/>  <span data-ttu-id="80ca6-191">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="80ca6-191">CorrelationID.</span></span> <span data-ttu-id="80ca6-192">Vea el origen de una de las páginas de office y busque el valor de Id. de correlación y envíelo para admitir:</span><span class="sxs-lookup"><span data-stu-id="80ca6-192">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="80ca6-193">Clientes enriquecidos (Windows y Mac)</span><span class="sxs-lookup"><span data-stu-id="80ca6-193">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="80ca6-194">Registros Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="80ca6-194">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="80ca6-195">Generar números de la aplicación cliente (preferiblemente como una captura de pantalla de **Archivo/Cuenta**)</span><span class="sxs-lookup"><span data-stu-id="80ca6-195">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="80ca6-196">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="80ca6-196">Related content</span></span>

<span data-ttu-id="80ca6-197">[Implementar complementos en el Centro](../manage/manage-deployment-of-add-ins.md) de administración (artículo)</span><span class="sxs-lookup"><span data-stu-id="80ca6-197">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="80ca6-198">[Administrar complementos en el Centro de administración](manage-addins-in-the-admin-center.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="80ca6-198">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>\
<span data-ttu-id="80ca6-199">[Preguntas más frecuentes sobre implementación](../manage/centralized-deployment-faq.md) centralizada (artículo)</span><span class="sxs-lookup"><span data-stu-id="80ca6-199">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>\
<span data-ttu-id="80ca6-200">[Actualizar su Microsoft 365 usuarios empresariales al último Office cliente](../setup/upgrade-users-to-latest-office-client.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="80ca6-200">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 