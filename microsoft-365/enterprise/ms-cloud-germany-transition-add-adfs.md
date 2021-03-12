---
title: Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: 'Resumen: pasos de migración de Servicios de federación de Active Directory (AD FS) para la migración desde Microsoft Cloud Deutschland.'
ms.openlocfilehash: 030515227f3abdae82736807a01d1691d2d45552
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727472"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="e1dee-103">Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="e1dee-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="e1dee-104">Este cambio de configuración se puede aplicar en cualquier momento antes de que se inicie la fase 4.</span><span class="sxs-lookup"><span data-stu-id="e1dee-104">This configuration change can be applied at any time before phase 4 is starting.</span></span>
<span data-ttu-id="e1dee-105">Una vez completada la fase 2, el cambio de configuración funcionará y podrá iniciar sesión en puntos de conexión globales de Office 365, como `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="e1dee-105">Once phase 2 is completed the configuration change will work and you are able to sign in to Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="e1dee-106">Si va a implementar el cambio de configuración antes de la fase  2, los extremos globales de Office 365 aún no funcionarán, pero la nueva confianza de usuario de confianza sigue formando parte de la configuración de servicios de federación de Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="e1dee-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="e1dee-107">Para migrar la granja de AD FS desde Microsoft Cloud Deutschland:</span><span class="sxs-lookup"><span data-stu-id="e1dee-107">To migrate your AD FS farm from Microsoft Cloud Deutschland:</span></span>

1. <span data-ttu-id="e1dee-108">Haga una copia de seguridad de la configuración de AD FS, incluida la información de confianza de FF con [estos pasos](#backup).</span><span class="sxs-lookup"><span data-stu-id="e1dee-108">Back up your AD FS settings including FF trust info with [these steps](#backup).</span></span> <span data-ttu-id="e1dee-109">Asigne un nombre a **la copia de seguridad de Microsoft Cloud Deutschland_Only** para indicar que solo tiene la información del inquilino de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="e1dee-109">Name the backup **Microsoft Cloud Deutschland_Only** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>
2. <span data-ttu-id="e1dee-110">Pruebe la restauración con la copia de seguridad de Microsoft Cloud Deutschland_Only, la granja de servidores de AD FS debe seguir funcionando como Microsoft Cloud Deutschland solamente.</span><span class="sxs-lookup"><span data-stu-id="e1dee-110">Test the restore using the Microsoft Cloud Deutschland_Only backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="e1dee-111">Una vez completada y probada la copia de seguridad de AD FS, siga estos pasos para agregar una nueva confianza de usuario de confianza a la configuración de ADFS:</span><span class="sxs-lookup"><span data-stu-id="e1dee-111">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="e1dee-112">Abrir la consola de administración de AD FS</span><span class="sxs-lookup"><span data-stu-id="e1dee-112">Open the AD FS management console</span></span>
2. <span data-ttu-id="e1dee-113">En el panel izquierdo de la consola de administración de **ADFS, expanda ADFS**, luego **Relaciones** de confianza y, a continuación, **Confianzas de usuario de confianza**</span><span class="sxs-lookup"><span data-stu-id="e1dee-113">In the left pane of the ADFS management console, expand **ADFS**, then **Trust Relationships**, then **Relying Party Trusts**</span></span>
3. <span data-ttu-id="e1dee-114">En el panel derecho, seleccione **Agregar confianza de usuario de confianza...**</span><span class="sxs-lookup"><span data-stu-id="e1dee-114">In the right pane, select **Add Relying Party Trust...**</span></span>
4. <span data-ttu-id="e1dee-115">Seleccione **Siguiente** en la **página de** bienvenida del Asistente para agregar confianza de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="e1dee-115">Select **Next** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>
5. <span data-ttu-id="e1dee-116">En la **página Seleccionar origen de** datos, seleccione Importar datos sobre el usuario de confianza publicado en línea o en una red **local**.</span><span class="sxs-lookup"><span data-stu-id="e1dee-116">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="e1dee-117">El **valor de dirección de metadatos de** federación (nombre de host o dirección URL) debe establecerse en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="e1dee-117">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="e1dee-118">Luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1dee-118">Then, click **Next**.</span></span>
6. <span data-ttu-id="e1dee-119">En la **página Seleccionar origen de** datos, escriba el nombre para mostrar como Microsoft Office **365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="e1dee-119">On the **Select Data Source** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="e1dee-120">Luego, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e1dee-120">Then, click **Next**.</span></span>
7. <span data-ttu-id="e1dee-121">En la página del asistente **Configure Multi-factor Authentication Now?,** seleccione la opción adecuada según sus requisitos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="e1dee-121">On the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="e1dee-122">Si sigue con el valor predeterminado, seleccione No quiero configurar la configuración de autenticación **multifactor** para esta confianza de usuario de confianza en este momento .</span><span class="sxs-lookup"><span data-stu-id="e1dee-122">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="e1dee-123">Puede cambiar esta configuración más adelante si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e1dee-123">You can change this setting later if you want to.</span></span>
8. <span data-ttu-id="e1dee-124">En elegir reglas **de autorización de emisión,** mantenga permitir que todos los usuarios **accedan** a este usuario de confianza seleccionado haga clic en **Siguiente**</span><span class="sxs-lookup"><span data-stu-id="e1dee-124">On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected click **Next**</span></span>
9. <span data-ttu-id="e1dee-125">Haga **clic en** Siguiente en la página Listo para agregar **confianza** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e1dee-125">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>
10. <span data-ttu-id="e1dee-126">Haga **clic en** Cerrar en la **página** Finalizar.</span><span class="sxs-lookup"><span data-stu-id="e1dee-126">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="e1dee-127">Al cerrar el asistente, se establece la confianza de usuario de confianza con los servicios globales de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1dee-127">By closing the wizard, the Relying Party Trust with the Office 365 Global services is established.</span></span> <span data-ttu-id="e1dee-128">Sin embargo, aún no se han configurado reglas de transformación de emisión.</span><span class="sxs-lookup"><span data-stu-id="e1dee-128">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="e1dee-129">Puedes usar la [Ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para generar las reglas de transformación de emisión correctas.</span><span class="sxs-lookup"><span data-stu-id="e1dee-129">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="e1dee-130">Las reglas de notificación generadas creadas con la Ayuda de AD FS se pueden agregar manualmente a través de la consola de administración de AD FS o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1dee-130">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="e1dee-131">La Ayuda de AD FS generará los scripts de PowerShell necesarios que deben ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e1dee-131">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

<!--
    Question from ckinder
    is step #3 true?
    how to verify step 5? Need more information!
-->
1. <span data-ttu-id="e1dee-132">Ejecute **la ayuda Generar notificaciones** en AD FS y  copie el script de transformación de notificaciones de PowerShell con la opción Copiar en la esquina superior derecha del script.</span><span class="sxs-lookup"><span data-stu-id="e1dee-132">Run **Generate Claims** on AD FS help and copy the PowerShell claims transformation script using the **Copy** option on the right upper corner of the script.</span></span>
2. <span data-ttu-id="e1dee-133">Abra el editor de texto que prefiera y pegue el script de PowerShell en una nueva ventana de texto.</span><span class="sxs-lookup"><span data-stu-id="e1dee-133">Open your preferred text editor and paste the PowerShell script into a new text window.</span></span>
3. <span data-ttu-id="e1dee-134">Agregue las siguientes líneas de PowerShell al final del script pegada del paso 2</span><span class="sxs-lookup"><span data-stu-id="e1dee-134">Add the following PowerShell lines to the end of the pasted script from step 2</span></span>
    ```powershell
    $authzRules = "=>issue(Type = `"http://schemas.microsoft.com/authorization/claims/permit`", Value = `"true`"); "
    $RuleSet = New-AdfsClaimRuleSet -ClaimRule "<AD FS Help generated PSH>"
    Set-AdfsRelyingPartyTrust -TargetName “Microsoft Office 365 Identity Platform WorldWide” -IssuanceTransformRules $RuleSet.ClaimRulesString -IssuanceAuthorizationRules $authzRules
    ```
4. <span data-ttu-id="e1dee-135">A salvo y ejecute el script de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1dee-135">Safe and execute the PowerShell script.</span></span>
5. <span data-ttu-id="e1dee-136">Compruebe que hay dos confianzas de usuario de confianza presentes; uno para Microsoft Cloud Deutschland y otro para el servicio global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1dee-136">Verify that two Relying Party trusts are present; one for the Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span>
6. <span data-ttu-id="e1dee-137">Haga una copia de seguridad de sus confianzas [con estos pasos](#backup).</span><span class="sxs-lookup"><span data-stu-id="e1dee-137">Backup your trusts using [these steps](#backup).</span></span> <span data-ttu-id="e1dee-138">Guárdelo con el **nombre FFAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="e1dee-138">Save it with the name **FFAndWorldwide**.</span></span>
7. <span data-ttu-id="e1dee-139">Complete la migración back-end y compruebe que AD FS todavía funciona durante el proceso de migración.</span><span class="sxs-lookup"><span data-stu-id="e1dee-139">Complete your backend migration and verify that AD FS still works during the migration process.</span></span>

## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="e1dee-140">Recuperación ante desastres de AD FS (base de datos WID)</span><span class="sxs-lookup"><span data-stu-id="e1dee-140">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="e1dee-141">Para restaurar la granja de servidores de AD FS en una herramienta de restauración rápida de [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres, debe aprovecharse.</span><span class="sxs-lookup"><span data-stu-id="e1dee-141">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="e1dee-142">Por lo tanto, la herramienta debe descargarse y antes del inicio de la migración se debe crear una copia de seguridad y almacenarla de forma segura.</span><span class="sxs-lookup"><span data-stu-id="e1dee-142">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="e1dee-143">En este ejemplo (entornos TAT), se han ejecutado los siguientes comandos para realizar una copia de seguridad de la granja de servidores:</span><span class="sxs-lookup"><span data-stu-id="e1dee-143">In this example (TAT environments) the following commands have been run to back up the farm:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="e1dee-144">Copia de seguridad de una granja de servidores de AD FS</span><span class="sxs-lookup"><span data-stu-id="e1dee-144">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="e1dee-145">Instale la herramienta de restauración rápida de AD FS en el servidor principal de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e1dee-145">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>
2. <span data-ttu-id="e1dee-146">Importe el módulo en una sesión de PowerShell con este comando.</span><span class="sxs-lookup"><span data-stu-id="e1dee-146">Import the module in a PowerShell session with this command.</span></span>
    ```powershell
    Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
    ```
3. <span data-ttu-id="e1dee-147">Ejecute el comando de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="e1dee-147">Run the backup command:</span></span>
    ```powershell
    Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
    ```
4. <span data-ttu-id="e1dee-148">Almacene la copia de seguridad de forma segura en un destino deseado.</span><span class="sxs-lookup"><span data-stu-id="e1dee-148">Store the backup safely on a desired destination.</span></span>

### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="e1dee-149">Restaurar una granja de servidores de AD FS</span><span class="sxs-lookup"><span data-stu-id="e1dee-149">Restore an AD FS Farm</span></span>

<span data-ttu-id="e1dee-150">Si la granja de servidores ha fallado por completo y no hay ninguna forma de volver a la granja de servidores antigua, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e1dee-150">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="e1dee-151">Mueva la copia de seguridad generada y almacenada anteriormente al nuevo servidor principal de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e1dee-151">Move the previously generated and stored backup to the new primary AD FS server.</span></span>
2. <span data-ttu-id="e1dee-152">Ejecute el siguiente `Restore-ADFS` comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1dee-152">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="e1dee-153">Si es necesario, importe el certificado SSL de AD FS de antemano.</span><span class="sxs-lookup"><span data-stu-id="e1dee-153">If necessary, import the AD FS SSL certificate beforehand.</span></span>

    ```powershell
    Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
    ```

3. <span data-ttu-id="e1dee-154">Apunte los nuevos registros DNS o el equilibrador de carga a los nuevos servidores de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e1dee-154">Point your new DNS records or load balancer to the new AD FS servers.</span></span>

## <a name="more-information"></a><span data-ttu-id="e1dee-155">Más información</span><span class="sxs-lookup"><span data-stu-id="e1dee-155">More information</span></span>

<span data-ttu-id="e1dee-156">Introducción:</span><span class="sxs-lookup"><span data-stu-id="e1dee-156">Getting started:</span></span>

- [<span data-ttu-id="e1dee-157">Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán</span><span class="sxs-lookup"><span data-stu-id="e1dee-157">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="e1dee-158">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="e1dee-158">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="e1dee-159">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="e1dee-159">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="e1dee-160">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="e1dee-160">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="e1dee-161">Pasar a través de la transición:</span><span class="sxs-lookup"><span data-stu-id="e1dee-161">Moving through the transition:</span></span>

- [<span data-ttu-id="e1dee-162">Impactos y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="e1dee-162">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="e1dee-163">Pre-work adicional</span><span class="sxs-lookup"><span data-stu-id="e1dee-163">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="e1dee-164">Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="e1dee-164">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="e1dee-165">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="e1dee-165">Cloud apps:</span></span>

- [<span data-ttu-id="e1dee-166">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e1dee-166">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="e1dee-167">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="e1dee-167">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="e1dee-168">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e1dee-168">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
