---
title: Usar un script para agregar usuarios a una retención en un caso de exhibición de documentos electrónicos principal
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: bad352ff-d5d2-45d8-ac2a-6cb832f10e73
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo ejecutar un script para agregar buzones & sitios de OneDrive para la Empresa a una nueva retención asociada a un caso de exhibición de documentos electrónicos en el Centro de cumplimiento de Microsoft 365.
ms.openlocfilehash: 72fd9b8e7b63b36399d055e2eb710e8b53967e44
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126443"
---
# <a name="use-a-script-to-add-users-to-a-hold-in-a-core-ediscovery-case"></a><span data-ttu-id="66077-103">Usar un script para agregar usuarios a una retención en un caso de exhibición de documentos electrónicos principal</span><span class="sxs-lookup"><span data-stu-id="66077-103">Use a script to add users to a hold in a Core eDiscovery case</span></span>

<span data-ttu-id="66077-104">PowerShell & Centro de seguridad y cumplimiento proporciona cmdlets que le permiten automatizar tareas que requieren mucho tiempo relacionadas con la creación y administración de casos de exhibición de documentos electrónicos.</span><span class="sxs-lookup"><span data-stu-id="66077-104">Security & Compliance Center PowerShell provides cmdlets that let you automate time-consuming tasks related to creating and managing eDiscovery cases.</span></span> <span data-ttu-id="66077-105">Actualmente, el uso del caso de exhibición de documentos electrónicos principal en el Centro de seguridad y cumplimiento de & para poner un gran número de ubicaciones de contenido de administrador en retención requiere tiempo y preparación.</span><span class="sxs-lookup"><span data-stu-id="66077-105">Currently, using the Core eDiscovery case in the Security & Compliance Center to place a large number of custodian content locations on hold takes time and preparation.</span></span> <span data-ttu-id="66077-106">Por ejemplo, antes de crear una retención, debe recopilar la dirección URL de cada sitio de OneDrive para la Empresa que desee poner en retención.</span><span class="sxs-lookup"><span data-stu-id="66077-106">For example, before you create a hold, you have to collect the URL for each OneDrive for Business site that you want to place on hold.</span></span> <span data-ttu-id="66077-107">A continuación, para cada usuario que quiera poner en retención, tiene que agregar su buzón de correo y su sitio de OneDrive para la Empresa a la retención.</span><span class="sxs-lookup"><span data-stu-id="66077-107">Then for each user you want to place on hold, you have to add their mailbox and their OneDrive for Business site to the hold.</span></span> <span data-ttu-id="66077-108">Puede usar el script de este artículo para automatizar este proceso.</span><span class="sxs-lookup"><span data-stu-id="66077-108">You can use the script in this article to automate this process.</span></span>
  
