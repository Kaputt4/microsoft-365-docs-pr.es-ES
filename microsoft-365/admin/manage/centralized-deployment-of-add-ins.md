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
description: Determine si el espacio empresarial y los usuarios cumplen los requisitos, de modo que pueda usar la implementación centralizada para implementar complementos de Office.
ms.openlocfilehash: db5a9669464a9c4cb150dee119d8c0bcc2dc9833
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399817"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="09426-103">Determinar si la implementación centralizada de complementos funciona para su organización</span><span class="sxs-lookup"><span data-stu-id="09426-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="09426-104">La implementación centralizada es la forma recomendada y con más características para la mayoría de los clientes de implementar complementos de Office para los usuarios y grupos de su organización.</span><span class="sxs-lookup"><span data-stu-id="09426-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="09426-105">Si es administrador, use esta guía para determinar si el inquilino y los usuarios cumplen los requisitos para que pueda usar la implementación centralizada.</span><span class="sxs-lookup"><span data-stu-id="09426-105">If you're an admin, use this guidance to determine if your tenant and users meet the requirements so that you can use Centralized Deployment.</span></span>
<span data-ttu-id="09426-106">La implementación centralizada es compatible con Windows, Mac, iOS, Android y aplicaciones de Office en línea.</span><span class="sxs-lookup"><span data-stu-id="09426-106">Centralized Deployment supports Windows, Mac, iOS, Android and Online Office apps.</span></span>
<span data-ttu-id="09426-107">Un complemento puede tardar hasta 12 horas en mostrarse para el cliente para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="09426-107">It can take up to 12 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="09426-108">Requirements</span><span class="sxs-lookup"><span data-stu-id="09426-108">Requirements</span></span>

