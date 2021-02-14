---
title: Agregar un dominio a un arrendamiento de cliente con Windows PowerShell para asociados dap
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: 'Resumen: use PowerShell para Microsoft 365 para agregar un nombre de dominio alternativo a un inquilino de cliente existente.'
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694203"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="68c4d-103">Agregar un dominio a un arrendamiento de cliente con Windows PowerShell para asociados con permiso de acceso delegado (DAP)</span><span class="sxs-lookup"><span data-stu-id="68c4d-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="68c4d-104">*Este artículo afecta tanto a Office 365 Enterprise como a Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="68c4d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="68c4d-105">Puede crear y asociar nuevos dominios con el arrendamiento del cliente con PowerShell para Microsoft 365 más rápido que con el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68c4d-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="68c4d-106">Los asociados con permiso de acceso delegado (DAP) son asociados de sindicación y proveedor de soluciones en la nube (CSP).</span><span class="sxs-lookup"><span data-stu-id="68c4d-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="68c4d-107">Con frecuencia son los proveedores de red o de telecomunicaciones para otras compañías.</span><span class="sxs-lookup"><span data-stu-id="68c4d-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="68c4d-108">Agrupan suscripciones de Microsoft 365 en sus ofertas de servicio a sus clientes.</span><span class="sxs-lookup"><span data-stu-id="68c4d-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="68c4d-109">Cuando se vende una suscripción de Microsoft 365, se les conceden automáticamente permisos Administrar en nombre de (AOBO) a los tenencias del cliente para que puedan administrar e informar sobre los tenencias del cliente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="68c4d-110">¿Qué necesita saber antes de comenzar?</span><span class="sxs-lookup"><span data-stu-id="68c4d-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="68c4d-111">Los procedimientos de este tema requieren conectarse a Conectarse a [Microsoft 365 con PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="68c4d-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="68c4d-112">Necesita también las credenciales del administrador de inquilinos del asociado.</span><span class="sxs-lookup"><span data-stu-id="68c4d-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="68c4d-113">También necesitará la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="68c4d-113">You also need the following information:</span></span>
  
