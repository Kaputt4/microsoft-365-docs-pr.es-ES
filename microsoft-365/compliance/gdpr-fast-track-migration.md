---
title: RGPD
description: 'Guía técnica de Microsoft: CONJUNTO DE HERRAMIENTAS DE MIGRACIONES DE FASTTRACK PARA ENVIAR SOLICITUDES DE ELIMINACIÓN'
keywords: Migración de FastTrack, Microsoft 365 Educación, documentación de Microsoft 365, RGPD
localization_priority: Priority
Robots: NOFOLLOW,NOINDEX
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: mohitku
author: MohitKumar
manager: laurawi
audience: itpro
ms.collection:
- GDPR
- M365-security-compliance
titleSuffix: Microsoft GDPR
ms.openlocfilehash: 89ddb00045e2a17821ef2e841ad9a9b4c38d2219
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596467"
---
# <a name="fasttrack-migration-toolset-for-submitting-delete-request"></a><span data-ttu-id="c45a0-104">Conjunto de herramientas de migración de FastTrack para cursar solicitudes de eliminación</span><span class="sxs-lookup"><span data-stu-id="c45a0-104">FastTrack Migration Toolset for Submitting Delete Request</span></span>

## <a name="toolset-purpose"></a><span data-ttu-id="c45a0-105">Finalidad del conjunto de herramientas</span><span class="sxs-lookup"><span data-stu-id="c45a0-105">Toolset purpose</span></span>

<span data-ttu-id="c45a0-p101">Si es un cliente que actualmente está realizando una migración de FastTrack, eliminar la cuenta de usuario de Office 365 no hará que se elimine la copia de datos que el equipo de FastTrack de Microsoft conserva, cosa que hace con el único propósito de completar la migración. Si quiere que el equipo de Microsoft FastTrack elimine también esa copia de datos durante la migración, curse una solicitud a través de este conjunto de herramientas. En el transcurso habitual de las actividades, Microsoft FastTrack eliminará todas las copias de datos cuando la migración finalice.</span><span class="sxs-lookup"><span data-stu-id="c45a0-p101">In the event that you are a customer currently engaged in FastTrack migrations, deleting the Office 365 user account will not delete the data copy held by the Microsoft FastTrack team, which is held for the sole purpose of completing the migration. If during the migration you would like the Microsoft FastTrack team to also delete the data copy, submit a request via this tool set. In the ordinary course of business, Microsoft FastTrack will delete all data copies once the migration is complete.</span></span>

### <a name="supported-platforms"></a><span data-ttu-id="c45a0-109">Plataformas compatibles</span><span class="sxs-lookup"><span data-stu-id="c45a0-109">Supported platforms</span></span>
<span data-ttu-id="c45a0-p102">Microsoft admite la versión inicial de este conjunto de herramientas en la plataforma de Windows y en la consola de PowerShell. Este conjunto de herramientas admite las siguientes plataformas conocidas:</span><span class="sxs-lookup"><span data-stu-id="c45a0-p102">Microsoft supports the initial release of this  toolset in the Windows platform and PowerShell console. The following known platforms are supported by this toolset:</span></span>
 
<span data-ttu-id="c45a0-112">***Tabla 1: plataformas admitidas por este conjunto de herramientas***</span><span class="sxs-lookup"><span data-stu-id="c45a0-112">***Table 1 — Platforms supported by this toolset***</span></span>
 
