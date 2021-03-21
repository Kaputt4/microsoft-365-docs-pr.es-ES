---
title: Cómo configurar Exchange Server local para usar la autenticación moderna híbrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo configurar una Exchange Server local para usar la autenticación moderna híbrida (HMA), lo que le ofrece una autenticación y autorización de usuario más seguras.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 46646f35d3b41821424269f66721fbf829d339f7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928207"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a><span data-ttu-id="3a8cf-103">Cómo configurar Exchange Server local para usar la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="3a8cf-103">How to configure Exchange Server on-premises to use Hybrid Modern Authentication</span></span>

<span data-ttu-id="3a8cf-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="3a8cf-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="3a8cf-105">La autenticación moderna híbrida (HMA) es un método de administración de identidades que ofrece una autenticación y autorización de usuario más seguras, y está disponible para las implementaciones híbridas locales del servidor Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-105">Hybrid Modern Authentication (HMA) is a method of identity management that offers more secure user authentication and authorization, and is available for Exchange server on-premises hybrid deployments.</span></span>

## <a name="fyi"></a><span data-ttu-id="3a8cf-106">FYI</span><span class="sxs-lookup"><span data-stu-id="3a8cf-106">FYI</span></span>

<span data-ttu-id="3a8cf-107">Antes de empezar, llama a:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-107">Before we begin, I call:</span></span>

- <span data-ttu-id="3a8cf-108">Autenticación moderna \> híbrida HMA</span><span class="sxs-lookup"><span data-stu-id="3a8cf-108">Hybrid Modern Authentication \> HMA</span></span>

- <span data-ttu-id="3a8cf-109">EXCH local de Exchange \></span><span class="sxs-lookup"><span data-stu-id="3a8cf-109">Exchange on-premises \> EXCH</span></span>

- <span data-ttu-id="3a8cf-110">Exo de Exchange Online \></span><span class="sxs-lookup"><span data-stu-id="3a8cf-110">Exchange Online \> EXO</span></span>

<span data-ttu-id="3a8cf-111">Además, si un gráfico de este artículo tiene un objeto "atenuado" o atenuado, significa que el elemento que se muestra en gris no se incluye en la configuración específica de *HMA.*</span><span class="sxs-lookup"><span data-stu-id="3a8cf-111">Also, *if a graphic in this article has an object that's 'grayed-out' or 'dimmed' that means the element shown in gray is not included in HMA-specific configuration*.</span></span>

## <a name="enabling-hybrid-modern-authentication"></a><span data-ttu-id="3a8cf-112">Habilitar la autenticación moderna híbrida</span><span class="sxs-lookup"><span data-stu-id="3a8cf-112">Enabling Hybrid Modern Authentication</span></span>

<span data-ttu-id="3a8cf-113">Activar HMA significa:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-113">Turning on HMA means:</span></span>

1. <span data-ttu-id="3a8cf-114">Asegúrese de cumplir con las preguntas previas antes de comenzar.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-114">Being sure you meet the prereqs before you begin.</span></span>

1. <span data-ttu-id="3a8cf-115">Dado que **muchos requisitos previos** son comunes tanto para Skype Empresarial como para Exchange, la introducción a la autenticación moderna híbrida y los [requisitos previos](hybrid-modern-auth-overview.md)para usarlo con servidores locales de Skype Empresarial y Exchange.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-115">Since many **prerequisites** are common for both Skype for Business and Exchange, [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="3a8cf-116">Haga esto antes de comenzar cualquiera de los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-116">Do this before you begin any of the steps in this article.</span></span>

1. <span data-ttu-id="3a8cf-117">Agregar direcciones URL de servicio web locales como nombres de entidad de seguridad de servicio **(SPN)** en Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-117">Adding on-premises web service URLs as **Service Principal Names (SPNs)** in Azure AD.</span></span>

1. <span data-ttu-id="3a8cf-118">Garantizar que todos los directorios virtuales estén habilitados para HMA</span><span class="sxs-lookup"><span data-stu-id="3a8cf-118">Ensuring all Virtual Directories are enabled for HMA</span></span>

1. <span data-ttu-id="3a8cf-119">Comprobación del objeto EvoSTS Auth Server</span><span class="sxs-lookup"><span data-stu-id="3a8cf-119">Checking for the EvoSTS Auth Server object</span></span>

