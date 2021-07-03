---
title: Cómo configurar Skype Empresarial local para usar la autenticación moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar Skype Empresarial local para usar la autenticación moderna híbrida (HMA), lo que le ofrece una autenticación y autorización de usuario más seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9695815d0a085931b10f7f64b9fca2e997af9077
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286062"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="86d24-103">Cómo configurar Skype Empresarial local para usar la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="86d24-103">How to configure Skype for Business on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="86d24-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="86d24-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="86d24-105">La autenticación moderna, es un método de administración de identidades que ofrece una autenticación y autorización de usuario más segura Skype Empresarial s, está disponible para servidores locales y Exchange servidores locales y híbridos de dominio dividido Skype Empresarial servidores.</span><span class="sxs-lookup"><span data-stu-id="86d24-105">Modern Authentication, is a method of identity management that offers more secure user authentication and authorization, is available for Skype for Business server on-premises and Exchange server on-premises, and split-domain Skype for Business hybrids.</span></span>

 <span data-ttu-id="86d24-106">**Importante** ¿Le gustaría saber más acerca de la autenticación moderna (MA) y por qué podría preferir usarla en su empresa u organización?</span><span class="sxs-lookup"><span data-stu-id="86d24-106">**Important** Would you like to know more about Modern Authentication (MA) and why you might prefer to use it in your company or organization?</span></span> <span data-ttu-id="86d24-107">Consulte [este documento para](hybrid-modern-auth-overview.md) obtener información general.</span><span class="sxs-lookup"><span data-stu-id="86d24-107">Check [this document](hybrid-modern-auth-overview.md) for an overview.</span></span> <span data-ttu-id="86d24-108">Si necesita saber qué tipo Skype Empresarial topologías son compatibles con MA, esto se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="86d24-108">If you need to know what Skype for Business topologies are supported with MA, that's documented here!</span></span>

 <span data-ttu-id="86d24-109">**Antes de empezar,** uso estos términos:</span><span class="sxs-lookup"><span data-stu-id="86d24-109">**Before we begin**, I use these terms:</span></span>

- <span data-ttu-id="86d24-110">Autenticación moderna (MA)</span><span class="sxs-lookup"><span data-stu-id="86d24-110">Modern Authentication (MA)</span></span>

- <span data-ttu-id="86d24-111">Autenticación moderna híbrida (HMA)</span><span class="sxs-lookup"><span data-stu-id="86d24-111">Hybrid Modern Authentication (HMA)</span></span>

- <span data-ttu-id="86d24-112">Exchange local (EXCH)</span><span class="sxs-lookup"><span data-stu-id="86d24-112">Exchange on-premises (EXCH)</span></span>

- <span data-ttu-id="86d24-113">Exchange Online (EXO)</span><span class="sxs-lookup"><span data-stu-id="86d24-113">Exchange Online (EXO)</span></span>

- <span data-ttu-id="86d24-114">Skype Empresarial local (SFB)</span><span class="sxs-lookup"><span data-stu-id="86d24-114">Skype for Business on-premises (SFB)</span></span>

- <span data-ttu-id="86d24-115">Skype Empresarial En línea (SFBO)</span><span class="sxs-lookup"><span data-stu-id="86d24-115">Skype for Business Online (SFBO)</span></span>

<span data-ttu-id="86d24-116">Además, si un gráfico de este artículo tiene un objeto atenuado o atenuado, significa que el elemento que se muestra en gris no se incluye en la configuración específica de MA. </span><span class="sxs-lookup"><span data-stu-id="86d24-116">Also, if a graphic in this article has an object that's grayed-out or dimmed that means the element shown in gray **isn't** included in MA-specific configuration.</span></span>

## <a name="read-the-summary"></a><span data-ttu-id="86d24-117">Leer el resumen</span><span class="sxs-lookup"><span data-stu-id="86d24-117">Read the summary</span></span>

<span data-ttu-id="86d24-118">Este resumen desglosa el proceso en pasos que, de lo contrario, podrían perderse durante la ejecución y es bueno para que una lista de comprobación general realice un seguimiento de dónde se encuentra en el proceso.</span><span class="sxs-lookup"><span data-stu-id="86d24-118">This summary breaks down the process into steps that might otherwise get lost during the execution, and is good for an overall checklist to keep track of where you are in the process.</span></span>

