---
title: Detectar y corregir las concesiones ilegales de consentimiento
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Obtenga información sobre cómo reconocer y corregir el ataque de concesión de consentimientos ilícitos en Microsoft Office 365.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7869419677ba1d5d6b480b7f0dea7f67880af0c7
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644685"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="741ae-103">Detectar y corregir las concesiones ilegales de consentimiento</span><span class="sxs-lookup"><span data-stu-id="741ae-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="741ae-104">**Se aplica a**</span><span class="sxs-lookup"><span data-stu-id="741ae-104">**Applies to**</span></span>
- [<span data-ttu-id="741ae-105">Plan 1 y Plan 2 de Microsoft Defender para Office 365</span><span class="sxs-lookup"><span data-stu-id="741ae-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="741ae-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="741ae-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="741ae-107">**Resumen**  Obtenga información sobre cómo reconocer y corregir el ataque de concesión de consentimientos ilícitos en Office 365.</span><span class="sxs-lookup"><span data-stu-id="741ae-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="741ae-108">¿Cuál es el ataque de concesión de consentimiento ilegal en Office 365?</span><span class="sxs-lookup"><span data-stu-id="741ae-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="741ae-109">En un ataque de concesión de consentimiento ilegal, el atacante crea una aplicación registrada en Azure que solicita acceso a datos como información de contacto, correo electrónico o documentos.</span><span class="sxs-lookup"><span data-stu-id="741ae-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="741ae-110">A continuación, el atacante hace un truco al usuario final para conceder a esa aplicación el consentimiento para acceder a sus datos a través de un ataque de suplantación de identidad (phishing) o mediante la inyección de código ilícito en un sitio web de confianza.</span><span class="sxs-lookup"><span data-stu-id="741ae-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="741ae-111">Una vez que se ha concedido el consentimiento a la aplicación ilícita, tiene acceso a los datos a nivel de cuenta sin necesidad de una cuenta organizativa.</span><span class="sxs-lookup"><span data-stu-id="741ae-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="741ae-112">Los pasos normales de corrección, como restablecer contraseñas para cuentas vulneradas o requerir autenticación multifactor (MFA) en las cuentas, no son efectivos contra este tipo de ataque, ya que son aplicaciones de terceros y son externas a la organización.</span><span class="sxs-lookup"><span data-stu-id="741ae-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="741ae-113">Estos ataques aprovechan un modelo de interacción que supone que la entidad que llama a la información es la automatización y no un ser humano.</span><span class="sxs-lookup"><span data-stu-id="741ae-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="741ae-114">¿Sospecha que está experimentando problemas con las concesiones de consentimiento ilegales de una aplicación en este momento?</span><span class="sxs-lookup"><span data-stu-id="741ae-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="741ae-115">Microsoft Cloud App Security (MCAS) tiene herramientas para detectar, investigar y corregir las aplicaciones de OAuth.</span><span class="sxs-lookup"><span data-stu-id="741ae-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="741ae-116">Este artículo de MCAS tiene un tutorial que describe cómo investigar aplicaciones [de OAuth arriesgadas.](/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="741ae-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="741ae-117">También puedes establecer directivas de [aplicación de OAuth](/cloud-app-security/app-permission-policy) para investigar los permisos solicitados por la aplicación, qué usuarios autorizan estas aplicaciones y aprobar o prohibir ampliamente estas solicitudes de permisos.</span><span class="sxs-lookup"><span data-stu-id="741ae-117">You can also set [OAuth app policies](/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="741ae-118">¿Cómo es un ataque de concesión de consentimiento ilegal en Office 365?</span><span class="sxs-lookup"><span data-stu-id="741ae-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="741ae-119">Debe buscar en el registro de **auditoría** para encontrar signos, también denominados Indicadores de compromiso (IOC) de este ataque.</span><span class="sxs-lookup"><span data-stu-id="741ae-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="741ae-120">Para las organizaciones con muchas aplicaciones registradas en Azure y una gran base de usuarios, el procedimiento recomendado es revisar las concesiones de consentimiento de las organizaciones cada semana.</span><span class="sxs-lookup"><span data-stu-id="741ae-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="741ae-121">Pasos para encontrar signos de este ataque</span><span class="sxs-lookup"><span data-stu-id="741ae-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="741ae-122">Abra el **Centro de seguridad & cumplimiento en** <https://protection.office.com> .</span><span class="sxs-lookup"><span data-stu-id="741ae-122">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="741ae-123">Vaya a **Buscar y** seleccione Búsqueda de registro **de auditoría.**</span><span class="sxs-lookup"><span data-stu-id="741ae-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="741ae-124">Busque (todas las actividades y todos los usuarios) y escriba la fecha de inicio y la fecha de finalización si es necesario y, a continuación, haga clic en **Buscar**.</span><span class="sxs-lookup"><span data-stu-id="741ae-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="741ae-125">Haga **clic en Filtrar resultados** y escriba Consentimiento para la aplicación en el **campo** Actividad.</span><span class="sxs-lookup"><span data-stu-id="741ae-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="741ae-126">Haga clic en el resultado para ver los detalles de la actividad.</span><span class="sxs-lookup"><span data-stu-id="741ae-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="741ae-127">Haga **clic en Más información** para obtener detalles de la actividad.</span><span class="sxs-lookup"><span data-stu-id="741ae-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="741ae-128">Compruebe si IsAdminContent está establecido en True.</span><span class="sxs-lookup"><span data-stu-id="741ae-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="741ae-129">La entrada del registro de auditoría correspondiente puede tardar entre 30 minutos y 24 horas en mostrarse en los resultados de búsqueda después de que se produzca un evento.</span><span class="sxs-lookup"><span data-stu-id="741ae-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="741ae-130">El tiempo durante el que se conserva y se puede buscar un registro de auditoría en el registro de auditoría depende de la suscripción de Microsoft 365 y, específicamente, del tipo de licencia asignada a un usuario específico.</span><span class="sxs-lookup"><span data-stu-id="741ae-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="741ae-131">Para obtener más información, vea [Registro de auditoría](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="741ae-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="741ae-132">Si este valor es true, indica que alguien con acceso de administrador global puede haber concedido un amplio acceso a los datos.</span><span class="sxs-lookup"><span data-stu-id="741ae-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="741ae-133">Si esto es inesperado, siga los pasos [necesarios para confirmar un ataque](#how-to-confirm-an-attack).</span><span class="sxs-lookup"><span data-stu-id="741ae-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="741ae-134">Cómo confirmar un ataque</span><span class="sxs-lookup"><span data-stu-id="741ae-134">How to confirm an attack</span></span>

<span data-ttu-id="741ae-135">Si tiene una o más instancias de los IIC enumerados anteriormente, debe realizar una investigación adicional para confirmar positivamente que se produjo el ataque.</span><span class="sxs-lookup"><span data-stu-id="741ae-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="741ae-136">Puedes usar cualquiera de estos tres métodos para confirmar el ataque:</span><span class="sxs-lookup"><span data-stu-id="741ae-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="741ae-137">Aplicaciones de inventario y sus permisos mediante el portal de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="741ae-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="741ae-138">Este método es exhaustivo, pero solo puede comprobar un usuario a la vez, lo que puede llevar mucho tiempo si tiene muchos usuarios que comprobar.</span><span class="sxs-lookup"><span data-stu-id="741ae-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="741ae-139">Aplicaciones de inventario y sus permisos con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="741ae-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="741ae-140">Este es el método más rápido y exhaustivo, con la menor cantidad de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="741ae-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="741ae-141">Haga que los usuarios comprueben individualmente sus aplicaciones y permisos e informen los resultados a los administradores para que los solucionen.</span><span class="sxs-lookup"><span data-stu-id="741ae-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="741ae-142">Inventario de aplicaciones con acceso en la organización</span><span class="sxs-lookup"><span data-stu-id="741ae-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="741ae-143">Puede hacerlo para los usuarios con el Portal de Azure Active Directory o PowerShell o hacer que los usuarios enumeren individualmente su acceso a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="741ae-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="741ae-144">Pasos para usar Azure Active Directory Portal</span><span class="sxs-lookup"><span data-stu-id="741ae-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="741ae-145">Puede buscar las aplicaciones a las que cualquier usuario individual ha concedido permisos mediante [el Portal de Azure Active Directory](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="741ae-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="741ae-146">Inicie sesión en Azure Portal con derechos administrativos.</span><span class="sxs-lookup"><span data-stu-id="741ae-146">Sign in to the Azure portal with administrative rights.</span></span>

2. <span data-ttu-id="741ae-147">Seleccione la hoja Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="741ae-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="741ae-148">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="741ae-148">Select **Users**.</span></span>

4. <span data-ttu-id="741ae-149">Seleccione el usuario que desea revisar.</span><span class="sxs-lookup"><span data-stu-id="741ae-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="741ae-150">Seleccione **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="741ae-150">Select **Applications**.</span></span>

<span data-ttu-id="741ae-151">Esto te mostrará las aplicaciones asignadas al usuario y los permisos que tienen las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="741ae-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="741ae-152">Pasos para que los usuarios enumeren su acceso a la aplicación</span><span class="sxs-lookup"><span data-stu-id="741ae-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="741ae-153">Haga que los usuarios vayan y https://myapps.microsoft.com revisen su propio acceso a la aplicación allí.</span><span class="sxs-lookup"><span data-stu-id="741ae-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="741ae-154">Deben poder ver todas las aplicaciones con acceso, ver detalles sobre ellas (incluido el ámbito de acceso) y poder revocar privilegios a aplicaciones sospechosas o ilícitas.</span><span class="sxs-lookup"><span data-stu-id="741ae-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="741ae-155">Pasos para hacerlo con PowerShell</span><span class="sxs-lookup"><span data-stu-id="741ae-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="741ae-156">La forma más sencilla de comprobar el ataque de concesión ilegal de consentimiento es ejecutar [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), que volcará todas las concesiones de consentimiento de OAuth y las aplicaciones de OAuth para todos los usuarios del arrendamiento en un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="741ae-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="741ae-157">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="741ae-157">Pre-requisites</span></span>

- <span data-ttu-id="741ae-158">La biblioteca de PowerShell de Azure AD instalada.</span><span class="sxs-lookup"><span data-stu-id="741ae-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="741ae-159">Derechos de administrador global en el inquilino en el que se ejecutará el script.</span><span class="sxs-lookup"><span data-stu-id="741ae-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="741ae-160">Administrador local en el equipo desde el que se ejecutarán los scripts.</span><span class="sxs-lookup"><span data-stu-id="741ae-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="741ae-161">Se ***recomienda encarecidamente*** que necesite autenticación multifactor en su cuenta administrativa.</span><span class="sxs-lookup"><span data-stu-id="741ae-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="741ae-162">Este script admite la autenticación MFA.</span><span class="sxs-lookup"><span data-stu-id="741ae-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="741ae-163">Inicie sesión en el equipo desde el que ejecutará el script con derechos de administrador local.</span><span class="sxs-lookup"><span data-stu-id="741ae-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="741ae-164">Descargue o copie el script [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) de GitHub en una carpeta desde la que ejecutará el script.</span><span class="sxs-lookup"><span data-stu-id="741ae-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="741ae-165">Esta será la misma carpeta en la que se escribirá el archivo "permissions.csv" de salida.</span><span class="sxs-lookup"><span data-stu-id="741ae-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="741ae-166">Abra una instancia de PowerShell como administrador y abra la carpeta en la que guardó el script.</span><span class="sxs-lookup"><span data-stu-id="741ae-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="741ae-167">Conéctese al directorio mediante el cmdlet [Connect-AzureAD.](/powershell/module/azuread/connect-azuread)</span><span class="sxs-lookup"><span data-stu-id="741ae-167">Connect to your directory using the [Connect-AzureAD](/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="741ae-168">Ejecute este comando de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="741ae-168">Run this PowerShell command:</span></span>

   ```powershell
   .\Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="741ae-169">El script genera un archivo denominado Permissions.csv.</span><span class="sxs-lookup"><span data-stu-id="741ae-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="741ae-170">Siga estos pasos para buscar concesiones de permisos de aplicación ilegales:</span><span class="sxs-lookup"><span data-stu-id="741ae-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="741ae-171">En la columna ConsentType (columna G) busque el valor "AllPrinciples".</span><span class="sxs-lookup"><span data-stu-id="741ae-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="741ae-172">El permiso AllPrincipals permite a la aplicación cliente obtener acceso al contenido de todos los usuarios del arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="741ae-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="741ae-173">Las aplicaciones nativas de Microsoft 365 necesitan este permiso para funcionar correctamente.</span><span class="sxs-lookup"><span data-stu-id="741ae-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="741ae-174">Todas las aplicaciones que no sean de Microsoft con este permiso deben revisarse detenidamente.</span><span class="sxs-lookup"><span data-stu-id="741ae-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="741ae-175">En la columna Permiso (columna F) revise los permisos que cada aplicación delegada tiene para el contenido.</span><span class="sxs-lookup"><span data-stu-id="741ae-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="741ae-176">Busque el permiso "Lectura" y "Escritura" o "\*. All" permiso y revisar estos cuidadosamente porque puede que no sean adecuados.</span><span class="sxs-lookup"><span data-stu-id="741ae-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="741ae-177">Revise los usuarios específicos que tienen los consentimientos concedidos.</span><span class="sxs-lookup"><span data-stu-id="741ae-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="741ae-178">Si los usuarios de alto perfil o de alto impacto tienen consentimientos inadecuados concedidos, debe investigar más a fondo.</span><span class="sxs-lookup"><span data-stu-id="741ae-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="741ae-179">En la columna ClientDisplayName (columna C) busque aplicaciones que parezcan sospechosas.</span><span class="sxs-lookup"><span data-stu-id="741ae-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="741ae-180">Las aplicaciones con nombres mal escritos, nombres super bland o nombres de sonido de hacker deben revisarse cuidadosamente.</span><span class="sxs-lookup"><span data-stu-id="741ae-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="741ae-181">Determinar el ámbito del ataque</span><span class="sxs-lookup"><span data-stu-id="741ae-181">Determine the scope of the attack</span></span>

<span data-ttu-id="741ae-182">Una vez que haya terminado de realizar el inventario del acceso a la aplicación, revise el registro de **auditoría** para determinar el ámbito completo de la infracción.</span><span class="sxs-lookup"><span data-stu-id="741ae-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="741ae-183">Busque en los usuarios afectados, los períodos de tiempo a los que la aplicación ilícita tuvo acceso a su organización y los permisos que tenía la aplicación.</span><span class="sxs-lookup"><span data-stu-id="741ae-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="741ae-184">Puede buscar el registro **de auditoría** en el Centro de seguridad y cumplimiento de [Microsoft 365.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="741ae-184">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="741ae-185">[La auditoría de buzones](../../compliance/enable-mailbox-auditing.md) de correo y la auditoría de actividad para administradores y usuarios deben estar [habilitadas](../../compliance/turn-audit-log-search-on-or-off.md) antes del ataque para que pueda obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="741ae-185">[Mailbox auditing](../../compliance/enable-mailbox-auditing.md) and [Activity auditing for admins and users](../../compliance/turn-audit-log-search-on-or-off.md) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="741ae-186">Cómo detener y corregir un ataque de concesión de consentimiento ilegal</span><span class="sxs-lookup"><span data-stu-id="741ae-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="741ae-187">Después de identificar una aplicación con permisos ilícitos, tiene varias formas de quitar ese acceso.</span><span class="sxs-lookup"><span data-stu-id="741ae-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="741ae-188">Puede revocar el permiso de la aplicación en el Portal de Azure Active Directory:</span><span class="sxs-lookup"><span data-stu-id="741ae-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="741ae-189">Vaya al usuario afectado en la **hoja Usuario de Azure Active Directory.**</span><span class="sxs-lookup"><span data-stu-id="741ae-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="741ae-190">Seleccione **Aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="741ae-190">Select **Applications**.</span></span>

  - <span data-ttu-id="741ae-191">Seleccione la aplicación ilícita.</span><span class="sxs-lookup"><span data-stu-id="741ae-191">Select the illicit application.</span></span>

  - <span data-ttu-id="741ae-192">Haga **clic en** Quitar en el desglose.</span><span class="sxs-lookup"><span data-stu-id="741ae-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="741ae-193">Puede revocar la concesión de consentimiento de OAuth con PowerShell siguiendo los pasos descritos en [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span><span class="sxs-lookup"><span data-stu-id="741ae-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="741ae-194">Puede revocar la asignación de roles de aplicación de servicio con PowerShell siguiendo los pasos descritos en [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span><span class="sxs-lookup"><span data-stu-id="741ae-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="741ae-195">También puedes deshabilitar el inicio de sesión para la cuenta afectada por completo, lo que a su vez deshabilitará el acceso de la aplicación a los datos de esa cuenta.</span><span class="sxs-lookup"><span data-stu-id="741ae-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="741ae-196">Esto no es ideal para la productividad del usuario final, por supuesto, pero si está trabajando para limitar el impacto rápidamente, puede ser una corrección viable a corto plazo.</span><span class="sxs-lookup"><span data-stu-id="741ae-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="741ae-197">Puede desactivar las aplicaciones integradas para su arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="741ae-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="741ae-198">Este es un paso drástico que deshabilita la posibilidad de que los usuarios finales concedan su consentimiento en todo el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="741ae-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="741ae-199">Esto evita que los usuarios concedan acceso a una aplicación malintencionada de forma involuntaria.</span><span class="sxs-lookup"><span data-stu-id="741ae-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="741ae-200">Esto no es muy recomendable, ya que afecta gravemente la capacidad de los usuarios para ser productivos con aplicaciones de terceros.</span><span class="sxs-lookup"><span data-stu-id="741ae-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="741ae-201">Para ello, siga los pasos descritos en Activar o desactivar aplicaciones [integradas.](../../admin/misc/user-consent.md)</span><span class="sxs-lookup"><span data-stu-id="741ae-201">You can do this by following the steps in [Turning Integrated Apps on or off](../../admin/misc/user-consent.md).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="741ae-202">Proteger Microsoft 365 como un profesional de la ciberseguridad</span><span class="sxs-lookup"><span data-stu-id="741ae-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="741ae-203">Su suscripción a Microsoft 365 incluye un potente conjunto de capacidades de seguridad que puede usar para proteger sus datos y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="741ae-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="741ae-204">Use el [Plan de seguridad de Microsoft 365: principales prioridades para los primeros 30 días, 90 días y en adelante](security-roadmap.md) para implementar las prácticas recomendadas de Microsoft para proteger su espacio empresarial de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="741ae-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="741ae-205">Tareas a realizar en los primeros 30 días.</span><span class="sxs-lookup"><span data-stu-id="741ae-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="741ae-206">Estas tienen un efecto inmediato y de bajo impacto para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="741ae-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="741ae-207">Tareas para llevar a cabo en 90 días.</span><span class="sxs-lookup"><span data-stu-id="741ae-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="741ae-208">Estas tareas necesitan un poco más de tiempo para planearlas e implementarlas, pero mejoran considerablemente el nivel de seguridad.</span><span class="sxs-lookup"><span data-stu-id="741ae-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="741ae-209">Más de 90 días.</span><span class="sxs-lookup"><span data-stu-id="741ae-209">Beyond 90 days.</span></span> <span data-ttu-id="741ae-210">Estas mejoras se crean en el trabajo de los 90 primeros días.</span><span class="sxs-lookup"><span data-stu-id="741ae-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="741ae-211">Vea también:</span><span class="sxs-lookup"><span data-stu-id="741ae-211">See also:</span></span>

- <span data-ttu-id="741ae-212">[Una aplicación inesperada en la lista de](/azure/active-directory/application-access-unexpected-application) aplicaciones guía a los administradores a través de varias acciones que pueden querer realizar después de darse cuenta de que hay aplicaciones inesperadas con acceso a datos.</span><span class="sxs-lookup"><span data-stu-id="741ae-212">[Unexpected application in my applications list](/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="741ae-213">[La integración de aplicaciones con Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) es una introducción de alto nivel de consentimiento y permisos.</span><span class="sxs-lookup"><span data-stu-id="741ae-213">[Integrating applications with Azure Active Directory](/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="741ae-214">[Los problemas de desarrollo de mi aplicación](/azure/active-directory/active-directory-application-dev-development-content-map) proporcionan vínculos a diversos artículos relacionados con el consentimiento.</span><span class="sxs-lookup"><span data-stu-id="741ae-214">[Problems developing my application](/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="741ae-215">Los objetos de entidad de seguridad de aplicación y servicio de [Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) proporcionan una introducción a los objetos de entidad de seguridad de aplicación y servicio que son esenciales para el modelo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="741ae-215">[Application and service principal objects in Azure Active Directory (Azure AD)](/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="741ae-216">[Administrar el acceso a las aplicaciones](/azure/active-directory/active-directory-managing-access-to-apps) es una introducción a las capacidades que los administradores tienen para administrar el acceso de los usuarios a las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="741ae-216">[Manage access to apps](/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