1. <span data-ttu-id="3a8cf-120">Habilitar HMA en EXCH.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-120">Enabling HMA in EXCH.</span></span>

 <span data-ttu-id="3a8cf-121">**Nota** ¿La versión de Office es compatible con MA?</span><span class="sxs-lookup"><span data-stu-id="3a8cf-121">**Note** Does your version of Office support MA?</span></span> <span data-ttu-id="3a8cf-122">Vea [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span><span class="sxs-lookup"><span data-stu-id="3a8cf-122">See [How modern authentication works for Office 2013 and Office 2016 client apps](modern-auth-for-office-2013-and-2016.md).</span></span>

## <a name="make-sure-you-meet-all-the-prerequisites"></a><span data-ttu-id="3a8cf-123">Asegúrese de cumplir todos los requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3a8cf-123">Make sure you meet all the prerequisites</span></span>

<span data-ttu-id="3a8cf-124">Dado que muchos requisitos previos son comunes tanto para Skype Empresarial como para Exchange, revise [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3a8cf-124">Since many prerequisites are common for both Skype for Business and Exchange, review [Hybrid Modern Authentication overview and prerequisites for using it with on-premises Skype for Business and Exchange servers](hybrid-modern-auth-overview.md).</span></span> <span data-ttu-id="3a8cf-125">Haga esto  *antes*  de comenzar cualquiera de los pasos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-125">Do this  *before*  you begin any of the steps in this article.</span></span>

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a><span data-ttu-id="3a8cf-126">Agregar direcciones URL de servicio web local como SPN en Azure AD</span><span class="sxs-lookup"><span data-stu-id="3a8cf-126">Add on-premises web service URLs as SPNs in Azure AD</span></span>

<span data-ttu-id="3a8cf-127">Ejecute los comandos que asignan las direcciones URL del servicio web local como SPN de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-127">Run the commands that assign your on-premises web service URLs as Azure AD SPNs.</span></span> <span data-ttu-id="3a8cf-128">Los SPN los usan los dispositivos y máquinas cliente durante la autenticación y autorización.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-128">SPNs are used by client machines and devices during authentication and authorization.</span></span> <span data-ttu-id="3a8cf-129">Todas las direcciones URL que se pueden usar para conectarse desde local a Azure Active Directory (Azure AD) deben estar registradas en Azure AD (esto incluye espacios de nombres internos y externos).</span><span class="sxs-lookup"><span data-stu-id="3a8cf-129">All the URLs that might be used to connect from on-premises to Azure Active Directory (Azure AD) must be registered in Azure AD (this includes both internal and external namespaces).</span></span>

<span data-ttu-id="3a8cf-130">En primer lugar, recopile todas las direcciones URL que necesita agregar en AAD.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-130">First, gather all the URLs that you need to add in AAD.</span></span> <span data-ttu-id="3a8cf-131">Ejecute estos comandos localmente:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-131">Run these commands on-premises:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

<span data-ttu-id="3a8cf-132">Asegúrese de que las direcciones URL a las que pueden conectarse los clientes aparecen como nombres de entidad de seguridad de servicio HTTPS en AAD.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-132">Ensure the URLs clients may connect to are listed as HTTPS service principal names in AAD.</span></span>

1. <span data-ttu-id="3a8cf-133">En primer lugar, conéctese a AAD con [estas instrucciones](connect-to-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="3a8cf-133">First, connect to AAD with [these instructions](connect-to-microsoft-365-powershell.md).</span></span>

   <span data-ttu-id="3a8cf-134">**Nota** Debe usar la opción _Connect-MsolService_ de esta página para poder usar el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-134">**Note** You need to use the _Connect-MsolService_ option from this page to be able to use the command below.</span></span>

2. <span data-ttu-id="3a8cf-135">Para las direcciones URL relacionadas con Exchange, escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-135">For your Exchange-related URLs, type the following command:</span></span>

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   <span data-ttu-id="3a8cf-136">Tome nota de (y captura de pantalla para la comparación posterior) del resultado de este comando, que debe incluir una dirección URL de https://  *autodiscover.yourdomain.com*  y  *https:// mail.yourdomain.com,* pero en su mayoría consisten en SPN que comienzan por 00000002-0000-0ff1-ce00-0000000000000000000.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-136">Take note of (and screenshot for later comparison) the output of this command, which should include an https://  *autodiscover.yourdomain.com*  and https://  *mail.yourdomain.com* URL, but mostly consist of SPNs that begin with 00000002-0000-0ff1-ce00-000000000000/.</span></span> <span data-ttu-id="3a8cf-137">Si faltan https:// direcciones URL de las instalaciones locales, tendremos que agregar esos registros específicos a esta lista.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-137">If there are https:// URLs from your on-premises that are missing, we will need to add those specific records to this list.</span></span>

3. <span data-ttu-id="3a8cf-138">Si no ve los registros MAPI/HTTP, EWS, ActiveSync, OAB y Autodiscover internos y externos en esta lista, debe agregarlos con el comando siguiente (las direcciones URL de ejemplo son ' ' y ' ', pero reemplazaría las direcciones URL de ejemplo por las `mail.corp.contoso.com` `owa.contoso.com` **suyas** propias ):</span><span class="sxs-lookup"><span data-stu-id="3a8cf-138">If you don't see your internal and external MAPI/HTTP, EWS, ActiveSync, OAB, and Autodiscover records in this list, you must add them using the command below (the example URLs are '`mail.corp.contoso.com`' and '`owa.contoso.com`', but you'd **replace the example URLs with your own**):</span></span>

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. <span data-ttu-id="3a8cf-139">Compruebe que los nuevos registros se agregaron ejecutando el comando Get-MsolServicePrincipal desde el paso 2 de nuevo y mirando a través de la salida.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-139">Verify your new records were added by running the Get-MsolServicePrincipal command from step 2 again, and looking through the output.</span></span> <span data-ttu-id="3a8cf-140">Compare la lista /captura de pantalla de antes con la nueva lista de SPN.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-140">Compare the list / screenshot from before to the new list of SPNs.</span></span> <span data-ttu-id="3a8cf-141">También puedes hacer una captura de pantalla de la nueva lista de los registros.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-141">You might also take a screenshot of the new list for your records.</span></span> <span data-ttu-id="3a8cf-142">Si se ha realizado correctamente, verá las dos nuevas direcciones URL de la lista.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-142">If you were successful, you will see the two new URLs in the list.</span></span> <span data-ttu-id="3a8cf-143">En nuestro ejemplo, la lista de SPN incluirá ahora las direcciones URL específicas  `https://mail.corp.contoso.com`  y  `https://owa.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="3a8cf-143">Going by our example, the list of SPNs will now include the specific URLs  `https://mail.corp.contoso.com`  and  `https://owa.contoso.com`.</span></span>

## <a name="verify-virtual-directories-are-properly-configured"></a><span data-ttu-id="3a8cf-144">Comprobar que los directorios virtuales están configurados correctamente</span><span class="sxs-lookup"><span data-stu-id="3a8cf-144">Verify Virtual Directories are Properly Configured</span></span>

<span data-ttu-id="3a8cf-145">Ahora compruebe que OAuth está habilitado correctamente en Exchange en todos los directorios virtuales que Outlook puede usar ejecutando los siguientes comandos:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-145">Now verify OAuth is properly enabled in Exchange on all of the Virtual Directories Outlook might use by running the following commands:</span></span>

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

<span data-ttu-id="3a8cf-146">Compruebe el resultado para asegurarse de que **OAuth** está habilitado en cada uno de estos VDirs, tendrá un aspecto parecido a este (y la clave a tener en cuenta es "OAuth"):</span><span class="sxs-lookup"><span data-stu-id="3a8cf-146">Check the output to make sure **OAuth** is enabled on each of these VDirs, it will look something like this (and the key thing to look at is 'OAuth'):</span></span>

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

<span data-ttu-id="3a8cf-147">Si falta OAuth en cualquier servidor y en cualquiera de los cuatro directorios virtuales, debe agregarlo con los comandos pertinentes antes de continuar ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)y [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span><span class="sxs-lookup"><span data-stu-id="3a8cf-147">If OAuth is missing from any server and any of the four virtual directories, you need to add it using the relevant commands before proceeding ([Set-MapiVirtualDirectory](/powershell/module/exchange/set-mapivirtualdirectory), [Set-WebServicesVirtualDirectory](/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory), and [Set-AutodiscoverVirtualDirectory](/powershell/module/exchange/set-autodiscovervirtualdirectory)).</span></span>

## <a name="confirm-the-evosts-auth-server-object-is-present"></a><span data-ttu-id="3a8cf-148">Confirmar que el objeto del servidor de autenticación de EvoSTS está presente</span><span class="sxs-lookup"><span data-stu-id="3a8cf-148">Confirm the EvoSTS Auth Server Object is Present</span></span>

<span data-ttu-id="3a8cf-149">Vuelva al Shell de administración de Exchange local para este último comando.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-149">Return to the on-premises Exchange Management Shell for this last command.</span></span> <span data-ttu-id="3a8cf-150">Ahora puede validar que su local tiene una entrada para el proveedor de autenticación de evoSTS:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-150">Now you can validate that your on-premises has an entry for the evoSTS authentication provider:</span></span>

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

<span data-ttu-id="3a8cf-151">El resultado debe mostrar un AuthServer del nombre EvoSts y el estado "Habilitado" debe ser True.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-151">Your output should show an AuthServer of the Name EvoSts and the 'Enabled' state should be True.</span></span> <span data-ttu-id="3a8cf-152">Si no lo ve, debe descargar y ejecutar la versión más reciente del Asistente para configuración híbrida.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-152">If you don't see this, you should download and run the most recent version of the Hybrid Configuration Wizard.</span></span>

 <span data-ttu-id="3a8cf-153">**Importante** Si ejecuta Exchange 2010 en su entorno, no se creará el proveedor de autenticación EvoSTS.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-153">**Important** If you're running Exchange 2010 in your environment, the EvoSTS authentication provider won't be created.</span></span>

## <a name="enable-hma"></a><span data-ttu-id="3a8cf-154">Habilitar HMA</span><span class="sxs-lookup"><span data-stu-id="3a8cf-154">Enable HMA</span></span>

<span data-ttu-id="3a8cf-155">Ejecute el siguiente comando en el Shell de administración de Exchange local:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-155">Run the following command in the Exchange Management Shell, on-premises:</span></span>

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a><span data-ttu-id="3a8cf-156">Comprobar</span><span class="sxs-lookup"><span data-stu-id="3a8cf-156">Verify</span></span>

<span data-ttu-id="3a8cf-157">Una vez que habilite HMA, el siguiente inicio de sesión de un cliente usará el nuevo flujo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-157">Once you enable HMA, a client's next login will use the new auth flow.</span></span> <span data-ttu-id="3a8cf-158">Tenga en cuenta que al activar HMA no se desencadenará una reauthentication para ningún cliente.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-158">Note that just turning on HMA won't trigger a reauthentication for any client.</span></span> <span data-ttu-id="3a8cf-159">Los clientes reauthenticate en función de la duración de los tokens de autenticación y/o certificados que tienen.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-159">The clients reauthenticate based on the lifetime of the auth tokens and/or certs they have.</span></span>

<span data-ttu-id="3a8cf-160">También debe mantener presionada la tecla CTRL al mismo tiempo que haga clic con el botón secundario en el icono del cliente de Outlook (también en la bandeja notificaciones de Windows) y haga clic en "Estado de conexión".</span><span class="sxs-lookup"><span data-stu-id="3a8cf-160">You should also hold down the CTRL key at the same time you right-click the icon for the Outlook client (also in the Windows Notifications tray) and click 'Connection Status'.</span></span> <span data-ttu-id="3a8cf-161">Busque la dirección SMTP del cliente en un tipo de "Authn" de "Portador", que representa el token de portador usado \* en OAuth.</span><span class="sxs-lookup"><span data-stu-id="3a8cf-161">Look for the client's SMTP address against an 'Authn' type of 'Bearer\*', which represents the bearer token used in OAuth.</span></span>

 <span data-ttu-id="3a8cf-162">**Nota** ¿Necesita configurar Skype Empresarial con HMA?</span><span class="sxs-lookup"><span data-stu-id="3a8cf-162">**Note** Need to configure Skype for Business with HMA?</span></span> <span data-ttu-id="3a8cf-163">Necesitará dos artículos: uno [](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)que enumera las topologías admitidas y otro que muestra cómo [realizar la configuración](configure-skype-for-business-for-hybrid-modern-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3a8cf-163">You'll need two articles: One that lists [supported topologies](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported), and one that shows you [how to do the configuration](configure-skype-for-business-for-hybrid-modern-authentication.md).</span></span>

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a><span data-ttu-id="3a8cf-164">Uso de híbridos modernos de autenticación con Outlook para iOS y Android</span><span class="sxs-lookup"><span data-stu-id="3a8cf-164">Using hybrid Modern Authentication with Outlook for iOS and Android</span></span>

<span data-ttu-id="3a8cf-165">Si es un cliente local que usa exchange server en TCP 443, omita el procesamiento de tráfico para los siguientes intervalos IP:</span><span class="sxs-lookup"><span data-stu-id="3a8cf-165">If you are an on-premises customer using Exchange server on TCP 443, bypass traffic processing for the following IP ranges:</span></span>

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a><span data-ttu-id="3a8cf-166">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3a8cf-166">Related topics</span></span>

[<span data-ttu-id="3a8cf-167">Requisitos de configuración de autenticación moderna para la transición de Office 365 dedicado/ITAR a vNext</span><span class="sxs-lookup"><span data-stu-id="3a8cf-167">Modern Authentication configuration requirements for transition from Office 365 dedicated/ITAR to vNext</span></span>](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)