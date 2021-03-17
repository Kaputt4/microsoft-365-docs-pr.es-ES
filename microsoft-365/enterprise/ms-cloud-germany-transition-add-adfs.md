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
ms.openlocfilehash: 852fc8f93158d7b6080f1add5a05e7367539f889
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838418"
---
# <a name="ad-fs-migration-steps-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="e7227-103">Pasos de migración de AD FS para la migración desde Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="e7227-103">AD FS migration steps for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="e7227-104">Este cambio de configuración debe aplicarse en cualquier momento antes de que se inicie la fase 2.</span><span class="sxs-lookup"><span data-stu-id="e7227-104">This configuration change needs to be applied any time before phase 2 is starting.</span></span>
<span data-ttu-id="e7227-105">Una vez completada la fase 2, el cambio de configuración funcionará y podrá iniciar sesión a través de puntos de conexión globales de Office 365, como `https://portal.office.com` .</span><span class="sxs-lookup"><span data-stu-id="e7227-105">Once phase 2 is completed the configuration change will work and you are able to sign in via Office 365 Global endpoints such as `https://portal.office.com`.</span></span> <span data-ttu-id="e7227-106">Si va a implementar el cambio de configuración antes de la fase  2, los extremos globales de Office 365 aún no funcionarán, pero la nueva confianza de usuario de confianza sigue formando parte de la configuración de servicios de federación de Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="e7227-106">If you are implementing the configuration change before phase 2, the Office 365 Global endpoints will _not yet work_ but the new relying party trust is still part of your Active Directory Federation Services (AD FS) configuration.</span></span>

<span data-ttu-id="e7227-107">Los clientes que usan la autenticación federada con Servicios de federación de Active Directory (AD FS) no deben realizar cambios en los URI del emisor que se usan para todas las autenticaciones con servicios de dominio de Active Directory (AD DS) locales durante la migración.</span><span class="sxs-lookup"><span data-stu-id="e7227-107">Customers who use federated authentication with Active Directory Federation Services (AD FS) shouldn't make changes to issuer URIs that are used for all authentications with on-premises Active Directory Domain Services (AD DS) during migration.</span></span> <span data-ttu-id="e7227-108">Cambiar los URI del emisor provocará errores de autenticación para los usuarios del dominio.</span><span class="sxs-lookup"><span data-stu-id="e7227-108">Changing issuer URIs will lead to authentication failures for users in the domain.</span></span> <span data-ttu-id="e7227-109">Los URI del emisor se pueden cambiar directamente en AD  FS o cuando un dominio se convierte de administrado a _federado_ y viceversa.</span><span class="sxs-lookup"><span data-stu-id="e7227-109">Issuer URIs can be changed directly in AD FS or when a domain is converted from _managed_ to _federated_ and vice-versa.</span></span> <span data-ttu-id="e7227-110">Se recomienda no agregar, quitar ni convertir un dominio federado en el inquilino de Azure AD que se ha migrado.</span><span class="sxs-lookup"><span data-stu-id="e7227-110">We recommend that you do not add, remove, or convert a federated domain in the Azure AD tenant that has been migrated.</span></span> <span data-ttu-id="e7227-111">Los URI del emisor se pueden cambiar una vez completada la migración.</span><span class="sxs-lookup"><span data-stu-id="e7227-111">Issuer URIs can be changed after the migration is fully complete.</span></span>

<span data-ttu-id="e7227-112">Para preparar la granja de AD FS para la migración desde Microsoft Cloud Deutschland, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="e7227-112">To prepare your AD FS farm for the migration from Microsoft Cloud Deutschland perform the following steps:</span></span>