1. <span data-ttu-id="86d24-119">En primer lugar, asegúrese de cumplir todos los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="86d24-119">First, make sure you meet all the prerequisites.</span></span>

1. <span data-ttu-id="86d24-120">Dado que **muchos requisitos previos** son comunes para Skype Empresarial y Exchange, vea el artículo de introducción para la lista de comprobación [previa a la consulta](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d24-120">Since many **prerequisites** are common for both Skype for Business and Exchange, [see the overview article for your pre-req checklist](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="86d24-121">Haga esto  *antes*  de comenzar cualquiera de los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="86d24-121">Do this  *before*  you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="86d24-122">Recopila la información específica de HMA que necesitarás en un archivo o OneNote.</span><span class="sxs-lookup"><span data-stu-id="86d24-122">Collect the HMA-specific info you'll need in a file, or OneNote.</span></span>

1. <span data-ttu-id="86d24-123">Activar la autenticación moderna para EXO (si aún no está activada).</span><span class="sxs-lookup"><span data-stu-id="86d24-123">Turn ON Modern Authentication for EXO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="86d24-124">Activar la autenticación moderna para SFBO (si aún no está activada).</span><span class="sxs-lookup"><span data-stu-id="86d24-124">Turn ON Modern Authentication for SFBO (if it isn't already turned on).</span></span>

1. <span data-ttu-id="86d24-125">Active la autenticación moderna híbrida para Exchange local.</span><span class="sxs-lookup"><span data-stu-id="86d24-125">Turn ON Hybrid Modern Authentication for Exchange on-premises.</span></span>

1. <span data-ttu-id="86d24-126">Active la autenticación moderna híbrida para Skype Empresarial local.</span><span class="sxs-lookup"><span data-stu-id="86d24-126">Turn ON Hybrid Modern Authentication for Skype for Business on-premises.</span></span>

<span data-ttu-id="86d24-127">Estos pasos activan MA para SFB, SFBO, EXCH y EXO; es decir, todos los productos que pueden participar en una configuración de HMA de SFB y SFBO (incluidas las dependencias de EXCH/EXO).</span><span class="sxs-lookup"><span data-stu-id="86d24-127">These steps turn on MA for SFB, SFBO, EXCH, and EXO - that is, all the products that can participate in an HMA configuration of SFB and SFBO (including dependencies on EXCH/EXO).</span></span> <span data-ttu-id="86d24-128">En otras palabras, si los usuarios están internados en o tienen buzones creados en cualquier parte del híbrido (EXO + SFBO, EXO + SFB, EXCH + SFBO, o EXCH + SFB), el producto terminado tendrá este aspecto:</span><span class="sxs-lookup"><span data-stu-id="86d24-128">In other words, if your users are homed in/have mailboxes created in any part of the Hybrid (EXO + SFBO, EXO + SFB, EXCH + SFBO, or EXCH + SFB), your finished product will look like this:</span></span>

![Una topología mixta de 6 Skype HMA para empresas tiene MA en las cuatro ubicaciones posibles.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)

<span data-ttu-id="86d24-130">Como puede ver, hay cuatro lugares diferentes para activar MA.</span><span class="sxs-lookup"><span data-stu-id="86d24-130">As you can see there are four different places to turn on MA!</span></span> <span data-ttu-id="86d24-131">Para obtener la mejor experiencia de usuario, se recomienda activar MA en las cuatro ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="86d24-131">For the best user experience, we recommend you turn on MA in all four of these locations.</span></span> <span data-ttu-id="86d24-132">Si no puede activar MA en todas estas ubicaciones, ajuste los pasos para que active MA solo en las ubicaciones necesarias para su entorno.</span><span class="sxs-lookup"><span data-stu-id="86d24-132">If you can't turn MA on in all these locations, adjust the steps so that you turn on MA only in the locations that are necessary for your environment.</span></span>

<span data-ttu-id="86d24-133">Consulte el [tema Compatibilidad para obtener Skype Empresarial con MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) para obtener topologías compatibles.</span><span class="sxs-lookup"><span data-stu-id="86d24-133">See the [Supportability topic for Skype for Business with MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) for supported topologies.</span></span>

 <span data-ttu-id="86d24-134">**Importante** Compruebe que ha cumplido todos los requisitos previos antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="86d24-134">**Important** Double-check that you've met all the prerequisites before you begin.</span></span> <span data-ttu-id="86d24-135">Encontrará esa información en Introducción a la autenticación moderna híbrida [y requisitos previos.](hybrid-modern-auth-overview.md)</span><span class="sxs-lookup"><span data-stu-id="86d24-135">You'll find that information in [Hybrid modern authentication overview and prerequisites](hybrid-modern-auth-overview.md).</span></span>

## <a name="collect-all-hma-specific-info-youll-need"></a><span data-ttu-id="86d24-136">Recopilar toda la información específica de HMA que necesitarás</span><span class="sxs-lookup"><span data-stu-id="86d24-136">Collect all HMA-specific info you'll need</span></span>

<span data-ttu-id="86d24-137">Después de comprobar que cumples los [requisitos previos](hybrid-modern-auth-overview.md) para usar la autenticación moderna (consulta la nota anterior), debes crear un archivo para contener la información que necesitarás para configurar HMA en los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="86d24-137">After you've double-checked that you meet the [prerequisites](hybrid-modern-auth-overview.md) to use Modern Authentication (see the note above), you should create a file to hold the info you'll need for configuring HMA in the steps ahead.</span></span> <span data-ttu-id="86d24-138">Ejemplos usados en este artículo:</span><span class="sxs-lookup"><span data-stu-id="86d24-138">Examples used in this article:</span></span>

- <span data-ttu-id="86d24-139">**Dominio SIP/SMTP**</span><span class="sxs-lookup"><span data-stu-id="86d24-139">**SIP/SMTP domain**</span></span>

  - <span data-ttu-id="86d24-140">Ex.</span><span class="sxs-lookup"><span data-stu-id="86d24-140">Ex.</span></span> <span data-ttu-id="86d24-141">contoso.com (se federa con Office 365)</span><span class="sxs-lookup"><span data-stu-id="86d24-141">contoso.com (is federated with Office 365)</span></span>

- <span data-ttu-id="86d24-142">**Identificación del inquilino**</span><span class="sxs-lookup"><span data-stu-id="86d24-142">**Tenant ID**</span></span>

  - <span data-ttu-id="86d24-143">GUID que representa el Office 365 inquilino (en el inicio de sesión de contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="86d24-143">The GUID that represents your Office 365 tenant (at the login of contoso.onmicrosoft.com).</span></span>

- <span data-ttu-id="86d24-144">**DIRECCIONES URL del servicio web DE SFB 2015 CU5**</span><span class="sxs-lookup"><span data-stu-id="86d24-144">**SFB 2015 CU5 Web Service URLs**</span></span>

<span data-ttu-id="86d24-145">necesitará direcciones URL de servicio web internos y externos para todos los grupos de servidores de SfB 2015 implementados.</span><span class="sxs-lookup"><span data-stu-id="86d24-145">you'll need internal and external web service URLs for all SfB 2015 pools deployed.</span></span> <span data-ttu-id="86d24-146">Para obtener estos, ejecute lo siguiente desde Skype Empresarial Shell de administración:</span><span class="sxs-lookup"><span data-stu-id="86d24-146">To obtain these, run the following from Skype for Business Management Shell:</span></span>

```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- <span data-ttu-id="86d24-147">Ex.</span><span class="sxs-lookup"><span data-stu-id="86d24-147">Ex.</span></span> <span data-ttu-id="86d24-148">Interno: https://lyncwebint01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="86d24-148">Internal: https://lyncwebint01.contoso.com</span></span>

- <span data-ttu-id="86d24-149">Ex.</span><span class="sxs-lookup"><span data-stu-id="86d24-149">Ex.</span></span> <span data-ttu-id="86d24-150">Externo: https://lyncwebext01.contoso.com</span><span class="sxs-lookup"><span data-stu-id="86d24-150">External: https://lyncwebext01.contoso.com</span></span>

<span data-ttu-id="86d24-151">Si usa un servidor Standard Edition, la dirección URL interna estará en blanco.</span><span class="sxs-lookup"><span data-stu-id="86d24-151">If you're using a Standard Edition server, the internal URL will be blank.</span></span> <span data-ttu-id="86d24-152">En este caso, use el fqdn del grupo para la dirección URL interna.</span><span class="sxs-lookup"><span data-stu-id="86d24-152">In this case, use the pool fqdn for the internal URL.</span></span>

## <a name="turn-on-modern-authentication-for-exo"></a><span data-ttu-id="86d24-153">Activar la autenticación moderna para EXO</span><span class="sxs-lookup"><span data-stu-id="86d24-153">Turn on Modern Authentication for EXO</span></span>

<span data-ttu-id="86d24-154">Siga las instrucciones aquí: Exchange Online: Cómo habilitar el espacio empresarial [para la autenticación moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span><span class="sxs-lookup"><span data-stu-id="86d24-154">Follow the instructions here: [Exchange Online: How to enable your tenant for modern authentication.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)</span></span>

## <a name="turn-on-modern-authentication-for-sfbo"></a><span data-ttu-id="86d24-155">Activar la autenticación moderna para SFBO</span><span class="sxs-lookup"><span data-stu-id="86d24-155">Turn on Modern Authentication for SFBO</span></span>

<span data-ttu-id="86d24-156">Siga las instrucciones aquí: [Skype Empresarial Online: Habilitar el espacio empresarial para la autenticación moderna](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span><span class="sxs-lookup"><span data-stu-id="86d24-156">Follow the instructions here: [Skype for Business Online: Enable your tenant for modern authentication](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).</span></span>

## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a><span data-ttu-id="86d24-157">Activar la autenticación moderna híbrida para Exchange local</span><span class="sxs-lookup"><span data-stu-id="86d24-157">Turn on Hybrid Modern Authentication for Exchange on-premises</span></span>

<span data-ttu-id="86d24-158">Siga las instrucciones aquí: [Cómo configurar Exchange Server local para usar la autenticación moderna híbrida.](configure-exchange-server-for-hybrid-modern-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="86d24-158">Follow the instructions here: [How to configure Exchange Server on-premises to use Hybrid Modern Authentication](configure-exchange-server-for-hybrid-modern-authentication.md).</span></span>

## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a><span data-ttu-id="86d24-159">Activar la autenticación moderna híbrida para Skype Empresarial local</span><span class="sxs-lookup"><span data-stu-id="86d24-159">Turn on Hybrid Modern Authentication for Skype for Business on-premises</span></span>

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a><span data-ttu-id="86d24-160">Agregar direcciones URL de servicio web local como SPN en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="86d24-160">Add on-premises web service URLs as SPNs in Azure Active Directory</span></span>

<span data-ttu-id="86d24-161">Ahora tendrá que ejecutar comandos para agregar las direcciones URL (recopiladas anteriormente) como entidades de servicio en SFBO.</span><span class="sxs-lookup"><span data-stu-id="86d24-161">Now you'll need to run commands to add the URLs (collected earlier) as Service Principals in SFBO.</span></span>

 <span data-ttu-id="86d24-162">**Nota** Los nombres de entidad de seguridad de servicio (SPN) identifican los servicios web y los asocian con una entidad de seguridad (como un nombre de cuenta o un grupo) para que el servicio pueda actuar en nombre de un usuario autorizado.</span><span class="sxs-lookup"><span data-stu-id="86d24-162">**Note** Service principal names (SPNs) identify web services and associate them with a security principal (such as an account name or group) so that the service can act on the behalf of an authorized user.</span></span> <span data-ttu-id="86d24-163">Los clientes que se autentican en un servidor usan la información contenida en spns.</span><span class="sxs-lookup"><span data-stu-id="86d24-163">Clients authenticating to a server make use of information that's contained in SPNs.</span></span>

1. <span data-ttu-id="86d24-164">En primer lugar, conéctese a Azure Active Directory (Azure AD) con [estas instrucciones](/powershell/azure/active-directory/overview).</span><span class="sxs-lookup"><span data-stu-id="86d24-164">First, connect to Azure Active Directory (Azure AD) with [these instructions](/powershell/azure/active-directory/overview).</span></span>

2. <span data-ttu-id="86d24-165">Ejecute este comando localmente para obtener una lista de direcciones URL de servicio web SFB.</span><span class="sxs-lookup"><span data-stu-id="86d24-165">Run this command, on-premises, to get a list of SFB web service URLs.</span></span>

   <span data-ttu-id="86d24-166">Tenga en cuenta que AppPrincipalId comienza por `00000004` .</span><span class="sxs-lookup"><span data-stu-id="86d24-166">Note that the AppPrincipalId begins with `00000004`.</span></span> <span data-ttu-id="86d24-167">Esto corresponde a Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="86d24-167">This corresponds to Skype for Business Online.</span></span>

   <span data-ttu-id="86d24-168">Tome nota de (y captura de pantalla para la comparación posterior) del resultado de este comando, que incluirá una dirección URL de SE y WS, pero en su mayoría constan de SPN que comienzan por `00000004-0000-0ff1-ce00-000000000000/` .</span><span class="sxs-lookup"><span data-stu-id="86d24-168">Take note of (and screenshot for later comparison) the output of this command, which will include an SE and WS URL, but mostly consist of SPNs that begin with `00000004-0000-0ff1-ce00-000000000000/`.</span></span>

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. <span data-ttu-id="86d24-169">Si faltan **las** direcciones URL SFB internas o externas de las instalaciones locales (por ejemplo, y tendremos que agregar esos registros específicos https://lyncwebint01.contoso.com a esta https://lyncwebext01.contoso.com) lista.</span><span class="sxs-lookup"><span data-stu-id="86d24-169">If the internal **or** external SFB URLs from on-premises are missing (for example, https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com) we will need to add those specific records to this list.</span></span>

    <span data-ttu-id="86d24-170">Asegúrese de reemplazar las  *direcciones URL de ejemplo* siguientes por las direcciones URL reales en los comandos Agregar.</span><span class="sxs-lookup"><span data-stu-id="86d24-170">Be sure to replace  *the example URLs* below with your actual URLs in the Add commands!</span></span>

```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```

4. <span data-ttu-id="86d24-171">Compruebe que los nuevos registros se agregaron ejecutando el comando **Get-MsolServicePrincipal** desde el paso 2 de nuevo y mirando el resultado.</span><span class="sxs-lookup"><span data-stu-id="86d24-171">Verify your new records were added by running the **Get-MsolServicePrincipal** command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="86d24-172">Compare la lista o captura de pantalla de antes con la nueva lista de SPN.</span><span class="sxs-lookup"><span data-stu-id="86d24-172">Compare the list or screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="86d24-173">También es posible que hagas una captura de pantalla de la nueva lista de los registros.</span><span class="sxs-lookup"><span data-stu-id="86d24-173">You might also screenshot the new list for your records.</span></span> <span data-ttu-id="86d24-174">Si se ha realizado correctamente, verá las dos nuevas direcciones URL de la lista.</span><span class="sxs-lookup"><span data-stu-id="86d24-174">If you were successful, you'll see the two new URLs in the list.</span></span> <span data-ttu-id="86d24-175">En nuestro ejemplo, la lista de SPN incluirá ahora las direcciones URL específicas https://lyncwebint01.contoso.com y https://lyncwebext01.contoso.com/ .</span><span class="sxs-lookup"><span data-stu-id="86d24-175">Going by our example, the list of SPNs will now include the specific URLs https://lyncwebint01.contoso.com and https://lyncwebext01.contoso.com/.</span></span>

### <a name="create-the-evosts-auth-server-object"></a><span data-ttu-id="86d24-176">Crear el objeto de servidor de autenticación de EvoSTS</span><span class="sxs-lookup"><span data-stu-id="86d24-176">Create the EvoSTS Auth Server Object</span></span>

<span data-ttu-id="86d24-177">Ejecute el siguiente comando en el Shell Skype Empresarial administración.</span><span class="sxs-lookup"><span data-stu-id="86d24-177">Run the following command in the Skype for Business Management Shell.</span></span>

```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a><span data-ttu-id="86d24-178">Habilitar la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="86d24-178">Enable Hybrid Modern Authentication</span></span>

<span data-ttu-id="86d24-179">Este es el paso que realmente activa MA.</span><span class="sxs-lookup"><span data-stu-id="86d24-179">This is the step that actually turns on MA.</span></span> <span data-ttu-id="86d24-180">Todos los pasos anteriores se pueden ejecutar con antelación sin cambiar el flujo de autenticación de cliente.</span><span class="sxs-lookup"><span data-stu-id="86d24-180">All the previous steps can be run ahead of time without changing the client authentication flow.</span></span> <span data-ttu-id="86d24-181">Cuando esté listo para cambiar el flujo de autenticación, ejecute este comando en el Shell Skype Empresarial administración.</span><span class="sxs-lookup"><span data-stu-id="86d24-181">When you're ready to change the authentication flow, run this command in the Skype for Business Management Shell.</span></span>

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a><span data-ttu-id="86d24-182">Comprobar</span><span class="sxs-lookup"><span data-stu-id="86d24-182">Verify</span></span>

<span data-ttu-id="86d24-183">Una vez que habilite HMA, el siguiente inicio de sesión de un cliente usará el nuevo flujo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="86d24-183">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="86d24-184">Tenga en cuenta que al activar HMA no se desencadenará una reauthentication para ningún cliente.</span><span class="sxs-lookup"><span data-stu-id="86d24-184">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="86d24-185">Los clientes reauthenticate en función de la duración de los tokens de autenticación y/o certificados que tienen.</span><span class="sxs-lookup"><span data-stu-id="86d24-185">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="86d24-186">Para probar que HMA funciona después de habilitarlo, salga de un sfb de prueba Windows cliente y asegúrese de hacer clic en "eliminar mis credenciales".</span><span class="sxs-lookup"><span data-stu-id="86d24-186">To test that HMA is working after you've enabled it, sign out of a test SFB Windows client and be sure to click 'delete my credentials'.</span></span> <span data-ttu-id="86d24-187">Vuelva a iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="86d24-187">Sign in again.</span></span> <span data-ttu-id="86d24-188">El cliente ahora debe usar el flujo de autenticación moderna y el inicio de sesión ahora incluirá un mensaje de **Office 365** para una cuenta "Trabajo o escuela", que se ve justo antes de que el cliente se pone en contacto con el servidor y le inicia sesión.</span><span class="sxs-lookup"><span data-stu-id="86d24-188">The client should now use the Modern Auth flow and your login will now include an **Office 365** prompt for a 'Work or school' account, seen right before the client contacts the server and logs you in.</span></span>

<span data-ttu-id="86d24-189">También debe comprobar la "Información de configuración" para Skype Empresarial clientes para una "autoridad de OAuth".</span><span class="sxs-lookup"><span data-stu-id="86d24-189">You should also check the 'Configuration Information' for Skype for Business Clients for an 'OAuth Authority'.</span></span> <span data-ttu-id="86d24-190">Para ello en el equipo cliente, mantenga presionada la tecla CTRL al mismo tiempo que haga clic con el botón secundario en el icono de Skype Empresarial en la bandeja de Windows de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="86d24-190">To do this on your client computer, hold down the CTRL key at the same time you right-click the Skype for Business Icon in the Windows Notification tray.</span></span> <span data-ttu-id="86d24-191">Haga **clic en Información de** configuración en el menú que aparece.</span><span class="sxs-lookup"><span data-stu-id="86d24-191">Click **Configuration Information** in the menu that appears.</span></span> <span data-ttu-id="86d24-192">En la ventana "Skype Empresarial de configuración" que aparecerá en el escritorio, busque lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="86d24-192">In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:</span></span>

![La información de configuración de un cliente Skype Empresarial mediante autenticación moderna muestra una dirección URL de la autoridad de OAUTH de Lync y EWS de https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)

<span data-ttu-id="86d24-194">También debe mantener presionada la tecla CTRL al mismo tiempo que haga clic con el botón secundario en el icono del cliente de Outlook (también en la bandeja de notificaciones de Windows) y haga clic en "Estado de conexión".</span><span class="sxs-lookup"><span data-stu-id="86d24-194">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="86d24-195">Busque la dirección SMTP del cliente en un tipo de AuthN de "Portador", que representa el token de portador usado \* en OAuth.</span><span class="sxs-lookup"><span data-stu-id="86d24-195">Look for the client's SMTP address against an AuthN type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

## <a name="related-articles"></a><span data-ttu-id="86d24-196">Artículos relacionados</span><span class="sxs-lookup"><span data-stu-id="86d24-196">Related articles</span></span>

<span data-ttu-id="86d24-197">[Vuelva a vincular a la información general sobre autenticación moderna](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d24-197">[Link back to the Modern Authentication overview](hybrid-modern-auth-overview.md).</span></span>

<span data-ttu-id="86d24-198">¿Necesita saber cómo usar la autenticación moderna (ADAL) para sus Skype Empresarial cliente?</span><span class="sxs-lookup"><span data-stu-id="86d24-198">Do you need to know how to use Modern Authentication (ADAL) for your Skype for Business clients?</span></span> <span data-ttu-id="86d24-199">Aquí tenemos los [pasos](./hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="86d24-199">We've got steps [here](./hybrid-modern-auth-overview.md).</span></span>