<span data-ttu-id="09426-109">La implementación centralizada de complementos requiere que los usuarios usen las aplicaciones de Microsoft 365 para empresas (y que hayan iniciado sesión en Office con su identificador de organización) y tengan Exchange Online y los buzones activos de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="09426-109">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="09426-110">El directorio de suscripción debe estar en el o ser federado en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="09426-110">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="09426-111">Puede ver los requisitos específicos para Office y Exchange, o usar el [Comprobador de compatibilidad de implementación centralizada](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="09426-111">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="09426-112">La implementación centralizada no es compatible con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="09426-112">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="09426-113">Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013</span><span class="sxs-lookup"><span data-stu-id="09426-113">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span>
    
- <span data-ttu-id="09426-114">Un servicio de directorio local</span><span class="sxs-lookup"><span data-stu-id="09426-114">An on-premises directory service</span></span>
    
- <span data-ttu-id="09426-115">Implementación de complemento a SharePoint</span><span class="sxs-lookup"><span data-stu-id="09426-115">Add-in deployment to SharePoint</span></span>  

- <span data-ttu-id="09426-116">Aplicaciones de Teams</span><span class="sxs-lookup"><span data-stu-id="09426-116">Teams apps</span></span>
   
- <span data-ttu-id="09426-117">Implementación complementos de modelo de objetos componentes (COM) o de Visual Studio Tools para Office (VSTO)</span><span class="sxs-lookup"><span data-stu-id="09426-117">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
    
- <span data-ttu-id="09426-118">Implementaciones de Microsoft 365 que no incluyen Exchange, como Microsoft 365 apps for Business</span><span class="sxs-lookup"><span data-stu-id="09426-118">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="09426-119">Requisitos de Office</span><span class="sxs-lookup"><span data-stu-id="09426-119">Office Requirements</span></span>

- <span data-ttu-id="09426-120">Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="09426-120">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="09426-121">En un dispositivo Windows, versión 1704 o posterior de Microsoft 365 apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="09426-121">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="09426-122">En un equipo Mac, versión 15,34 o posterior.</span><span class="sxs-lookup"><span data-stu-id="09426-122">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="09426-123">Para Outlook, los usuarios deben usar una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="09426-123">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="09426-124">Versión 1701 o posterior de las aplicaciones de Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="09426-124">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="09426-125">La versión 1808 o posterior de Office Professional Plus 2019 u Office Standard 2019.</span><span class="sxs-lookup"><span data-stu-id="09426-125">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="09426-126">Versión 16.0.4494.1000 o posterior de Office Professional Plus 2016 (MSI) u Office Standard 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="09426-126">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="09426-127">Versión 15.0.4937.1000 o posterior de Office Professional Plus 2013 (MSI) u Office Standard 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="09426-127">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="09426-128">Versión 16.0.9318.1000 o posterior de Office 2016 para Mac</span><span class="sxs-lookup"><span data-stu-id="09426-128">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="09426-129">Versión 2.75.0 o posterior de Outlook Mobile para iOS</span><span class="sxs-lookup"><span data-stu-id="09426-129">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="09426-130">Versión 2.2.145 o posterior de Outlook Mobile para Android</span><span class="sxs-lookup"><span data-stu-id="09426-130">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="09426-131">\* Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de Outlook correspondiente, no en la sección "mis complementos".</span><span class="sxs-lookup"><span data-stu-id="09426-131">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="09426-132">Averiguar si Microsoft 365 apps for Enterprise está instalado</span><span class="sxs-lookup"><span data-stu-id="09426-132">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="09426-133">Para usar las aplicaciones de Microsoft 365 para empresas, un usuario debe tener una cuenta de Microsoft 365 y debe tener una licencia asignada.</span><span class="sxs-lookup"><span data-stu-id="09426-133">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="09426-134">Para obtener más información, vea [información general de las aplicaciones de Microsoft 365 para empresas](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="09426-134">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="09426-135">La forma más sencilla de detectar si un usuario tiene Microsoft 365 apps for Enterprise instalado y lo ha usado recientemente es usar el informe de activaciones de Microsoft Office, que está disponible en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="09426-135">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="09426-136">El informe proporciona una lista de todos los usuarios que han activado Microsoft 365 apps for Enterprise en los últimos 7 días, 30 días, 90 días o 180 días.</span><span class="sxs-lookup"><span data-stu-id="09426-136">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="09426-137">Con fines de implementación centralizada, las activaciones de escritorio para Windows o Mac son las columnas importantes del informe.</span><span class="sxs-lookup"><span data-stu-id="09426-137">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="09426-138">Puede exportar el informe a Excel.</span><span class="sxs-lookup"><span data-stu-id="09426-138">You can export the report to Excel.</span></span> <span data-ttu-id="09426-139">Para obtener más información acerca del informe, vea [informes de microsoft 365 en el centro de administración: activaciones de Microsoft Office](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="09426-139">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="09426-140">Si no desea usar el informe de activaciones, puede pedir a un usuario que abra una aplicación de Office, como Word en su equipo y, a continuación, elija cuenta de **archivo** \> **Account**.</span><span class="sxs-lookup"><span data-stu-id="09426-140">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="09426-141">En **información del producto**, debería ver **producto de suscripción** y **Microsoft 365 para empresas**, como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="09426-141">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**, as shown in the following image.</span></span>

![Información de producto en una aplicación de Office](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="09426-143">Para obtener ayuda con Microsoft 365 apps for Enterprise, vea [Troubleshooting Tips for microsoft 365 apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="09426-143">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="09426-144">Requisitos de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="09426-144">Exchange Online requirements</span></span>

<span data-ttu-id="09426-145">Microsoft Exchange almacena los manifiestos de complementos dentro del espacio empresarial de la organización.</span><span class="sxs-lookup"><span data-stu-id="09426-145">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="09426-146">El administrador que implementa los complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange online que admita la autenticación de OAuth.</span><span class="sxs-lookup"><span data-stu-id="09426-146">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="09426-p107">Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="09426-p107">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="09426-149">Comprobador de compatibilidad de implementación centralizada</span><span class="sxs-lookup"><span data-stu-id="09426-149">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="09426-150">Con el comprobador de compatibilidad de implementación centralizada, puede comprobar si los usuarios de su espacio empresarial están configurados para usar la implementación centralizada para Word, Excel y PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="09426-150">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="09426-151">El Comprobador de compatibilidad no es necesario para la compatibilidad con Outlook.</span><span class="sxs-lookup"><span data-stu-id="09426-151">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="09426-152">Descargue el Comprobador de compatibilidad [aquí](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="09426-152">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="09426-153">Ejecutar el comprobador de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="09426-153">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="09426-154">Inicie una ventana de PowerShell. exe con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="09426-154">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="09426-155">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="09426-155">Run the following command:</span></span>

```powershell
Import-Module O365CompatibilityChecker
```
    
3. <span data-ttu-id="09426-156">Ejecute el comando **Invoke-CompatabilityCheck** :</span><span class="sxs-lookup"><span data-stu-id="09426-156">Run the **Invoke-CompatabilityCheck** command:</span></span>

```powershell
Invoke-CompatibilityCheck
```
   <span data-ttu-id="09426-157">le solicita *_TenantDomain_* (por ejemplo, *TailspinToysIncorporated. en Microsoft. </span> com*) y *_TenantAdmin_* (use las credenciales de administrador global) y, a continuación, solicite el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="09426-157">which prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
> [!NOTE]
> <span data-ttu-id="09426-158">Según el número de usuarios de su espacio empresarial, el comprobador puede tardar minutos u horas en realizar la comprobación.</span><span class="sxs-lookup"><span data-stu-id="09426-158">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="09426-159">Cuando la herramienta completa el proceso, genera un archivo de salida en formato delimitado por comas (.csv).</span><span class="sxs-lookup"><span data-stu-id="09426-159">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="09426-160">El archivo se guarda en **C:\windows\system32** de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="09426-160">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="09426-161">El archivo de salida contiene la información siguiente:</span><span class="sxs-lookup"><span data-stu-id="09426-161">The output file contains the following information:</span></span>
  
- <span data-ttu-id="09426-162">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="09426-162">User Name</span></span>
    
- <span data-ttu-id="09426-163">Id. de usuario (dirección de correo electrónico del usuario)</span><span class="sxs-lookup"><span data-stu-id="09426-163">User ID (User's email address)</span></span>
    
- <span data-ttu-id="09426-164">Preparado para la Implementación centralizada: si los elementos restantes son ciertos</span><span class="sxs-lookup"><span data-stu-id="09426-164">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="09426-165">Plan de Office: el plan de Office para el que se tiene licencia</span><span class="sxs-lookup"><span data-stu-id="09426-165">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="09426-166">Office activado: si Office está activado</span><span class="sxs-lookup"><span data-stu-id="09426-166">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="09426-167">Buzón compatible: si están en un buzón habilitado para OAuth</span><span class="sxs-lookup"><span data-stu-id="09426-167">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="09426-168">Asignaciones de usuario y de grupo</span><span class="sxs-lookup"><span data-stu-id="09426-168">User and group assignments</span></span>

<span data-ttu-id="09426-169">La característica de implementación centralizada es compatible actualmente con la mayoría de los grupos compatibles con Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución y los grupos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="09426-169">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="09426-170">Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos.</span><span class="sxs-lookup"><span data-stu-id="09426-170">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="09426-171">La implementación centralizada admite asignaciones a usuarios individuales, grupos y a todos los miembros del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="09426-171">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="09426-172">La implementación centralizada es compatible con usuarios en grupos de nivel superior o grupos sin grupo primario, pero no con usuarios en grupos anidados o grupos que forman parte de otros primarios.</span><span class="sxs-lookup"><span data-stu-id="09426-172">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="09426-p111">Eche un vistazo al siguiente ejemplo, en el que Sandra, Sheila y el grupo del departamento de ventas están asignados a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento.</span><span class="sxs-lookup"><span data-stu-id="09426-p111">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Diagrama del Departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="09426-176">Averiguar si un grupo contiene grupos anidados</span><span class="sxs-lookup"><span data-stu-id="09426-176">Find out if a group contains nested groups</span></span>

<span data-ttu-id="09426-177">La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook.</span><span class="sxs-lookup"><span data-stu-id="09426-177">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="09426-178">Si escribe el nombre de grupo en el campo **para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, mostrará si contiene usuarios o grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="09426-178">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="09426-179">En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos.</span><span class="sxs-lookup"><span data-stu-id="09426-179">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Pestaña miembros de la tarjeta de contacto de Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="09426-p113">Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña **Miembros** de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas.</span><span class="sxs-lookup"><span data-stu-id="09426-p113">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Ficha pertenencia de la tarjeta de contacto de Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="09426-p114">De forma alternativa, puede usar la API de Graph Azure Active Directory para ejecutar consultas para encontrar una lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="09426-p114">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="09426-186">Ponerse en contacto con Microsoft para obtener soporte técnico</span><span class="sxs-lookup"><span data-stu-id="09426-186">Contacting Microsoft for support</span></span>

<span data-ttu-id="09426-187">Si usted o sus usuarios experimentan problemas al cargar el complemento mientras usan aplicaciones de Office para la web (Word, Excel, etc.), que se implementaron de forma centralizada, es posible que deba ponerse en contacto con el soporte técnico de Microsoft ([obtenga información](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="09426-187">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="09426-188">Proporcione la siguiente información sobre el entorno de Microsoft 365 en la incidencia de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="09426-188">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="09426-189">**Plataforma**</span><span class="sxs-lookup"><span data-stu-id="09426-189">**Platform**</span></span>|<span data-ttu-id="09426-190">**Información de depuración**</span><span class="sxs-lookup"><span data-stu-id="09426-190">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="09426-191">Office</span><span class="sxs-lookup"><span data-stu-id="09426-191">Office</span></span>  <br/> | <span data-ttu-id="09426-192">Registros Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="09426-192">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="09426-193">Id. del espacio empresarial ( [más información](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))    </span><span class="sxs-lookup"><span data-stu-id="09426-193">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="09426-194">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="09426-194">CorrelationID.</span></span> <span data-ttu-id="09426-195">Vea el origen de una de las páginas de Office y busque el valor del identificador de correlación y envíelo a soporte técnico:</span><span class="sxs-lookup"><span data-stu-id="09426-195">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="09426-196">Clientes enriquecidos (Windows y Mac)</span><span class="sxs-lookup"><span data-stu-id="09426-196">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="09426-197">Registros Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="09426-197">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="09426-198">Números de compilación de la aplicación cliente (preferiblemente como una captura de pantalla de **archivo/cuenta**)</span><span class="sxs-lookup"><span data-stu-id="09426-198">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

