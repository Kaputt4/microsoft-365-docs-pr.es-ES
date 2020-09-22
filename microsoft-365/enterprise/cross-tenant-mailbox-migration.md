---
title: Migración de buzones de correo entre inquilinos
description: Cómo mover buzones entre los inquilinos de Microsoft 365 o de Office 365.
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
ms.openlocfilehash: f649a72dc5569e8aec46347df295aa3ff9d93613
ms.sourcegitcommit: 327163f70eac0de568ebe3c9a97a744c3ed408cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48177194"
---
# <a name="cross-tenant-mailbox-migration-preview"></a><span data-ttu-id="96a38-103">Migración de buzones de correo entre espacios empresariales (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="96a38-103">Cross-tenant mailbox migration (preview)</span></span>

<span data-ttu-id="96a38-104">Anteriormente, cuando un inquilino de Exchange Online necesitaba mover buzones de correo a otro inquilino en el mismo servicio de Exchange Online, tendría que desincorporarlas por completo y luego incorporarlas a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="96a38-104">Previously, when an Exchange Online tenant needed to move mailboxes to another tenant in the same Exchange Online service, they would have to completely offboard them to on-premises and then onboard them to a new tenant.</span></span> <span data-ttu-id="96a38-105">Con la nueva característica de migración de buzones de correo entre inquilinos, los administradores de espacios empresariales de los inquilinos de origen y de destino pueden mover buzones de correo entre los inquilinos con las dependencias de infraestructura mínimas en sus sistemas locales.</span><span class="sxs-lookup"><span data-stu-id="96a38-105">With the new cross-tenant mailbox migration feature, tenant administrators in both source and target tenants can move mailboxes between the tenants with minimal infrastructure dependencies in their on-premises systems.</span></span> <span data-ttu-id="96a38-106">Esto elimina la necesidad de desincorpora e incorporar buzones de correo.</span><span class="sxs-lookup"><span data-stu-id="96a38-106">This removes the need to offboard and onboard mailboxes.</span></span>

<span data-ttu-id="96a38-107">Por lo general, durante fusiones o desinversiones, es necesario poder mover usuarios y contenido a un nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="96a38-107">Commonly, during mergers or divestitures, you need the ability to move users and content into a new tenant.</span></span> <span data-ttu-id="96a38-108">Cuando el administrador del espacio empresarial de destino ejecuta el movimiento, se denomina movimiento de extracción, similar a las migraciones locales a la incorporación de la nube.</span><span class="sxs-lookup"><span data-stu-id="96a38-108">When the target tenant administrator executes the move, it’s called a Pull move, similar to on-premises to cloud onboarding migrations.</span></span>

<span data-ttu-id="96a38-109">Los administradores de espacios empresariales administran completamente los movimientos de buzones de Exchange entre inquilinos, usando interfaces bien conocidas que se pueden incluir en scripts en los flujos de trabajo más grandes necesarios para realizar la transición de los usuarios a la nueva organización.</span><span class="sxs-lookup"><span data-stu-id="96a38-109">Cross-tenant Exchange mailbox moves are fully self-serviced by tenant administrators, using well known interfaces that can be scripted into the larger workflows needed to transition users to their new organization.</span></span> <span data-ttu-id="96a38-110">Los administradores pueden usar el `New-MigrationBatch` cmdlet, que está disponible a través del rol de administración mover buzones, para ejecutar movimientos entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-110">Administrators can use the `New-MigrationBatch` cmdlet, available through the Move Mailboxes management role, to execute cross-tenant moves.</span></span> <span data-ttu-id="96a38-111">El proceso de traslado incluye las comprobaciones de autorización del inquilino durante la sincronización y finalización del buzón.</span><span class="sxs-lookup"><span data-stu-id="96a38-111">The move process includes tenant authorization checks during mailbox synchronization and finalization.</span></span> 
 
<span data-ttu-id="96a38-112">Los usuarios que migren deben estar presentes en el sistema Exchange online del inquilino de destino como MailUsers, marcados con atributos específicos para habilitar los movimientos entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-112">Users migrating must be present in the target tenant Exchange Online system as MailUsers, marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="96a38-113">Se producirá un error en el sistema para los usuarios que no se hayan configurado correctamente en el espacio empresarial de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-113">The system will fail moves for users that are not properly set up in the target tenant.</span></span> 

<span data-ttu-id="96a38-114">Cuando se completan los movimientos, el buzón del sistema de origen se convierte en MailUser y el targetAddress (que se muestra como ExternalEmailAddress en Exchange) se marca con la dirección de enrutamiento para el inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-114">When the moves are complete, the source system mailbox is converted to MailUser and the targetAddress (shown as ExternalEmailAddress in Exchange) is stamped with the routing address to the destination tenant.</span></span> <span data-ttu-id="96a38-115">Este proceso abandona el MailUser heredado en el espacio empresarial de origen y permite un período de coexistencia y enrutamiento de correo.</span><span class="sxs-lookup"><span data-stu-id="96a38-115">This process leaves the legacy MailUser in the source tenant, and allows for a period of co-existence and mail routing.</span></span> <span data-ttu-id="96a38-116">Cuando los procesos de negocio lo permiten, el inquilino de origen puede quitar el MailUser de origen o convertirlos en un contacto de correo.</span><span class="sxs-lookup"><span data-stu-id="96a38-116">When business processes allow, the source tenant may remove the source MailUser or convert them to a mail contact.</span></span> 

<span data-ttu-id="96a38-117">Las migraciones de buzones de correo de Exchange entre inquilinos son compatibles para los inquilinos de solo híbrida o de nube, o cualquier combinación de los dos.</span><span class="sxs-lookup"><span data-stu-id="96a38-117">Cross-tenant Exchange mailbox migrations are supported for tenants in hybrid or cloud only, or any combination of the two.</span></span>

<span data-ttu-id="96a38-118">En este artículo se describe el proceso para los movimientos entre inquilinos de buzones y se proporcionan instrucciones sobre cómo preparar los inquilinos de origen y de destino para el movimiento de contenido.</span><span class="sxs-lookup"><span data-stu-id="96a38-118">This article describes the process for cross-tenant mailbox moves and provides guidance on how to prepare source and target tenants for the content move.</span></span> 

## <a name="preparing-source-and-target-tenants"></a><span data-ttu-id="96a38-119">Preparar los inquilinos de origen y de destino</span><span class="sxs-lookup"><span data-stu-id="96a38-119">Preparing source and target tenants</span></span>

<span data-ttu-id="96a38-120">La característica de migración de buzones de correo de Exchange entre inquilinos requiere autorización y ámbito para las migraciones entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-120">The Cross-tenant Exchange mailbox migration feature requires authorization and scoping for cross-tenant migrations.</span></span> <span data-ttu-id="96a38-121">Mediante el uso de las soluciones de almacenamiento de la aplicación empresarial de Azure y de Key Vault, los administradores de espacios empresariales ahora están autorizados para administrar la autorización y el alcance de las migraciones de buzones de Exchange online de un inquilino a otro.</span><span class="sxs-lookup"><span data-stu-id="96a38-121">Using the Azure Enterprise application and Key Vault storage solutions, tenant admins are now empowered to manage both authorization and scoping of Exchange Online mailbox migrations from one tenant to another.</span></span> <span data-ttu-id="96a38-122">Los movimientos entre inquilinos de buzones admiten un modelo de invitación y consentimiento para establecer una aplicación de Azure Active Directory (Azure AD) que se usa para la autenticación entre un par de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-122">Cross-tenant mailbox moves supports an invitation and consent model to establish an Azure Active Directory (Azure AD) application used for authentication between a tenant pair.</span></span> <span data-ttu-id="96a38-123">También se requieren componentes adicionales, como una relación de organización y un extremo de migración.</span><span class="sxs-lookup"><span data-stu-id="96a38-123">Additional components such as an organization relationship and a migration endpoint are also required.</span></span>