- <span data-ttu-id="68c4d-114">Necesitará el nombre de dominio completo (FQDN) que desea el cliente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="68c4d-115">Necesita el **TenantId** del cliente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="68c4d-p102">El FQDN debe estar registrado con un registrador del servicio de nombres de dominio (DNS), como GoDaddy. Para obtener más información sobre cómo registrar públicamente un nombre de dominio, vea [Cómo comprar un nombre de dominio](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span><span class="sxs-lookup"><span data-stu-id="68c4d-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span></span>
    
- <span data-ttu-id="68c4d-118">Necesita saber cómo agregar un registro TXT a la zona DNS registrada para su registrador DNS.</span><span class="sxs-lookup"><span data-stu-id="68c4d-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="68c4d-119">Para obtener más información sobre cómo agregar un registro TXT, vea [Agregar registros DNS para conectar su dominio.](https://go.microsoft.com/fwlink/p/?LinkId=532542)</span><span class="sxs-lookup"><span data-stu-id="68c4d-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="68c4d-120">Si esos procedimientos no funcionan, necesitará encontrar los procedimientos de su registrador DNS.</span><span class="sxs-lookup"><span data-stu-id="68c4d-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="68c4d-121">Crear dominios</span><span class="sxs-lookup"><span data-stu-id="68c4d-121">Create domains</span></span>

 <span data-ttu-id="68c4d-p104">Sus clientes probablemente le pedirán crear dominios adicionales para asociar con su arrendamiento, ya que no desean que el dominio predeterminado <domain>.onmicrosoft.com sea el dominio principal que represente su identidad corporativa en el mundo. En este procedimiento se explica cómo crear un nuevo dominio asociado con el arrendamiento de su cliente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68c4d-124">Para realizar algunas de estas operaciones, la cuenta de  administrador de  partners con la que inicia sesión debe establecerse en Administración completa para la opción Asignar acceso administrativo a las empresas a las que admite, que se encuentra en los detalles de la cuenta de administrador en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68c4d-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="68c4d-125">Para obtener más información sobre cómo administrar roles de administrador de partners, consulta [Partners: Ofrecer administración delegada.](https://go.microsoft.com/fwlink/p/?LinkId=532435)</span><span class="sxs-lookup"><span data-stu-id="68c4d-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="68c4d-126">Crear el dominio en Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="68c4d-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="68c4d-127">Este comando crea el dominio en Azure Active Directory, pero no lo asocia al dominio registrado públicamente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="68c4d-128">Esto ocurre cuando demuestra que es el propietario del dominio registrado públicamente en Microsoft 365 para empresas.</span><span class="sxs-lookup"><span data-stu-id="68c4d-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="68c4d-129">PowerShell Core no es compatible con el Módulo Microsoft Azure Active Directory para Windows PowerShell ni los cmdlet que llevan **Msol** en su nombre.</span><span class="sxs-lookup"><span data-stu-id="68c4d-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="68c4d-130">Para seguir usando estos cmdlets, debe ejecutarlos desde Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="68c4d-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="68c4d-131">Obtener los datos para la verificación del registro TXT de DNS</span><span class="sxs-lookup"><span data-stu-id="68c4d-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="68c4d-132">Microsoft 365 generará los datos específicos que debe colocar en el registro de verificación TXT de DNS.</span><span class="sxs-lookup"><span data-stu-id="68c4d-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="68c4d-133">Para obtener los datos, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="68c4d-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="68c4d-134">Se obtendrá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="68c4d-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="68c4d-135">Necesitará este texto para crear el registro TXT en la zona DNS registrada públicamente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="68c4d-136">Asegúrese de copiarlo y guardarlo.</span><span class="sxs-lookup"><span data-stu-id="68c4d-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="68c4d-137">Agregar un registro TXT a la zona DNS registrada públicamente</span><span class="sxs-lookup"><span data-stu-id="68c4d-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="68c4d-138">Antes de que Microsoft 365 empiece a aceptar tráfico que se dirige al nombre de dominio registrado públicamente, debe demostrar que posee y tiene permisos de administrador en el dominio.</span><span class="sxs-lookup"><span data-stu-id="68c4d-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="68c4d-139">Demuestre que el dominio le pertenece mediante la creación de un registro TXT en el dominio.</span><span class="sxs-lookup"><span data-stu-id="68c4d-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="68c4d-140">Un registro TXT no hace nada en su dominio y puede eliminarse una vez que se establezca su propiedad del dominio.</span><span class="sxs-lookup"><span data-stu-id="68c4d-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="68c4d-141">Para crear los registros TXT, siga los procedimientos descritos [en Agregar registros DNS para conectar su dominio.](https://go.microsoft.com/fwlink/p/?LinkId=532542)</span><span class="sxs-lookup"><span data-stu-id="68c4d-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="68c4d-142">Si esos procedimientos no funcionan, necesitará encontrar los procedimientos de su registrador DNS.</span><span class="sxs-lookup"><span data-stu-id="68c4d-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="68c4d-p111">Confirme la creación correcta del registro TXT mediante nslookup. Siga esta sintaxis.</span><span class="sxs-lookup"><span data-stu-id="68c4d-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="68c4d-145">Se obtendrá el siguiente resultado:</span><span class="sxs-lookup"><span data-stu-id="68c4d-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="68c4d-146">Validar la propiedad del dominio en Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="68c4d-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="68c4d-147">En este último paso, valida a Microsoft 365 que es el propietario del dominio registrado públicamente.</span><span class="sxs-lookup"><span data-stu-id="68c4d-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="68c4d-148">Después de este paso, Microsoft 365 empezará a aceptar tráfico enrutado al nuevo nombre de dominio.</span><span class="sxs-lookup"><span data-stu-id="68c4d-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="68c4d-149">Para completar la creación del dominio y el proceso de registro, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="68c4d-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="68c4d-150">Este comando no devolverá ningún resultado, por lo tanto, para confirmar que funcionó, ejecute este comando.</span><span class="sxs-lookup"><span data-stu-id="68c4d-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="68c4d-151">Se mostrará un resultado semejante a</span><span class="sxs-lookup"><span data-stu-id="68c4d-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="68c4d-152">Consulte también</span><span class="sxs-lookup"><span data-stu-id="68c4d-152">See also</span></span>

#### 

[<span data-ttu-id="68c4d-153">Ayuda para asociados</span><span class="sxs-lookup"><span data-stu-id="68c4d-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)

