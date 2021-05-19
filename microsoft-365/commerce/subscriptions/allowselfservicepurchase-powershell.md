---
title: Usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Obtenga información sobre cómo usar el cmdlet De PowerShell AllowSelfServicePurchase para activar o desactivar la compra de autoservicio.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 012874a8794e006d97c4f74014e92e1f7f3c2709
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536135"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="b0cbf-103">Usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce</span><span class="sxs-lookup"><span data-stu-id="b0cbf-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="b0cbf-104">El módulo de PowerShell de **MSCommerce** ya está disponible en la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="b0cbf-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="b0cbf-105">El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras de autoservicio.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="b0cbf-106">Puede usar el módulo **MSCommerce** PowerShell para:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="b0cbf-107">Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase,** independientemente de si está habilitado o deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="b0cbf-108">Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada</span><span class="sxs-lookup"><span data-stu-id="b0cbf-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="b0cbf-109">Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo</span><span class="sxs-lookup"><span data-stu-id="b0cbf-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="b0cbf-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b0cbf-110">Requirements</span></span>

<span data-ttu-id="b0cbf-111">Para usar el **módulo de PowerShell de MSCommerce,** necesita:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="b0cbf-112">Un Windows 10 móvil</span><span class="sxs-lookup"><span data-stu-id="b0cbf-112">A Windows 10 device</span></span>
- <span data-ttu-id="b0cbf-113">PowerShell 5 o inferior.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-113">PowerShell 5 or below.</span></span> <span data-ttu-id="b0cbf-114">Actualmente, PowerShell 6.x/7.x no es compatible con este módulo.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="b0cbf-115">Permiso de administrador para el dispositivo</span><span class="sxs-lookup"><span data-stu-id="b0cbf-115">Administrator permission for the device</span></span>
- <span data-ttu-id="b0cbf-116">Rol de administrador global o de facturación para el inquilino</span><span class="sxs-lookup"><span data-stu-id="b0cbf-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="b0cbf-117">Instalar el módulo de PowerShell de MSCommerce</span><span class="sxs-lookup"><span data-stu-id="b0cbf-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="b0cbf-118">El módulo **de PowerShell de MSCommerce** se instala en el dispositivo Windows 10 una vez y, a continuación, se importa en cada sesión de PowerShell que inicie.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="b0cbf-119">Descargue el **módulo MSCommerce** PowerShell de la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="b0cbf-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="b0cbf-120">Para instalar el **módulo de PowerShell de MSCommerce** con **PowerShellGet,** ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="b0cbf-121">Importar MSCommerce a la sesión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="b0cbf-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="b0cbf-122">Después de instalar el módulo en el dispositivo Windows 10, luego lo importa en cada sesión de PowerShell que inicie.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="b0cbf-123">Para importarlo en una sesión de PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="b0cbf-124">Conectar a MSCommerce con sus credenciales</span><span class="sxs-lookup"><span data-stu-id="b0cbf-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="b0cbf-125">Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="b0cbf-126">Este comando conecta la sesión actual de PowerShell a un Azure Active Directory inquilino.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="b0cbf-127">El comando le pide un nombre de usuario y una contraseña para el espacio empresarial al que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="b0cbf-128">Si la autenticación multifactor está habilitada para sus credenciales, use la opción interactiva para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="b0cbf-129">Ver detalles de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="b0cbf-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="b0cbf-130">Para ver una descripción del valor del parámetro **AllowSelfServicePurchase** y el estado predeterminado, según la organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="b0cbf-131">Ver una lista de productos de compra de autoservicio y su estado</span><span class="sxs-lookup"><span data-stu-id="b0cbf-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="b0cbf-132">Para ver una lista de todos los productos de compra de autoservicio disponibles y el estado de cada uno, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="b0cbf-133">En la tabla siguiente se enumeran los productos disponibles y **su ProductId**.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="b0cbf-134">Producto</span><span class="sxs-lookup"><span data-stu-id="b0cbf-134">Product</span></span> | <span data-ttu-id="b0cbf-135">ProductId</span><span class="sxs-lookup"><span data-stu-id="b0cbf-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="b0cbf-136">Power Apps por usuario</span><span class="sxs-lookup"><span data-stu-id="b0cbf-136">Power Apps per user</span></span> | <span data-ttu-id="b0cbf-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="b0cbf-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="b0cbf-138">Power Automate por usuario</span><span class="sxs-lookup"><span data-stu-id="b0cbf-138">Power Automate per user</span></span> | <span data-ttu-id="b0cbf-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="b0cbf-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="b0cbf-140">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="b0cbf-140">Power Automate RPA</span></span> | <span data-ttu-id="b0cbf-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="b0cbf-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="b0cbf-142">Power BI Premium (independiente)</span><span class="sxs-lookup"><span data-stu-id="b0cbf-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="b0cbf-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="b0cbf-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="b0cbf-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="b0cbf-144">Power BI Pro</span></span> | <span data-ttu-id="b0cbf-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="b0cbf-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="b0cbf-146">Project Plan 1</span><span class="sxs-lookup"><span data-stu-id="b0cbf-146">Project Plan 1</span></span> | <span data-ttu-id="b0cbf-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="b0cbf-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="b0cbf-148">Project Plan 3</span><span class="sxs-lookup"><span data-stu-id="b0cbf-148">Project Plan 3</span></span> | <span data-ttu-id="b0cbf-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="b0cbf-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="b0cbf-150">Visio Plan 1</span><span class="sxs-lookup"><span data-stu-id="b0cbf-150">Visio Plan 1</span></span> | <span data-ttu-id="b0cbf-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="b0cbf-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="b0cbf-152">Visio Plan 2</span><span class="sxs-lookup"><span data-stu-id="b0cbf-152">Visio Plan 2</span></span> | <span data-ttu-id="b0cbf-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="b0cbf-153">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="b0cbf-154">Ver o establecer el estado de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="b0cbf-154">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="b0cbf-155">Después de ver la lista de productos disponibles para la compra de autoservicio, puede ver o modificar la configuración de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-155">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="b0cbf-156">Para obtener la configuración de directiva de un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-156">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="b0cbf-157">Para habilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-157">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="b0cbf-158">Para deshabilitar la configuración de directiva de un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-158">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="b0cbf-159">Script de ejemplo para deshabilitar AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="b0cbf-159">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="b0cbf-160">En el siguiente ejemplo se explica cómo importar el módulo **MSCommerce,** iniciar sesión con su cuenta, obtener **el ProductId** para Power Automate y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-160">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="b0cbf-161">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="b0cbf-161">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="b0cbf-162">Problema</span><span class="sxs-lookup"><span data-stu-id="b0cbf-162">Problem</span></span>