<span data-ttu-id="66077-109">El script le solicita el nombre del dominio de Mi sitio de su organización (por ejemplo, en la dirección URL, el nombre de un caso de exhibición de documentos electrónicos existente, el nombre de la nueva retención asociada con el caso, una lista de direcciones de correo electrónico de los usuarios que desea poner en espera y una consulta de búsqueda para usar si desea crear una retención basada en `contoso` https://contoso-my.sharepoint.com) consultas.</span><span class="sxs-lookup"><span data-stu-id="66077-109">The script prompts you for the name of your organization's My Site domain (for example, `contoso` in the URL https://contoso-my.sharepoint.com), the name of an existing eDiscovery case, the name of the new hold that associated with the case, a list of email addresses of the users you want to put on hold, and a search query to use if you want to create a query-based hold.</span></span> <span data-ttu-id="66077-110">A continuación, el script obtiene la dirección URL del sitio de OneDrive para la Empresa para cada usuario de la lista, crea la nueva retención y, a continuación, agrega el buzón y el sitio de OneDrive para la Empresa para cada usuario de la lista a la retención.</span><span class="sxs-lookup"><span data-stu-id="66077-110">The script then gets the URL for the OneDrive for Business site for each user in the list, creates the new hold, and then adds the mailbox and OneDrive for Business site for each user in the list to the hold.</span></span> <span data-ttu-id="66077-111">El script también genera archivos de registro que contienen información sobre la nueva retención.</span><span class="sxs-lookup"><span data-stu-id="66077-111">The script also generates log files that contain information about the new hold.</span></span>
  
<span data-ttu-id="66077-112">Estos son los pasos para que esto suceda:</span><span class="sxs-lookup"><span data-stu-id="66077-112">Here are the steps to make this happen:</span></span>
  
[<span data-ttu-id="66077-113">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="66077-113">Step 1: Install the SharePoint Online Management Shell</span></span>](#step-1-install-the-sharepoint-online-management-shell)
  
[<span data-ttu-id="66077-114">Paso 2: Generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="66077-114">Step 2: Generate a list of users</span></span>](#step-2-generate-a-list-of-users)
  
[<span data-ttu-id="66077-115">Paso 3: Ejecutar el script para crear una retención y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="66077-115">Step 3: Run the script to create a hold and add users</span></span>](#step-3-run-the-script-to-create-a-hold-and-add-users)
  
## <a name="before-you-add-users-to-a-hold"></a><span data-ttu-id="66077-116">Antes de agregar usuarios a una retención</span><span class="sxs-lookup"><span data-stu-id="66077-116">Before you add users to a hold</span></span>

- <span data-ttu-id="66077-117">Debe ser miembro del grupo de roles administrador de exhibición de documentos electrónicos en el Centro de seguridad y cumplimiento de & y un administrador de SharePoint Online para ejecutar el script en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="66077-117">You have to be a member of the eDiscovery Manager role group in the Security & Compliance Center and a SharePoint Online administrator to run the script in Step 3.</span></span> <span data-ttu-id="66077-118">Para obtener más información, vea Asignar permisos de exhibición de documentos electrónicos en el Centro de seguridad & [cumplimiento de Office 365.](assign-ediscovery-permissions.md)</span><span class="sxs-lookup"><span data-stu-id="66077-118">For more information, see [Assign eDiscovery permissions in the Office‍ 365 Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>

- <span data-ttu-id="66077-119">Se puede agregar un máximo de 1.000 buzones y 100 sitios a una retención asociada a un caso de exhibición de documentos electrónicos en el Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="66077-119">A maximum of 1,000 mailboxes and 100 sites can be added to a hold that's associated with an eDiscovery case in the Security & Compliance Center.</span></span> <span data-ttu-id="66077-120">Suponiendo que todos los usuarios que quiera poner en retención tienen un sitio de OneDrive para la Empresa, puede agregar un máximo de 100 usuarios a una retención con el script de este artículo.</span><span class="sxs-lookup"><span data-stu-id="66077-120">Assuming that every user that you want to place on hold has a OneDrive for Business site, you can add a maximum of 100 users to a hold using the script in this article.</span></span>

- <span data-ttu-id="66077-121">Asegúrese de guardar la lista de usuarios que crea en el paso 2 y el script del paso 3 en la misma carpeta.</span><span class="sxs-lookup"><span data-stu-id="66077-121">Be sure to save the list of users that you create in Step 2 and the script in Step 3 to the same folder.</span></span> <span data-ttu-id="66077-122">Esto facilitará la ejecución del script.</span><span class="sxs-lookup"><span data-stu-id="66077-122">That will make it easier to run the script.</span></span>

- <span data-ttu-id="66077-123">El script agrega la lista de usuarios a una nueva retención asociada a un caso existente.</span><span class="sxs-lookup"><span data-stu-id="66077-123">The script adds the list of users to a new hold that is associated with an existing case.</span></span> <span data-ttu-id="66077-124">Asegúrese de que el caso con el que desea asociar la retención se crea antes de ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="66077-124">Be sure the case that you want to associate the hold with is created before you run the script.</span></span>

- <span data-ttu-id="66077-125">El script de este artículo admite la autenticación moderna al conectarse a PowerShell & Centro de seguridad y cumplimiento y Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="66077-125">The script in this article supports modern authentication when connecting to Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span> <span data-ttu-id="66077-126">Puede usar el script tal como está si es una organización de Microsoft 365 o GCC de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="66077-126">You can use the script as-is if you are a Microsoft 365 or a Microsoft 365 GCC organization.</span></span> <span data-ttu-id="66077-127">Si es una organización de Office 365 Germany, una organización de Microsoft 365 GCC High o una organización de Microsoft 365 DoD, tendrá que editar el script para ejecutarlo correctamente.</span><span class="sxs-lookup"><span data-stu-id="66077-127">If you are an Office 365 Germany organization, a Microsoft 365 GCC High organization, or a Microsoft 365 DoD organization, you will have to edit the script to successfully run it.</span></span> <span data-ttu-id="66077-128">En concreto, debe editar la línea y usar los parámetros `Connect-IPPSSession` *ConnectionUri* y *AzureADAuthorizationEndpointUri* (y los valores adecuados para el tipo de organización) para conectarse a PowerShell del Centro de seguridad & cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="66077-128">Specifically, you have to edit the line `Connect-IPPSSession` and use the *ConnectionUri* and *AzureADAuthorizationEndpointUri* parameters (and the appropriate values for your organization type) to connect to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="66077-129">Para obtener más información, vea los ejemplos de [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span><span class="sxs-lookup"><span data-stu-id="66077-129">For more information, see the examples in [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell#connect-to-security--compliance-center-powershell-without-using-mfa).</span></span>

- <span data-ttu-id="66077-130">El script se desconecta automáticamente de PowerShell del Centro & cumplimiento y del Shell de administración de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="66077-130">The script automatically disconnects from Security & Compliance Center PowerShell and SharePoint Online Management Shell.</span></span>

- <span data-ttu-id="66077-131">El script incluye un control de errores mínimo.</span><span class="sxs-lookup"><span data-stu-id="66077-131">The script includes minimal error handling.</span></span> <span data-ttu-id="66077-132">Su propósito principal es poner en espera de forma rápida y sencilla el buzón y el sitio de OneDrive para la Empresa de cada usuario.</span><span class="sxs-lookup"><span data-stu-id="66077-132">Its primary purpose is to quickly and easily place the mailbox and OneDrive for Business site of each user on hold.</span></span>

- <span data-ttu-id="66077-p109">Los scripts de ejemplo que se proporcionan en este tema no son compatibles con ningún servicio o programa de soporte técnico estándar de Microsoft. Los scripts de ejemplo se proporcionan tal cual, sin garantía de ningún tipo. Además, Microsoft se exime de todas las garantías implícitas, incluidas (sin limitación) las garantías implícitas de comerciabilidad o idoneidad para un propósito específico. El usuario asume todos los riesgos derivados del uso o del rendimiento de los scripts de ejemplo y la documentación. Microsoft, sus autores o cualquier persona relacionada con la creación, producción o entrega de los scripts no serán en ningún caso responsables de cualesquiera daños (incluidos, sin limitación, los daños producidos por la pérdida de beneficios comerciales, interrupción de la actividad comercial, pérdida de información empresarial u otras pérdidas económicas) derivados del uso o de la imposibilidad de uso de los scripts de ejemplo o la documentación, incluso aunque Microsoft tenga constancia de la posibilidad de que dichos daños se produzcan.</span><span class="sxs-lookup"><span data-stu-id="66077-p109">The sample scripts provided in this topic aren't supported under any Microsoft standard support program or service. The sample scripts are provided AS IS without warranty of any kind. Microsoft further disclaims all implied warranties including, without limitation, any implied warranties of merchantability or of fitness for a particular purpose. The entire risk arising out of the use or performance of the sample scripts and documentation remains with you. In no event shall Microsoft, its authors, or anyone else involved in the creation, production, or delivery of the scripts be liable for any damages whatsoever (including, without limitation, damages for loss of business profits, business interruption, loss of business information, or other pecuniary loss) arising out of the use of or inability to use the sample scripts or documentation, even if Microsoft has been advised of the possibility of such damages.</span></span>

## <a name="step-1-install-the-sharepoint-online-management-shell"></a><span data-ttu-id="66077-138">Paso 1: Instalar el Shell de administración de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="66077-138">Step 1: Install the SharePoint Online Management Shell</span></span>

<span data-ttu-id="66077-139">El primer paso es instalar el Shell de administración de SharePoint Online si aún no está instalado en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="66077-139">The first step is to install the SharePoint Online Management Shell if it's not already installed on your local computer.</span></span> <span data-ttu-id="66077-140">No es necesario usar el shell en este procedimiento, pero tiene que instalarlo porque contiene los requisitos previos requeridos por el script que se ejecuta en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="66077-140">You don't have to use the shell in this procedure, but you have to install it because it contains pre-requisites required by the script that you run in Step 3.</span></span> <span data-ttu-id="66077-141">Estos requisitos previos permiten que el script se comunique con SharePoint Online para obtener las direcciones URL de los sitios de OneDrive para la Empresa.</span><span class="sxs-lookup"><span data-stu-id="66077-141">These prerequisites allow the script to communicate with SharePoint Online to get the URLs for the OneDrive for Business sites.</span></span>
  
<span data-ttu-id="66077-142">Vaya a Configurar el entorno de Windows PowerShell shell de administración de [SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=286318) y realice los pasos 1 y 2 para instalar el Shell de administración de SharePoint Online en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="66077-142">Go to [Set up the SharePoint Online Management Shell Windows PowerShell environment](https://go.microsoft.com/fwlink/p/?LinkID=286318) and perform Step 1 and Step 2 to install the SharePoint Online Management Shell on your local computer.</span></span>

## <a name="step-2-generate-a-list-of-users"></a><span data-ttu-id="66077-143">Paso 2: Generar una lista de usuarios</span><span class="sxs-lookup"><span data-stu-id="66077-143">Step 2: Generate a list of users</span></span>

<span data-ttu-id="66077-144">El script del paso 3 creará una retención asociada a un caso de exhibición de documentos electrónicos y agregará los buzones y los sitios de OneDrive para la Empresa de una lista de usuarios a la retención.</span><span class="sxs-lookup"><span data-stu-id="66077-144">The script in Step 3 will create a hold that's associated with an eDiscovery case, and the add the mailboxes and OneDrive for Business sites of a list of users to the hold.</span></span> <span data-ttu-id="66077-145">Solo puede escribir las direcciones de correo electrónico en un archivo de texto o puede ejecutar un comando en Windows PowerShell para obtener una lista de direcciones de correo electrónico y guardarlas en un archivo (ubicado en la misma carpeta en la que guardará el script en el paso 3).</span><span class="sxs-lookup"><span data-stu-id="66077-145">You can just type the email addresses in a text file, or you can run a command in Windows PowerShell to get a list of email addresses and save them to a file (located in same folder that you'll save the script to in Step 3).</span></span>
  
<span data-ttu-id="66077-146">Este es un comando de PowerShell (que se ejecuta mediante PowerShell remoto conectado a su organización de Exchange Online) para obtener una lista de direcciones de correo electrónico para todos los usuarios de su organización y guardarlo en un archivo de texto denominado HoldUsers.txt.</span><span class="sxs-lookup"><span data-stu-id="66077-146">Here's a PowerShell command (that you run by using remote PowerShell connected to your Exchange Online organization) to get a list of email addresses for all users in your organization and save it to a text file named HoldUsers.txt.</span></span>
  
```powershell
Get-Mailbox -ResultSize unlimited -Filter { RecipientTypeDetails -eq 'UserMailbox'} | Select-Object PrimarySmtpAddress > HoldUsers.txt
```

<span data-ttu-id="66077-147">Después de ejecutar este comando, abra el archivo de texto y quite el encabezado que contiene el nombre de la  `PrimarySmtpAddress` propiedad.</span><span class="sxs-lookup"><span data-stu-id="66077-147">After you run this command, open the text file and remove the header that contains the property name,  `PrimarySmtpAddress`.</span></span> <span data-ttu-id="66077-148">A continuación, quite todas las direcciones de correo electrónico excepto las de los usuarios que desee agregar a la retención que creará en el paso 3.</span><span class="sxs-lookup"><span data-stu-id="66077-148">Then remove all email addresses except the ones for the users that you want to add to the hold that you'll create in Step 3.</span></span> <span data-ttu-id="66077-149">Asegúrese de que no hay filas en blanco antes o después de la lista de direcciones de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="66077-149">Make sure there are no blank rows before or after the list of email addresses.</span></span>
  
## <a name="step-3-run-the-script-to-create-a-hold-and-add-users"></a><span data-ttu-id="66077-150">Paso 3: Ejecutar el script para crear una retención y agregar usuarios</span><span class="sxs-lookup"><span data-stu-id="66077-150">Step 3: Run the script to create a hold and add users</span></span>

<span data-ttu-id="66077-151">Cuando ejecute el script en este paso, se le pedirá la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="66077-151">When you run the script in this step, it will prompt you for the following information.</span></span> <span data-ttu-id="66077-152">Asegúrese de tener esta información lista antes de ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="66077-152">Be sure to have this information ready before you run the script.</span></span>
  
- <span data-ttu-id="66077-153">**Sus credenciales de usuario:** El script usará sus credenciales para conectarse al Centro de seguridad & cumplimiento con PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="66077-153">**Your user credentials:** The script will use your credentials to connect to the Security & Compliance Center with remote PowerShell.</span></span> <span data-ttu-id="66077-154">También usará estas credenciales para obtener acceso a SharePoint Online y obtener las direcciones URL de OneDrive para la Empresa para la lista de usuarios.</span><span class="sxs-lookup"><span data-stu-id="66077-154">It will also use these credentials to access SharePoint Online to get the OneDrive for Business URLs for the list of users.</span></span>

- <span data-ttu-id="66077-155">**Nombre de su dominio de Mi sitio:** El dominio Mi sitio es el dominio que contiene todos los sitios de OneDrive para la Empresa de su organización.</span><span class="sxs-lookup"><span data-stu-id="66077-155">**Name of your My Site domain:** The My Site domain is the domain that contains all the OneDrive for Business sites in your organization.</span></span> <span data-ttu-id="66077-156">Por ejemplo, si la dirección URL de su dominio de Mi sitio es , escribiría cuando el script le pida el nombre de **https://contoso-my.sharepoint.com** su dominio de Mi  `contoso` sitio.</span><span class="sxs-lookup"><span data-stu-id="66077-156">For example, if the URL for your My Site domain is **https://contoso-my.sharepoint.com**, then you would enter  `contoso` when the script prompts you for the name of your My Site domain.</span></span>

- <span data-ttu-id="66077-157">**Nombre del caso:** Nombre de un caso existente.</span><span class="sxs-lookup"><span data-stu-id="66077-157">**Name of the case:** The name of an existing case.</span></span> <span data-ttu-id="66077-158">El script creará una nueva retención asociada a este caso.</span><span class="sxs-lookup"><span data-stu-id="66077-158">The script will create a new hold that is associated with this case.</span></span>

- <span data-ttu-id="66077-159">**Nombre de la retención:** Nombre de la retención que el script creará y asociará con el caso especificado.</span><span class="sxs-lookup"><span data-stu-id="66077-159">**Name of the hold:** The name of the hold the script will create and associate with the specified case.</span></span>

- <span data-ttu-id="66077-160">**Consulta de búsqueda para una retención basada en consulta:** Puede crear una retención basada en consultas para que solo se reteje el contenido que cumpla los criterios de búsqueda especificados.</span><span class="sxs-lookup"><span data-stu-id="66077-160">**Search query for a query-based hold:** You can create a query-based hold so that only the content that meets the specified search criteria is placed on hold.</span></span> <span data-ttu-id="66077-161">Para poner todo el contenido en espera, presione **ENTRAR** cuando se le solicite una consulta de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="66077-161">To place all content on hold, just press **Enter** when you're prompted for a search query.</span></span>

- <span data-ttu-id="66077-162">**Activar o no la retención:** Puede hacer que el script active la retención después de crearla o puede hacer que el script cree la retención sin habilitarla.</span><span class="sxs-lookup"><span data-stu-id="66077-162">**Turning on the hold or not:** You can have the script turn on the hold after it's created or you can have the script create the hold without enabling it.</span></span> <span data-ttu-id="66077-163">Si no tiene el script activando la retención, puede activarla más adelante en el Centro de seguridad & Cumplimiento o ejecutando los siguientes comandos de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="66077-163">If you don't have the script turn on the hold, you can turn it on later in the Security & Compliance Center or by running the following PowerShell commands:</span></span>

  ```powershell
  Set-CaseHoldPolicy -Identity <name of the hold> -Enabled $true
  ```

  ```powershell
  Set-CaseHoldRule -Identity <name of the hold> -Disabled $false
  ```

- <span data-ttu-id="66077-164">**Nombre del archivo de texto con** la lista de usuarios: el nombre del archivo de texto del paso 2 que contiene la lista de usuarios que se agregarán a la retención.</span><span class="sxs-lookup"><span data-stu-id="66077-164">**Name of the text file with the list of users** - The name of the text file from Step 2 that contains the list of users to add to the hold.</span></span> <span data-ttu-id="66077-165">Si este archivo se encuentra en la misma carpeta que el script, simplemente escriba el nombre del archivo (por ejemplo, HoldUsers.txt).</span><span class="sxs-lookup"><span data-stu-id="66077-165">If this file is located in the same folder as the script, just type the name of the file (for example, HoldUsers.txt).</span></span> <span data-ttu-id="66077-166">Si el archivo de texto está en otra carpeta, escriba el nombre de la ruta de acceso completa del archivo.</span><span class="sxs-lookup"><span data-stu-id="66077-166">If the text file is in another folder, type the full pathname of the file.</span></span>

<span data-ttu-id="66077-167">Después de recopilar la información que el script le pedirá, el paso final es ejecutar el script para crear la nueva retención y agregar usuarios a él.</span><span class="sxs-lookup"><span data-stu-id="66077-167">After you've collected the information that the script will prompt you for, the final step is to run the script to create the new hold and add users to it.</span></span>
  
1. <span data-ttu-id="66077-168">Guarde el siguiente texto en un archivo Windows PowerShell script con el sufijo de nombre de archivo `.ps1` .</span><span class="sxs-lookup"><span data-stu-id="66077-168">Save the following text to a Windows PowerShell script file by using a filename suffix of `.ps1`.</span></span> <span data-ttu-id="66077-169">Por ejemplo, `AddUsersToHold.ps1`.</span><span class="sxs-lookup"><span data-stu-id="66077-169">For example, `AddUsersToHold.ps1`.</span></span>

```powershell
#script begin
" "
write-host "***********************************************"
write-host "   Security & Compliance Center PowerShell  " -foregroundColor yellow -backgroundcolor darkgreen
write-host "   Core eDiscovery cases - Add users to a hold   " -foregroundColor yellow -backgroundcolor darkgreen 
write-host "***********************************************"
" "
# Connect to SCC PowerShell using modern authentication
if (!$SccSession)
{
  Import-Module ExchangeOnlineManagement
  Connect-IPPSSession
}

# Get the organization's domain name. We use this to create the SharePoint admin URL and root URL for OneDrive for Business.
""
$mySiteDomain = Read-Host "Enter the domain name for your SharePoint organization. We use this name to connect to SharePoint admin center and for the OneDrive URLs in your organization. For example, 'contoso' in 'https://contoso-admin.sharepoint.com' and 'https://contoso-my.sharepoint.com'"
""

# Connect to PnP Online using modern authentication
Import-Module PnP.PowerShell
Connect-PnPOnline -Url https://$mySiteDomain-admin.sharepoint.com -UseWebLogin

# Load the SharePoint assemblies from the SharePoint Online Management Shell
# To install, go to https://go.microsoft.com/fwlink/p/?LinkId=255251
if (!$SharePointClient -or !$SPRuntime -or !$SPUserProfile)
{
    $SharePointClient = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client")
    $SPRuntime = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.Runtime")
    $SPUserProfile = [System.Reflection.Assembly]::LoadWithPartialName("Microsoft.SharePoint.Client.UserProfiles")
    if (!$SharePointClient)
    {
        Write-Error "The SharePoint Online Management Shell isn't installed. Please install it from: https://go.microsoft.com/fwlink/p/?LinkId=255251 and then re-run this script."
        return;
    }
}

# Get other required information
do{
$casename = Read-Host "Enter the name of the case"
$caseexists = (get-compliancecase -identity "$casename" -erroraction SilentlyContinue).isvalid
if($caseexists -ne 'True')
{""
write-host "A case named '$casename' doesn't exist. Please specify the name of an existing case, or create a new case and then re-run the script." -foregroundColor Yellow
""}
}While($caseexists -ne 'True')
""
do{
$holdName = Read-Host "Enter the name of the new hold"
$holdexists=(get-caseholdpolicy -identity "$holdname" -case "$casename" -erroraction SilentlyContinue).isvalid
if($holdexists -eq 'True')
{""
write-host "A hold named '$holdname' already exists. Please specify a new hold name." -foregroundColor Yellow
""}
}While($holdexists -eq 'True')
""
$holdQuery = Read-Host "Enter a search query to create a query-based hold, or press Enter to hold all content"
""
$holdstatus = read-host "Do you want the hold enabled after it's created? (Yes/No)"
do{
""
$inputfile = read-host "Enter the name of the text file that contains the email addresses of the users to add to the hold"
""
$fileexists = test-path -path $inputfile
if($fileexists -ne 'True'){write-host "$inputfile doesn't exist. Please enter a valid file name." -foregroundcolor Yellow}
}while($fileexists -ne 'True')
#Import the list of addresses from the txt file.  Trim any excess spaces and make sure all addresses 
    #in the list are unique.
  [array]$emailAddresses = Get-Content $inputfile -ErrorAction SilentlyContinue | where {$_.trim() -ne ""}  | foreach{ $_.Trim() }
  [int]$dupl = $emailAddresses.count
  [array]$emailAddresses = $emailAddresses | select-object -unique
  $dupl -= $emailAddresses.count
#Validate email addresses so the hold creation does not run in to an error.
if($emailaddresses.count -gt 0){
write-host ($emailAddresses).count "addresses were found in the text file. There were $dupl duplicate entries in the file." -foregroundColor Yellow
""
Write-host "Validating the email addresses. Please wait..." -foregroundColor Yellow
""
$finallist =@()
foreach($emailAddress in $emailAddresses)
{
if((get-recipient $emailaddress -erroraction SilentlyContinue).isvalid -eq 'True')
{$finallist += $emailaddress}
else {"Unable to find the user $emailaddress"
[array]$excludedlist += $emailaddress}
}
""
#Find user's OneDrive account URL using email address
Write-Host "Getting the URL for each user's OneDrive for Business site." -foregroundColor Yellow 
""
$AdminUrl = "https://$mySiteDomain-admin.sharepoint.com"
$mySiteUrlRoot = "https://$mySiteDomain-my.sharepoint.com"
$urls = @()
foreach($emailAddress in $emailAddresses)
{
try
{
$url=Get-PnPUserProfileProperty -Account $emailAddress | Select PersonalUrl
$urls += $url.PersonalUrl
       Write-Host "- $emailAddress => $url"
       [array]$ODadded += $url.PersonalUrl
       }catch { 
 Write-Warning "Could not locate OneDrive for $emailAddress"
 [array]$ODExluded += $emailAddress
 Continue }
}
$urls | FL
if(($finallist.count -gt 0) -or ($urls.count -gt 0)){
""
Write-Host "Creating the hold named $holdname. Please wait..." -foregroundColor Yellow
if(($holdstatus -eq "Y") -or ($holdstatus -eq  "y") -or ($holdstatus -eq "yes") -or ($holdstatus -eq "YES")){
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $True | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery | out-null
}
else{
New-CaseHoldPolicy -Name "$holdName" -Case "$casename" -ExchangeLocation $finallist -SharePointLocation $urls -Enabled $false | out-null
New-CaseHoldRule -Name "$holdName" -Policy "$holdname" -ContentMatchQuery $holdQuery -disabled $true | out-null
}
""
}
else {"No valid locations were identified. Therefore, the hold wasn't created."}
#write log files (if needed)
$newhold=Get-CaseHoldPolicy -Identity "$holdname" -Case "$casename" -erroraction SilentlyContinue
$newholdrule=Get-CaseHoldRule -Identity "$holdName" -erroraction SilentlyContinue
if(($ODAdded.count -gt 0) -or ($ODExluded.count -gt 0) -or ($finallist.count -gt 0) -or ($excludedlist.count -gt 0) -or ($newhold.isvalid -eq 'True') -or ($newholdrule.isvalid -eq 'True'))
{
Write-Host "Generating output files..." -foregroundColor Yellow
if($ODAdded.count -gt 0){
"OneDrive Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.SharePointLocation.name | add-content .\LocationsOnHold.txt}
if($ODExluded.count -gt 0){ 
"Users without OneDrive locations" | add-content .\LocationsNotOnHold.txt
"================================" | add-content .\LocationsNotOnHold.txt
$ODExluded | add-content .\LocationsNotOnHold.txt}
if($finallist.count -gt 0){
" " | add-content .\LocationsOnHold.txt
"Exchange Locations" | add-content .\LocationsOnHold.txt
"==================" | add-content .\LocationsOnHold.txt 
$newhold.ExchangeLocation.name | add-content .\LocationsOnHold.txt}
if($excludedlist.count -gt 0){
" "| add-content .\LocationsNotOnHold.txt
"Mailboxes not added to the hold" | add-content .\LocationsNotOnHold.txt
"===============================" | add-content .\LocationsNotOnHold.txt
$excludedlist | add-content .\LocationsNotOnHold.txt}
$FormatEnumerationLimit=-1
if($newhold.isvalid -eq 'True'){$newhold|fl >.\GetCaseHoldPolicy.txt}
if($newholdrule.isvalid -eq 'True'){$newholdrule|Fl >.\GetCaseHoldRule.txt}
}
}
else {"The hold wasn't created because no valid entries were found in the text file."}
""
#Disconnect from SCC PowerShell and PnPOnline

Write-host "Disconnecting from SCC PowerShell and PnP Online" -foregroundColor Yellow
Get-PSSession | Remove-PSSession
Disconnect-PnPOnline

Write-host "Script complete!" -foregroundColor Yellow
""
#script end
```

2. <span data-ttu-id="66077-170">En el equipo local, abra Windows PowerShell vaya a la carpeta donde guardó el script.</span><span class="sxs-lookup"><span data-stu-id="66077-170">On your local computer, open Windows PowerShell and go to the folder where you saved the script.</span></span>

3. <span data-ttu-id="66077-171">Ejecute el script; por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="66077-171">Run the script; for example:</span></span>

   ```powershell
   .\AddUsersToHold.ps1
   ```

4. <span data-ttu-id="66077-172">Escriba la información que el script le solicita.</span><span class="sxs-lookup"><span data-stu-id="66077-172">Enter the information that the script prompts you for.</span></span>

   <span data-ttu-id="66077-173">El script se conecta a PowerShell del Centro de seguridad & Cumplimiento y, a continuación, crea la nueva retención en el caso de eDiscovery y agrega los buzones y OneDrive para la Empresa para los usuarios de la lista.</span><span class="sxs-lookup"><span data-stu-id="66077-173">The script connects to Security & Compliance Center PowerShell, and then creates the new hold in the eDiscovery case and adds the mailboxes and OneDrive for Business for the users in the list.</span></span> <span data-ttu-id="66077-174">Puede ir al caso en la página **eDiscovery** en el Centro de seguridad y & cumplimiento para ver la nueva retención.</span><span class="sxs-lookup"><span data-stu-id="66077-174">You can go to the case on the **eDiscovery** page in the Security & Compliance Center to view the new hold.</span></span>

<span data-ttu-id="66077-175">Una vez que el script haya terminado de ejecutarse, crea los siguientes archivos de registro y los guarda en la carpeta donde se encuentra el script.</span><span class="sxs-lookup"><span data-stu-id="66077-175">After the script is finished running, it creates the following log files, and saves them to the folder where the script is located.</span></span>
  
- <span data-ttu-id="66077-176">**LocationsOnHold.txt:** Contiene una lista de buzones y sitios de OneDrive para la Empresa que el script colocó correctamente en retención.</span><span class="sxs-lookup"><span data-stu-id="66077-176">**LocationsOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script successfully placed on hold.</span></span>

- <span data-ttu-id="66077-177">**LocationsNotOnHold.txt:** Contiene una lista de buzones y sitios de OneDrive para la Empresa que el script no ha puesto en retención.</span><span class="sxs-lookup"><span data-stu-id="66077-177">**LocationsNotOnHold.txt:** Contains a list of mailboxes and OneDrive for Business sites that the script did not place on hold.</span></span> <span data-ttu-id="66077-178">Si un usuario tiene un buzón, pero no un sitio de OneDrive para la Empresa, el usuario se incluiría en la lista de sitios de OneDrive para la Empresa que no se colocaron en retención.</span><span class="sxs-lookup"><span data-stu-id="66077-178">If a user has a mailbox, but not a OneDrive for Business site, the user would be included in the list of OneDrive for Business sites that weren't placed on hold.</span></span>

- <span data-ttu-id="66077-179">**GetCaseHoldPolicy.txt:** Contiene el resultado del cmdlet **Get-CaseHoldPolicy** para la nueva retención, que el script ejecutó después de crear la nueva retención.</span><span class="sxs-lookup"><span data-stu-id="66077-179">**GetCaseHoldPolicy.txt:** Contains the output of the **Get-CaseHoldPolicy** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="66077-180">La información devuelta por este cmdlet incluye una lista de usuarios cuyos buzones y sitios de OneDrive para la Empresa se colocaron en retención y si la retención está habilitada o deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="66077-180">The information returned by this cmdlet includes a list of users whose mailboxes and OneDrive for Business sites were placed on hold and whether the hold is enabled or disabled.</span></span> 

- <span data-ttu-id="66077-181">**GetCaseHoldRule.txt:** Contiene el resultado del cmdlet **Get-CaseHoldRule para** la nueva retención, que el script ejecutó después de crear la nueva retención.</span><span class="sxs-lookup"><span data-stu-id="66077-181">**GetCaseHoldRule.txt:** Contains the output of the **Get-CaseHoldRule** cmdlet for the new hold, which the script ran after creating the new hold.</span></span> <span data-ttu-id="66077-182">La información devuelta por este cmdlet incluye la consulta de búsqueda si usó el script para crear una retención basada en consulta.</span><span class="sxs-lookup"><span data-stu-id="66077-182">The information returned by this cmdlet includes the search query if you used the script to create a query-based hold.</span></span>