<!--start table here HEADER -->
 
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
| |<span data-ttu-id="c45a0-113">**Windows 7**</span><span class="sxs-lookup"><span data-stu-id="c45a0-113">**Windows 7**</span></span>|<span data-ttu-id="c45a0-114">**Windows 8**</span><span class="sxs-lookup"><span data-stu-id="c45a0-114">**Windows 8**</span></span>|<span data-ttu-id="c45a0-115">**Windows 10**</span><span class="sxs-lookup"><span data-stu-id="c45a0-115">**Windows 10**</span></span>|<span data-ttu-id="c45a0-116">**Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="c45a0-116">**Windows Server 2012**</span></span>|<span data-ttu-id="c45a0-117">**Windows Server 2016**</span><span class="sxs-lookup"><span data-stu-id="c45a0-117">**Windows Server 2016**</span></span>|
|<span data-ttu-id="c45a0-118">PS 5.0</span><span class="sxs-lookup"><span data-stu-id="c45a0-118">PS 5.0</span></span>|<span data-ttu-id="c45a0-119">No</span><span class="sxs-lookup"><span data-stu-id="c45a0-119">Not</span></span><br/><span data-ttu-id="c45a0-120">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-120">Supported</span></span>|<span data-ttu-id="c45a0-121">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-121">Supported</span></span>|<span data-ttu-id="c45a0-122">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-122">Supported</span></span>|<span data-ttu-id="c45a0-123">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-123">Supported</span></span>|<span data-ttu-id="c45a0-124">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-124">Supported</span></span>|
|<span data-ttu-id="c45a0-125">PS 5.1</span><span class="sxs-lookup"><span data-stu-id="c45a0-125">PS 5.1</span></span>|<span data-ttu-id="c45a0-126">No</span><span class="sxs-lookup"><span data-stu-id="c45a0-126">Not</span></span><br/><span data-ttu-id="c45a0-127">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-127">Supported</span></span>|<span data-ttu-id="c45a0-128">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-128">Supported</span></span>|<span data-ttu-id="c45a0-129">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-129">Supported</span></span>|<span data-ttu-id="c45a0-130">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-130">Supported</span></span>|<span data-ttu-id="c45a0-131">Compatible.</span><span class="sxs-lookup"><span data-stu-id="c45a0-131">Supported</span></span>|
|||
 
<!-- end of table -->

### <a name="obtaining-the-toolset"></a><span data-ttu-id="c45a0-132">Obtener el conjunto de herramientas</span><span class="sxs-lookup"><span data-stu-id="c45a0-132">Obtaining the toolset</span></span>

<span data-ttu-id="c45a0-p103">Este conjunto de herramientas está disponible en la Galería de PowerShell de la aplicación de consola de PowerShell. Para encontrar y cargar este módulo de cmdlet, abra primero PowerShell en el modo de administrador para, así, contar con los permisos adecuados para instalar el módulo. Si no ha usado PowerShell anteriormente, vaya a la barra de tareas de Windows y, en el cuadro de búsqueda, escriba "PowerShell". Seleccione la aplicación de consola haciendo clic con el botón derecho, elija **Ejecutar como administrador** y haga clic en **Sí** para ejecutar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c45a0-p103">This toolset is available in the PowerShell Gallery on the PowerShell console application.  To locate and load this cmdlet module, first open PowerShell in administrator mode so it has the appropriate permissions to install the module. If you have not used PowerShell previously go to your Windows Task Bar and in the search box type “PowerShell”. Select the console app using right-click and choose **Run as administrator**, then click **Yes** to run Windows PowerShell.</span></span>

![PowerShell: ejecutar como administrador](media/fasttrack-powershell_image.png)

![PowerShell: permitir que la aplicación haga cambios](media/fasttrack-run-powershell_image.png)

<span data-ttu-id="c45a0-p104">Con la consola ya abierta, hay que configurar los permisos que permitan ejecutar scripts. Para ello, escriba el siguiente comando: "Set-ExecutionPolicy – ExecutionPolicy: Bypass – Scope: Process".</span><span class="sxs-lookup"><span data-stu-id="c45a0-p104">Now that the console is open, you need to set permissions for script execution. Type the following command to allow the scripts to run: ‘Set-ExecutionPolicy — ExecutionPolicy: Bypass — Scope: Process’</span></span>

<span data-ttu-id="c45a0-141">Se le pedirá que confirme esta acción, dado que el administrador puede cambiar el ámbito a su conveniencia.</span><span class="sxs-lookup"><span data-stu-id="c45a0-141">You will be prompted to confirm this action, as the administrator can change the scope at their discretion.</span></span>