<span data-ttu-id="b0cbf-163">Verá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="b0cbf-163">You see the following error message:</span></span>

> <span data-ttu-id="b0cbf-164">HandleError: no se pudo recuperar la directiva con PolicyId 'AllowSelfServicePurchase', ErrorMessage: se cerró la conexión subyacente: se produjo un error inesperado en un envío.</span><span class="sxs-lookup"><span data-stu-id="b0cbf-164">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="b0cbf-165">Esto puede deberse a una versión anterior de Seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="b0cbf-165">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="b0cbf-166">Para conectar este servicio, debe usar TLS 1.2 o posterior</span><span class="sxs-lookup"><span data-stu-id="b0cbf-166">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="b0cbf-167">Solución</span><span class="sxs-lookup"><span data-stu-id="b0cbf-167">Solution</span></span>

<span data-ttu-id="b0cbf-168">Actualización a TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="b0cbf-168">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="b0cbf-169">Contenido relacionado</span><span class="sxs-lookup"><span data-stu-id="b0cbf-169">Related content</span></span>

<span data-ttu-id="b0cbf-170">[Administrar compras de autoservicio (administrador)](manage-self-service-purchases-admins.md) (artículo)</span><span class="sxs-lookup"><span data-stu-id="b0cbf-170">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="b0cbf-171">[Preguntas más frecuentes sobre la compra de](self-service-purchase-faq.yml) autoservicio (artículo)</span><span class="sxs-lookup"><span data-stu-id="b0cbf-171">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>