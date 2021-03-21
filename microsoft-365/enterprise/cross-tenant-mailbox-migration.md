---
title: Migración de buzones de inquilinos cruzados
description: Cómo mover buzones entre inquilinos de Microsoft 365 u Office 365.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: 09/21/2020
ms.reviewer: georgiah
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 7c3b4f82d94888cfa6c63b25f20130a38f8b4c9f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919205"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="8e2f0-103">Migración de buzones entre inquilinos (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="8e2f0-104">Anteriormente, cuando un inquilino de Exchange Online necesitaba mover buzones a otro inquilino en el mismo servicio de Exchange Online, tendría que desasogarlos completamente en el entorno local y, a continuación, incorporarlos a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="8e2f0-105">Con la nueva característica de migración de buzones entre inquilinos, los administradores de inquilinos de los inquilinos de origen y de destino pueden mover buzones entre los inquilinos con dependencias mínimas de infraestructura en sus sistemas locales.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="8e2f0-106">Esto quita la necesidad de retirar y incorporar buzones.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-106">This removes the need to off-board and onboard mailboxes.</span></span>

<span data-ttu-id="8e2f0-107">Normalmente, durante fusiones o desinstituras, necesita la capacidad de mover usuarios y contenido a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="8e2f0-108">Cuando el administrador de inquilinos de destino ejecuta el movimiento, se denomina movimiento de extracción, similar a las migraciones locales a las migraciones de incorporación en la nube.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="8e2f0-109">Los administradores de inquilinos pueden realizar un autoservicio total de los movimientos de buzones de Exchange entre inquilinos, mediante interfaces conocidas que se pueden incluir en los flujos de trabajo más grandes necesarios para realizar la transición de usuarios a su nueva organización.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="8e2f0-110">Los administradores pueden usar el cmdlet, disponible a través del rol de administración Mover buzones, para ejecutar movimientos `New-MigrationBatch` entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="8e2f0-111">El proceso de movimiento incluye comprobaciones de autorización de inquilino durante la sincronización y la finización de buzones.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="8e2f0-112">Los usuarios que migran deben estar presentes en el sistema exchange online de inquilino de destino como MailUsers, marcados con atributos específicos para habilitar los movimientos entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="8e2f0-113">El sistema producirá un error en los movimientos de los usuarios que no estén configurados correctamente en el espacio empresarial de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span>  

<span data-ttu-id="8e2f0-114">Cuando se completan los movimientos, el buzón del sistema de origen se convierte en MailUser y el targetAddress (que se muestra como ExternalEmailAddress en Exchange) se marca con la dirección de enrutamiento al inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="8e2f0-115">Este proceso deja el mailuser heredado en el inquilino de origen y permite un período de coexistencia y enrutamiento de correo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="8e2f0-116">Cuando los procesos empresariales lo permiten, el inquilino de origen puede quitar el mailuser de origen o convertirlo en un contacto de correo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="8e2f0-117">Las migraciones de buzones de Exchange entre inquilinos se admiten solo para inquilinos en la nube o híbrida, o cualquier combinación de los dos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="8e2f0-118">En este artículo se describe el proceso de movimientos de buzones entre inquilinos y se proporcionan instrucciones sobre cómo preparar los inquilinos de origen y de destino para el movimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span>  

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="8e2f0-119">Preparación de inquilinos de origen y de destino</span><span class="sxs-lookup"><span data-stu-id="8e2f0-119">Preparing source and target tenants</span></span>