<span data-ttu-id="c45a0-142">***Definir la directiva de ejecución***</span><span class="sxs-lookup"><span data-stu-id="c45a0-142">***Set Execution Policy***</span></span>

![Cambio de establecimiento de la directiva de ejecución en PowerShell](media/powershell-set-execution-policy_image.png)

<span data-ttu-id="c45a0-144">Ahora que la consola está configurada para permitir la ejecución de scripts, ejecute el siguiente comando para instalar el módulo:</span><span class="sxs-lookup"><span data-stu-id="c45a0-144">Now that the console is set to allow the script,  run this next command to install the module:</span></span>

><span data-ttu-id="c45a0-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span><span class="sxs-lookup"><span data-stu-id="c45a0-145">`Install-Module -Name Microsoft.FastTrack ` -Repository PSGallery \`</span></span>
>        
>               -WarningAction: SilentlyContinue `
>               -Force’

### <a name="prerequisites-for-module"></a><span data-ttu-id="c45a0-146">Requisitos previos del módulo</span><span class="sxs-lookup"><span data-stu-id="c45a0-146">Prerequisites for module</span></span>
<span data-ttu-id="c45a0-p105">Para ejecutar correctamente este módulo, puede que sea necesario instalar módulos dependientes para usarlos si aún no están instalados. Posiblemente deba reiniciar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c45a0-p105">To successfully execute this module, you may need to install dependent modules for use if they are not already installed. You may need to restart PowerShell.</span></span>  

<span data-ttu-id="c45a0-149">Para enviar una solicitud de interesado, antes tiene que iniciar sesión con sus credenciales de Office 365; cuando especifique las credenciales apropiadas, se validará el estado de su cuenta de administrador global y se recopilará información del inquilino.</span><span class="sxs-lookup"><span data-stu-id="c45a0-149">In order to submit a DSR, you must first log in using your Office 365 credentials — entering the proper credentials will validate your global administrator status and collect tenant information.</span></span> 

<span data-ttu-id="c45a0-150">**Login-FastTrackAccount -ApiKey: \<Clave de API proporcionada por FastTrack MVM\>**</span><span class="sxs-lookup"><span data-stu-id="c45a0-150">**Login-FastTrackAccount -ApiKey: \<API Key provided by FastTrack MVM\>**</span></span>

<span data-ttu-id="c45a0-151">Tras haber iniciado sesión correctamente, la clave y las credenciales se almacenarán para su uso con módulos FastTrack durante lo que quede de la sesión actual de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c45a0-151">Once successfully logged in, the credentials and key will be stored for use with FastTrack modules for the remainder of the current PowerShell session.</span></span>

<span data-ttu-id="c45a0-152">Si necesita conectarse a un entorno de nube que no sea comercial, deberá agregar *-Environment* al comando *Login* con uno de los siguientes entornos válidos:</span><span class="sxs-lookup"><span data-stu-id="c45a0-152">If you need to connect to a cloud environment, other than commercial, *-Environment* will need to be added to *Log in* command with one of the following valid environments:</span></span>
- <span data-ttu-id="c45a0-153">AzureCloud</span><span class="sxs-lookup"><span data-stu-id="c45a0-153">AzureCloud</span></span>
- <span data-ttu-id="c45a0-154">AzureChinaCloud</span><span class="sxs-lookup"><span data-stu-id="c45a0-154">AzureChinaCloud</span></span>
- <span data-ttu-id="c45a0-155">AzureGermanCloud</span><span class="sxs-lookup"><span data-stu-id="c45a0-155">AzureGermanCloud</span></span>
- <span data-ttu-id="c45a0-156">AzureUSGovernmentCloud</span><span class="sxs-lookup"><span data-stu-id="c45a0-156">AzureUSGovernmentCloud</span></span>

<span data-ttu-id="c45a0-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <entorno de nube\>**</span><span class="sxs-lookup"><span data-stu-id="c45a0-157">**Login-FastTrackAcccount -ApiKey\ <API Key provided by FastTrack MVM> -Environment: <cloud environment\>**</span></span>

<span data-ttu-id="c45a0-158">Para enviar una solicitud de interesado, ejecute el siguiente comando: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span><span class="sxs-lookup"><span data-stu-id="c45a0-158">To submit a DSR request, run the following command: Submit-FastTrackGdprDsrRequest -DsrRequestUserEmail: SubjectUserEmail@mycompany.com</span></span>

<span data-ttu-id="c45a0-p106">Si el cmdlet se ejecuta correctamente, devolverá un objeto de identificador de transacción. Guárdelo.</span><span class="sxs-lookup"><span data-stu-id="c45a0-p106">On success — the cmdlet will return a Transaction ID object. Please retain the Transaction ID.</span></span>


#### <a name="checking-the-status-of-a-request-transaction"></a><span data-ttu-id="c45a0-161">Comprobar el estado de una transacción de solicitud</span><span class="sxs-lookup"><span data-stu-id="c45a0-161">Checking the status of a request transaction</span></span>

<span data-ttu-id="c45a0-162">Ejecutar la siguiente función usando el identificador de transacción obtenido anteriormente: Get-FastTrackGdprDsrRequest -TransactionID: "identificadorDeTransacción"</span><span class="sxs-lookup"><span data-stu-id="c45a0-162">Run the following function using the previously obtained Transaction ID: Get-FastTrackGdprDsrRequest -TransactionID: “YourTransactionID”</span></span>

#### <a name="transaction-status-codes"></a><span data-ttu-id="c45a0-163">Códigos de estado de la transacción</span><span class="sxs-lookup"><span data-stu-id="c45a0-163">Transaction Status Codes</span></span>
<!--start table here no header -->

|||
|:-----|:-----|:-----|
|<span data-ttu-id="c45a0-164">**Transacción**</span><span class="sxs-lookup"><span data-stu-id="c45a0-164">**Transaction**</span></span> |<span data-ttu-id="c45a0-165">**Estado**</span><span class="sxs-lookup"><span data-stu-id="c45a0-165">**Status**</span></span>|
|<span data-ttu-id="c45a0-166">**Created**</span><span class="sxs-lookup"><span data-stu-id="c45a0-166">**Created**</span></span> |<span data-ttu-id="c45a0-167">La solicitud se ha creado.</span><span class="sxs-lookup"><span data-stu-id="c45a0-167">Request has been created</span></span>|
|<span data-ttu-id="c45a0-168">**Failed**</span><span class="sxs-lookup"><span data-stu-id="c45a0-168">**Failed**</span></span>|<span data-ttu-id="c45a0-169">La solicitud no se ha podido crear. Vuelva a enviarla o póngase en contacto con el equipo de soporte técnico.</span><span class="sxs-lookup"><span data-stu-id="c45a0-169">Request failed to create, please resubmit, or contact support</span></span>|
|<span data-ttu-id="c45a0-170">**Completed**</span><span class="sxs-lookup"><span data-stu-id="c45a0-170">**Completed**</span></span>|<span data-ttu-id="c45a0-171">La solicitud se ha completado y saneado.</span><span class="sxs-lookup"><span data-stu-id="c45a0-171">Request has been completed and sanitized</span></span>|
|||

<!-- end of table -->

<!-- original version: **Created**  Request has been created<br/>**Failed** Request failed to create, please resubmit, or contact support<br/>**Completed** Request has been completed and sanitized -->


## <a name="learn-more"></a><span data-ttu-id="c45a0-172">Más información</span><span class="sxs-lookup"><span data-stu-id="c45a0-172">Learn more</span></span>
[<span data-ttu-id="c45a0-173">Centro de confianza de Microsoft</span><span class="sxs-lookup"><span data-stu-id="c45a0-173">Microsoft Trust Center</span></span>](https://www.microsoft.com/TrustCenter/Privacy/gdpr/default.aspx)