1. <span data-ttu-id="e7227-113">Haga una copia de seguridad de la configuración de AD FS, incluida la confianza existente del usuario de confianza de Microsoft Cloud Deutschland, con [estos pasos](#backup).</span><span class="sxs-lookup"><span data-stu-id="e7227-113">Back up your AD FS settings, including the existing Microsoft Cloud Deutschland Relying Party trust, with [these steps](#backup).</span></span> <span data-ttu-id="e7227-114">Asigne un nombre a **la copia de seguridad MicrosoftCloudDeutschlandOnly** para indicar que solo tiene la información del inquilino de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="e7227-114">Name the backup **MicrosoftCloudDeutschlandOnly** to indicate it only has the Microsoft Cloud Deutschland tenant info.</span></span>

   > [!NOTE]
   > <span data-ttu-id="e7227-115">La copia de seguridad no solo contendrá la confianza de usuario de confianza de Office 365 existente para Microsoft Cloud Deutschland, sino también todas las demás confianzas de usuario de confianza presentes en la granja de servidores de AD FS correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e7227-115">The backup will not only contain the existing Office 365 Relying Party Trust for Microsoft Cloud Deutschland, but also all other Relying Party Trusts present on the respective AD FS farm.</span></span>

2. <span data-ttu-id="e7227-116">Probar la restauración con la copia de seguridad de MicrosoftCloudDeutschlandOnly, la granja de servidores de AD FS debe seguir funcionando como Microsoft Cloud Deutschland solamente.</span><span class="sxs-lookup"><span data-stu-id="e7227-116">Test the restore using the MicrosoftCloudDeutschlandOnly backup, The AD FS farm should continue to operate as Microsoft Cloud Deutschland only.</span></span>

<span data-ttu-id="e7227-117">Una vez completada y probada la copia de seguridad de AD FS, siga estos pasos para agregar una nueva confianza de usuario de confianza a la configuración de ADFS:</span><span class="sxs-lookup"><span data-stu-id="e7227-117">Once you have completed and tested the AD FS backup, perform the following steps to add a new relying party trust to your ADFS configuration:</span></span>

1. <span data-ttu-id="e7227-118">Abra la consola de administración de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e7227-118">Open the AD FS management console.</span></span>

2. <span data-ttu-id="e7227-119">En el panel izquierdo de la consola de administración de ADFS, vaya al menú **Confianzas de usuario de** confianza.</span><span class="sxs-lookup"><span data-stu-id="e7227-119">In the left pane of the ADFS management console navigate to the **Relying Party Trusts** menu.</span></span>

3. <span data-ttu-id="e7227-120">En el panel derecho, seleccione **Agregar confianza de usuario de confianza...**</span><span class="sxs-lookup"><span data-stu-id="e7227-120">In the right pane, select **Add Relying Party Trust...**</span></span>

4. <span data-ttu-id="e7227-121">Seleccione **Inicio en** la página **de** bienvenida del Asistente para agregar confianza de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="e7227-121">Select **Start** on the **Welcome** page of the Add Relying Party Trust wizard.</span></span>

5. <span data-ttu-id="e7227-122">En la **página Seleccionar origen de** datos, seleccione Importar datos sobre el usuario de confianza publicado en línea o en una red **local**.</span><span class="sxs-lookup"><span data-stu-id="e7227-122">On the **Select Data Source** page, select **Import data about the relying party published online or on a local network**.</span></span> <span data-ttu-id="e7227-123">El **valor de dirección de metadatos de** federación (nombre de host o dirección URL) debe establecerse en `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml` .</span><span class="sxs-lookup"><span data-stu-id="e7227-123">The **Federation metadata address (host name or URL)** value must be set to `https://nexus.microsoftonline-p.com/federationmetadata/2007-06/federationmetadata.xml`.</span></span> <span data-ttu-id="e7227-124">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7227-124">Click **Next**.</span></span>

6. <span data-ttu-id="e7227-125">En la **página Especificar nombre para** mostrar, escriba el nombre para mostrar como Microsoft Office **365 Identity Platform WorldWide**.</span><span class="sxs-lookup"><span data-stu-id="e7227-125">On the **Specify Display Name** page, type the display name such as **Microsoft Office 365 Identity Platform WorldWide**.</span></span> <span data-ttu-id="e7227-126">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7227-126">Click **Next**.</span></span>

7. <span data-ttu-id="e7227-127">Si estás usando ADFS en Windows Server 2012, en la página del asistente Configurar la autenticación **multifactor ahora?**, selecciona la opción adecuada según tus requisitos de autenticación.</span><span class="sxs-lookup"><span data-stu-id="e7227-127">If you are using ADFS in Windows Server 2012, on the wizard page **Configure Multi-factor Authentication Now?**, select the appropriate choice according to your authentication requirements.</span></span> <span data-ttu-id="e7227-128">Si sigue con el valor predeterminado, seleccione No quiero configurar la configuración de autenticación **multifactor** para esta confianza de usuario de confianza en este momento .</span><span class="sxs-lookup"><span data-stu-id="e7227-128">If you stick with the default, select **I don't want to configure multi-factor authentication settings for this relying party trust at this time**.</span></span> <span data-ttu-id="e7227-129">Puede cambiar esta configuración más adelante si lo desea.</span><span class="sxs-lookup"><span data-stu-id="e7227-129">You can change this setting later if you want to.</span></span>

8. <span data-ttu-id="e7227-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep Permit all users to access this **relying party** selected and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="e7227-130">For AD FS 2012: On the **Choose Issuance Authorization Rules**, keep **Permit all users to access this relying party** selected and click **Next**.</span></span>

8. <span data-ttu-id="e7227-131">Para AD FS 2016 y AD FS 2019: en la página Elegir directiva de control de acceso, seleccione la directiva de **control** de acceso adecuada y haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="e7227-131">For AD FS 2016 and AD FS 2019: On the **Choose Access Control Policy** page, select the appropriate access control policy and click **Next**.</span></span> <span data-ttu-id="e7227-132">Si no se elige ninguno, la confianza de usuario de confianza **no funcionará.**</span><span class="sxs-lookup"><span data-stu-id="e7227-132">If none is chosen, the Relying Party Trust will **NOT** work.</span></span>

9. <span data-ttu-id="e7227-133">Haga **clic en** Siguiente en la página Listo para agregar **confianza** para completar el asistente.</span><span class="sxs-lookup"><span data-stu-id="e7227-133">Click **Next** on the **Ready to Add Trust** page to complete the wizard.</span></span>

10. <span data-ttu-id="e7227-134">Haga **clic en** Cerrar en la **página** Finalizar.</span><span class="sxs-lookup"><span data-stu-id="e7227-134">Click **Close** on the **Finish** page.</span></span>

<span data-ttu-id="e7227-135">Al cerrar el asistente, se establece la confianza de usuario de confianza con el servicio global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7227-135">By closing the wizard, the Relying Party Trust with the Office 365 Global service is established.</span></span> <span data-ttu-id="e7227-136">Sin embargo, aún no se han configurado reglas de transformación de emisión.</span><span class="sxs-lookup"><span data-stu-id="e7227-136">However, no Issuance Transform rules are configured yet.</span></span>

<span data-ttu-id="e7227-137">Puedes usar la [Ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) para generar las reglas de transformación de emisión correctas.</span><span class="sxs-lookup"><span data-stu-id="e7227-137">You can use [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) to generate the correct Issuance Transform rules.</span></span> <span data-ttu-id="e7227-138">Las reglas de notificación generadas creadas con la Ayuda de AD FS se pueden agregar manualmente a través de la consola de administración de AD FS o con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7227-138">The generated claim rules created with AD FS Help can either be manually added through the AD FS management console or with PowerShell.</span></span> <span data-ttu-id="e7227-139">La Ayuda de AD FS generará los scripts de PowerShell necesarios que deben ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="e7227-139">AD FS Help will generate the necessary PowerShell scripts that need to be executed.</span></span>  

> [!NOTE]
> <span data-ttu-id="e7227-140">[La Ayuda de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) generará las reglas de transformación de emisión estándar que se envían con el producto.</span><span class="sxs-lookup"><span data-stu-id="e7227-140">[AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) will generate the standard issuance transform rules that ship with the product.</span></span> <span data-ttu-id="e7227-141">Sin embargo, si las reglas de transformación de emisión personalizadas se aplican en la confianza de usuario de confianza de usuario de confianza de Microsoft Cloud Deutschland (por ejemplo, URI de emisor personalizado, IDs inmutables no estándar o cualquier otra personalización), las reglas generadas por la ayuda de AD FS deben modificarse de forma que se ajusten a la lógica personalizada que se aplica actualmente para la confianza de usuario de confianza de Microsoft Cloud Deutschland.</span><span class="sxs-lookup"><span data-stu-id="e7227-141">However, if custom issuance transform rules are in place in the Microsoft Cloud Deutschland Relying Party Trust (for example, custom issuer URIs, non-standard immutable IDs, or any other customizations), the rules generated by AD FS help must be modified in a way that they fit the custom logic currently in place for the Microsoft Cloud Deutschland relying party trust.</span></span> <span data-ttu-id="e7227-142">Si estas personalizaciones no están integradas en las reglas generadas a través de la Ayuda  de [AD FS,](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator)la autenticación **en Microsoft Office 365 Identity Platform WorldWide** probablemente no funcionará para las identidades federadas.</span><span class="sxs-lookup"><span data-stu-id="e7227-142">If these customizations are not integrated in the rules generated via [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator), authentication to **Microsoft Office 365 Identity Platform WorldWide** will most likely **not** work for your federated identities.</span></span>

1. <span data-ttu-id="e7227-143">Ejecute **Generar notificaciones** en la Ayuda de AD [FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) y copie el script de PowerShell con la **opción Copiar** en la esquina superior derecha del script.</span><span class="sxs-lookup"><span data-stu-id="e7227-143">Run **Generate Claims** on [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) and copy the PowerShell script using the **Copy** option on the right upper corner of the script.</span></span>

2. <span data-ttu-id="e7227-144">Siga los pasos descritos en la Ayuda [de AD FS](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) sobre cómo ejecutar el script de PowerShell en la granja de servidores de AD FS para generar la confianza global de usuario de confianza.</span><span class="sxs-lookup"><span data-stu-id="e7227-144">Follow the steps outlined at [AD FS Help](https://adfshelp.microsoft.com/AadTrustClaims/ClaimsGenerator) on how to run the PowerShell script in your AD FS farm to generate the global Relying Party Trust.</span></span>

3. <span data-ttu-id="e7227-145">Compruebe que hay dos confianzas de usuario de confianza; uno para Microsoft Cloud Deutschland y otro para el servicio global de Office 365.</span><span class="sxs-lookup"><span data-stu-id="e7227-145">Verify that two Relying PartyTtrusts are present; one for Microsoft Cloud Deutschland and one for the Office 365 Global service.</span></span> <span data-ttu-id="e7227-146">El siguiente comando se puede aprovechar para la comprobación.</span><span class="sxs-lookup"><span data-stu-id="e7227-146">The following command can be leveraged for the check.</span></span> <span data-ttu-id="e7227-147">Debe devolver dos filas y los nombres e identificadores respectivos.</span><span class="sxs-lookup"><span data-stu-id="e7227-147">It should return two rows and the respective names and identifiers.</span></span>

   ```powershell
   Get-AdfsRelyingPartyTrust | Where-Object {$_.Identifier -like 'urn:federation:MicrosoftOnline*'} | Select-Object Name, Identifier
   ```

4. <span data-ttu-id="e7227-148">Haga una copia de seguridad de la configuración de migración completa, incluidas ambas confianzas de usuario de confianza, mediante [estos pasos](#backup).</span><span class="sxs-lookup"><span data-stu-id="e7227-148">Backup your full migration configuration, including both Relying Party trusts, using [these steps](#backup).</span></span> <span data-ttu-id="e7227-149">Guárdelo con el nombre **MicrosoftCloudDeutschlandAndWorldwide**.</span><span class="sxs-lookup"><span data-stu-id="e7227-149">Save it with the name **MicrosoftCloudDeutschlandAndWorldwide**.</span></span>

5. <span data-ttu-id="e7227-150">Mientras el inquilino está en migración, compruebe periódicamente que la autenticación de AD FS funciona con Microsoft Cloud Deutschland y la nube global de Microsoft en los distintos pasos de migración admitidos.</span><span class="sxs-lookup"><span data-stu-id="e7227-150">While your tenant is in migration, regularly verify that AD FS authentication is working with Microsoft Cloud Deutschland and Microsoft Global cloud in the various supported migration steps.</span></span>


## <a name="ad-fs-disaster-recovery-wid-database"></a><span data-ttu-id="e7227-151">Recuperación ante desastres de AD FS (base de datos WID)</span><span class="sxs-lookup"><span data-stu-id="e7227-151">AD FS Disaster Recovery (WID Database)</span></span>

<span data-ttu-id="e7227-152">Para restaurar la granja de servidores de AD FS en una herramienta de restauración rápida de [AD FS](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) ante desastres, debe aprovecharse.</span><span class="sxs-lookup"><span data-stu-id="e7227-152">To restore the AD FS farm in a disaster [AD FS Rapid Restore Tool](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/ad-fs-rapid-restore-tool) needs to be leveraged.</span></span> <span data-ttu-id="e7227-153">Por lo tanto, la herramienta debe descargarse y antes del inicio de la migración se debe crear una copia de seguridad y almacenarla de forma segura.</span><span class="sxs-lookup"><span data-stu-id="e7227-153">Therefore, the tool must be downloaded and before the start of the migration a backup must be created and safely stored.</span></span> <span data-ttu-id="e7227-154">En este ejemplo, se han ejecutado los siguientes comandos para realizar una copia de seguridad de una granja de servidores que se ejecuta en una base de datos WID:</span><span class="sxs-lookup"><span data-stu-id="e7227-154">In this example, the following commands have been run to back up a farm running on a WID database:</span></span>

<h2 id="backup"></h2>

### <a name="back-up-an-ad-fs-farm"></a><span data-ttu-id="e7227-155">Copia de seguridad de una granja de servidores de AD FS</span><span class="sxs-lookup"><span data-stu-id="e7227-155">Back up an AD FS Farm</span></span>

1. <span data-ttu-id="e7227-156">Instale la herramienta de restauración rápida de AD FS en el servidor principal de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e7227-156">Install the AD FS Rapid Restore Tool on the primary AD FS server.</span></span>

2. <span data-ttu-id="e7227-157">Importe el módulo en una sesión de PowerShell con este comando.</span><span class="sxs-lookup"><span data-stu-id="e7227-157">Import the module in a PowerShell session with this command.</span></span>

   ```powershell
   Import-Module "C:\Program Files (x86)\ADFS Rapid Recreation Tool\ADFSRapidRecreationTool.dll"
   ```

3. <span data-ttu-id="e7227-158">Ejecute el comando de copia de seguridad:</span><span class="sxs-lookup"><span data-stu-id="e7227-158">Run the backup command:</span></span>

   ```powershell
   Backup-ADFS -StorageType "FileSystem" -storagePath "<Storage path of backup>" -EncryptionPassword "<password>" -BackupComment "Restore Doku" -BackupDKM
   ```

4. <span data-ttu-id="e7227-159">Almacene la copia de seguridad de forma segura en un destino deseado.</span><span class="sxs-lookup"><span data-stu-id="e7227-159">Store the backup safely on a desired destination.</span></span>


### <a name="restore-an-ad-fs-farm"></a><span data-ttu-id="e7227-160">Restaurar una granja de servidores de AD FS</span><span class="sxs-lookup"><span data-stu-id="e7227-160">Restore an AD FS Farm</span></span>

<span data-ttu-id="e7227-161">Si la granja de servidores ha fallado por completo y no hay ninguna forma de volver a la granja de servidores antigua, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="e7227-161">If your farm failed completely and there is no way to return to the old farm, do the following.</span></span> 

1. <span data-ttu-id="e7227-162">Mueva la copia de seguridad generada y almacenada anteriormente al nuevo servidor principal de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e7227-162">Move the previously generated and stored backup to the new primary AD FS server.</span></span>

2. <span data-ttu-id="e7227-163">Ejecute el siguiente `Restore-ADFS` comando de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7227-163">Run the following `Restore-ADFS` PowerShell command.</span></span> <span data-ttu-id="e7227-164">Si es necesario, importe el certificado SSL de AD FS de antemano.</span><span class="sxs-lookup"><span data-stu-id="e7227-164">If necessary, import the AD FS SSL certificate beforehand.</span></span>

   ```powershell
   Restore-ADFS -StorageType "FileSystem" -StoragePath "<Path to Backup>" -DecryptionPassword "<password>" -GroupServiceAccountIdentifier "<gMSA>" -DBConnectionString "WID" -RestoreDKM
   ```

3. <span data-ttu-id="e7227-165">Apunte los nuevos registros DNS o el equilibrador de carga a los nuevos servidores de AD FS.</span><span class="sxs-lookup"><span data-stu-id="e7227-165">Point your new DNS records or load balancer to the new AD FS servers.</span></span>


## <a name="more-information"></a><span data-ttu-id="e7227-166">Más información</span><span class="sxs-lookup"><span data-stu-id="e7227-166">More information</span></span>

<span data-ttu-id="e7227-167">Introducción:</span><span class="sxs-lookup"><span data-stu-id="e7227-167">Getting started:</span></span>

- [<span data-ttu-id="e7227-168">Migración de Microsoft Cloud Deutschland a servicios de Office 365 en las nuevas regiones del centro de datos alemán</span><span class="sxs-lookup"><span data-stu-id="e7227-168">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="e7227-169">Asistencia para la migración a Microsoft Cloud Alemania</span><span class="sxs-lookup"><span data-stu-id="e7227-169">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="e7227-170">Cómo participar en la migración</span><span class="sxs-lookup"><span data-stu-id="e7227-170">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="e7227-171">Experiencia del cliente durante la migración</span><span class="sxs-lookup"><span data-stu-id="e7227-171">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="e7227-172">Pasar a través de la transición:</span><span class="sxs-lookup"><span data-stu-id="e7227-172">Moving through the transition:</span></span>

- [<span data-ttu-id="e7227-173">Impactos y acciones de las fases de migración</span><span class="sxs-lookup"><span data-stu-id="e7227-173">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="e7227-174">Pre-work adicional</span><span class="sxs-lookup"><span data-stu-id="e7227-174">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="e7227-175">Información adicional para [Azure AD,](ms-cloud-germany-transition-azure-ad.md) [dispositivos,](ms-cloud-germany-transition-add-devices.md) [experiencias](ms-cloud-germany-transition-add-experience.md)y [AD FS](ms-cloud-germany-transition-add-adfs.md).</span><span class="sxs-lookup"><span data-stu-id="e7227-175">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="e7227-176">Aplicaciones en la nube:</span><span class="sxs-lookup"><span data-stu-id="e7227-176">Cloud apps:</span></span>

- [<span data-ttu-id="e7227-177">Información del programa de migración de Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="e7227-177">Dynamics 365 migration program information</span></span>](https://aka.ms/d365ceoptin)
- [<span data-ttu-id="e7227-178">Información del programa de migración de Power BI</span><span class="sxs-lookup"><span data-stu-id="e7227-178">Power BI migration program information</span></span>](https://aka.ms/pbioptin)
- [<span data-ttu-id="e7227-179">Introducción a su actualización de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7227-179">Getting started with your Microsoft Teams upgrade</span></span>](https://aka.ms/SkypeToTeams-Home)