<span data-ttu-id="96a38-124">Esta sección no incluye los pasos específicos necesarios para preparar los objetos de usuario de MailUser en el directorio de destino, ni incluye el comando de ejemplo para enviar un lote de migración.</span><span class="sxs-lookup"><span data-stu-id="96a38-124">This section does not include the specific steps required to prepare the MailUser user objects in the target directory, nor does it include the sample command to submit a migration batch.</span></span> <span data-ttu-id="96a38-125">Para obtener más información, vea [preparar objetos de usuario de destino para la migración](#prepare-target-user-objects-for-migration) .</span><span class="sxs-lookup"><span data-stu-id="96a38-125">Please see [Prepare target user objects for migration](#prepare-target-user-objects-for-migration) for this information.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96a38-126">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="96a38-126">Prerequisites</span></span>

<span data-ttu-id="96a38-127">La característica de movimiento de buzones entre inquilinos requiere que [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) establezca una aplicación de Azure específica para el par de inquilinos para almacenar de forma segura y tener acceso al certificado o secreto usado para autenticar y autorizar la migración de buzones de un inquilino a otro, quitando los requisitos para compartir certificados y secretos entre los inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-127">The cross-tenant mailbox move feature requires [Azure Key Vault](https://docs.microsoft.com/azure/key-vault/basic-concepts) to establish a tenant pair-specific Azure application to securely store and access the certificate/secret used to authenticate and authorize mailbox migration from one tenant to the other, removing any requirements to share certificates/secrets between tenants.</span></span> 

<span data-ttu-id="96a38-128">Antes de empezar, asegúrese de que dispone de los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar Azure Key Vault, Move Mailbox Application, el extremo de migración de EXO y la relación de organización EXO.</span><span class="sxs-lookup"><span data-stu-id="96a38-128">Before starting, be sure you have the necessary permissions to run the deployment scripts in order to configure Azure Key Vault, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span> <span data-ttu-id="96a38-129">Normalmente, el administrador global tiene permiso para realizar todos los pasos de configuración.</span><span class="sxs-lookup"><span data-stu-id="96a38-129">Typically, Global Admin has permission to perform all configuration steps.</span></span>

<span data-ttu-id="96a38-130">Además, los grupos de seguridad habilitados para correo electrónico en el espacio empresarial de origen son necesarios antes de ejecutar el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="96a38-130">Additionally, mail-enabled security groups in the source tenant are required prior to running setup.</span></span> <span data-ttu-id="96a38-131">Estos grupos se usan para definir el ámbito de la lista de buzones de correo que pueden moverse del inquilino de origen (o, en ocasiones, denominado recurso) al inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-131">These groups are used to scope the list of mailboxes that can move from source (or sometimes referred to as resource) tenant to the target tenant.</span></span> <span data-ttu-id="96a38-132">Esto permite que el administrador del espacio empresarial de origen restrinja o alcance el conjunto específico de buzones que se deben mover, evitando que se migren los usuarios no deseados.</span><span class="sxs-lookup"><span data-stu-id="96a38-132">This allows the source tenant admin to restrict or scope the specific set of mailboxes that need to be moved, preventing unintended users from being migrated.</span></span> <span data-ttu-id="96a38-133">No se admiten los grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="96a38-133">Nested groups are not supported.</span></span>

<span data-ttu-id="96a38-134">También tendrá que comunicarse con la empresa de asociados de confianza (con la que va a mover buzones) para obtener su identificador de inquilino de 365 de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="96a38-134">You will also need to communicate with your trusted partner company (with whom you will be moving mailboxes) to obtain their Microsoft 365 tenant ID.</span></span> <span data-ttu-id="96a38-135">Este identificador de inquilino se usa en el campo relación de la organización `DomainName` .</span><span class="sxs-lookup"><span data-stu-id="96a38-135">This tenant ID is used in the Organization Relationship `DomainName` field.</span></span>

<span data-ttu-id="96a38-136">Para obtener el identificador de inquilino de una suscripción, inicie sesión en el centro de administración de Microsoft 365 y vaya a [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties) .</span><span class="sxs-lookup"><span data-stu-id="96a38-136">To obtain the tenant ID of a subscription, sign-in to the Microsoft 365 admin center and go to [https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="96a38-137">Haga clic en el icono de copia de la propiedad de ID de inquilino para copiarla en el portapapeles.</span><span class="sxs-lookup"><span data-stu-id="96a38-137">Click the copy icon for the Tenant ID property to copy it to the clipboard.</span></span>

<span data-ttu-id="96a38-138">Este es el funcionamiento del proceso.</span><span class="sxs-lookup"><span data-stu-id="96a38-138">Here is how the process works.</span></span>

:::image type="content" source="../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg" alt-text="Preparación del espacio empresarial para la migración de buzones.":::

<!--
[![Tenant preparation for mailbox migration](../media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg)

[See a larger version of this image](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/tenant-to-tenant-mailbox-move/prepare-tenants-flow.svg).
--> 

### <a name="prepare-tenants"></a><span data-ttu-id="96a38-140">Preparar inquilinos</span><span class="sxs-lookup"><span data-stu-id="96a38-140">Prepare tenants</span></span>

<span data-ttu-id="96a38-141">En un nivel superior, se producen las siguientes acciones de configuración cuando se ejecutan los scripts de instalación.</span><span class="sxs-lookup"><span data-stu-id="96a38-141">At a high level, the following configuration actions take place when executing the setup scripts.</span></span>

<span data-ttu-id="96a38-142">Preparar el inquilino de destino:</span><span class="sxs-lookup"><span data-stu-id="96a38-142">Prepare the target tenant:</span></span>

1. <span data-ttu-id="96a38-143">Si no se proporciona un grupo de recursos de Azure existente, se crea uno nuevo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-143">If an existing Azure Resource Group is not provided, a new one is created (SCRIPT).</span></span>
2. <span data-ttu-id="96a38-144">Si no se proporciona un almacén de claves existente, se creará uno nuevo (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-144">If an existing Key Vault is not provided, a new one is created (SCRIPT).</span></span>
3. <span data-ttu-id="96a38-145">Se crea una nueva Directiva de acceso para la aplicación de migración de buzones de correo de Exchange Online (SCRIPT) de Office 365.</span><span class="sxs-lookup"><span data-stu-id="96a38-145">A new Access Policy is created for the Office 365 Exchange Online Mailbox Migration application (SCRIPT).</span></span>
4. <span data-ttu-id="96a38-146">Se crea un nuevo certificado (o uno existente, si se especifica) para contener el secreto de la aplicación de migración (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-146">A new certificate is created (or existing one, if specified) to hold the secret to the Migration application (SCRIPT).</span></span>
5. <span data-ttu-id="96a38-147">Se crea una nueva aplicación de Azure AD (secuencia de comandos).</span><span class="sxs-lookup"><span data-stu-id="96a38-147">A new Azure AD application is created (SCRIPT).</span></span>
6. <span data-ttu-id="96a38-148">El certificado/secreto se carga en la aplicación de migración (secuencia de comandos).</span><span class="sxs-lookup"><span data-stu-id="96a38-148">The certificate/secret is uploaded to the migration application (SCRIPT).</span></span>
7. <span data-ttu-id="96a38-149">Los permisos de migración de buzones de correo se asignan a la aplicación (secuencia de comandos).</span><span class="sxs-lookup"><span data-stu-id="96a38-149">Mailbox migration permissions are assigned to the application (SCRIPT).</span></span>
8. <span data-ttu-id="96a38-150">El script de implementación se pausa hasta que el administrador de destino haya dado su consentimiento a su propia aplicación (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-150">The deployment script pauses until target admin consents to their own application (SCRIPT).</span></span>
9. <span data-ttu-id="96a38-151">El administrador del espacio empresarial de destino se remitirá a los permisos asignados a la aplicación (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="96a38-151">The target tenant admin consents to the permissions given to the application (MANUAL).</span></span>
10. <span data-ttu-id="96a38-152">Se crea una relación de organización con el espacio empresarial de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-152">An organization relationship is created to the target tenant (SCRIPT).</span></span>
11. <span data-ttu-id="96a38-153">Se crea un extremo de migración para extraer buzones al inquilino de destino (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-153">A migration endpoint is created to pull mailboxes to the target tenant (SCRIPT).</span></span>

<span data-ttu-id="96a38-154">Prepare el inquilino de origen:</span><span class="sxs-lookup"><span data-stu-id="96a38-154">Prepare the source tenant:</span></span>

1. <span data-ttu-id="96a38-155">El administrador del espacio empresarial de origen acepta el consentimiento para la invitación de la aplicación de migración del buzón de correo del espacio empresarial de destino (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="96a38-155">The source tenant admin accepts consent to Mailbox Migration application invitation from the Target tenant (MANUAL).</span></span>
2. <span data-ttu-id="96a38-156">El administrador del espacio empresarial de origen crea un grupo de seguridad habilitado para correo en su inquilino para incluir la lista de buzones que la aplicación de migración puede mover (MANUAL).</span><span class="sxs-lookup"><span data-stu-id="96a38-156">The source tenant admin creates a mail-enabled security group in their tenant to contain the list of mailboxes allowed to be moved by the migration application (MANUAL).</span></span>
3. <span data-ttu-id="96a38-157">Se crea una relación de organización con el inquilino de destino que especifica la aplicación de migración de buzones de correo que se debe usar para la comprobación de OAuth para aceptar la solicitud de movimiento (SCRIPT).</span><span class="sxs-lookup"><span data-stu-id="96a38-157">An organization relationship is created to the target tenant specifying the mailbox migration application should be used for OAuth verification to accept the move request (SCRIPT).</span></span>

#### <a name="step-by-step-instructions-for-the-target-tenant-admin"></a><span data-ttu-id="96a38-158">Instrucciones paso a paso para el administrador del espacio empresarial de destino</span><span class="sxs-lookup"><span data-stu-id="96a38-158">Step-by-step instructions for the target tenant admin</span></span>

1. <span data-ttu-id="96a38-159">Descargue el script de SetupCrossTenantRelationshipForTargetTenant.ps1 para la configuración del inquilino de destino desde el [repositorio de github](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span><span class="sxs-lookup"><span data-stu-id="96a38-159">Download the SetupCrossTenantRelationshipForTargetTenant.ps1 script for the target tenant setup from the [GitHub repository](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 
2. <span data-ttu-id="96a38-160">Guarde el script (SetupCrossTenantRelationshipForTargetTenant.ps1) en el equipo desde el que va a ejecutar el script.</span><span class="sxs-lookup"><span data-stu-id="96a38-160">Save the script (SetupCrossTenantRelationshipForTargetTenant.ps1) to the computer from which you will be executing the script.</span></span>
3. <span data-ttu-id="96a38-161">Cree una conexión de PowerShell remota con el inquilino de destino de Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="96a38-161">Create a Remote PowerShell connection to the Exchange Online target tenant.</span></span> <span data-ttu-id="96a38-162">De nuevo, asegúrese de que tiene los permisos necesarios para ejecutar los scripts de implementación con el fin de configurar el certificado y el almacenamiento de la clave de Azure para la aplicación mover buzones, el extremo de migración de EXO y la relación de organización EXO.</span><span class="sxs-lookup"><span data-stu-id="96a38-162">Again, make sure you have the necessary permissions to run the deployment scripts in order to configure the Azure Key Vault storage and certificate, Move Mailbox application, EXO Migration Endpoint, and the EXO Organization Relationship.</span></span>
4. <span data-ttu-id="96a38-163">Cambie el directorio de la carpeta de archivos a la ubicación del script o Compruebe que el script se haya guardado actualmente en la ubicación actual de la sesión de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="96a38-163">Change the file folder directory to the script location or verify the script is currently saved to the location currently in your Remote PowerShell session.</span></span>
5. <span data-ttu-id="96a38-164">Ejecute el script con los siguientes parámetros y valores.</span><span class="sxs-lookup"><span data-stu-id="96a38-164">Run the script with the following parameters and values.</span></span>

    | <span data-ttu-id="96a38-165">Parámetro</span><span class="sxs-lookup"><span data-stu-id="96a38-165">Parameter</span></span> | <span data-ttu-id="96a38-166">Valor</span><span class="sxs-lookup"><span data-stu-id="96a38-166">Value</span></span> | <span data-ttu-id="96a38-167">Obligatorio u opcional</span><span class="sxs-lookup"><span data-stu-id="96a38-167">Required or Optional</span></span>
    |---------------------------------------------|-----------------|--------------|
    | <span data-ttu-id="96a38-168">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="96a38-168">-ResourceTenantDomain</span></span>                       | <span data-ttu-id="96a38-169">Dominio de inquilino de origen, como Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="96a38-169">Source tenant domain, such as fabrikam\.onmicrosoft.com.</span></span> | <span data-ttu-id="96a38-170">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-170">Required</span></span> |
    | <span data-ttu-id="96a38-171">-ResourceTenantAdminEmail</span><span class="sxs-lookup"><span data-stu-id="96a38-171">-ResourceTenantAdminEmail</span></span>                   | <span data-ttu-id="96a38-172">Dirección de correo electrónico del administrador del inquilino de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-172">Source tenant admin’s email address.</span></span> <span data-ttu-id="96a38-173">Este es el administrador de inquilinos de origen que contratará el uso de la aplicación de migración de buzones de correo enviada desde el administrador de destino. Este es el administrador que recibirá la invitación por correo electrónico para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96a38-173">This is the source tenant admin who will be consenting to the use of the mailbox migration application sent from the target admin. This is the admin who will receive the email invite for the application.</span></span> | <span data-ttu-id="96a38-174">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-174">Required</span></span> |
    | <span data-ttu-id="96a38-175">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="96a38-175">-TargetTenantDomain</span></span>                         | <span data-ttu-id="96a38-176">Dominio de inquilino de destino, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="96a38-176">Target tenant domain, such as contoso\.onmicrosoft.com.</span></span> | <span data-ttu-id="96a38-177">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-177">Required</span></span> |
    | <span data-ttu-id="96a38-178">-ResourceTenantId</span><span class="sxs-lookup"><span data-stu-id="96a38-178">-ResourceTenantId</span></span>                           | <span data-ttu-id="96a38-179">IDENTIFICADOR de la organización del espacio empresarial de origen (GUID).</span><span class="sxs-lookup"><span data-stu-id="96a38-179">Source tenant organization ID (GUID).</span></span> | <span data-ttu-id="96a38-180">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-180">Required</span></span> |
    | <span data-ttu-id="96a38-181">-SubscriptionId</span><span class="sxs-lookup"><span data-stu-id="96a38-181">-SubscriptionId</span></span>                             | <span data-ttu-id="96a38-182">La suscripción de Azure que se va a usar para crear recursos.</span><span class="sxs-lookup"><span data-stu-id="96a38-182">The Azure subscription to use for creating resources.</span></span> | <span data-ttu-id="96a38-183">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-183">Required</span></span> |
    | <span data-ttu-id="96a38-184">-ResourceGroup</span><span class="sxs-lookup"><span data-stu-id="96a38-184">-ResourceGroup</span></span>                              | <span data-ttu-id="96a38-185">Nombre del grupo de recursos de Azure que contiene o contendrá el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="96a38-185">Azure resource group name that contains or will contain the Key Vault.</span></span> | <span data-ttu-id="96a38-186">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-186">Required</span></span> |
    | <span data-ttu-id="96a38-187">-KeyVaultName</span><span class="sxs-lookup"><span data-stu-id="96a38-187">-KeyVaultName</span></span>                               | <span data-ttu-id="96a38-188">Instancia de Azure Key Vault que almacenará el secreto o certificado de la aplicación de migración de buzones.</span><span class="sxs-lookup"><span data-stu-id="96a38-188">Azure Key Vault instance that will store your mailbox migration application certificate/secret.</span></span> | <span data-ttu-id="96a38-189">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-189">Required</span></span> |
    | <span data-ttu-id="96a38-190">-CertificateName</span><span class="sxs-lookup"><span data-stu-id="96a38-190">-CertificateName</span></span>                            | <span data-ttu-id="96a38-191">Nombre del certificado al generar o buscar un certificado en el almacén de claves.</span><span class="sxs-lookup"><span data-stu-id="96a38-191">Certificate name when generating or searching for certificate in key vault.</span></span> | <span data-ttu-id="96a38-192">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-192">Required</span></span> |
    | <span data-ttu-id="96a38-193">-CertificateSubject</span><span class="sxs-lookup"><span data-stu-id="96a38-193">-CertificateSubject</span></span>                         | <span data-ttu-id="96a38-194">Nombre del firmante del certificado de Azure Key Vault, como CN = contoso_fabrikam.</span><span class="sxs-lookup"><span data-stu-id="96a38-194">Azure Key Vault certificate subject name, such as CN=contoso_fabrikam.</span></span> | <span data-ttu-id="96a38-195">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-195">Required</span></span> |
    | <span data-ttu-id="96a38-196">-ExistingApplicationId</span><span class="sxs-lookup"><span data-stu-id="96a38-196">-ExistingApplicationId</span></span>                      | <span data-ttu-id="96a38-197">Aplicación de migración de correo para usar si ya se creó una.</span><span class="sxs-lookup"><span data-stu-id="96a38-197">Mail migration application to use if one was already created.</span></span> | <span data-ttu-id="96a38-198">Opcional</span><span class="sxs-lookup"><span data-stu-id="96a38-198">Optional</span></span> |
    | <span data-ttu-id="96a38-199">-AzureAppPermissions</span><span class="sxs-lookup"><span data-stu-id="96a38-199">-AzureAppPermissions</span></span>                        | <span data-ttu-id="96a38-200">Los permisos que se deben dar a la aplicación de migración de buzones de correo, como Exchange o MSGraph (Exchange para mover buzones de correo, MSGraph para usar esta aplicación para enviar una invitación de vínculo de consentimiento al espacio empresarial de recursos).</span><span class="sxs-lookup"><span data-stu-id="96a38-200">The permissions required to be given to the mailbox migration application, such as Exchange or MSGraph (Exchange for moving mailboxes, MSGraph for using this application to send a consent link invitation to resource tenant).</span></span> | <span data-ttu-id="96a38-201">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="96a38-201">Required</span></span> |
    | <span data-ttu-id="96a38-202">-UseAppAndCertGeneratedForSendingInvitation</span><span class="sxs-lookup"><span data-stu-id="96a38-202">-UseAppAndCertGeneratedForSendingInvitation</span></span> | <span data-ttu-id="96a38-203">Parámetro de uso de la aplicación creada para la migración que se va a usar para enviar la invitación del vínculo de consentimiento al administrador del espacio empresarial de origen. Si no está presente, se le pedirá a las credenciales del administrador de destino que se conecten al administrador de invitaciones de Azure y que envíen la invitación como administrador de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-203">Parameter for using the application created for migration to be used for sending consent link invitation to source tenant admin. If not present this will prompt for the target admin’s credentials to connect to Azure invitation manager and send the invitation as target admin.</span></span> | <span data-ttu-id="96a38-204">Opcional</span><span class="sxs-lookup"><span data-stu-id="96a38-204">Optional</span></span> |
    | <span data-ttu-id="96a38-205">-KeyVaultAuditStorageAccountName</span><span class="sxs-lookup"><span data-stu-id="96a38-205">-KeyVaultAuditStorageAccountName</span></span>            | <span data-ttu-id="96a38-206">La cuenta de almacenamiento en la que se almacenarán los registros de auditoría del almacén clave.</span><span class="sxs-lookup"><span data-stu-id="96a38-206">The storage account where Key Vault’s audit logs would be stored.</span></span> | <span data-ttu-id="96a38-207">Opcional</span><span class="sxs-lookup"><span data-stu-id="96a38-207">Optional</span></span> |
    | <span data-ttu-id="96a38-208">-KeyVaultAuditStorageResourceGroup</span><span class="sxs-lookup"><span data-stu-id="96a38-208">-KeyVaultAuditStorageResourceGroup</span></span>          | <span data-ttu-id="96a38-209">El grupo de recursos que contiene la cuenta de almacenamiento para almacenar los registros de auditoría de bóveda clave.</span><span class="sxs-lookup"><span data-stu-id="96a38-209">The resource group that contains the storage account for storing Key Vault audit logs.</span></span> | <span data-ttu-id="96a38-210">Opcional</span><span class="sxs-lookup"><span data-stu-id="96a38-210">Optional</span></span> |
    ||||

6. <span data-ttu-id="96a38-211">La secuencia de comandos se pausará y le pedirá que acepte o dé su consentimiento a la aplicación de migración de buzones de Exchange que se creó durante este proceso.</span><span class="sxs-lookup"><span data-stu-id="96a38-211">The script will pause and ask you to accept or consent to the Exchange mailbox migration application that was created during this process.</span></span> <span data-ttu-id="96a38-212">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-212">Here is an example.</span></span>

    ```powershell
    PS C:\Users\Admin\scripts\T2TMovesV2> .\SetupCrossTenantRelationshipForTargetTenant.ps1 -ResourceTenantDomain contoso.onmicrosoft.com -ResourceTenantAdminEmail admin@contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ResourceTenantId ksagjid39-ede2-4d2c-98ae-874709325b00 -SubscriptionId e4ssd05d-a327-49ss-849a-sd0932439023 -ResourceGroup "Cross-TenantMoves" -KeyVaultName "Cross-TenantMovesVault" -CertificateName "Contoso-Fabrikam-cert" -CertificateSubject "CN=Contoso_Fabrikam" -AzureAppPermissions Exchange, MSGraph -UseAppAndCertGeneratedForSendingInvitation -KeyVaultAuditStorageAccountName "t2tstorageaccount" -KeyVaultAuditStorageResourceGroup "Demo"

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

7. <span data-ttu-id="96a38-213">Se mostrará una dirección URL en la sesión de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="96a38-213">A URL will be displayed in the Remote PowerShell session.</span></span> <span data-ttu-id="96a38-214">Copie el vínculo proporcionado para el consentimiento del espacio empresarial y péguelo en un explorador Web.</span><span class="sxs-lookup"><span data-stu-id="96a38-214">Copy the link provided for your tenant consent and paste it into a Web browser.</span></span>

8. <span data-ttu-id="96a38-215">Inicie sesión con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="96a38-215">Sign in with your Global Admin credentials.</span></span> <span data-ttu-id="96a38-216">Cuando aparezca la siguiente pantalla, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="96a38-216">When the following screen is presented, select **Accept**.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-dialog.png" alt-text="Cuadro de diálogo aceptar permisos":::
    
9. <span data-ttu-id="96a38-218">Vuelva a la sesión remota de PowerShell y presione Entrar para continuar.</span><span class="sxs-lookup"><span data-stu-id="96a38-218">Switch back to the Remote PowerShell session and hit Enter to proceed.</span></span>

10. <span data-ttu-id="96a38-219">El script configurará los restantes objetos de instalación.</span><span class="sxs-lookup"><span data-stu-id="96a38-219">The script will configure the remaining setup objects.</span></span> <span data-ttu-id="96a38-220">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-220">Here is an example.</span></span>

    ```powershell
    Successfully sent invitation to admin@contoso.onmicrosoft.com
    Setting up exchange components on target tenant: fabrikam.onmicrosoft.com
    MigrationEndpoint created in fabrikam.onmicrosoft.com for target contoso.onmicrosoft.com
    Exchange setup complete. Migration endpoint details are available in $MigrationEndpoint variable
    ```

<span data-ttu-id="96a38-221">Se ha completado la configuración de administración de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-221">The target admin setup is now complete!</span></span>

#### <a name="step-by-step-instructions-for-the-source-tenant-admin"></a><span data-ttu-id="96a38-222">Instrucciones paso a paso para el administrador del espacio empresarial de origen</span><span class="sxs-lookup"><span data-stu-id="96a38-222">Step-by-step instructions for the source tenant admin</span></span>

1.  <span data-ttu-id="96a38-223">Inicie sesión en su buzón de correo como el-ResourceTenantAdminEmail especificado por el administrador de destino durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="96a38-223">Sign in to your mailbox as the -ResourceTenantAdminEmail specified by the target admin during their setup.</span></span> <span data-ttu-id="96a38-224">Busque la invitación por correo electrónico del inquilino de destino y, después, seleccione el botón **Introducción** .</span><span class="sxs-lookup"><span data-stu-id="96a38-224">Find the email invitation from the target tenant, and then select the **Get Started** button.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/invited-by-target-tenant.png" alt-text="Se ha invided cuadro de diálogo":::

2. <span data-ttu-id="96a38-226">Seleccione **Aceptar** para aceptar la invitación.</span><span class="sxs-lookup"><span data-stu-id="96a38-226">Select **Accept** to accept the invitation.</span></span>

    :::image type="content" source="../media/tenant-to-tenant-mailbox-move/permissions-requested-accept.png" alt-text="Cuadro de diálogo para aceptar permissons":::

   > [!NOTE]
   > <span data-ttu-id="96a38-228">Si no obtiene este correo electrónico o no lo encuentra, el administrador del espacio empresarial de destino le proporcionó una dirección URL directa que puede darle para aceptar la invitación.</span><span class="sxs-lookup"><span data-stu-id="96a38-228">If you do not get this email or cannot find it, the target tenant admin was provided a direct URL that can be given to you to accept the invitation.</span></span> <span data-ttu-id="96a38-229">La dirección URL debe encontrarse en la transcripción de la sesión de PowerShell remoto del administrador de inquilinos de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-229">The URL should in the in the transcript of the target tenant admin's Remote PowerShell session.</span></span>

3. <span data-ttu-id="96a38-230">En el centro de administración de Microsoft 365 o en una sesión remota de PowerShell, cree uno o varios grupos de seguridad habilitados para correo para controlar la lista de buzones que permite el inquilino de destino extraer (mover) del inquilino de origen al inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-230">In either the Microsoft 365 admin center or a Remote PowerShell session, create one or more mail-enabled security groups to control the list of mailboxes allowed by the target tenant to pull (move) from the source tenant to the target tenant.</span></span> <span data-ttu-id="96a38-231">No es necesario rellenar este grupo por adelantado, pero se debe proporcionar al menos un grupo para ejecutar los pasos de configuración (Script).</span><span class="sxs-lookup"><span data-stu-id="96a38-231">You do not need to populate this group in advance, but at least one group must be provided to run the setup steps (script).</span></span> <span data-ttu-id="96a38-232">No se admiten los grupos anidados.</span><span class="sxs-lookup"><span data-stu-id="96a38-232">Nest groups are not supported.</span></span> 

4. <span data-ttu-id="96a38-233">Descargue [aquí](https://github.com/microsoft/cross-tenant/releases/tag/Preview)el script de SetupCrossTenantRelationshipForTargetResource.ps1 para la configuración del inquilino de origen del repositorio de github.</span><span class="sxs-lookup"><span data-stu-id="96a38-233">Download the SetupCrossTenantRelationshipForTargetResource.ps1 script for the source tenant setup from the GitHub repository [here](https://github.com/microsoft/cross-tenant/releases/tag/Preview).</span></span> 

5. <span data-ttu-id="96a38-234">Cree una conexión de PowerShell remota con los permisos de administrador de Exchange en el inquilino de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-234">Create a Remote PowerShell connection to the source tenant with your Exchange Administrator permissions.</span></span> <span data-ttu-id="96a38-235">No se necesitan permisos de administrador global para configurar el inquilino de origen, solo el inquilino de destino a causa del proceso de creación de la aplicación de Azure.</span><span class="sxs-lookup"><span data-stu-id="96a38-235">Global Admin permissions are not required to configure the source tenant, only the target tenant because of the Azure application creation process.</span></span>

6. <span data-ttu-id="96a38-236">Cambie el directorio a la ubicación del script o Compruebe que el script esté guardado actualmente en la ubicación actual de la sesión de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="96a38-236">Change directory to the script location or verify that the script is currently saved to the location currently in your Remote PowerShell session.</span></span>

7. <span data-ttu-id="96a38-237">Ejecute el script con los siguientes valores y parámetros necesarios.</span><span class="sxs-lookup"><span data-stu-id="96a38-237">Run the script with the following required parameters and values.</span></span>

    | <span data-ttu-id="96a38-238">Parámetro</span><span class="sxs-lookup"><span data-stu-id="96a38-238">Parameter</span></span> | <span data-ttu-id="96a38-239">Valor</span><span class="sxs-lookup"><span data-stu-id="96a38-239">Value</span></span> |
    |-----|------|
    | <span data-ttu-id="96a38-240">-SourceMailboxMovePublishedScopes</span><span class="sxs-lookup"><span data-stu-id="96a38-240">-SourceMailboxMovePublishedScopes</span></span> | <span data-ttu-id="96a38-241">Grupo de seguridad habilitado para correo electrónico creado por el inquilino de origen para las identidades y los buzones que están en el ámbito de la migración.</span><span class="sxs-lookup"><span data-stu-id="96a38-241">Mail-enabled security group created by source tenant for the identities/mailboxes that are in scope for migration.</span></span> |
    | <span data-ttu-id="96a38-242">-ResourceTenantDomain</span><span class="sxs-lookup"><span data-stu-id="96a38-242">-ResourceTenantDomain</span></span> | <span data-ttu-id="96a38-243">Nombre de dominio del inquilino de origen, como Fabrikam \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="96a38-243">Source tenant domain name, such as fabrikam\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="96a38-244">-TargetTenantDomain</span><span class="sxs-lookup"><span data-stu-id="96a38-244">-TargetTenantDomain</span></span> | <span data-ttu-id="96a38-245">Nombre de dominio del inquilino de destino, como contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="96a38-245">Target tenant domain name, such as contoso\.onmicrosoft.com.</span></span> |
    | <span data-ttu-id="96a38-246">-ApplicationId</span><span class="sxs-lookup"><span data-stu-id="96a38-246">-ApplicationId</span></span> | <span data-ttu-id="96a38-247">IDENTIFICADOR de la aplicación de Azure (GUID) de la aplicación usada para la migración.</span><span class="sxs-lookup"><span data-stu-id="96a38-247">Azure application ID (GUID) of the application used for migration.</span></span> <span data-ttu-id="96a38-248">IDENTIFICADOR de la aplicación disponible a través de Azure portal (Azure AD, aplicaciones empresariales, nombre de la aplicación, identificador de la aplicación) o incluido en el correo electrónico de invitación.</span><span class="sxs-lookup"><span data-stu-id="96a38-248">Application ID available via your Azure portal (Azure AD, Enterprise Applications, app name, application ID) or included in your invitation email.</span></span>  |
    | <span data-ttu-id="96a38-249">-TargetTenantId</span><span class="sxs-lookup"><span data-stu-id="96a38-249">-TargetTenantId</span></span> | <span data-ttu-id="96a38-250">IDENTIFICADOR de inquilino del inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-250">Tenant ID of the target tenant.</span></span> <span data-ttu-id="96a38-251">Por ejemplo, el identificador de inquilino de Azure AD de Contoso \. onmicrosoft.com tenant.</span><span class="sxs-lookup"><span data-stu-id="96a38-251">For example, the Azure AD tenant ID of contoso\.onmicrosoft.com tenant.</span></span> |
    |||
    
    <span data-ttu-id="96a38-252">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-252">Here is an example.</span></span>
    ```powershell
    SetupCrossTenantRelationshipForResourceTenant.ps1 -SourceMailboxMovePublishedScopes "MigScope","MyGroup" -ResourceTenantDomain contoso.onmicrosoft.com -TargetTenantDomain fabrikam.onmicrosoft.com -ApplicationId sdf5e87sa-0753-dd88-ad35-c71a15cs8e44c -TargetTenantId 4sdkfo933-3904-sd93-bf9a-sdi39402834
    Exchange setup complete.

    ```

<span data-ttu-id="96a38-253">Se ha completado la configuración del administrador de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-253">The source admin setup is now complete!</span></span>

### <a name="verify-setup"></a><span data-ttu-id="96a38-254">Comprobar la configuración</span><span class="sxs-lookup"><span data-stu-id="96a38-254">Verify setup</span></span>

<span data-ttu-id="96a38-255">Compruebe que la relación de la organización en los inquilinos de origen y de destino y el extremo de migración en el destino se hayan creado correctamente.</span><span class="sxs-lookup"><span data-stu-id="96a38-255">Verify that the organization relationships in both source and target tenants and migration endpoint in the target were created successfully.</span></span>

#### <a name="target-tenant"></a><span data-ttu-id="96a38-256">Inquilino de destino</span><span class="sxs-lookup"><span data-stu-id="96a38-256">Target tenant</span></span>

<span data-ttu-id="96a38-257">**Relación de organización**</span><span class="sxs-lookup"><span data-stu-id="96a38-257">**Organization relationship**</span></span>

<span data-ttu-id="96a38-258">Compruebe que el objeto de relación de organización se haya creado y configurado con este comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-258">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship <source tenant organization name> | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability
```
<span data-ttu-id="96a38-259">Aquí le mostramos un ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96a38-259">Here is an example:</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship fabrikam_contoso_1178 | fl name, DomainNames, MailboxMoveEnabled, MailboxMoveCapability

Name                  : fabrikam_contoso_1123
DomainNames           : {sd0933me9f-9304-s903-s093-s093mfi903m4}
MailboxMoveEnabled    : True
MailboxMoveCapability : Inbound

```

<span data-ttu-id="96a38-260">**Extremo de migración**</span><span class="sxs-lookup"><span data-stu-id="96a38-260">**Migration endpoint**</span></span>

<span data-ttu-id="96a38-261">Compruebe que el objeto de extremo de migración se haya creado y configurado con este comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-261">Verify that the migration endpoint object was created and configured with this command.</span></span>

```powershell
Get-MigrationEndpoint "<fabrikam_contoso_1123> | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl
```

<span data-ttu-id="96a38-262">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-262">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-MigrationEndpoint fabrikam_contoso_1123 | fl Identity, RemoteTenant, ApplicationId, AppSecretKeyVaultUrl


Identity             : fabrikam_contoso_1123
RemoteTenant         : contoso.onmicrosoft.com
ApplicationId        : s93mf93-das9-dq24-dq234-dada9033904m
AppSecretKeyVaultUrl : https://cross-tenantmyvaultformoves.vault.azure.net:443/certificates/Contoso-Fabrikam-cert/ae79348mx94384c288c5a3dfsioepw308

```

#### <a name="source-tenant"></a><span data-ttu-id="96a38-263">Inquilino de origen</span><span class="sxs-lookup"><span data-stu-id="96a38-263">Source tenant</span></span>

<span data-ttu-id="96a38-264">**Relación de organización**</span><span class="sxs-lookup"><span data-stu-id="96a38-264">**Organization relationship**</span></span>

<span data-ttu-id="96a38-265">Compruebe que el objeto de relación de organización se haya creado y configurado con este comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-265">Verify that the organization relationship object was created and configured with this command.</span></span>

```powershell
Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId
```
<span data-ttu-id="96a38-266">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-266">Here is an example.</span></span>

```powershell
PS C:\Users\Admin\scripts\T2TMovesV2> Get-OrganizationRelationship | fl name, MailboxMoveEnabled, MailboxMoveCapability, MailboxMovePublishedScopes, OAuthApplicationId


Name                       : fabrikam_contoso_001
MailboxMoveEnabled         : True
MailboxMoveCapability      : RemoteOutbound
MailboxMovePublishedScopes : {MigScope}
OAuthApplicationId         : sd9890342-3243-3242-fe3w2-fsdade93m0
```

### <a name="move-mailboxes-back-to-the-original-source"></a><span data-ttu-id="96a38-267">Mover buzones de nuevo al origen inicial</span><span class="sxs-lookup"><span data-stu-id="96a38-267">Move mailboxes back to the original source</span></span>

<span data-ttu-id="96a38-268">Si es necesario volver a mover un buzón de correo al inquilino de origen inicial, se debe ejecutar el mismo conjunto de pasos y scripts en los nuevos inquilinos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-268">If a mailbox move back to the original source tenant is required, the same set of steps and scripts will need to be run in both new source and new target tenants.</span></span> <span data-ttu-id="96a38-269">El objeto de relación de organización existente se actualizará o se anexará, no se volverá a crear.</span><span class="sxs-lookup"><span data-stu-id="96a38-269">The existing Organization Relationship object will be updated or appended, not recreated.</span></span>

## <a name="prepare-target-user-objects-for-migration"></a><span data-ttu-id="96a38-270">Preparar objetos de usuario de destino para la migración</span><span class="sxs-lookup"><span data-stu-id="96a38-270">Prepare target user objects for migration</span></span>

<span data-ttu-id="96a38-271">Los usuarios que migren deben estar presentes en el inquilino de destino y en el sistema de Exchange Online (como MailUsers) marcado con atributos específicos para habilitar los movimientos entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-271">Users migrating must be present in the target tenant and Exchange Online system (as MailUsers) marked with specific attributes to enable the cross-tenant moves.</span></span> <span data-ttu-id="96a38-272">Se producirá un error en el sistema para los usuarios que no se hayan configurado correctamente en el espacio empresarial de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-272">The system will fail moves for users that are not properly set up in the target tenant.</span></span> <span data-ttu-id="96a38-273">En la siguiente sección se detallan los requisitos de objetos MailUser para el inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-273">The following section details the MailUser object requirements for the target tenant.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="96a38-274">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="96a38-274">Prerequisites</span></span>
  
<span data-ttu-id="96a38-275">Debe asegurarse de que los siguientes objetos y atributos se establecen en la organización de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-275">You must ensure the following objects and attributes are set in the target organization.</span></span>  

1. <span data-ttu-id="96a38-276">Para los buzones que se mueven de una organización de origen, debe aprovisionar un objeto MailUser en la organización de destino:</span><span class="sxs-lookup"><span data-stu-id="96a38-276">For any mailbox moving from a source organization, you must provision a MailUser object in the Target organization:</span></span> 
   - <span data-ttu-id="96a38-277">El MailUser de destino debe tener estos atributos del buzón de origen o asignarse con el nuevo objeto de usuario:</span><span class="sxs-lookup"><span data-stu-id="96a38-277">The Target MailUser must have these attributes from the source mailbox or assigned with the new User object:</span></span>
      - <span data-ttu-id="96a38-278">ExchangeGUID (flujo directo desde el origen hasta el destino): el GUID del buzón debe coincidir.</span><span class="sxs-lookup"><span data-stu-id="96a38-278">ExchangeGUID (direct flow from source to target) – The mailbox GUID must match.</span></span> <span data-ttu-id="96a38-279">El proceso de traslado no continuará si no está presente en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-279">The move process will not proceed if this is not present on target object.</span></span> 
      - <span data-ttu-id="96a38-280">ArchiveGUID (flujo directo desde el origen hasta el destino): el GUID de archivo debe coincidir.</span><span class="sxs-lookup"><span data-stu-id="96a38-280">ArchiveGUID (direct flow from source to target) – The archive GUID must match.</span></span> <span data-ttu-id="96a38-281">El proceso de traslado no continuará si no está presente en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-281">The move process will not proceed if this is not present on the target object.</span></span> <span data-ttu-id="96a38-282">(Solo es necesario si el buzón de origen está habilitado para el archivo).</span><span class="sxs-lookup"><span data-stu-id="96a38-282">(This is only required if the source mailbox is Archive enabled).</span></span> 
      - <span data-ttu-id="96a38-283">LegacyExchangeDN (flujo como proxyAddress, "x500: <LegacyExchangeDN> ") – el legacyExchangeDN debe estar presente en el MailUser de destino como x500: proxyAddress.</span><span class="sxs-lookup"><span data-stu-id="96a38-283">LegacyExchangeDN (flow as proxyAddress, “x500:<LegacyExchangeDN>”) – The LegacyExchangeDN must be present on target MailUser as x500: proxyAddress.</span></span> <span data-ttu-id="96a38-284">Los procesos de movimiento no continuarán si no está presente en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-284">The move processes will not proceed if this is not present on the target object.</span></span> 
      - <span data-ttu-id="96a38-285">UserPrincipalName – UPN se alineará con la nueva identidad o compañía de destino del usuario (por ejemplo, user@northwindtraders.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="96a38-285">UserPrincipalName – UPN will align to the user’s NEW identity or target company (for example, user@northwindtraders.onmicrosoft.com).</span></span> 
      - <span data-ttu-id="96a38-286">SMTPAddress principal: la dirección SMTP principal se alineará con la nueva empresa del usuario (por ejemplo, user@northwind.com).</span><span class="sxs-lookup"><span data-stu-id="96a38-286">Primary SMTPAddress – Primary SMTP address will align to the user’s NEW company (for example, user@northwind.com).</span></span> 
      - <span data-ttu-id="96a38-287">TargetAddress/ExternalEmailAddress – MailUser hará referencia al buzón actual del usuario hospedado en el inquilino de origen (por ejemplo, user@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="96a38-287">TargetAddress/ExternalEmailAddress – MailUser will reference the user’s current mailbox hosted in source tenant (for example user@contoso.onmicrosoft.com).</span></span> <span data-ttu-id="96a38-288">Al asignar este valor, compruebe que también está asignando PrimarySMTPAddress o que este valor establecerá PrimarySMTPAddress, lo que provocará errores de movimiento.</span><span class="sxs-lookup"><span data-stu-id="96a38-288">When assigning this value, verify that you have/are also assigning PrimarySMTPAddress or this value will set the PrimarySMTPAddress which will cause move failures.</span></span> 
      - <span data-ttu-id="96a38-289">No puede agregar direcciones proxy SMTP heredadas desde el buzón de origen al usuario MailUser.</span><span class="sxs-lookup"><span data-stu-id="96a38-289">You cannot add legacy smtp proxy addresses from source mailbox to target MailUser.</span></span> <span data-ttu-id="96a38-290">Por ejemplo, no puede mantener contoso.com en la unidad MEU en los objetos de inquilino de fabrikam.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="96a38-290">For example, you cannot maintain contoso.com on the MEU in fabrikam.onmicrosoft.com tenant objects).</span></span> <span data-ttu-id="96a38-291">Los dominios están asociados solo a un inquilino de Azure AD o Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="96a38-291">Domains are associated with one Azure AD or Exchange Online tenant only.</span></span>
 
    <span data-ttu-id="96a38-292">Ejemplo de objeto de MailUser de **destino** :</span><span class="sxs-lookup"><span data-stu-id="96a38-292">Example **target** MailUser object:</span></span>
 
    | <span data-ttu-id="96a38-293">Atributo</span><span class="sxs-lookup"><span data-stu-id="96a38-293">Attribute</span></span>             | <span data-ttu-id="96a38-294">Valor</span><span class="sxs-lookup"><span data-stu-id="96a38-294">Value</span></span>                                                                                                                    |
    |-----------------------|--------------------------------------------------------------------------------------------------------------------------|
    | <span data-ttu-id="96a38-295">Alias</span><span class="sxs-lookup"><span data-stu-id="96a38-295">Alias</span></span>                 | <span data-ttu-id="96a38-296">LaraN</span><span class="sxs-lookup"><span data-stu-id="96a38-296">LaraN</span></span>                                                                                                                    |
    | <span data-ttu-id="96a38-297">RecipientType</span><span class="sxs-lookup"><span data-stu-id="96a38-297">RecipientType</span></span>         | <span data-ttu-id="96a38-298">MailUser</span><span class="sxs-lookup"><span data-stu-id="96a38-298">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="96a38-299">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="96a38-299">RecipientTypeDetails</span></span>  | <span data-ttu-id="96a38-300">MailUser</span><span class="sxs-lookup"><span data-stu-id="96a38-300">MailUser</span></span>                                                                                                                 |
    | <span data-ttu-id="96a38-301">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="96a38-301">UserPrincipalName</span></span>     | <span data-ttu-id="96a38-302">LaraN@northwintraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96a38-302">LaraN@northwintraders\.onmicrosoft.com</span></span>                                                                                    |
    | <span data-ttu-id="96a38-303">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="96a38-303">PrimarySmtpAddress</span></span>    | <span data-ttu-id="96a38-304">Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="96a38-304">Lara\.Newton@northwind.com</span></span>                                                                                                |
    | <span data-ttu-id="96a38-305">ExternalEmailAddress</span><span class="sxs-lookup"><span data-stu-id="96a38-305">ExternalEmailAddress</span></span>  | <span data-ttu-id="96a38-306">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96a38-306">SMTP:LaraN@contoso\.onmicrosoft.com</span></span>                                                                                       |
    | <span data-ttu-id="96a38-307">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="96a38-307">ExchangeGuid</span></span>          | <span data-ttu-id="96a38-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="96a38-308">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                                                                     |
    | <span data-ttu-id="96a38-309">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="96a38-309">LegacyExchangeDN</span></span>      | <span data-ttu-id="96a38-310">/o = First Organization/ou = grupo administrativo de Exchange</span><span class="sxs-lookup"><span data-stu-id="96a38-310">/o=First Organization/ou=Exchange Administrative Group</span></span>                                                                   |
    |                       | <span data-ttu-id="96a38-311">(FYDIBOHF23SPDLT)/CN = Recipients/CN = 74e5385fce4b46d19006876949855035Lara</span><span class="sxs-lookup"><span data-stu-id="96a38-311">(FYDIBOHF23SPDLT)/cn=Recipients/cn=74e5385fce4b46d19006876949855035Lara</span></span>                                                  |
    | <span data-ttu-id="96a38-312">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="96a38-312">EmailAddresses</span></span>        | <span data-ttu-id="96a38-313">x500:/o = primera organización o unidad organizativa = grupo administrativo de Exchange (FYDIBOHF23SPDLT)/CN = destinatarios/CN = d11ec1a2cacd4f81858c8190</span><span class="sxs-lookup"><span data-stu-id="96a38-313">x500:/o=First Organization/ou=Exchange Administrative Group (FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c8190</span></span>  |
    |                       | <span data-ttu-id="96a38-314">7273f1f9-Lara</span><span class="sxs-lookup"><span data-stu-id="96a38-314">7273f1f9-Lara</span></span>                                                                                                            |
    |                       | <span data-ttu-id="96a38-315">SMTP: LaraN@northwindtraders \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96a38-315">smtp:LaraN@northwindtraders\.onmicrosoft.com</span></span>                                                                              |
    |                       | <span data-ttu-id="96a38-316">SMTP: Lara \. Newton@northwind.com</span><span class="sxs-lookup"><span data-stu-id="96a38-316">SMTP:Lara\.Newton@northwind.com</span></span>                                                                                           |
    |||

   <span data-ttu-id="96a38-317">Ejemplo de objeto de buzón de **origen** :</span><span class="sxs-lookup"><span data-stu-id="96a38-317">Example **source** Mailbox object:</span></span>

   | <span data-ttu-id="96a38-318">Atributo</span><span class="sxs-lookup"><span data-stu-id="96a38-318">Attribute</span></span>             | <span data-ttu-id="96a38-319">Valor</span><span class="sxs-lookup"><span data-stu-id="96a38-319">Value</span></span>                                                                    |
   |-----------------------|--------------------------------------------------------------------------|
   | <span data-ttu-id="96a38-320">Alias</span><span class="sxs-lookup"><span data-stu-id="96a38-320">Alias</span></span>                 | <span data-ttu-id="96a38-321">LaraN</span><span class="sxs-lookup"><span data-stu-id="96a38-321">LaraN</span></span>                                                                    |
   | <span data-ttu-id="96a38-322">RecipientType</span><span class="sxs-lookup"><span data-stu-id="96a38-322">RecipientType</span></span>         | <span data-ttu-id="96a38-323">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="96a38-323">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="96a38-324">RecipientTypeDetails</span><span class="sxs-lookup"><span data-stu-id="96a38-324">RecipientTypeDetails</span></span>  | <span data-ttu-id="96a38-325">UserMailbox</span><span class="sxs-lookup"><span data-stu-id="96a38-325">UserMailbox</span></span>                                                              |
   | <span data-ttu-id="96a38-326">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="96a38-326">UserPrincipalName</span></span>     | <span data-ttu-id="96a38-327">LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96a38-327">LaraN@contoso\.onmicrosoft.com</span></span>                                            |
   | <span data-ttu-id="96a38-328">PrimarySmtpAddress</span><span class="sxs-lookup"><span data-stu-id="96a38-328">PrimarySmtpAddress</span></span>    | <span data-ttu-id="96a38-329">Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96a38-329">Lara\.Newton@contoso.com</span></span>                                                  |
   | <span data-ttu-id="96a38-330">ExchangeGuid</span><span class="sxs-lookup"><span data-stu-id="96a38-330">ExchangeGuid</span></span>          | <span data-ttu-id="96a38-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span><span class="sxs-lookup"><span data-stu-id="96a38-331">1ec059c7-8396-4d0b-af4e-d6bd4c12a8d8</span></span>                                     |
   | <span data-ttu-id="96a38-332">LegacyExchangeDN</span><span class="sxs-lookup"><span data-stu-id="96a38-332">LegacyExchangeDN</span></span>      | <span data-ttu-id="96a38-333">/o = First Organization/ou = grupo administrativo de Exchange</span><span class="sxs-lookup"><span data-stu-id="96a38-333">/o=First Organization/ou=Exchange Administrative Group</span></span>                   |
   |                       | <span data-ttu-id="96a38-334">(FYDIBOHF23SPDLT)/CN = Recipients/CN = d11ec1a2cacd4f81858c81907273f1f9Lara</span><span class="sxs-lookup"><span data-stu-id="96a38-334">(FYDIBOHF23SPDLT)/cn=Recipients/cn=d11ec1a2cacd4f81858c81907273f1f9Lara</span></span>  |
   | <span data-ttu-id="96a38-335">EmailAddresses</span><span class="sxs-lookup"><span data-stu-id="96a38-335">EmailAddresses</span></span>        | <span data-ttu-id="96a38-336">SMTP: LaraN@contoso \. onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="96a38-336">smtp:LaraN@contoso\.onmicrosoft.com</span></span> 
   |                       | <span data-ttu-id="96a38-337">SMTP: Lara \. Newton@contoso.com</span><span class="sxs-lookup"><span data-stu-id="96a38-337">SMTP:Lara\.Newton@contoso.com</span></span>          |
   |||

   - <span data-ttu-id="96a38-338">Es posible que ya se incluyan atributos adicionales en Exchange Hybrid Writer back.</span><span class="sxs-lookup"><span data-stu-id="96a38-338">Additional attributes may be included in Exchange hybrid write back already.</span></span> <span data-ttu-id="96a38-339">Si no es así, se deben incluir.</span><span class="sxs-lookup"><span data-stu-id="96a38-339">If not, they should be included.</span></span> 
   - <span data-ttu-id="96a38-340">msExchBlockedSendersHash – escribe datos de remitentes seguros y bloqueados en línea de los clientes en una implementación local de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96a38-340">msExchBlockedSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="96a38-341">msExchSafeRecipientsHash – escribe datos de remitentes seguros y bloqueados en línea de los clientes en una implementación local de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96a38-341">msExchSafeRecipientsHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>
   - <span data-ttu-id="96a38-342">msExchSafeSendersHash – escribe datos de remitentes seguros y bloqueados en línea de los clientes en una implementación local de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="96a38-342">msExchSafeSendersHash – Writes back online safe and blocked sender data from clients to on-premises Active Directory.</span></span>

2. <span data-ttu-id="96a38-343">Si el buzón de origen está en LitigationHold y el tamaño de los elementos recuperables del buzón de origen es mayor que el valor predeterminado de la base de datos (30 GB), el movimiento no continuará porque la cuota de destino sea menor que el tamaño del buzón de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-343">If the source mailbox is on LitigationHold and the source mailbox Recoverable Items size is greater than our database default (30 GB), moves will not proceed since the target quota is less than the source mailbox size.</span></span> <span data-ttu-id="96a38-344">Puede actualizar el objeto MailUser de destino para realizar la transición de las marcas de buzón ELC del entorno de origen al destino, lo que activa el sistema de destino para expandir la cuota del MailUser a 100 GB, lo que permite mover al destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-344">You can update the target MailUser object to transition the ELC mailbox flags from the source environment to the target, which triggers the target system to expand the quota of the MailUser to 100 GB, thus allowing the move to the target.</span></span> <span data-ttu-id="96a38-345">Estas instrucciones funcionarán solo para la identidad híbrida que ejecuta Azure AD Connect, ya que los comandos para marcar las marcas ELC no se exponen a los administradores de espacios empresariales.</span><span class="sxs-lookup"><span data-stu-id="96a38-345">These instructions will work only for hybrid identity running Azure AD Connect, as the commands to stamp the ELC flags are not exposed to tenant administrators.</span></span>

    >[!Note]
    > <span data-ttu-id="96a38-346">MUESTRA: COMO ES, SIN GARANTÍA</span><span class="sxs-lookup"><span data-stu-id="96a38-346">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="96a38-347">Esta secuencia de comandos presupone la conexión con el buzón de origen (para obtener los valores de origen) y el destino local de Active Directory (para marcar el objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="96a38-347">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory (to stamp the ADUser object).</span></span> <span data-ttu-id="96a38-348">Si el origen tiene habilitada una recuperación por juicio o un elemento único, establézcalo en la cuenta de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-348">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="96a38-349">Esto aumentará el tamaño de la papelera de la cuenta de destino a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="96a38-349">This will increase the dumpster size of destination account to 100 GB.</span></span>

    ```powershell
    $ELCValue = 0 
    if ($source.LitigationHoldEnabled) {$ELCValue = $ELCValue + 8} if ($source.SingleItemRecoveryEnabled) {$ELCValue = $ELCValue + 16} if ($ELCValue -gt 0) {Set-ADUser -Server $domainController -Identity $destination.SamAccountName -Replace @{msExchELCMailboxFlags=$ELCValue}} 
    ```
3. <span data-ttu-id="96a38-350">Los inquilinos no híbridos de destino pueden modificar la cuota de la carpeta elementos recuperables para la MailUsers antes de la migración, mediante la ejecución del siguiente comando para habilitar la retención por juicio en el objeto MailUser y aumentar la cuota a 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE` .</span><span class="sxs-lookup"><span data-stu-id="96a38-350">Non-hybrid target tenants can modify the quota on the Recoverable Items folder for the MailUsers prior to migration by running the following command to enable Litigation Hold on the MailUser object and increasing the quota to 100 GB: `Set-MailUser -EnableLitigationHoldForMigration $TRUE`.</span></span> <span data-ttu-id="96a38-351">Nota Esto no funcionará para los inquilinos en entornos híbridos.</span><span class="sxs-lookup"><span data-stu-id="96a38-351">Note this will not work for tenants in hybrid.</span></span>

4. <span data-ttu-id="96a38-352">Es necesario que los usuarios de la organización de destino tengan una licencia con las suscripciones de Exchange Online adecuadas para la organización.</span><span class="sxs-lookup"><span data-stu-id="96a38-352">Users in the target organization must be licensed with appropriate Exchange Online subscriptions applicable for the organization.</span></span> <span data-ttu-id="96a38-353">Puede aplicar una licencia por anticipado a un movimiento de buzón de correo, pero solo una vez que el MailUser de destino esté correctamente configurado con ExchangeGUID y direcciones de proxy.</span><span class="sxs-lookup"><span data-stu-id="96a38-353">You may apply a license in advance of a mailbox move but ONLY once the target MailUser is properly set up with ExchangeGUID and proxy addresses.</span></span> <span data-ttu-id="96a38-354">La aplicación de una licencia antes de aplicar el ExchangeGUID dará como resultado un nuevo buzón aprovisionado en la organización de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-354">Applying a license before the ExchangeGUID is applied will result in a new mailbox provisioned in target organization.</span></span> 

    > [!Note]
    > <span data-ttu-id="96a38-355">Cuando se aplica una licencia en un objeto Mailbox o MailUser, todos los tipos de SMTP proxyAddresses se borran para garantizar que solo los dominios comprobados se incluyen en la matriz de EmailAddresses de Exchange.</span><span class="sxs-lookup"><span data-stu-id="96a38-355">When you apply a license on a Mailbox or MailUser object, all SMTP type proxyAddresses are scrubbed to ensure only verified domains are included in the Exchange EmailAddresses array.</span></span> 

5. <span data-ttu-id="96a38-356">Debe asegurarse de que el MailUser de destino no tiene un ExchangeGuid anterior que no coincide con el ExchangeGuid de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-356">You must ensure that the target MailUser has no previous ExchangeGuid that does not match the Source ExchangeGuid.</span></span> <span data-ttu-id="96a38-357">Esto puede ocurrir si la MEU de destino fue previamente autorizada para Exchange Online y ha aprovisionado un buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="96a38-357">This might occur if the target MEU was previously licensed for Exchange Online and provisioned a mailbox.</span></span> <span data-ttu-id="96a38-358">Si el MailUser de destino ha sido previamente autorizado para o tenía un ExchangeGuid que no coincide con el ExchangeGuid de origen, debe realizar una limpieza de la unidad MEU de la nube.</span><span class="sxs-lookup"><span data-stu-id="96a38-358">If the target MailUser was previously licensed for or had an ExchangeGuid that does not match the Source ExchangeGuid, you need to perform a cleanup of the cloud MEU.</span></span> <span data-ttu-id="96a38-359">Para estos MEU en la nube, puede ejecutar el `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-359">For these cloud MEUs, you can run the `Set-User <identity> -PermanentlyClearPreviousMailboxInfo` command.</span></span> 

    > [!Caution]
    > <span data-ttu-id="96a38-360">Este proceso es irreversible.</span><span class="sxs-lookup"><span data-stu-id="96a38-360">This process is irreversible.</span></span> <span data-ttu-id="96a38-361">Si el objeto tiene un buzón de softDeleted, no se podrá restaurar después de este punto.</span><span class="sxs-lookup"><span data-stu-id="96a38-361">If the object has a softDeleted mailbox, it cannot be restored after this point.</span></span> <span data-ttu-id="96a38-362">Sin embargo, una vez desactivada, puede sincronizar el ExchangeGuid correcto con el objeto de destino y MRS conectará el buzón de origen al buzón de destino recién creado.</span><span class="sxs-lookup"><span data-stu-id="96a38-362">Once cleared, however, you can sync the correct ExchangeGuid to the target object and MRS will connect the source mailbox to the newly created target mailbox.</span></span> <span data-ttu-id="96a38-363">(Consulte el blog de EHLO de referencia en el nuevo parámetro).</span><span class="sxs-lookup"><span data-stu-id="96a38-363">(Reference EHLO blog on the new parameter.)</span></span> 
 
    <span data-ttu-id="96a38-364">Buscar objetos que eran buzones anteriores mediante este comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-364">Find objects that were previously mailboxes using this command.</span></span>

    ```powershell
    Get-User <identity> | select Name, *recipient* | ft -a**.
    ```
    <span data-ttu-id="96a38-365">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-365">Here is an example.</span></span> 

    ```powershell
    PS demo> get-user John@northwindtraders.com |select name, *recipient*| ft -AutoSize 
 
    Name        PreviousRecipientTypeDetails     RecipientType RecipientTypeDetails 
    ----       ---------------------------- ------------- -------------------- 
    John       UserMailbox                  MailUser      MailUser 
    ```   
 
    <span data-ttu-id="96a38-366">Borre el buzón de correo eliminado temporalmente con este comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-366">Clear the soft-deleted mailbox using this command.</span></span>

    ````
    Set-User <identity> -PermanentlyClearPreviousMailboxInfo
    ```` 

    <span data-ttu-id="96a38-367">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-367">Here is an example.</span></span>

    ```powershell
    PS demo> Set-User John@northwindtraders.com -PermanentlyClearPreviousMailboxInfo Confirm 
    Are you sure you want to perform this action? 
    Delete all existing information about user “John@northwindtraders.com"?. This operation will clear existing values from Previous home MDB and Previous Mailbox GUID of the user. After deletion, reconnecting to the previous mailbox that existed in the cloud will not be possible and any content it had will be unrecoverable PERMANENTLY. 
    Do you want to continue? 
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [?] Help (default is "Y"): Y 
    ```

## <a name="perform-mailbox-migrations"></a><span data-ttu-id="96a38-368">Realizar migraciones de buzones de correo</span><span class="sxs-lookup"><span data-stu-id="96a38-368">Perform mailbox migrations</span></span>

<span data-ttu-id="96a38-369">Las migraciones de buzones de correo de Exchange entre inquilinos se envían como lotes de migración iniciados desde el inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-369">Cross-tenant Exchange mailbox migrations are submitted as migration batches initiated from the target tenant.</span></span> <span data-ttu-id="96a38-370">Esto es similar a la forma en que funcionan los lotes de migración de la incorporación al migrar de Exchange local a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96a38-370">This is similar to the way that on-boarding migration batches work when migrating from Exchange on-premises to Microsoft 365.</span></span> 

### <a name="create-migration-batches"></a><span data-ttu-id="96a38-371">Crear lotes de migración</span><span class="sxs-lookup"><span data-stu-id="96a38-371">Create Migration batches</span></span>

<span data-ttu-id="96a38-372">Este es un cmdlet de lote de migración de ejemplo para iniciar los movimientos.</span><span class="sxs-lookup"><span data-stu-id="96a38-372">Here is an example migration batch cmdlet for kicking off moves.</span></span>

```powershell
New-MigrationBatch -Name T2Tbatch-testforignitedemo -SourceEndpoint target_source_7977 -CSVData ([System.IO.File]::ReadAllBytes('users.csv')) -Autostart -TargetDeliveryDomain targetformoves.onmicrosoft.com -AutoComplete

Identity                   Status  Type               TotalCount
--------                   ------  ----               ----------
T2Tbatch-testforignitedemo Syncing ExchangeRemoteMove 1

```

> [!Note]
> <span data-ttu-id="96a38-373">La dirección de correo electrónico del archivo CSV debe ser la especificada en el inquilino de destino, no el inquilino de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-373">The email address in the CSV file must be the one specified in the target tenant, not the source tenant.</span></span>

<span data-ttu-id="96a38-374">El envío por lotes de migración también se admite desde el nuevo centro de administración de Exchange cuando se selecciona la opción Cross-tenant.</span><span class="sxs-lookup"><span data-stu-id="96a38-374">Migration batch submission is also supported from the new Exchange Admin Center when selecting the cross-tenant option.</span></span>
 
#### <a name="update-on-premises-mailusers"></a><span data-ttu-id="96a38-375">Actualizar MailUsers local</span><span class="sxs-lookup"><span data-stu-id="96a38-375">Update on-premises MailUsers</span></span>

<span data-ttu-id="96a38-376">Una vez que el buzón de correo se mueve del origen al destino, debe asegurarse de que los usuarios de correo locales, tanto de origen como de destino, se actualizan con el nuevo targetAddress.</span><span class="sxs-lookup"><span data-stu-id="96a38-376">Once the mailbox moves from source to target, you should ensure that the on-premises mail users, both Source and target, are updated with the new targetAddress.</span></span> <span data-ttu-id="96a38-377">En los ejemplos, el targetDeliveryDomain usado en la transferencia es **contoso \. onmicrosoft.com**.</span><span class="sxs-lookup"><span data-stu-id="96a38-377">In the examples, the targetDeliveryDomain used in the move is **contoso\.onmicrosoft.com**.</span></span> <span data-ttu-id="96a38-378">Actualice los usuarios de correo con este targetAddress.</span><span class="sxs-lookup"><span data-stu-id="96a38-378">Update the mail users with this targetAddress.</span></span>
 
## <a name="frequently-asked-questions"></a><span data-ttu-id="96a38-379">Preguntas más frecuentes</span><span class="sxs-lookup"><span data-stu-id="96a38-379">Frequently asked questions</span></span>
 
<span data-ttu-id="96a38-380">**¿Es necesario actualizar RemoteMailboxes en el origen local después del traslado?**</span><span class="sxs-lookup"><span data-stu-id="96a38-380">**Do we need to update RemoteMailboxes in source on-premises after the move?**</span></span>
 
<span data-ttu-id="96a38-381">Sí, debe actualizar el targetAddress (RemoteRoutingAddress/ExternalEmailAddress) de los usuarios locales de origen cuando el buzón de origen del espacio empresarial se mueva al inquilino de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-381">Yes, you should update the targetAddress (RemoteRoutingAddress/ExternalEmailAddress) of the source on-premises users when the source tenant mailbox moves to target tenant.</span></span>  <span data-ttu-id="96a38-382">Mientras que el enrutamiento de correo puede seguir las referencias entre varios usuarios de correo con diferentes targetAddresses, las búsquedas de disponibilidad para los usuarios de correo deben dirigirse a la ubicación del usuario del buzón.</span><span class="sxs-lookup"><span data-stu-id="96a38-382">While mail routing can follow the referrals across multiple mail users with different targetAddresses, Free/Busy lookups for mail users MUST target the location of the mailbox user.</span></span> <span data-ttu-id="96a38-383">Las búsquedas de disponibilidad no realizarán varias redirecciones.</span><span class="sxs-lookup"><span data-stu-id="96a38-383">Free/Busy lookups will not chase multiple redirects.</span></span> 
 
<span data-ttu-id="96a38-384">**¿El contenido de la carpeta de chat de Teams migra entre los inquilinos?**</span><span class="sxs-lookup"><span data-stu-id="96a38-384">**Does the Teams chat folder content migrate cross-tenant?**</span></span> 

<span data-ttu-id="96a38-385">No, el contenido de la carpeta de chats de Microsoft Teams no migra el inquilino cruzado.</span><span class="sxs-lookup"><span data-stu-id="96a38-385">No, the Teams chat folder content does not migrate cross-tenant.</span></span> 
 
<span data-ttu-id="96a38-386">**¿Cómo puedo ver solo movimientos que son movimientos entre inquilinos, no mis movimientos de incorporación y retirada?**</span><span class="sxs-lookup"><span data-stu-id="96a38-386">**How can I see just moves that are cross-tenant moves, not my onboarding and offboarding moves?**</span></span>

<span data-ttu-id="96a38-387">Use el `-flags` parámetro.</span><span class="sxs-lookup"><span data-stu-id="96a38-387">Use the `-flags` parameter.</span></span> <span data-ttu-id="96a38-388">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-388">Here is an example.</span></span>

```powershell
Get-MoveRequest -Flags "CrossTenant" 
```
 
<span data-ttu-id="96a38-389">**¿Puede proporcionar scripts de ejemplo para copiar atributos usados en las pruebas?**</span><span class="sxs-lookup"><span data-stu-id="96a38-389">**Can you provide example scripts for copying attributes used in testing?**</span></span>

> [!Note]
> <span data-ttu-id="96a38-390">MUESTRA: COMO ES, SIN GARANTÍA</span><span class="sxs-lookup"><span data-stu-id="96a38-390">SAMPLE – AS IS, NO WARRANTY</span></span><br/><span data-ttu-id="96a38-391">Esta secuencia de comandos presupone una conexión al buzón de origen (para obtener los valores de origen) y a los servicios de dominio de Active Directory locales de destino (para marcar el objeto ADUser).</span><span class="sxs-lookup"><span data-stu-id="96a38-391">This script assumes a connection to both source mailbox (to get source values) and the target on-premises Active Directory Domain Services (to stamp the ADUser object).</span></span> <span data-ttu-id="96a38-392">Si el origen tiene habilitada una recuperación por juicio o un elemento único, establézcalo en la cuenta de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-392">If source has litigation or single item recovery enabled, set this on the destination account.</span></span>  <span data-ttu-id="96a38-393">Esto aumentará el tamaño de la papelera de la cuenta de destino a 100 GB.</span><span class="sxs-lookup"><span data-stu-id="96a38-393">This will increase the dumpster size of destination account to 100 GB.</span></span>

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
<span data-ttu-id="96a38-394">**¿Cómo se obtiene acceso a Outlook el día 1 después de que se mueva el buzón de uso?**</span><span class="sxs-lookup"><span data-stu-id="96a38-394">**How do we access Outlook on Day 1 after the use mailbox is moved?**</span></span>

<span data-ttu-id="96a38-395">Dado que solo un inquilino puede poseer un dominio, la anterior SMTPAddress primaria no se asociará al usuario en el inquilino de destino cuando se complete el movimiento del buzón; solo los dominios asociados con el nuevo inquilino.</span><span class="sxs-lookup"><span data-stu-id="96a38-395">Since only one tenant can own a domain, the former primary SMTPAddress will not be associated to the user in the target tenant when the mailbox move completes; only those domains associated with the new tenant.</span></span> <span data-ttu-id="96a38-396">Outlook usa el nuevo UPN de los usuarios para autenticarse en el servicio y el perfil de Outlook espera encontrar la SMTPAddress principal heredada para que se corresponda con el buzón del sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-396">Outlook uses the users new UPN to authenticate to the service and the Outlook profile expects to find the legacy primary SMTPAddress to match the mailbox in the target system.</span></span> <span data-ttu-id="96a38-397">Como la dirección heredada no se encuentra en el sistema de destino, el perfil de Outlook no se conectará para encontrar el buzón recién movido.</span><span class="sxs-lookup"><span data-stu-id="96a38-397">Since the legacy address is not in the target System the outlook profile will not connect to find the newly moved mailbox.</span></span> 

<span data-ttu-id="96a38-398">Para esta implementación inicial, los usuarios tendrán que volver a crear su perfil con el nuevo UPN, la dirección SMTP principal y volver a sincronizar el contenido OST.</span><span class="sxs-lookup"><span data-stu-id="96a38-398">For this initial deployment, users will need to rebuild their profile with their new UPN, primary SMTP address and re-sync OST content.</span></span> 

> [!Note]
> <span data-ttu-id="96a38-399">Planee según los usuarios por lotes para la finalización.</span><span class="sxs-lookup"><span data-stu-id="96a38-399">Plan accordingly as you batch your users for completion.</span></span> <span data-ttu-id="96a38-400">Debe tener en cuenta la capacidad y el uso de red cuando se crean perfiles de cliente de Outlook y los archivos OST y OAB subsiguientes se descargan a los clientes.</span><span class="sxs-lookup"><span data-stu-id="96a38-400">You need to account for network utilization and capacity when Outlook client profiles are created and subsequent OST and OAB files are downloaded to clients.</span></span> 
 
<span data-ttu-id="96a38-401">**¿En qué roles RBAC de Exchange debo ser miembro para configurar o completar un movimiento entre inquilinos?**</span><span class="sxs-lookup"><span data-stu-id="96a38-401">**What Exchange RBAC roles do I need to be member of to set up or complete a cross-tenant move?**</span></span>
 
<span data-ttu-id="96a38-402">Hay una matriz de funciones basadas en la suposición de derechos delegados al ejecutar un movimiento de buzón.</span><span class="sxs-lookup"><span data-stu-id="96a38-402">There a matrix of roles based on assumption of delegated duties when executing a mailbox move.</span></span> <span data-ttu-id="96a38-403">Actualmente, se requieren dos roles:</span><span class="sxs-lookup"><span data-stu-id="96a38-403">Currently, two roles are required:</span></span>  

- <span data-ttu-id="96a38-404">La primera función es para una tarea de configuración de una sola vez que establece la autorización de mover el contenido hacia dentro o fuera del límite de la organización o del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="96a38-404">The first role is for a one-time setup task that establishes the authorization of moving content into or out of your tenant/organizational boundary.</span></span> <span data-ttu-id="96a38-405">Como la transferencia de datos del control organizacional es una preocupación fundamental para todas las empresas, decidimos con el rol asignado más alto del administrador de la organización (OrgAdmin).</span><span class="sxs-lookup"><span data-stu-id="96a38-405">As moving data out of your organizational control is a critical concern for all companies, we opted with the highest assigned role of Organization Administrator (OrgAdmin).</span></span> <span data-ttu-id="96a38-406">Este rol debe modificar o configurar un nuevo OrganizationRelationship que defina el-MailboxMoveCapability con la organización remota.</span><span class="sxs-lookup"><span data-stu-id="96a38-406">This role must alter or setup a new OrganizationRelationship that defines the -MailboxMoveCapability with the remote organization.</span></span> <span data-ttu-id="96a38-407">Solo el OrgAdmin puede modificar la configuración de MailboxMoveCapability, mientras que el administrador federado compartido puede administrar otros atributos de OrganizationRelationhip.</span><span class="sxs-lookup"><span data-stu-id="96a38-407">Only the OrgAdmin can alter the MailboxMoveCapability setting, while other attributes on the OrganizationRelationhip can be managed by the Federated Sharing administrator.</span></span> 
 
- <span data-ttu-id="96a38-408">El rol de ejecución de los comandos de movimiento reales se puede delegar en una función de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="96a38-408">The role of executing the actual move commands can be delegated to a lower-level function.</span></span> <span data-ttu-id="96a38-409">El rol de mover buzones de correo tiene asignada la capacidad de mover buzones dentro o fuera de la organización mediante el `-RemoteTenant` parámetro.</span><span class="sxs-lookup"><span data-stu-id="96a38-409">The role of Move Mailboxes is assigned the capability of moving mailboxes in or out of the organization by using the `-RemoteTenant` parameter.</span></span>  

<span data-ttu-id="96a38-410">**¿Cómo se destina la dirección SMTP seleccionada para targetAddress (TargetDeliveryDomain) en el buzón convertido (a la conversión de MailUser)?**</span><span class="sxs-lookup"><span data-stu-id="96a38-410">**How do we target which SMTP address is selected for targetAddress (TargetDeliveryDomain) on the converted mailbox (to MailUser conversion)?**</span></span>
 
<span data-ttu-id="96a38-411">Los movimientos de buzones de correo de Exchange con MRS diseñan el targetAddress en el buzón de origen inicial al convertirlo en un MailUser con una dirección de correo electrónico (proxyAddress) en el objeto de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-411">Exchange mailbox moves using MRS craft the targetAddress on the original source mailbox when converting to a MailUser by matching an email address (proxyAddress) on the target object.</span></span> <span data-ttu-id="96a38-412">El proceso toma el valor-TargetDeliveryDomain que se pasa al comando move y, a continuación, comprueba si el dominio tiene un proxy correspondiente en el lado de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-412">The process takes the -TargetDeliveryDomain value passed into the move command, then checks for a matching proxy for that domain on the target side.</span></span> <span data-ttu-id="96a38-413">Cuando encontramos una coincidencia, se usa la coincidencia de proxyAddress para establecer ExternalEmailAddress (targetAddress) en el objeto de buzón de correo convertido (ahora MailUser).</span><span class="sxs-lookup"><span data-stu-id="96a38-413">When we find a match, the matching proxyAddress is used to set the ExternalEmailAddress (targetAddress) on the converted mailbox (now MailUser) object.</span></span>
 
<span data-ttu-id="96a38-414">**¿Cómo se realiza la transición de permisos de buzón?**</span><span class="sxs-lookup"><span data-stu-id="96a38-414">**How do mailbox permissions transition?**</span></span>

<span data-ttu-id="96a38-415">Los permisos de buzón incluyen enviar en nombre de y acceso al buzón:</span><span class="sxs-lookup"><span data-stu-id="96a38-415">Mailbox permissions include Send on Behalf of and Mailbox Access:</span></span> 

- <span data-ttu-id="96a38-416">Enviar en nombre de (AD: publicDelegates) almacena el DN de los destinatarios con acceso al buzón de un usuario como delegado.</span><span class="sxs-lookup"><span data-stu-id="96a38-416">Send On Behalf Of (AD:publicDelegates) stores the DN of recipients with access to a user’s mailbox as a delegate.</span></span> <span data-ttu-id="96a38-417">Este valor se almacena en Active Directory y actualmente no se mueve como parte de la transición del buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="96a38-417">This value is stored in Active Directory and currently does not move as part of the mailbox transition.</span></span> <span data-ttu-id="96a38-418">Si el buzón de origen tiene un grupo publicDelegates, deberá volver a estampar publicDelegates en el buzón de destino una vez que la conversión de la unidad MEU a la del buzón de correo se complete en el entorno de destino con el `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` comando.</span><span class="sxs-lookup"><span data-stu-id="96a38-418">If the source mailbox has publicDelegates set, you will need to restamp the publicDelegates on the target Mailbox once the MEU to Mailbox conversion completes in the target environment using the `Set-Mailbox <principle> -GrantSendOnBehalfTo <delegate>` command.</span></span> 
 
- <span data-ttu-id="96a38-419">Los permisos de buzón que se almacenan en el buzón se moverán con el buzón cuando la entidad de destino y el delegado se muevan al sistema de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-419">Mailbox Permissions that are stored in the mailbox will move with the mailbox when both the principal and the delegate are moved to the target system.</span></span> <span data-ttu-id="96a38-420">Por ejemplo, al usuario TestUser_7 se le concede FullAccess al buzón TestUser_8 en el inquilino SourceCompany.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="96a38-420">For example, the user TestUser_7 is granted FullAccess to the mailbox TestUser_8 in the tenant SourceCompany.onmicrosoft.com.</span></span> <span data-ttu-id="96a38-421">Una vez que el movimiento del buzón se haya completado a TargetCompany.onmicrosoft.com, se configuran los mismos permisos en el directorio de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-421">After the mailbox move completes to TargetCompany.onmicrosoft.com, the same permissions are set up in the target directory.</span></span> <span data-ttu-id="96a38-422">A continuación, se muestran ejemplos que usan *Get-MailboxPermission* para TestUser_7 en los inquilinos de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-422">Examples using *Get-MailboxPermission* for TestUser_7 in both source and target tenants are shown below.</span></span> <span data-ttu-id="96a38-423">Los cmdlets de Exchange llevan el prefijo de origen y destino en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="96a38-423">Exchange cmdlets are prefixed with source and target accordingly.</span></span> 
 
<span data-ttu-id="96a38-424">A continuación, se muestra un ejemplo del resultado del permiso de buzón antes de un movimiento.</span><span class="sxs-lookup"><span data-stu-id="96a38-424">Here's an example of the output of the mailbox permission before a move.</span></span> 

```powershell
PS C:\DEMO Get-SourceMailboxPermission testuser_7 |ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       False
TestUser_8@SourceCompany.onmicrosoft.com         {FullAccess}                                                            False       False....
```
<span data-ttu-id="96a38-425">A continuación, se muestra un ejemplo del resultado del permiso de buzón de correo después del traslado.</span><span class="sxs-lookup"><span data-stu-id="96a38-425">Here's an example of the output of the mailbox permission after the move.</span></span> 

```powershell
C:\DEMO> Get-TargetMailboxPermission testuser_7 | ft -AutoSize User, AccessRights, IsInherited, Deny
User                                             AccessRights                                                            IsInherited Deny
----                                             ------------                                                            ----------- ----
NT AUTHORITY\SELF                                {FullAccess, ReadPermission}                                            False       FalseTestUser_8@TargetCompany.onmicrosoft.com         {FullAccess}                                                            False       False
```
 
> [!Note]
> <span data-ttu-id="96a38-426">NO se admiten los permisos entre buzones de correo y calendario entre inquilinos.</span><span class="sxs-lookup"><span data-stu-id="96a38-426">Cross-tenant mailbox and calendar permissions are NOT supported.</span></span> <span data-ttu-id="96a38-427">Debe organizar los principales y los delegados en lotes de movimiento consolidado para que estos buzones conectados se pasen al mismo tiempo del inquilino de origen.</span><span class="sxs-lookup"><span data-stu-id="96a38-427">You must organize principals and delegates into consolidated move batches so that these connected mailboxes are transitioned at the same time from the source tenant.</span></span> 
 
## <a name="known-issues"></a><span data-ttu-id="96a38-428">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="96a38-428">Known issues</span></span> 

-  <span data-ttu-id="96a38-429">**Problema: los archivos expandidos automáticamente no se pueden migrar.**</span><span class="sxs-lookup"><span data-stu-id="96a38-429">**Issue: Auto Expanded archives cannot be migrated.**</span></span> <span data-ttu-id="96a38-430">La característica de migración entre espacios empresariales admite la migración del buzón de correo principal y el buzón de archivo para un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="96a38-430">The cross-tenant migration feature support migrations of the primary mailbox and archive mailbox for a specific user.</span></span> <span data-ttu-id="96a38-431">Sin embargo, si el usuario del origen tiene un archivo de expansión automática, lo que significa más de un buzón de archivo, la característica no puede migrar los archivos adicionales.</span><span class="sxs-lookup"><span data-stu-id="96a38-431">If the user in the source however has an auto expanded archive – meaning more than one archive mailbox, the feature is unable to migrate the additional archives.</span></span>

- <span data-ttu-id="96a38-432">**Problema: MailUsers en la nube con el bloque de la MRS con SMTP no poseído se mueve el fondo.**</span><span class="sxs-lookup"><span data-stu-id="96a38-432">**Issue: Cloud MailUsers with non-owned smtp proxyAddress block MRS moves background.**</span></span> <span data-ttu-id="96a38-433">Al crear objetos de MailUser de inquilino de destino, debe asegurarse de que todas las direcciones de proxy SMTP pertenezcan a la organización de inquilinos de destino.</span><span class="sxs-lookup"><span data-stu-id="96a38-433">When creating target tenant MailUser objects, you must ensure that all SMTP proxy addresses belong to the target tenant organization.</span></span> <span data-ttu-id="96a38-434">Si existe un proxyAddress SMTP en el usuario de correo de destino que no pertenece al inquilino local, se evita la conversión de MailUser en Mailbox.</span><span class="sxs-lookup"><span data-stu-id="96a38-434">If an SMTP proxyAddress exists on the target mail user that does not belong to the local tenant, the conversion of the MailUser to Mailbox is prevented.</span></span> <span data-ttu-id="96a38-435">Esto se debe a la garantía de que los objetos de buzón solo pueden enviar correo desde dominios para los que el inquilino tenga autoridad (dominios reclamados por el inquilino):</span><span class="sxs-lookup"><span data-stu-id="96a38-435">This is due to our assurance that mailbox objects can only send mail from domains for which the tenant is authoritative (domains claimed by the tenant):</span></span> 
- 
   - <span data-ttu-id="96a38-436">Al sincronizar usuarios de local mediante Azure AD Connect, se aprovisionan objetos de MailUser locales con ExternalEmailAddress que señalan al inquilino de origen donde existe el buzón (laran@contoso \. onmicrosoft.com) y se marca PrimarySMTPAddress como un dominio que reside en el inquilino de destino (Lara. Newton@northwind \. com).</span><span class="sxs-lookup"><span data-stu-id="96a38-436">When you sync users from on-premises using Azure AD Connect, you provision on-premises MailUser objects with ExternalEmailAddress pointing to the source tenant where the mailbox exists (laran@contoso\.onmicrosoft.com) and you stamp the PrimarySMTPAddress as a domain that resides in the target tenant (Lara.Newton@northwind\.com).</span></span> <span data-ttu-id="96a38-437">Estos valores se sincronizan con el inquilino y un usuario de correo adecuado se aprovisionan y están listos para la migración.</span><span class="sxs-lookup"><span data-stu-id="96a38-437">These values sync down to the tenant and an appropriate mail user is provisioned and ready for migration.</span></span> <span data-ttu-id="96a38-438">Aquí se muestra un objeto de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-438">An example object is shown here.</span></span>
     ```powershell
     target/AADSynced user] PS C> Get-MailUser laran | select ExternalEmailAddress, EmailAddresses   
     ExternalEmailAddress               EmailAddresses 
     --------------------               -------------- 
     SMTP:laran@contoso.onmicrosoft.com {SMTP:lara.newton@northwind.com} 
     ```

   > [!Note]
   > <span data-ttu-id="96a38-439">La dirección de *contoso. en Microsoft \. com* *no* está presente en la matriz EmailAddresses/proxyAddresses.</span><span class="sxs-lookup"><span data-stu-id="96a38-439">The *contoso.onmicrosoft\.com* address is *not* present in the EmailAddresses/proxyAddresses array.</span></span>

- <span data-ttu-id="96a38-440">**Problema: los objetos de MailUser con direcciones SMTP principales "externas" se modifican o se restablecen a "Internal" dominios reclamados por la empresa**</span><span class="sxs-lookup"><span data-stu-id="96a38-440">**Issue: MailUser objects with “external” primary SMTP addresses are modified/reset to “internal” company claimed domains**</span></span>

   <span data-ttu-id="96a38-441">Los objetos MailUser son punteros a buzones no locales.</span><span class="sxs-lookup"><span data-stu-id="96a38-441">MailUser objects are pointers to non-local mailboxes.</span></span> <span data-ttu-id="96a38-442">En el caso de las migraciones de buzones de correo entre inquilinos, usamos objetos de MailUser para representar el buzón de origen (desde el punto de vista de la organización de destino) o el buzón de correo de destino (desde el punto de vista de la organización de origen).</span><span class="sxs-lookup"><span data-stu-id="96a38-442">In the case for cross-tenant mailbox migrations, we use MailUser objects to represent either the source mailbox (from the target organization’s perspective) or target mailbox (from the source organization’s perspective).</span></span> <span data-ttu-id="96a38-443">El MailUsers tendrá un ExternalEmailAddress (targetAddress) que apunta a la dirección SMTP del buzón real (ProxyTest \@ fabrikam \. onmicrosoft.com) y la dirección primarySMTP que representa la dirección SMTP que se muestra del usuario del buzón de correo en el directorio.</span><span class="sxs-lookup"><span data-stu-id="96a38-443">The MailUsers will have an ExternalEmailAddress (targetAddress) that points to the smtp address of the actual mailbox (ProxyTest\@fabrikam\.onmicrosoft.com) and primarySMTP address that represents the displayed SMTP address of the mailbox user in the directory.</span></span> <span data-ttu-id="96a38-444">Algunas organizaciones optan por Mostrar la dirección SMTP principal como una dirección SMTP externa, no como una dirección propiedad o comprobada por el inquilino local (como fabrikam.com en lugar de contoso.com).</span><span class="sxs-lookup"><span data-stu-id="96a38-444">Some organizations choose to display the primary SMTP address as an external SMTP address, not as an address owned/verified by the local tenant (such as fabrikam.com rather than as contoso.com).</span></span>  <span data-ttu-id="96a38-445">Sin embargo, una vez que un objeto de plan de servicio de Exchange se aplica a el MailUser a través de operaciones de licencia, la dirección SMTP principal se modifica para mostrarse como un dominio comprobado por la organización local (contoso.com).</span><span class="sxs-lookup"><span data-stu-id="96a38-445">However, once an Exchange service plan object is applied to the MailUser via licensing operations, the primary SMTP address is modified to show as a domain verified by the local organization (contoso.com).</span></span> <span data-ttu-id="96a38-446">Hay dos motivos posibles:</span><span class="sxs-lookup"><span data-stu-id="96a38-446">There are two potential reasons:</span></span>
   
   - <span data-ttu-id="96a38-447">Cuando se aplica un plan de servicio de Exchange a un MailUser, el proceso de Azure AD comienza a forzar la depuración del proxy para garantizar que la organización local no puede enviar correo, falsificado o correo desde otro espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="96a38-447">When any Exchange service plan is applied to a MailUser, the Azure AD process starts to enforce proxy scrubbing to ensure that the local organization is not able to send mail out, spoof, or mail from another tenant.</span></span> <span data-ttu-id="96a38-448">Cualquier dirección SMTP de un objeto Recipient con estos planes de servicio se quitará si la dirección no es comprobada por la organización local.</span><span class="sxs-lookup"><span data-stu-id="96a38-448">Any SMTP address on a recipient object with these service plans will be removed if the address is not verified by the local organization.</span></span> <span data-ttu-id="96a38-449">Como en el caso del ejemplo, el inquilino de \. contoso ONMICROSOFT.com no comprueba el dominio com de Fabikam \. , por lo que el borrado quita el \. dominio com de fabrikam.</span><span class="sxs-lookup"><span data-stu-id="96a38-449">As is the case in the example, the Fabikam\.com domain is NOT verified by the contoso\.onmicrosoft.com tenant, so the scrubbing removes that fabrikam\.com domain.</span></span> <span data-ttu-id="96a38-450">Si desea conservar este dominio externo en MailUser, antes de la migración o después de la migración, debe modificar los procesos de migración para eliminar las licencias una vez que se complete el movimiento o antes de la transferencia para asegurarse de que los usuarios tienen aplicada la personalización de marca externa esperada.</span><span class="sxs-lookup"><span data-stu-id="96a38-450">If you wish to persist these external domain on MailUser, either before the migration or after migration, you need to alter your migration processes to strip licenses after the move completes or before the move to ensure that the users have the expected external branding applied.</span></span> <span data-ttu-id="96a38-451">Deberá asegurarse de que el objeto Mailbox tiene una licencia adecuada para no afectar al servicio de correo.</span><span class="sxs-lookup"><span data-stu-id="96a38-451">You will need to ensure that the mailbox object is properly licensed to not affect mail service.</span></span><br/><br/><span data-ttu-id="96a38-452">Aquí se muestra un script de ejemplo para quitar los planes de servicio de un MailUser en el inquilino de Contoso \. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="96a38-452">An example script to remove the service plans on a MailUser in the Contoso\.onmicrosoft.com tenant is shown here.</span></span>

    ```powershell
    $LO = New-MsolLicenseOptions -AccountSkuId "contoso:ENTERPRISEPREMIUM" DisabledPlans 
    "LOCKBOX_ENTERPRISE","EXCHANGE_S_ENTERPRISE","INFORMATION_BARRIERS","MIP_S_CLP2","
    MIP_S_CLP1","MYANALYTICS_P2","EXCHANGE_ANALYTICS","EQUIVIO_ANALYTICS","THREAT_INTE
    LLIGENCE","PAM_ENTERPRISE","PREMIUM_ENCRYPTION" 
    Set-MsolUserLicense -UserPrincipalName proxytest@contoso.com LicenseOptions $lo 
    ```

       <span data-ttu-id="96a38-453">Aquí se muestran los resultados del conjunto de ServicePlans asignado.</span><span class="sxs-lookup"><span data-stu-id="96a38-453">Results in the set of ServicePlans assigned are shown here.</span></span>

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
 
       <span data-ttu-id="96a38-454">El PrimarySMTPAddress del usuario ya no está borrado.</span><span class="sxs-lookup"><span data-stu-id="96a38-454">The user’s PrimarySMTPAddress is no longer scrubbed.</span></span> <span data-ttu-id="96a38-455">El dominio fabrikam.com no es propiedad del inquilino contoso.onmicrosoft.com y se conservará como la dirección SMTP principal que se muestra en el directorio.</span><span class="sxs-lookup"><span data-stu-id="96a38-455">The fabrikam.com domain is not owned by the contoso.onmicrosoft.com tenant and will persist as the primary SMTP address shown in the directory.</span></span>

       <span data-ttu-id="96a38-456">Aquí le mostramos un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="96a38-456">Here is an example.</span></span>

    ```powershell
    get-recipient proxytest | ft -a userprin*, primary*, external*   
    PrimarySmtpAddress        ExternalDirectoryObjectId               ExternalEmailAddress 
    ------------------        -------------------------               -------------------- 
    proxytest@fabrikam.com    e2513482-1d5b-4066-936a-cbc7f8f6f817    SMTP:proxytest@fabrikam.com 
    ```

   - <span data-ttu-id="96a38-457">Cuando msExchRemoteRecipientType se establece en 8 (DeprovisionMailbox), para la MailUsers local que se migra al espacio empresarial de destino, la lógica de limpieza de proxy en Azure quitará los dominios no propietarios y restablecerá el primarySMTP en un dominio propietario.</span><span class="sxs-lookup"><span data-stu-id="96a38-457">When msExchRemoteRecipientType is set to 8 (DeprovisionMailbox), for on-premises MailUsers that are migrated to the target tenant, the proxy scrubbing logic in Azure will remove nonowned domains and reset the primarySMTP to an owned domain.</span></span> <span data-ttu-id="96a38-458">Al borrar msExchRemoteRecipientType en el MailUser local, la lógica de limpieza de proxy ya no se aplica.</span><span class="sxs-lookup"><span data-stu-id="96a38-458">By clearing msExchRemoteRecipientType in the on-premises MailUser, the proxy scrub logic no longer applies.</span></span> <br/><br><span data-ttu-id="96a38-459">A continuación se muestra el conjunto completo de los planes de servicio posibles que incluyen Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="96a38-459">Below is the full set of possible Service Plans that include Exchange Online.</span></span>

   | <span data-ttu-id="96a38-460">Nombre</span><span class="sxs-lookup"><span data-stu-id="96a38-460">Name</span></span>                                              |
   |---------------------------------------------------|
   | <span data-ttu-id="96a38-461">Almacenamiento avanzado de eDiscovery (500 GB)</span><span class="sxs-lookup"><span data-stu-id="96a38-461">Advanced eDiscovery Storage (500GB)</span></span>               |
   | <span data-ttu-id="96a38-462">Caja de seguridad del cliente</span><span class="sxs-lookup"><span data-stu-id="96a38-462">Customer Lockbox</span></span>                                  |
   | <span data-ttu-id="96a38-463">Prevención de pérdida de datos</span><span class="sxs-lookup"><span data-stu-id="96a38-463">Data Loss Prevention</span></span>                              |
   | <span data-ttu-id="96a38-464">Servicios de Exchange Enterprise CAL (EOP, DLP)</span><span class="sxs-lookup"><span data-stu-id="96a38-464">Exchange Enterprise CAL Services (EOP, DLP)</span></span>       |
   | <span data-ttu-id="96a38-465">Aspectos básicos de Exchange</span><span class="sxs-lookup"><span data-stu-id="96a38-465">Exchange Essentials</span></span>                               |
   | <span data-ttu-id="96a38-466">Base de Exchange</span><span class="sxs-lookup"><span data-stu-id="96a38-466">Exchange Foundation</span></span>                               |
   | <span data-ttu-id="96a38-467">Exchange Online (P1)</span><span class="sxs-lookup"><span data-stu-id="96a38-467">Exchange Online (P1)</span></span>                              |
   | <span data-ttu-id="96a38-468">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="96a38-468">Exchange Online (Plan 1)</span></span>                          |
   | <span data-ttu-id="96a38-469">Exchange Online (plan 2)</span><span class="sxs-lookup"><span data-stu-id="96a38-469">Exchange Online (Plan 2)</span></span>                          |
   | <span data-ttu-id="96a38-470">Archivado de Exchange Online para Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96a38-470">Exchange Online Archiving for Exchange Online</span></span>     |
   | <span data-ttu-id="96a38-471">Archivado de Exchange Online para Exchange Server</span><span class="sxs-lookup"><span data-stu-id="96a38-471">Exchange Online Archiving for Exchange Server</span></span>     |
   | <span data-ttu-id="96a38-472">Complemento de usuario inactivo de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96a38-472">Exchange Online Inactive User Add-on</span></span>              |
   | <span data-ttu-id="96a38-473">Quiosco de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96a38-473">Exchange Online Kiosk</span></span>                             |
   | <span data-ttu-id="96a38-474">Exchange Online Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="96a38-474">Exchange Online Multi-Geo</span></span>                         |
   | <span data-ttu-id="96a38-475">Plan 1 de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96a38-475">Exchange Online Plan 1</span></span>                            |
   | <span data-ttu-id="96a38-476">POP de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="96a38-476">Exchange Online POP</span></span>                               |
   | <span data-ttu-id="96a38-477">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="96a38-477">Exchange Online Protection</span></span>                        |
   | <span data-ttu-id="96a38-478">Barreras de la información</span><span class="sxs-lookup"><span data-stu-id="96a38-478">Information Barriers</span></span>                              |
   | <span data-ttu-id="96a38-479">Information Protection para Office 365 - Premium</span><span class="sxs-lookup"><span data-stu-id="96a38-479">Information Protection for Office 365 - Premium</span></span>   |
   | <span data-ttu-id="96a38-480">Information Protection para Office 365 - Estándar</span><span class="sxs-lookup"><span data-stu-id="96a38-480">Information Protection for Office 365 - Standard</span></span>  |
   | <span data-ttu-id="96a38-481">Información de myanalytics</span><span class="sxs-lookup"><span data-stu-id="96a38-481">Insights by MyAnalytics</span></span>                           |
   | <span data-ttu-id="96a38-482">Microsoft 365 Advanced Auditing</span><span class="sxs-lookup"><span data-stu-id="96a38-482">Microsoft 365 Advanced Auditing</span></span>                   |
   | <span data-ttu-id="96a38-483">Microsoft Bookings</span><span class="sxs-lookup"><span data-stu-id="96a38-483">Microsoft Bookings</span></span>                                |
   | <span data-ttu-id="96a38-484">Microsoft Business Center</span><span class="sxs-lookup"><span data-stu-id="96a38-484">Microsoft Business Center</span></span>                         |
   | <span data-ttu-id="96a38-485">Microsoft MyAnalytics (Completo)</span><span class="sxs-lookup"><span data-stu-id="96a38-485">Microsoft MyAnalytics (Full)</span></span>                      |
   | <span data-ttu-id="96a38-486">eDiscovery avanzado de Office 365</span><span class="sxs-lookup"><span data-stu-id="96a38-486">Office 365 Advanced eDiscovery</span></span>                    |
   | <span data-ttu-id="96a38-487">Protección contra amenazas avanzada de Office 365 (plan 1)</span><span class="sxs-lookup"><span data-stu-id="96a38-487">Office 365 Advanced Threat Protection (Plan 1)</span></span>    |
   | <span data-ttu-id="96a38-488">Protección contra amenazas avanzada de Office 365 (plan 2)</span><span class="sxs-lookup"><span data-stu-id="96a38-488">Office 365 Advanced Threat Protection (Plan 2)</span></span>    |
   | <span data-ttu-id="96a38-489">Office 365 Privileged Access Management</span><span class="sxs-lookup"><span data-stu-id="96a38-489">Office 365 Privileged Access Management</span></span>           |
   | <span data-ttu-id="96a38-490">Outlook Customer Manager</span><span class="sxs-lookup"><span data-stu-id="96a38-490">Outlook Customer Manager</span></span>                          |
   | <span data-ttu-id="96a38-491">Cifrado Premium en Office 365</span><span class="sxs-lookup"><span data-stu-id="96a38-491">Premium Encryption in Office 365</span></span>                  |
   || 
 