<span data-ttu-id="8e2f0-120">La característica de migración de buzones de Exchange entre inquilinos requiere autorización y ámbito para las migraciones entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="8e2f0-121">Con la aplicación de Azure Enterprise y las soluciones de almacenamiento de Key Vault, los administradores de inquilinos ahora tienen la capacidad de administrar la autorización y el ámbito de las migraciones de buzones de Exchange Online de un inquilino a otro.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="8e2f0-122">Los movimientos de buzones entre inquilinos admiten un modelo de invitación y consentimiento para establecer una aplicación de Azure Active Directory (Azure AD) usada para la autenticación entre un par de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="8e2f0-123">También se requieren componentes adicionales, como una relación de organización y un extremo de migración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="8e2f0-124">Esta sección no incluye los pasos específicos necesarios para preparar los objetos de usuario MailUser en el directorio de destino, ni incluye el comando de ejemplo para enviar un lote de migración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="8e2f0-125">Consulte Prepare [target user objects for migration para](#prepare-target-user-objects-for-migration) obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8e2f0-126">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8e2f0-126">Prerequisites</span></span>

<span data-ttu-id="8e2f0-127">La característica de movimiento de buzones entre inquilinos requiere que [Azure Key Vault](/azure/key-vault/basic-concepts) establezca una aplicación de Azure específica del par de inquilinos para almacenar y obtener acceso de forma segura al certificado o secreto usado para autenticar y autorizar la migración de buzones de correo de un inquilino a otro, eliminando los requisitos para compartir certificados o secretos entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-127">The cross-tenant mailbox move feature requires [Azure Key Vault](/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="8e2f0-128">Antes de empezar, asegúrese de que tiene los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar Azure Key Vault, la aplicación Move Mailbox, exo Migration Endpoint y la relación de organización de EXO.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="8e2f0-129">Normalmente, el administrador global tiene permiso para realizar todos los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="8e2f0-130">Además, los grupos de seguridad habilitados para correo en el espacio empresarial de origen son necesarios antes de ejecutar la instalación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="8e2f0-131">Estos grupos se usan para establecer el ámbito de la lista de buzones que pueden moverse del espacio empresarial de origen (o a veces denominado recurso) al espacio empresarial de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="8e2f0-132">Esto permite al administrador de inquilinos de origen restringir o establecer el ámbito del conjunto específico de buzones que se deben mover, lo que impide que los usuarios no intencionados se migren.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="8e2f0-133">No se admiten grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-133">Nested groups are not supported.</span></span>

<span data-ttu-id="8e2f0-134">También tendrá que comunicarse con su empresa asociada de confianza (con la que va a mover buzones) para obtener su identificador de inquilino de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="8e2f0-135">Este identificador de inquilino se usa en el campo Relación de `DomainName` la organización.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="8e2f0-136">Para obtener el identificador de inquilino de una suscripción, inicie sesión en el Centro de administración de Microsoft 365 y vaya a [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="8e2f0-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="8e2f0-137">Haga clic en el icono de copia de la propiedad Id. de inquilino para copiarla en el Portapapeles.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="8e2f0-138">Este es el funcionamiento del proceso.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png" alt-text="Preparación del espacio empresarial para la migración de buzones de correo.":::

<span data-ttu-id="8e2f0-140">[Vea una versión más grande de esta imagen](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-140">[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png).</span></span>

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.png)
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="8e2f0-141">Preparar inquilinos</span><span class="sxs-lookup"><span data-stu-id="8e2f0-141">Prepare tenants</span></span>

<span data-ttu-id="8e2f0-142">En un nivel alto, se llevan a cabo las siguientes acciones de configuración al ejecutar los scripts de instalación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-142">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="8e2f0-143">Preparar el inquilino de destino:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-143">Prepare the target tenant:</span></span>

1. <span data-ttu-id="8e2f0-144">Si no se proporciona un grupo de recursos de Azure existente, se crea uno nuevo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-144">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="8e2f0-145">Si no se proporciona un almacén de claves existente, se crea uno nuevo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-145">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="8e2f0-146">Se crea una nueva directiva de acceso para la aplicación de migración de buzones de Correo (SCRIPT) de Office 365 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-146">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="8e2f0-147">Se crea un nuevo certificado (o uno existente, si se especifica) para mantener el secreto en la aplicación de migración (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-147">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="8e2f0-148">Se crea una nueva aplicación de Azure AD (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-148">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="8e2f0-149">El certificado o secreto se carga en la aplicación de migración (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-149">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="8e2f0-150">Los permisos de migración de buzones de correo se asignan a la aplicación (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-150">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="8e2f0-151">El script de implementación se detiene hasta que el administrador de destino da su consentimiento a su propia aplicación (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-151">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="8e2f0-152">El administrador de inquilinos de destino consiente los permisos concedidos a la aplicación (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-152">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="8e2f0-153">Se crea una relación de organización con el inquilino de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-153">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="8e2f0-154">Se crea un extremo de migración para extraer buzones al inquilino de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-154">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="8e2f0-155">Preparar el espacio empresarial de origen:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-155">Prepare the source tenant:</span></span>

1. <span data-ttu-id="8e2f0-156">El administrador del espacio empresarial de origen acepta el consentimiento para la invitación de la aplicación de migración de buzones desde el inquilino de destino (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-156">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="8e2f0-157">El administrador de inquilinos de origen crea un grupo de seguridad habilitado para correo en su inquilino para contener la lista de buzones permitidos por la aplicación de migración (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-157">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="8e2f0-158">Se crea una relación de organización con el inquilino de destino que especifica la aplicación de migración de buzones de correo que debe usarse para la comprobación de OAuth para aceptar la solicitud de movimiento (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-158">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="8e2f0-159">Instrucciones paso a paso para el administrador de inquilinos de destino</span><span class="sxs-lookup"><span data-stu-id="8e2f0-159">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="8e2f0-160">Descargue el script SetupCrossTenantRelationshipForTargetTenant.ps1 para la configuración del inquilino de destino desde el [repositorio de GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-160">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="8e2f0-161">Guarde el script (SetupCrossTenantRelationshipForTargetTenant.ps1) en el equipo desde el que va a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-161">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="8e2f0-162">Cree una conexión remota de PowerShell al inquilino de destino de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-162">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="8e2f0-163">De nuevo, asegúrese de que tiene los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar el certificado y el almacenamiento de Azure Key Vault, la aplicación Mover buzón de correo, el extremo de migración exo y la relación de la organización de EXO.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-163">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="8e2f0-164">Cambie el directorio de la carpeta de archivos a la ubicación del script o compruebe que el script está guardado actualmente en la ubicación que se encuentra actualmente en la sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-164">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="8e2f0-165">Ejecute el script con los siguientes parámetros y valores.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-165">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="8e2f0-166">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8e2f0-166">Parameter</span></span> | <span data-ttu-id="8e2f0-167">Valor</span><span class="sxs-lookup"><span data-stu-id="8e2f0-167">Value</span></span> | <span data-ttu-id="8e2f0-168">Obligatorio u opcional</span><span class="sxs-lookup"><span data-stu-id="8e2f0-168">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="8e2f0-169">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="8e2f0-169">-TargetTenantDomain</span></span>                         | <span data-ttu-id="8e2f0-170">Dominio de inquilino de destino, como fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-170">Target tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="8e2f0-171">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-171">Required</span></span> |
    | <span data-ttu-id="8e2f0-172">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="8e2f0-172">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="8e2f0-173">Dominio de inquilino de origen, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-173">Source tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="8e2f0-174">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-174">Required</span></span> |
    | <span data-ttu-id="8e2f0-175">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="8e2f0-175">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="8e2f0-176">Dirección de correo electrónico del administrador del espacio empresarial de origen.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-176">Source tenant admin’s email address.</span></span> <span data-ttu-id="8e2f0-177">Este es el administrador de inquilinos de origen que dará su consentimiento al uso de la aplicación de migración de buzones enviada desde el administrador de destino. Este es el administrador que recibirá la invitación de correo electrónico para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-177">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="8e2f0-178">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-178">Required</span></span> |
    | <span data-ttu-id="8e2f0-179">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="8e2f0-179">-ResourceTenantId</span></span>                           | <span data-ttu-id="8e2f0-180">Identificador de organización de inquilino de origen (GUID).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-180">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="8e2f0-181">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-181">Required</span></span> |
    | <span data-ttu-id="8e2f0-182">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="8e2f0-182">-SubscriptionId</span></span>                             | <span data-ttu-id="8e2f0-183">La suscripción de Azure que se usará para crear recursos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-183">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="8e2f0-184">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-184">Required</span></span> |
    | <span data-ttu-id="8e2f0-185">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="8e2f0-185">-ResourceGroup</span></span>                              | <span data-ttu-id="8e2f0-186">Nombre del grupo de recursos de Azure que contiene o contendrá el Almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-186">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="8e2f0-187">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-187">Required</span></span> |
    | <span data-ttu-id="8e2f0-188">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="8e2f0-188">-KeyVaultName</span></span>                               | <span data-ttu-id="8e2f0-189">Instancia de Azure Key Vault que almacenará el certificado o secreto de la aplicación de migración de buzones.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-189">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="8e2f0-190">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-190">Required</span></span> |
    | <span data-ttu-id="8e2f0-191">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="8e2f0-191">-CertificateName</span></span>                            | <span data-ttu-id="8e2f0-192">Nombre del certificado al generar o buscar certificado en el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-192">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="8e2f0-193">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-193">Required</span></span> |
    | <span data-ttu-id="8e2f0-194">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="8e2f0-194">-CertificateSubject</span></span>                         | <span data-ttu-id="8e2f0-195">Nombre de sujeto del certificado de Azure Key Vault, como CN=contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-195">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="8e2f0-196">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-196">Required</span></span> |
    | <span data-ttu-id="8e2f0-197">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="8e2f0-197">-ExistingApplicationId</span></span>                      | <span data-ttu-id="8e2f0-198">Aplicación de migración de correo que se usará si ya se creó una.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-198">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="8e2f0-199">Opcional</span><span class="sxs-lookup"><span data-stu-id="8e2f0-199">Optional</span></span> |
    | <span data-ttu-id="8e2f0-200">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="8e2f0-200">-AzureAppPermissions</span></span>                        | <span data-ttu-id="8e2f0-201">Los permisos necesarios para concederse a la aplicación de migración de buzones, como Exchange o MSGraph (Exchange para mover buzones, MSGraph para usar esta aplicación para enviar una invitación de vínculo de consentimiento al inquilino de recursos).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-201">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="8e2f0-202">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="8e2f0-202">Required</span></span> |
    | <span data-ttu-id="8e2f0-203">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="8e2f0-203">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="8e2f0-204">Parámetro para usar la aplicación creada para la migración que se usará para enviar una invitación de vínculo de consentimiento al administrador del espacio empresarial de origen. Si no está presente, se pedirán las credenciales del administrador de destino para conectarse al Administrador de invitaciones de Azure y enviar la invitación como administrador de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-204">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="8e2f0-205">Opcional</span><span class="sxs-lookup"><span data-stu-id="8e2f0-205">Optional</span></span> |
    | <span data-ttu-id="8e2f0-206">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="8e2f0-206">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="8e2f0-207">Cuenta de almacenamiento donde se almacenarían los registros de auditoría de Key Vault.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-207">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="8e2f0-208">Opcional</span><span class="sxs-lookup"><span data-stu-id="8e2f0-208">Optional</span></span> |
    | <span data-ttu-id="8e2f0-209">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="8e2f0-209">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="8e2f0-210">El grupo de recursos que contiene la cuenta de almacenamiento para almacenar registros de auditoría de Key Vault.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-210">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="8e2f0-211">Opcional</span><span class="sxs-lookup"><span data-stu-id="8e2f0-211">Optional</span></span> |
    ||||

    >[!Note]
    > <span data-ttu-id="8e2f0-212">Asegúrese de haber instalado el módulo de PowerShell de Azure AD antes de ejecutar los scripts.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-212">Please ensure you have installed the Azure AD PowerShell module prior to running the scripts.</span></span> <span data-ttu-id="8e2f0-213">Consulte aquí ![ los pasos de ](/powershell/azure/install-az-ps?view=azps-5.1.0) instalación</span><span class="sxs-lookup"><span data-stu-id="8e2f0-213">Please refer to ![here](/powershell/azure/install-az-ps?view=azps-5.1.0) for installation steps</span></span>

6. <span data-ttu-id="8e2f0-214">El script se pausará y le pedirá que acepte o acepte la aplicación de migración de buzones de Exchange que se creó durante este proceso.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-214">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="8e2f0-215">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-215">Here is an example.</span></span>

    ```powershell
    PS C:\PowerShell\> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

    cmdlet Get-Credential at command pipeline position 1
    Supply values for the following parameters:
    Credential
    Setting up key vault in the fabrikam.onmicrosoft.com tenant

    Name                                     Account                                 SubscriptionName                        Environment                             TenantId
        ----                                     -------                                 ----------------                        -----------                             --------
    Pay-As-You-Go (ewe23423-a3327-34232-343... Admin@fabrikam... Pay-As-You-Go                           AzureCloud                              dsad938432-dd8e-s9034-bf9a-83984293n43
    Auditing setup successfully for Cross-TenantMovesVault
    Exchange application given access to KeyVault Cross-TenantMovesVault
    Application fabrikam_Friends_contoso_2520 created successfully in fabrikam.onmicrosoft.com tenant with following permissions. MSGraph - Directory.ReadWrite.All. Exchange - Mailbox.Migration
    Admin consent URI for fabrikam.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/fabrikam.onmicrosoft.com/adminconsent?client_id=6fea6ere-0dwe-404d-ad35-c71a15cers5c&redirect_uri=https://office.com
    Admin consent URI for contoso.onmicrosoft.com tenant admin is -
    https://login.microsoftonline.com/contoso.onmicrosoft.com/adminconsent?client_id=6fea6ssd-0753-404d-wer5-c71a154d675c&redirect_uri=https://office.com
    Application details to be registered in organization relationship: ApplicationId: [ 6fes8en4-sjo3-406d-ad35-sldkfjiew993 ]. KeyVault secret Id: [ https://cross-tenantmovesvault.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ksdfj843nt8476h84c288c5a3fb8ec5fdb08 ]. These values are available in variables $AppId and $CertificateId respectively
    Please consent to the application for fabrikam.onmicrosoft.com before sending invitation to admin@contoso.onmicrosoft.com:
    ```  

7. <span data-ttu-id="8e2f0-216">Se mostrará una dirección URL en la sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-216">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="8e2f0-217">Copie el vínculo proporcionado para el consentimiento del inquilino y péguelo en un explorador web.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-217">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="8e2f0-218">Inicie sesión con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-218">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="8e2f0-219">Cuando se presente la siguiente pantalla, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-219">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Cuadro de diálogo Aceptar permisos":::

9. <span data-ttu-id="8e2f0-221">Vuelva a la sesión remota de PowerShell y presione Entrar para continuar.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-221">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="8e2f0-222">El script configurará los objetos de instalación restantes.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-222">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="8e2f0-223">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-223">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="8e2f0-224">La configuración de administración de destino ya está completa.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-224">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="8e2f0-225">Instrucciones paso a paso para el administrador del espacio empresarial de origen</span><span class="sxs-lookup"><span data-stu-id="8e2f0-225">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="8e2f0-226">Inicie sesión en el buzón como -ResourceTenantAdminEmail especificado por el administrador de destino durante su instalación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-226">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="8e2f0-227">Busque la invitación de correo electrónico desde el inquilino de destino y, a continuación, seleccione el **botón Introducción.**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-227">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Cuadro de diálogo invitado":::

2. <span data-ttu-id="8e2f0-229">Seleccione **Aceptar** para aceptar la invitación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-229">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Cuadro de diálogo para aceptar permisos":::

   > [!NOTE]
   > <span data-ttu-id="8e2f0-231">Si no recibe este correo electrónico o no lo encuentra, al administrador de inquilinos de destino se le proporcionó una dirección URL directa que se le puede dar para aceptar la invitación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-231">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="8e2f0-232">La dirección URL debe incluirse en la transcripción de la sesión remota de PowerShell del administrador de inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-232">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="8e2f0-233">En el Centro de administración de Microsoft 365 o en una sesión de PowerShell remoto, cree uno o varios grupos de seguridad habilitados para correo para controlar la lista de buzones permitidos por el inquilino de destino para extraer (mover) del inquilino de origen al inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-233">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="8e2f0-234">No es necesario rellenar este grupo por adelantado, pero se debe proporcionar al menos un grupo para ejecutar los pasos de instalación (script).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-234">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="8e2f0-235">No se admiten grupos de anidamiento.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-235">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="8e2f0-236">Descargue el script SetupCrossTenantRelationshipForResourceTenant.ps1 para la configuración del espacio empresarial de origen desde el repositorio de GitHub aquí: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview) .</span><span class="sxs-lookup"><span data-stu-id="8e2f0-236">Download the SetupCrossTenantRelationshipForResourceTenant.ps1 script for the source tenant setup from the GitHub repository here: [https://github.com/microsoft/cross-tenant/releases/tag/Preview](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="8e2f0-237">Cree una conexión remota de PowerShell al espacio empresarial de origen con los permisos de administrador de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-237">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="8e2f0-238">Los permisos de administración global no son necesarios para configurar el inquilino de origen, solo el inquilino de destino debido al proceso de creación de aplicaciones de Azure.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-238">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="8e2f0-239">Cambie el directorio a la ubicación del script o compruebe que el script está guardado actualmente en la ubicación actualmente en la sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-239">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="8e2f0-240">Ejecute el script con los siguientes parámetros y valores necesarios.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-240">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="8e2f0-241">Parámetro</span><span class="sxs-lookup"><span data-stu-id="8e2f0-241">Parameter</span></span> | <span data-ttu-id="8e2f0-242">Valor</span><span class="sxs-lookup"><span data-stu-id="8e2f0-242">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="8e2f0-243">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="8e2f0-243">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="8e2f0-244">Grupo de seguridad habilitado para correo creado por el inquilino de origen para las identidades o buzones que están en el ámbito de la migración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-244">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="8e2f0-245">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="8e2f0-245">-ResourceTenantDomain</span></span> | <span data-ttu-id="8e2f0-246">Nombre de dominio del espacio empresarial de origen, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-246">Source tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="8e2f0-247">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="8e2f0-247">-ApplicationId</span></span> | <span data-ttu-id="8e2f0-248">Identificador de aplicación de Azure (GUID) de la aplicación usada para la migración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-248">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="8e2f0-249">Id. de aplicación disponible a través de Azure Portal (Azure AD, Aplicaciones empresariales, nombre de la aplicación, id. de aplicación) o incluido en el correo electrónico de invitación.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-249">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="8e2f0-250">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="8e2f0-250">-TargetTenantDomain</span></span> | <span data-ttu-id="8e2f0-251">Nombre de dominio de inquilino de destino, como fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-251">Target tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="8e2f0-252">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="8e2f0-252">-TargetTenantId</span></span> | <span data-ttu-id="8e2f0-253">Identificador de inquilino del inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-253">Tenant ID of the target tenant.</span></span> <span data-ttu-id="8e2f0-254">Por ejemplo, el identificador de inquilino de Azure AD de contoso \. onmicrosoft.com inquilino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-254">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||

    <span data-ttu-id="8e2f0-255">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-255">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="8e2f0-256">La configuración de administración de origen ya está completa.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-256">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="8e2f0-257">Comprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="8e2f0-257">Verify setup</span></span>

<span data-ttu-id="8e2f0-258">Compruebe que las relaciones de la organización en los inquilinos de origen y de destino y el extremo de migración en el destino se crearon correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-258">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="8e2f0-259">Inquilino de destino</span><span class="sxs-lookup"><span data-stu-id="8e2f0-259">Target tenant</span></span>

<span data-ttu-id="8e2f0-260">**Relación de organización**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-260">**Organization relationship**</span></span>

<span data-ttu-id="8e2f0-261">Compruebe que el objeto de relación de organización se creó y configuró con este comando.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-261">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="8e2f0-262">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-262">Here is an example:</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="8e2f0-263">**Extremo de migración**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-263">**Migration endpoint**</span></span>

<span data-ttu-id="8e2f0-264">Compruebe que el objeto de extremo de migración se creó y configuró con este comando.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-264">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="8e2f0-265">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-265">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="8e2f0-266">Inquilino de origen</span><span class="sxs-lookup"><span data-stu-id="8e2f0-266">Source tenant</span></span>

<span data-ttu-id="8e2f0-267">**Relación de organización**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-267">**Organization relationship**</span></span>

<span data-ttu-id="8e2f0-268">Compruebe que el objeto de relación de organización se creó y configuró con este comando.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-268">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```

<span data-ttu-id="8e2f0-269">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-269">Here is an example.</span></span>

```powershell
PS C:\PowerShell\> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

#### <a name="verify-setup-script"></a><span data-ttu-id="8e2f0-270">Comprobar script de instalación</span><span class="sxs-lookup"><span data-stu-id="8e2f0-270">Verify Setup Script</span></span>

<span data-ttu-id="8e2f0-271">Si recibe algún error durante la configuración de los inquilinos de origen o de destino, puede ejecutar el script VerifySetup.ps1 ubicado en [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) y revisar el resultado.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-271">If you receive any errors during the configuration of the source or target tenants, you can run the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="8e2f0-272">Este es un ejemplo de ejecución de VerifySetup.ps1 en el inquilino de destino:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-272">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="8e2f0-273">Este es un ejemplo de VerifySetup.ps1 en el inquilino de origen:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-273">Here's an example of VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="8e2f0-274">Volver a mover buzones al origen original</span><span class="sxs-lookup"><span data-stu-id="8e2f0-274">Move mailboxes back to the original source</span></span>

<span data-ttu-id="8e2f0-275">Si es necesario volver a mover un buzón al espacio empresarial de origen original, deberá ejecutarse el mismo conjunto de pasos y scripts tanto en nuevos inquilinos de origen como en nuevos inquilinos de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-275">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="8e2f0-276">El objeto Relación de la organización existente se actualizará o anexará, no se volverá a crear.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-276">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="8e2f0-277">Preparar objetos de usuario de destino para la migración</span><span class="sxs-lookup"><span data-stu-id="8e2f0-277">Prepare target user objects for migration</span></span>

<span data-ttu-id="8e2f0-278">Los usuarios que migran deben estar presentes en el inquilino de destino y en el sistema de Exchange Online (como MailUsers) marcados con atributos específicos para habilitar los movimientos entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-278">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="8e2f0-279">El sistema producirá un error en los movimientos de los usuarios que no estén configurados correctamente en el espacio empresarial de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-279">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="8e2f0-280">En la siguiente sección se detallan los requisitos del objeto MailUser para el inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-280">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="8e2f0-281">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="8e2f0-281">Prerequisites</span></span>
  
<span data-ttu-id="8e2f0-282">Debe asegurarse de que los siguientes objetos y atributos se establecen en la organización de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-282">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="8e2f0-283">Para cualquier buzón que se mueva desde una organización de origen, debe aprovisionar un objeto MailUser en la organización de destino:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-283">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 

   - <span data-ttu-id="8e2f0-284">El mailuser de destino debe tener estos atributos del buzón de origen o asignados con el nuevo objeto User:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-284">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="8e2f0-285">ExchangeGUID (flujo directo de origen a destino): el GUID del buzón debe coincidir.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-285">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="8e2f0-286">El proceso de movimiento no continuará si no está presente en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-286">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="8e2f0-287">ArchiveGUID (flujo directo de origen a destino): el GUID de archivo debe coincidir.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-287">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="8e2f0-288">El proceso de movimiento no continuará si no está presente en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-288">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="8e2f0-289">(Esto solo es necesario si el buzón de origen está habilitado para archivo).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-289">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="8e2f0-290">LegacyExchangeDN (flujo como proxyAddress, "x500: ") : LegacyExchangeDN debe estar presente en mailUser de destino como <LegacyExchangeDN> x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-290">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="8e2f0-291">Los procesos de movimiento no procederán si no está presente en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-291">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="8e2f0-292">UserPrincipalName: UPN se alineará con la nueva identidad o la compañía de destino del usuario (por ejemplo, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-292">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="8e2f0-293">SMTPAddress principal: la dirección SMTP principal se alineará con la compañía NEW del usuario (por ejemplo, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-293">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="8e2f0-294">TargetAddress/ExternalEmailAddress: MailUser hará referencia al buzón actual del usuario hospedado en el inquilino de origen (por ejemplo, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-294">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="8e2f0-295">Al asignar este valor, compruebe que también ha asignado PrimarySMTPAddress o este valor establecerá primarySMTPAddress, lo que provocará errores de movimiento.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-295">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="8e2f0-296">No puede agregar direcciones de proxy smtp heredadas desde el buzón de origen al mailuser de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-296">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="8e2f0-297">Por ejemplo, no puede mantener contoso.com en el MEU en fabrikam.onmicrosoft.com objetos de inquilino).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-297">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="8e2f0-298">Los dominios solo están asociados a un inquilino de Azure AD o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-298">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
     <span data-ttu-id="8e2f0-299">Objeto  MailUser de destino de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-299">Example **target** MailUser object:</span></span>
 
     | <span data-ttu-id="8e2f0-300">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e2f0-300">Attribute</span></span>             | <span data-ttu-id="8e2f0-301">Valor</span><span class="sxs-lookup"><span data-stu-id="8e2f0-301">Value</span></span>                                                                                                                    |
     |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
     | <span data-ttu-id="8e2f0-302">Alias</span><span class="sxs-lookup"><span data-stu-id="8e2f0-302">Alias</span></span>                 | <span data-ttu-id="8e2f0-303">LaraN</span><span class="sxs-lookup"><span data-stu-id="8e2f0-303">LaraN</span></span>                                                                                                                    |
     | <span data-ttu-id="8e2f0-304">RecipientType</span><span class="sxs-lookup"><span data-stu-id="8e2f0-304">RecipientType</span></span>         | <span data-ttu-id="8e2f0-305">MailUser</span><span class="sxs-lookup"><span data-stu-id="8e2f0-305">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="8e2f0-306">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="8e2f0-306">RecipientTypeDetails</span></span>  | <span data-ttu-id="8e2f0-307">MailUser</span><span class="sxs-lookup"><span data-stu-id="8e2f0-307">MailUser</span></span>                                                                                                                 |
     | <span data-ttu-id="8e2f0-308">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="8e2f0-308">UserPrincipalName</span></span>     | <span data-ttu-id="8e2f0-309">LaraN@northwintraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-309">LaraN@northwintraders.onmicrosoft.com</span></span>                                                                                    |
     | <span data-ttu-id="8e2f0-310">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="8e2f0-310">PrimarySmtpAddress</span></span>    | <span data-ttu-id="8e2f0-311">Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-311">Lara.Newton@northwind.com</span></span>                                                                                                |
     | <span data-ttu-id="8e2f0-312">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="8e2f0-312">ExternalEmailAddress</span></span>  | <span data-ttu-id="8e2f0-313">SMTP:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-313">SMTP:LaraN@contoso.onmicrosoft.com</span></span>                                                                                       |
     | <span data-ttu-id="8e2f0-314">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="8e2f0-314">ExchangeGuid</span></span>          | <span data-ttu-id="8e2f0-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="8e2f0-315">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
     | <span data-ttu-id="8e2f0-316">DN de Exchange heredado</span><span class="sxs-lookup"><span data-stu-id="8e2f0-316">LegacyExchangeDN</span></span>      | <span data-ttu-id="8e2f0-317">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="8e2f0-317">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
     |                       | <span data-ttu-id="8e2f0-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="8e2f0-318">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
     | <span data-ttu-id="8e2f0-319">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="8e2f0-319">EmailAddresses</span></span>        | <span data-ttu-id="8e2f0-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="8e2f0-320">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
     |                       | <span data-ttu-id="8e2f0-321">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="8e2f0-321">7273f1f9-Lara</span></span>                                                                                                            |
     |                       | <span data-ttu-id="8e2f0-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-322">smtp:LaraN@northwindtraders.onmicrosoft.com</span></span>                                                                              |
     |                       | <span data-ttu-id="8e2f0-323">SMTP:Lara.Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-323">SMTP:Lara.Newton@northwind.com</span></span>                                                                                           |
     |||

     <span data-ttu-id="8e2f0-324">Objeto **Mailbox de origen** de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-324">Example **source** Mailbox object:</span></span>

     | <span data-ttu-id="8e2f0-325">Atributo</span><span class="sxs-lookup"><span data-stu-id="8e2f0-325">Attribute</span></span>             | <span data-ttu-id="8e2f0-326">Valor</span><span class="sxs-lookup"><span data-stu-id="8e2f0-326">Value</span></span>                                                                    |
     |-----------------------|--------------------------------------------------------------------------|
     | <span data-ttu-id="8e2f0-327">Alias</span><span class="sxs-lookup"><span data-stu-id="8e2f0-327">Alias</span></span>                 | <span data-ttu-id="8e2f0-328">LaraN</span><span class="sxs-lookup"><span data-stu-id="8e2f0-328">LaraN</span></span>                                                                    |
     | <span data-ttu-id="8e2f0-329">RecipientType</span><span class="sxs-lookup"><span data-stu-id="8e2f0-329">RecipientType</span></span>         | <span data-ttu-id="8e2f0-330">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="8e2f0-330">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="8e2f0-331">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="8e2f0-331">RecipientTypeDetails</span></span>  | <span data-ttu-id="8e2f0-332">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="8e2f0-332">UserMailbox</span></span>                                                              |
     | <span data-ttu-id="8e2f0-333">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="8e2f0-333">UserPrincipalName</span></span>     | <span data-ttu-id="8e2f0-334">LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-334">LaraN@contoso.onmicrosoft.com</span></span>                                            |
     | <span data-ttu-id="8e2f0-335">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="8e2f0-335">PrimarySmtpAddress</span></span>    | <span data-ttu-id="8e2f0-336">Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-336">Lara.Newton@contoso.com</span></span>                                                  |
     | <span data-ttu-id="8e2f0-337">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="8e2f0-337">ExchangeGuid</span></span>          | <span data-ttu-id="8e2f0-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="8e2f0-338">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
     | <span data-ttu-id="8e2f0-339">DN de Exchange heredado</span><span class="sxs-lookup"><span data-stu-id="8e2f0-339">LegacyExchangeDN</span></span>      | <span data-ttu-id="8e2f0-340">/o=First Organization/ou=Exchange Administrative Group</span><span class="sxs-lookup"><span data-stu-id="8e2f0-340">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
     |                       | <span data-ttu-id="8e2f0-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="8e2f0-341">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
     | <span data-ttu-id="8e2f0-342">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="8e2f0-342">EmailAddresses</span></span>        | <span data-ttu-id="8e2f0-343">smtp:LaraN@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-343">smtp:LaraN@contoso.onmicrosoft.com</span></span> 
     |                       | <span data-ttu-id="8e2f0-344">SMTP:Lara.Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="8e2f0-344">SMTP:Lara.Newton@contoso.com</span></span>          |
     |||

   - <span data-ttu-id="8e2f0-345">Es posible que ya se incluyan atributos adicionales en la escritura híbrida de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-345">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="8e2f0-346">Si no es así, deben incluirse.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-346">If not, they should be included.</span></span> 
   - <span data-ttu-id="8e2f0-347">msExchBlockedSendersHash: escribe datos de remitentes seguros y bloqueados de clientes en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-347">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="8e2f0-348">msExchSafeRecipientsHash: escribe los datos de remitentes seguros y bloqueados en línea de los clientes en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-348">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="8e2f0-349">msExchSafeSendersHash: escribe los datos de remitentes seguros y bloqueados de los clientes en Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-349">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="8e2f0-350">Si el buzón de origen está en LitigationHold y el tamaño de elementos recuperables del buzón de origen es mayor que el valor predeterminado de nuestra base de datos (30 GB), los movimientos no se realizarán ya que la cuota de destino es menor que el tamaño del buzón de origen.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-350">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="8e2f0-351">Puede actualizar el objeto MailUser de destino para realizar la transición de las marcas de buzón elC del entorno de origen al destino, lo que desencadena que el sistema de destino expanda la cuota de MailUser a 100 GB, lo que permite el movimiento al destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-351">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="8e2f0-352">Estas instrucciones solo funcionarán para identidad híbrida que ejecute Azure AD Connect, ya que los comandos para marcar las marcas de ELC no se exponen a los administradores de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-352">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="8e2f0-353">EJEMPLO: TAL COMO ESTÁ, SIN GARANTÍA</span><span class="sxs-lookup"><span data-stu-id="8e2f0-353">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="8e2f0-354">Este script supone una conexión con el buzón de origen (para obtener los valores de origen) y el Active Directory local de destino (para marcar el objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-354">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="8e2f0-355">Si el origen tiene habilitada la recuperación de un solo elemento o litigio, esta opción se establece en la cuenta de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-355">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="8e2f0-356">Esto aumentará el tamaño de contenedor de la cuenta de destino a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-356">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```

3. <span data-ttu-id="8e2f0-357">Los inquilinos de destino no híbridos pueden modificar la cuota de la carpeta Elementos recuperables de MailUsers antes de la migración ejecutando el siguiente comando para habilitar la retención por juicio en el objeto MailUser y aumentar la cuota a 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="8e2f0-357">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="8e2f0-358">Tenga en cuenta que esto no funcionará para los inquilinos en híbrido.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-358">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="8e2f0-359">Los usuarios de la organización de destino deben tener una licencia con las suscripciones adecuadas de Exchange Online aplicables a la organización.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-359">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="8e2f0-360">Puede aplicar una licencia antes de un movimiento de buzón, pero SOLO una vez que el mailuser de destino esté configurado correctamente con ExchangeGUID y las direcciones proxy.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-360">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="8e2f0-361">La aplicación de una licencia antes de que se aplique ExchangeGUID dará como resultado un nuevo buzón aprovisionado en la organización de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-361">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="8e2f0-362">Al aplicar una licencia en un objeto Mailbox o MailUser, todos los proxyAddresses de tipo SMTP se depuran para garantizar que solo se incluyan dominios comprobados en la matriz EmailAddresses de Exchange.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-362">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="8e2f0-363">Debe asegurarse de que mailuser de destino no tiene ExchangeGuid anterior que no coincida con el ExchangeGuid de origen.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-363">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="8e2f0-364">Esto puede ocurrir si el MEU de destino tenía licencia previa para Exchange Online y aprovisionaba un buzón.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-364">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="8e2f0-365">Si el mailuser de destino tenía una licencia previa para o tenía un ExchangeGuid que no coincide con el ExchangeGuid de origen, debe realizar una limpieza del MEU en la nube.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-365">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="8e2f0-366">Para estas MEUs en la nube, puede ejecutar `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` .</span><span class="sxs-lookup"><span data-stu-id="8e2f0-366">For these cloud MEUs, you can run `Set-User <identity> -PermanentlyClearPreviousMailboxInfo`.</span></span>  

    > [!Caution]
    > <span data-ttu-id="8e2f0-367">Este proceso es irreversible.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-367">This process is irreversible.</span></span> <span data-ttu-id="8e2f0-368">Si el objeto tiene un buzón softDeleted, no se puede restaurar después de este punto.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-368">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="8e2f0-369">Sin embargo, una vez desactivada, puede sincronizar el ExchangeGuid correcto con el objeto de destino y MRS conectará el buzón de origen al buzón de destino recién creado.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-369">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="8e2f0-370">(Consulte el blog EHLO sobre el nuevo parámetro).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-370">(Reference EHLO blog on the new parameter.)</span></span>  

    <span data-ttu-id="8e2f0-371">Busque objetos que anteriormente eran buzones de correo mediante este comando.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-371">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -AutoSize
    ```

    <span data-ttu-id="8e2f0-372">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-372">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize  

    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails  
    ----       ---------------------------- ------------- --------------------  
    John       UserMailbox                  MailUser      MailUser  
    ```  

    <span data-ttu-id="8e2f0-373">Borra el buzón eliminado temporalmente con este comando.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-373">Clear the soft-deleted mailbox using this command.</span></span>

    ```powershell
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```

    <span data-ttu-id="8e2f0-374">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-374">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY.  
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y  
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="8e2f0-375">Realizar migraciones de buzones</span><span class="sxs-lookup"><span data-stu-id="8e2f0-375">Perform mailbox migrations</span></span>

<span data-ttu-id="8e2f0-376">Las migraciones de buzones de Exchange entre inquilinos se envían como lotes de migración iniciados desde el inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-376">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="8e2f0-377">Esto es similar a la forma en que funcionan los lotes de migración al migrar de Exchange local a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-377">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="8e2f0-378">Crear lotes de migración</span><span class="sxs-lookup"><span data-stu-id="8e2f0-378">Create Migration batches</span></span>

<span data-ttu-id="8e2f0-379">Este es un cmdlet por lotes de migración de ejemplo para iniciar movimientos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-379">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="8e2f0-380">La dirección de correo electrónico del archivo CSV debe ser la especificada en el inquilino de destino, no el inquilino de origen.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-380">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="8e2f0-381">El envío por lotes de migración también se admite desde el nuevo Centro de administración de Exchange al seleccionar la opción entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-381">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>

#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="8e2f0-382">Actualizar MailUsers local</span><span class="sxs-lookup"><span data-stu-id="8e2f0-382">Update on-premises MailUsers</span></span>

<span data-ttu-id="8e2f0-383">Una vez que el buzón se mueve de origen a destino, debe asegurarse de que los usuarios de correo locales, tanto de origen como de destino, se actualicen con el nuevo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-383">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="8e2f0-384">En los ejemplos, el targetDeliveryDomain usado en el movimiento es **contoso.onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-384">In the examples, the targetDeliveryDomain used in the move is **contoso.onmicrosoft.com**.</span></span> <span data-ttu-id="8e2f0-385">Actualice los usuarios de correo con este targetAddress.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-385">Update the mail users with this targetAddress.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="8e2f0-386">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="8e2f0-386">Frequently asked questions</span></span>

<span data-ttu-id="8e2f0-387">**¿Es necesario actualizar RemoteMailboxes en el origen local después del movimiento?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-387">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>

<span data-ttu-id="8e2f0-388">Sí, debe actualizar el targetAddress (RemoteRoutingAddress/ExternalEmailAddress) de los usuarios locales de origen cuando el buzón de inquilino de origen se mueve al inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-388">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="8e2f0-389">Mientras que el enrutamiento de correo puede seguir las referencias entre varios usuarios de correo con diferentes targetAddresses, las búsquedas de disponibilidad para los usuarios de correo DEBEN dirigirse a la ubicación del usuario del buzón.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-389">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="8e2f0-390">Las búsquedas de disponibilidad no perseguirán varios redireccionamientos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-390">Free/Busy lookups will not chase multiple redirects.</span></span> 

<span data-ttu-id="8e2f0-391">**¿El contenido de la carpeta de chat de Teams migra entre inquilinos?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-391">**Does the Teams chat folder content migrate cross-tenant?**</span></span>  

<span data-ttu-id="8e2f0-392">No, el contenido de la carpeta de chat de Teams no migra entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-392">No, the Teams chat folder content does not migrate cross-tenant.</span></span>  

<span data-ttu-id="8e2f0-393">**¿Cómo puedo ver solo movimientos que son movimientos entre inquilinos, no mis movimientos de incorporación y de salida?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-393">**How can I see just moves that are cross-tenant moves, not my onboarding and off-boarding moves?**</span></span>

<span data-ttu-id="8e2f0-394">Use el `-flags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-394">Use the `-flags` parameter.</span></span> <span data-ttu-id="8e2f0-395">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-395">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant"  
```

<span data-ttu-id="8e2f0-396">**¿Puede proporcionar scripts de ejemplo para copiar atributos usados en las pruebas?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-396">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="8e2f0-397">EJEMPLO: TAL COMO ESTÁ, SIN GARANTÍA</span><span class="sxs-lookup"><span data-stu-id="8e2f0-397">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="8e2f0-398">Este script supone una conexión tanto con el buzón de origen (para obtener valores de origen) como con los servicios de dominio de Active Directory locales de destino (para marcar el objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-398">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="8e2f0-399">Si el origen tiene habilitada la recuperación de un solo elemento o litigio, esta opción se establece en la cuenta de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-399">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="8e2f0-400">Esto aumentará el tamaño de contenedor de la cuenta de destino a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-400">This will increase the dumpster size of destination account to 100 GB.</span></span>

```powershell
#Dumps out the test mailboxes from SourceTenant 
#Note, the filter applied on GetMailbox is for an attribute set on CA1 = “ProjectKermit” 
#These are the ‘target’ users to be moved to the Northwind org tenant #################################################################  
$outFile = "$home\desktop\UserListToImport.csv" 
$outArray = @() 
#output the test objects 
$Mailboxes = get-mailbox -filter "CustomAttribute1 -like ‘ProjectKermit'" -resultsize unlimited  
#created these mailboxes in adv using separate scripts but you get the idea on how to define the user list to move 
Foreach ($i in $Mailboxes)  
{ 
    $user = get-Recipient $i.alias 
    $myobj = New-Object System.Object 
    $myObj | Add-Member -type NoteProperty -name primarysmtpaddress -value $i.PrimarySMTPAddress 
    $myObj | Add-Member -type NoteProperty -name alias -value $i.alias 
    $myObj | Add-Member -type NoteProperty -name FirstName -value $User.FirstName 
    $myObj | Add-Member -type NoteProperty -name LastName -value $User.LastName 
    $myObj | Add-Member -type NoteProperty -name DisplayName -value $User.DisplayName 
    $myObj | Add-Member -type NoteProperty -name Name -value $i.Name 
    $myObj | Add-Member -type NoteProperty -name SamAccountName -value $i.SamAccountName 
    $myObj | Add-Member -type NoteProperty -name legacyExchangeDN -value $i.legacyExchangeDN    $myObj | Add-Member -type NoteProperty -name ExchangeGuid -value $i.ExchangeGuid 
    $outArray += $myObj 
} 
$outArray | Export-CSV $outfile -notypeinformation  
################################################################# 
#Copy the file $outfile to the desktop of the target on-premises 
#then run the below to create MEU in Target 
#################################################################  
$ImportUserList = import-csv "$home\desktop\UserListToImport.csv" 
$pwstr = "Something 98053 Random!!"; 
$pw = new-object "System.Security.SecureString"; 
for ($i=0; $i -lt $pwstr.Length; $i++) {$pw.AppendChar($pwstr[$i])} foreach ($user in $ImportUserList) { 
     $tmpUser = $null 
    $UPNSuffix = "@northwindtraders.com"    $UPN = $user.Alias+$upnsuffix 
    $tmpUser = New-MailUser -organization -UserPrincipalName $upn -ExternalEmailAddress $user.primarysmtpaddress -FirstName $user.FirstName ` 
                 -LastName $user.LastName -SamAccountName $user.SamAccountName -ResetPasswordOnNextLogon $false ` 
                 -Alias $user.alias -PrimarySmtpAddress $UPN -Name $User.Name -DisplayName $user.DisplayName ` 
                 -OrganizationalUnit "OU=ContosoUsers,OU=MLB,DC=ContosoLab,DC=net" -Password $pw       $x500 = "x500:" + $user.legacyExchangeDN 
    $tmpUser | Set-MailUser -ExchangeGuid $user.ExchangeGuid -EmailAddresses @{Add=$x500} -CustomAttribute1 "ProjectKermit" 
}  
################################################################# 
# On AADSync machine, run AADSync 
#################################################################  
Start-ADSyncSyncCycle 
 
#AADSync and FWDSync will create the target MEUs in the Target tenant 
```
<span data-ttu-id="8e2f0-401">**¿Cómo se accede a Outlook el día 1 después de mover el buzón de uso?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-401">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="8e2f0-402">Dado que solo un inquilino puede ser propietario de un dominio, el smtpaddress principal anterior no se asociará al usuario en el inquilino de destino cuando se complete el movimiento del buzón; solo los dominios asociados con el nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-402">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="8e2f0-403">Outlook usa el nuevo UPN de los usuarios para autenticarse en el servicio y el perfil de Outlook espera encontrar el SMTPAddress principal heredado para que coincida con el buzón en el sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-403">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="8e2f0-404">Dado que la dirección heredada no está en el sistema de destino, el perfil de outlook no se conectará para buscar el buzón recién movido.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-404">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="8e2f0-405">Para esta implementación inicial, los usuarios tendrán que volver a generar su perfil con su nuevo UPN, dirección SMTP principal y volver a sincronizar el contenido OST.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-405">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="8e2f0-406">Planee en consecuencia al procesar por lotes a los usuarios para su finalización.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-406">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="8e2f0-407">Debe tener en cuenta el uso y la capacidad de la red cuando se crean perfiles de cliente de Outlook y los archivos OST y OAB posteriores se descargan en los clientes.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-407">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="8e2f0-408">**¿De qué roles RBAC de Exchange necesito ser miembro para configurar o completar un movimiento entre inquilinos?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-408">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="8e2f0-409">Hay una matriz de roles basada en la suposición de tareas delegadas al ejecutar un movimiento de buzón.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-409">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="8e2f0-410">Actualmente, se requieren dos roles:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-410">Currently, two roles are required:</span></span>  

- <span data-ttu-id="8e2f0-411">El primer rol es para una tarea de configuración única que establece la autorización para mover contenido dentro o fuera del límite del espacio empresarial o de la organización.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-411">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="8e2f0-412">Como mover datos fuera del control de la organización es una preocupación crítica para todas las empresas, optamos por el rol más alto asignado de administrador de la organización (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-412">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="8e2f0-413">Este rol debe modificar o configurar un nuevo OrganizationRelationship que defina -MailboxMoveCapability con la organización remota.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-413">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="8e2f0-414">Solo OrgAdmin puede modificar la configuración MailboxMoveCapability, mientras que el administrador de uso compartido federado puede administrar otros atributos de OrganizationRelationhip.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-414">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="8e2f0-415">El rol de ejecutar los comandos de movimiento reales se puede delegar en una función de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-415">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="8e2f0-416">Al rol de Mover buzones se le asigna la capacidad de mover buzones de correo dentro o fuera de la organización mediante el `-RemoteTenant` parámetro.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-416">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="8e2f0-417">**¿Cómo se selecciona la dirección SMTP seleccionada para targetAddress (TargetDeliveryDomain) en el buzón convertido (en conversión MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-417">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="8e2f0-418">El buzón de Exchange se mueve mediante MRS craft el targetAddress en el buzón de origen original al convertir a un mailuser al hacer coincidir una dirección de correo electrónico (proxyAddress) en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-418">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="8e2f0-419">El proceso toma el valor -TargetDeliveryDomain pasado al comando move y, a continuación, comprueba si hay un proxy que coincida con ese dominio en el lado de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-419">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="8e2f0-420">Cuando se encuentra una coincidencia, se usa el proxyAddress correspondiente para establecer externalEmailAddress (targetAddress) en el objeto de buzón convertido (ahora MailUser).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-420">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="8e2f0-421">**¿Cómo se hacen las transiciones de permisos de buzón de correo?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-421">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="8e2f0-422">Los permisos de buzón incluyen Enviar en nombre de y Acceso de buzones:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-422">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="8e2f0-423">Enviar en nombre de (AD:publicDelegates) almacena el DN de los destinatarios con acceso al buzón de un usuario como delegado.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-423">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="8e2f0-424">Este valor se almacena en Active Directory y actualmente no se mueve como parte de la transición del buzón.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-424">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="8e2f0-425">Si el buzón de origen tiene publicDelegates establecido, tendrá que cambiar el tamaño de los publicDelegates en el buzón de destino una vez completada la conversión de MEU a buzón de correo en el entorno de destino ejecutando `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` .</span><span class="sxs-lookup"><span data-stu-id="8e2f0-425">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment by running `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>`.</span></span> 
 
- <span data-ttu-id="8e2f0-426">Los permisos de buzón que se almacenan en el buzón se moverán con el buzón cuando la entidad de seguridad y el delegado se muevan al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-426">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="8e2f0-427">Por ejemplo, al usuario TestUser_7 se le concede FullAccess al buzón TestUser_8 en el espacio empresarial SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-427">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="8e2f0-428">Una vez completado el movimiento del buzón TargetCompany.onmicrosoft.com, se establecen los mismos permisos en el directorio de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-428">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="8e2f0-429">A continuación se muestran ejemplos que usan *Get-MailboxPermission* TestUser_7 en los inquilinos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-429">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="8e2f0-430">Los cmdlets de Exchange tienen el prefijo source y target en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-430">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="8e2f0-431">Este es un ejemplo de la salida del permiso de buzón antes de un movimiento.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-431">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\PowerShell\> Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="8e2f0-432">Este es un ejemplo de la salida del permiso de buzón después del movimiento.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-432">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
PS C:\PowerShell\> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="8e2f0-433">No se admiten los permisos de buzón de correo y calendario entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-433">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="8e2f0-434">Debe organizar entidades de seguridad y delegados en lotes de movimiento consolidados para que estos buzones conectados se transiciónn al mismo tiempo desde el espacio empresarial de origen.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-434">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 

<span data-ttu-id="8e2f0-435">**¿Qué proxy X500 se debe agregar a las direcciones proxy mailuser de destino para habilitar la migración?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-435">**What X500 proxy should be added to the target MailUser proxy addresses to enable migration?**</span></span>  

<span data-ttu-id="8e2f0-436">La migración de buzones entre inquilinos requiere que el valor LegacyExchangeDN del objeto de buzón de origen se estampe como una dirección de correo electrónico x500 en el objeto MailUser de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-436">The cross-tenant mailbox migration requires that the LegacyExchangeDN value of the source mailbox object to be stamped as an x500 email address on the target MailUser object.</span></span>  

<span data-ttu-id="8e2f0-437">Ejemplo:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-437">Example:</span></span>  
```powershell
LegacyExchangeDN value on source mailbox is:  
/o=First Organization/ou=Exchange Administrative Group(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara  

so the x500 email address to be added to target MailUser object would be:  
x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9-Lara  
```

> [!Note]  
> <span data-ttu-id="8e2f0-438">Además de este proxy X500, deberá copiar todos los servidores proxy X500 del buzón del buzón de correo en el buzón de correo del destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-438">In addition to this X500 proxy, you will need to copy all X500 proxies from the mailbox in the source to the mailbox in the target.</span></span>  

<span data-ttu-id="8e2f0-439">**¿Dónde puedo empezar a solucionar problemas si los movimientos no funcionan?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-439">**Where do I start troubleshooting if moves do not work?**</span></span>  

<span data-ttu-id="8e2f0-440">Empiece por ejecutar el script VerifySetup.ps1 en [GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) y revise el resultado.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-440">Start by running the VerifySetup.ps1 script located [on GitHub](https://github.com/microsoft/cross-tenant/releases/tag/Preview) and review the output.</span></span>

<span data-ttu-id="8e2f0-441">Este es un ejemplo de ejecución de VerifySetup.ps1 en el inquilino de destino:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-441">Here's an example of running VerifySetup.ps1 on the target tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <SourceTenantId> -ApplicationId <AADApplicationId> -ApplicationKeyVaultUrl <appKeyVaultUrl> -PartnerTenantDomain <PartnerTenantDomain> -Verbose
```

<span data-ttu-id="8e2f0-442">Este es un eExample de ejecución de VerifySetup.ps1 en el inquilino de origen:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-442">Here's an eExample of running VerifySetup.ps1 on the source tenant:</span></span>

```powershell
VerifySetup.ps1 -PartnerTenantId <TargetTenantId> -ApplicationId <AADApplicationId>
```

<span data-ttu-id="8e2f0-443">**¿El inquilino de origen y de destino puede usar el mismo nombre de dominio?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-443">**Can the source and target tenant utilize the same domain name?**</span></span>  

<span data-ttu-id="8e2f0-444">No.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-444">No.</span></span> <span data-ttu-id="8e2f0-445">Los nombres de dominio de inquilino de origen y de destino deben ser únicos.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-445">The source and target tenant domain names must be unique.</span></span> <span data-ttu-id="8e2f0-446">Por ejemplo, un dominio de origen de contoso.com el dominio de destino de fourthcoffee.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-446">For example, a source domain of contoso.com and the target domain of fourthcoffee.com.</span></span>

<span data-ttu-id="8e2f0-447">**¿Los buzones compartidos se moverán y seguirán funcionando?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-447">**Will shared mailboxes move and still work?**</span></span>

<span data-ttu-id="8e2f0-448">Sí, pero solo guardamos los permisos de almacén como se describe en estos artículos:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-448">Yes, however we only keep the store permissions as described in these articles:</span></span>

- [<span data-ttu-id="8e2f0-449">Microsoft Docs | Administrar permisos para destinatarios en Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e2f0-449">Microsoft Docs | Manage permissions for recipients in Exchange Online</span></span>](/exchange/recipients-in-exchange-online/manage-permissions-for-recipients)

- [<span data-ttu-id="8e2f0-450">Soporte técnico de Microsoft | Cómo conceder permisos de buzón de Exchange y Outlook en Office 365 dedicado</span><span class="sxs-lookup"><span data-stu-id="8e2f0-450">Microsoft Support | How to grant Exchange and Outlook mailbox permissions in Office 365 dedicated</span></span>](https://support.microsoft.com/topic/how-to-grant-exchange-and-outlook-mailbox-permissions-in-office-365-dedicated-bac01b2c-08ff-2eac-e1c8-6dd01cf77287)

<span data-ttu-id="8e2f0-451">**¿Es necesario Azure Key Vault y cuándo se realizan las transacciones?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-451">**Is Azure Key Vault required and when are transactions made?**</span></span>  

<span data-ttu-id="8e2f0-452">Sí, se requiere una suscripción de Azure para usar Key Vault para almacenar el certificado para autorizar la migración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-452">Yes, an Azure subscription is required to use Key Vault to store the certificate to authorize migration.</span></span> <span data-ttu-id="8e2f0-453">A diferencia de las migraciones de incorporación que usan nombre de usuario & contraseña para autenticarse en el origen, las migraciones de buzones entre inquilinos usan OAuth y este certificado como secreto/credencial.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-453">Unlike onboarding migrations which use username & password to authenticate to the source, cross-tenant mailbox migrations use OAuth and this certificate as the secret/credential.</span></span> <span data-ttu-id="8e2f0-454">El acceso al almacén de claves debe mantenerse en todas las migraciones de buzones, ya que se tiene acceso a él una vez al principio y al final de la migración, así como una vez cada 24 horas durante los tiempos de sincronización incremental.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-454">Access to the Key Vault must be maintained throughout all mailbox migrations as it is accessed once at the beginning and once end of migration, as well as once every 24 hours during incremental sync times.</span></span> <span data-ttu-id="8e2f0-455">Puede revisar los detalles del costo de AKV [aquí]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-455">You can review AKV costing details [here]( https://azure.microsoft.com/en-us/pricing/details/key-vault/).</span></span>  

<span data-ttu-id="8e2f0-456">**¿Tiene alguna recomendación para lotes?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-456">**Do you have any recommendations for batches?**</span></span>  

<span data-ttu-id="8e2f0-457">No supere los 2000 buzones por lote.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-457">Do not exceed 2000 mailboxes per batch.</span></span> <span data-ttu-id="8e2f0-458">Recomendamos encarecidamente enviar lotes dos semanas antes de la fecha de corte, ya que no hay ningún impacto para los usuarios finales durante la sincronización. Si necesita instrucciones sobre las cantidades de buzones de correo que supere los 50 000, puede comunicarse con la Lista de distribución de comentarios de ingeniería en crosstenantmigrationpreview@service.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-458">We strongly recommend submitting batches two weeks prior to the cut-over date as there is no impact to the end users during sync. If you need guidance for mailboxes quantities over 50,000 you can reach out to the Engineering Feedback Distribution List at crosstenantmigrationpreview@service.microsoft.com.</span></span>

<span data-ttu-id="8e2f0-459">**¿Qué ocurre si uso el cifrado de servicio con clave de cliente?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-459">**What if I use Service encryption with Customer Key?**</span></span>

<span data-ttu-id="8e2f0-460">El buzón se descifrará antes de moverlo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-460">The mailbox will be decrypted prior to moving.</span></span> <span data-ttu-id="8e2f0-461">Asegúrese de que la clave de cliente está configurada en el espacio empresarial de destino si aún es necesaria.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-461">Ensure Customer Key is configured in the target tenant if it is still required.</span></span> <span data-ttu-id="8e2f0-462">Vea [aquí](../compliance/customer-key-overview.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-462">See [here](../compliance/customer-key-overview.md) for more information.</span></span>  

<span data-ttu-id="8e2f0-463">**¿Cuál es el tiempo estimado de migración?**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-463">**What is the estimated migration time?**</span></span>

<span data-ttu-id="8e2f0-464">Para ayudarle a planear la [](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) migración, la tabla que se muestra aquí muestra las directrices sobre cuándo esperar que se completen las migraciones masivas de buzones de correo o las migraciones individuales.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-464">To help you plan your migration, the table present [here](/exchange/mailbox-migration/office-365-migration-best-practices#estimated-migration-times) shows the guidelines about when to expect bulk mailbox migrations or individual migrations to complete.</span></span> <span data-ttu-id="8e2f0-465">Estas estimaciones se basan en un análisis de datos de migraciones de clientes anteriores.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-465">These estimates are based on a data analysis of previous customer migrations.</span></span> <span data-ttu-id="8e2f0-466">Dado que cada entorno es único, la velocidad exacta de migración puede variar.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-466">Because every environment is unique, your exact migration velocity may vary.</span></span>  

<span data-ttu-id="8e2f0-467">Recuerde que esta característica está actualmente en versión preliminar y el SLA y los niveles de servicio aplicables no se aplican a ningún problema de rendimiento o disponibilidad durante el estado de vista previa de esta característica.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-467">Do remember that this feature is currently in preview and the SLA and any applicable Service Levels do not apply to any performance or availability issues during the preview status of this feature.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8e2f0-468">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8e2f0-468">Known issues</span></span>  

-  <span data-ttu-id="8e2f0-469">**Problema: no se pueden migrar los archivos expandido automáticamente.**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-469">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="8e2f0-470">La característica de migración entre inquilinos admite las migraciones del buzón principal y del buzón de archivo para un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-470">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="8e2f0-471">Sin embargo, si el usuario del origen tiene un archivo expandido automáticamente, lo que significa más de un buzón de archivo, la característica no puede migrar los archivos adicionales y debería producir un error.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-471">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives and should fail.</span></span>

- <span data-ttu-id="8e2f0-472">**Problema: Los usuarios de correo en la nube con proxy smtp no propietarioSombre de dirección de dirección se mueve en segundo plano.**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-472">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="8e2f0-473">Al crear objetos MailUser de inquilino de destino, debe asegurarse de que todas las direcciones proxy SMTP pertenecen a la organización de inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-473">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="8e2f0-474">Si existe un proxy SMTPAddress en el usuario de correo de destino que no pertenece al inquilino local, se impide la conversión de MailUser a Mailbox.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-474">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="8e2f0-475">Esto se debe a nuestra seguridad de que los objetos de buzón solo pueden enviar correo desde dominios para los que el inquilino es autoritativo (dominios reclamados por el inquilino):</span><span class="sxs-lookup"><span data-stu-id="8e2f0-475">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 

   - <span data-ttu-id="8e2f0-476">Cuando sincroniza usuarios locales con Azure AD Connect, aprovisiona objetos MailUser locales con ExternalEmailAddress que apuntan al espacio empresarial de origen donde existe el buzón (laran@contoso.onmicrosoft.com) y se marca PrimarySMTPAddress como un dominio que reside en el inquilino de destino (Lara.Newton@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-476">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind.com).</span></span> <span data-ttu-id="8e2f0-477">Estos valores se sincronizan con el inquilino y se aprovisiona un usuario de correo adecuado y listo para la migración.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-477">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="8e2f0-478">Aquí se muestra un objeto de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-478">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="8e2f0-479">La *contoso.onmicrosoft.com* no *está presente* en la matriz EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-479">The *contoso.onmicrosoft.com* address is *not* present in the EmailAddresses / proxyAddresses array.</span></span>

- <span data-ttu-id="8e2f0-480">**Problema: Los objetos MailUser con direcciones SMTP principales "externas" se modifican o restablecen a dominios "internos" reclamados por la compañía**</span><span class="sxs-lookup"><span data-stu-id="8e2f0-480">**Issue: MailUser objects with “external” primary SMTP addresses are modified / reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="8e2f0-481">Los objetos MailUser son punteros a buzones no locales.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-481">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="8e2f0-482">En el caso de las migraciones de buzones entre inquilinos, se usan objetos MailUser para representar el buzón de origen (desde la perspectiva de la organización de destino) o el buzón de destino (desde la perspectiva de la organización de origen).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-482">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="8e2f0-483">Los MailUsers tendrán una dirección ExternalEmailAddress (targetAddress) que apunta a la dirección smtp del buzón real (ProxyTest@fabrikam.onmicrosoft.com) y la dirección primarySMTP que representa la dirección SMTP mostrada del usuario del buzón en el directorio.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-483">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest@fabrikam.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="8e2f0-484">Algunas organizaciones deciden mostrar la dirección SMTP principal como una dirección SMTP externa, no como una dirección propiedad o comprobada por el inquilino local (como fabrikam.com en lugar de como contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-484">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="8e2f0-485">Sin embargo, una vez que se aplica un objeto de plan de servicio de Exchange al MailUser mediante operaciones de licencia, la dirección SMTP principal se modifica para mostrarse como un dominio comprobado por la organización local (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="8e2f0-485">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="8e2f0-486">Existen dos posibles motivos:</span><span class="sxs-lookup"><span data-stu-id="8e2f0-486">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="8e2f0-487">Cuando se aplica cualquier plan de servicio de Exchange a un MailUser, el proceso de Azure AD comienza a aplicar el uso de la depuración de proxy para garantizar que la organización local no pueda enviar correo, suplantación de suplantación o correo de otro inquilino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-487">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="8e2f0-488">Cualquier dirección SMTP de un objeto de destinatario con estos planes de servicio se quitará si la organización local no comprueba la dirección.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-488">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="8e2f0-489">Como en el ejemplo, el inquilino de Fabikam.com no comprueba el dominio contoso.onmicrosoft.com, por lo que la depuración quita fabrikam.com dominio.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-489">As is the case in the example, the Fabikam.com domain is NOT verified by the contoso.onmicrosoft.com tenant, so the scrubbing removes that fabrikam.com domain.</span></span> <span data-ttu-id="8e2f0-490">Si desea conservar estos dominios externos en MailUser, ya sea antes de la migración o después de la migración, debe modificar los procesos de migración para quitar licencias una vez completado el movimiento o antes del movimiento para asegurarse de que los usuarios tienen aplicada la personalización de marca externa esperada.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-490">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="8e2f0-491">Deberá asegurarse de que el objeto de buzón tenga una licencia adecuada para no afectar al servicio de correo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-491">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="8e2f0-492">Aquí se muestra un script de ejemplo para quitar los planes de servicio de un mailuser en el Contoso.onmicrosoft.com inquilino.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-492">An example script to remove the service plans on a MailUser in the Contoso.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="8e2f0-493">Los resultados en el conjunto de ServicePlans asignados se muestran aquí.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-493">Results in the set of ServicePlans assigned are shown here.</span></span>

    ```powershell
    (Get-MsolUser -UserPrincipalName proxytest@contoso.com).licenses |select 
    -ExpandProperty servicestatus |sort ProvisioningStatus -Descending   
    ServicePlan           ProvisioningStatus 
    -----------           ------------------ 
    ATP_ENTERPRISE        PendingProvisioning 
    MICROSOFT_SEARCH      PendingProvisioning 
    INTUNE_O365           PendingActivation 
    PAM_ENTERPRISE        Disabled 
    EXCHANGE_ANALYTICS    Disabled 
    EQUIVIO_ANALYTICS     Disabled 
    THREAT_INTELLIGENCE   Disabled 
    LOCKBOX_ENTERPRISE    Disabled 
    PREMIUM_ENCRYPTION    Disabled 
    EXCHANGE_S_ENTERPRISE Disabled 
    INFORMATION_BARRIERS  Disabled 
    MYANALYTICS_P2        Disabled 
    MIP_S_CLP1            Disabled 
    MIP_S_CLP2            Disabled 
    ADALLOM_S_O365        PendingInput 
    RMS_S_ENTERPRISE      Success 
    YAMMER_ENTERPRISE     Success 
    PROJECTWORKMANAGEMENT Success 
    BI_AZURE_P2           Success 
    WHITEBOARD_PLAN3      Success 
    SHAREPOINTENTERPRISE  Success 
    SHAREPOINTWAC         Success 
    KAIZALA_STANDALONE    Success 
    OFFICESUBSCRIPTION    Success 
    MCOSTANDARD           Success 
    Deskless              Success 
    STREAM_O365_E5        Success 
    FLOW_O365_P3          Success 
    POWERAPPS_O365_P3     Success 
    TEAMS1                Success 
    MCOEV                 Success 
    MCOMEETADV            Success 
    BPOS_S_TODO_3         Success 
    FORMS_PLAN_E5         Success 
    SWAY                  Success 

    ```
 
       <span data-ttu-id="8e2f0-494">El primarySMTPAddress del usuario ya no se limpia.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-494">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="8e2f0-495">El fabrikam.com no es propiedad del inquilino contoso.onmicrosoft.com y persistirá como la dirección SMTP principal que se muestra en el directorio.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-495">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="8e2f0-496">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-496">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="8e2f0-497">Cuando msExchRemoteRecipientType se establece en 8 (DeprovisionMailbox), para los MailUser locales que se migran al inquilino de destino, la lógica de depuración de proxy en Azure quitará los dominios no conocidos y restablecerá el primarySMTP a un dominio de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-497">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="8e2f0-498">Al borrar msExchRemoteRecipientType en el mailuser local, la lógica de depuración de proxy ya no se aplica.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-498">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="8e2f0-499">A continuación se muestra el conjunto completo de posibles planes de servicio que incluyen Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e2f0-499">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="8e2f0-500">Nombre</span><span class="sxs-lookup"><span data-stu-id="8e2f0-500">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="8e2f0-501">Almacenamiento de exhibición de documentos electrónicos avanzado (500 GB)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-501">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="8e2f0-502">Caja de seguridad del cliente</span><span class="sxs-lookup"><span data-stu-id="8e2f0-502">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="8e2f0-503">Prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="8e2f0-503">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="8e2f0-504">Servicios CAL de Exchange Enterprise (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-504">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="8e2f0-505">Exchange Essentials</span><span class="sxs-lookup"><span data-stu-id="8e2f0-505">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="8e2f0-506">Exchange Foundation</span><span class="sxs-lookup"><span data-stu-id="8e2f0-506">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="8e2f0-507">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-507">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="8e2f0-508">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-508">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="8e2f0-509">Exchange Online (plan 2)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-509">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="8e2f0-510">Archivado de Exchange Online para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e2f0-510">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="8e2f0-511">Archivado de Exchange Online para Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8e2f0-511">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="8e2f0-512">Complemento de usuario inactivo de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e2f0-512">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="8e2f0-513">Quiosco de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e2f0-513">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="8e2f0-514">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="8e2f0-514">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="8e2f0-515">Plan 1 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e2f0-515">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="8e2f0-516">POP de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="8e2f0-516">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="8e2f0-517">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="8e2f0-517">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="8e2f0-518">Barreras de información</span><span class="sxs-lookup"><span data-stu-id="8e2f0-518">Information Barriers</span></span>                              |
   | <span data-ttu-id="8e2f0-519">Information Protection para Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="8e2f0-519">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="8e2f0-520">Information Protection para Office 365 - Estándar</span><span class="sxs-lookup"><span data-stu-id="8e2f0-520">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="8e2f0-521">Insights de MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="8e2f0-521">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="8e2f0-522">Auditoría avanzada de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e2f0-522">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="8e2f0-523">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="8e2f0-523">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="8e2f0-524">Centro de negocios de Microsoft</span><span class="sxs-lookup"><span data-stu-id="8e2f0-524">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="8e2f0-525">Microsoft MyAnalytics (Completo)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-525">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="8e2f0-526">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="8e2f0-526">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="8e2f0-527">Microsoft Defender para Office 365 (Plan 1)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-527">Microsoft Defender for Office 365 (Plan 1)</span></span>    |
   | <span data-ttu-id="8e2f0-528">Microsoft Defender para Office 365 (Plan 2)</span><span class="sxs-lookup"><span data-stu-id="8e2f0-528">Microsoft Defender for Office 365 (Plan 2)</span></span>    |
   | <span data-ttu-id="8e2f0-529">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="8e2f0-529">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="8e2f0-530">Cifrado premium en Office 365</span><span class="sxs-lookup"><span data-stu-id="8e2f0-530">Premium Encryption in Office 365</span></span>                  |
