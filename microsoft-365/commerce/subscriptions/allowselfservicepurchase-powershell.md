---
title: Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo usar el cmdlet de PowerShell AllowSelfServicePurchase para activar o desactivar la compra de autoservicio.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653718"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="67243-103">Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce</span><span class="sxs-lookup"><span data-stu-id="67243-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="67243-104">El módulo de PowerShell **MSCommerce** ahora está disponible en la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="67243-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="67243-105">El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras sin servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="67243-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="67243-106">Puede usar el módulo de PowerShell **MSCommerce** para:</span><span class="sxs-lookup"><span data-stu-id="67243-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="67243-107">Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase** (si está habilitado o deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="67243-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="67243-108">Ver una lista de los productos aplicables y si la compra de servicios automáticos está habilitada o deshabilitada</span><span class="sxs-lookup"><span data-stu-id="67243-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="67243-109">Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo</span><span class="sxs-lookup"><span data-stu-id="67243-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="67243-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="67243-110">Requirements</span></span>

<span data-ttu-id="67243-111">Para usar el módulo de PowerShell **MSCommerce** , necesita:</span><span class="sxs-lookup"><span data-stu-id="67243-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="67243-112">Un dispositivo con Windows 10</span><span class="sxs-lookup"><span data-stu-id="67243-112">A Windows 10 device</span></span>
- <span data-ttu-id="67243-113">Permisos de administrador para el dispositivo</span><span class="sxs-lookup"><span data-stu-id="67243-113">Administrator permission for the device</span></span>
- <span data-ttu-id="67243-114">Rol de administrador global o de facturación para su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="67243-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="67243-115">Instalar el módulo de PowerShell MSCommerce</span><span class="sxs-lookup"><span data-stu-id="67243-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="67243-116">Instale el módulo de PowerShell **MSCommerce** en su dispositivo con Windows 10 y, a continuación, impórtelo en cada sesión de PowerShell que inicie.</span><span class="sxs-lookup"><span data-stu-id="67243-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="67243-117">Descargue el módulo de PowerShell **MSCommerce** de la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="67243-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="67243-118">Para instalar el módulo de PowerShell **MSCommerce** con **PowerShellGet**, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="67243-119">Importar MSCommerce en la sesión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="67243-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="67243-120">Después de instalar el módulo en el dispositivo con Windows 10, se importa a cada sesión de PowerShell que se inicie.</span><span class="sxs-lookup"><span data-stu-id="67243-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="67243-121">Para importarla en una sesión de PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="67243-122">Conectarse a MSCommerce con sus credenciales</span><span class="sxs-lookup"><span data-stu-id="67243-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="67243-123">Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="67243-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="67243-124">Este comando conecta la sesión actual de PowerShell con un inquilino de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="67243-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="67243-125">El comando le pedirá un nombre de usuario y una contraseña para el inquilino al que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="67243-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="67243-126">Si está habilitada la autenticación multifactor para sus credenciales, puede usar la opción interactiva para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="67243-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="67243-127">Ver detalles de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="67243-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="67243-128">Para ver una descripción del valor del parámetro **AllowSelfServicePurchase** y el estado predeterminado, en función de la organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="67243-129">Ver una lista de productos de compra de autoservicio y su estado</span><span class="sxs-lookup"><span data-stu-id="67243-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="67243-130">Para ver una lista de todos los productos de compra de autoservicio disponibles y el estado de cada uno, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="67243-131">En la siguiente tabla se enumeran los productos disponibles y su **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="67243-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="67243-132">Producto</span><span class="sxs-lookup"><span data-stu-id="67243-132">Product</span></span> | <span data-ttu-id="67243-133">Cuyo</span><span class="sxs-lookup"><span data-stu-id="67243-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="67243-134">Power apps por usuario</span><span class="sxs-lookup"><span data-stu-id="67243-134">Power Apps per user</span></span> | <span data-ttu-id="67243-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="67243-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="67243-136">Potencia automatizada por usuario</span><span class="sxs-lookup"><span data-stu-id="67243-136">Power Automate per user</span></span> | <span data-ttu-id="67243-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="67243-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="67243-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="67243-138">Power BI Pro</span></span> | <span data-ttu-id="67243-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="67243-139">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="67243-140">Plan de proyecto 1</span><span class="sxs-lookup"><span data-stu-id="67243-140">Project Plan 1</span></span> | <span data-ttu-id="67243-141">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="67243-141">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="67243-142">Plan de proyecto 3</span><span class="sxs-lookup"><span data-stu-id="67243-142">Project Plan 3</span></span> | <span data-ttu-id="67243-143">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="67243-143">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="67243-144">Visio plan 1</span><span class="sxs-lookup"><span data-stu-id="67243-144">Visio Plan 1</span></span> | <span data-ttu-id="67243-145">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="67243-145">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="67243-146">Visio plan 2</span><span class="sxs-lookup"><span data-stu-id="67243-146">Visio Plan 2</span></span> | <span data-ttu-id="67243-147">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="67243-147">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="67243-148">Ver o establecer el estado de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="67243-148">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="67243-149">Después de ver la lista de productos disponibles para la compra de autoservicio, puede ver o modificar la configuración de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="67243-149">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="67243-150">Para obtener la configuración de directiva de un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-150">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="67243-151">Para habilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-151">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="67243-152">Para deshabilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="67243-152">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="67243-153">Script de ejemplo para deshabilitar AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="67243-153">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="67243-154">En el ejemplo siguiente se explica cómo importar el módulo **MSCommerce** , iniciar sesión con su cuenta, obtener el **ProductID** para la automatización automática y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.</span><span class="sxs-lookup"><span data-stu-id="67243-154">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="67243-155">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="67243-155">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="67243-156">Problema</span><span class="sxs-lookup"><span data-stu-id="67243-156">Problem</span></span>

<span data-ttu-id="67243-157">Verá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="67243-157">You see the following error message:</span></span>

> <span data-ttu-id="67243-158">HandleError: no se pudo recuperar la Directiva con PolicyId ' AllowSelfServicePurchase ', ErrorMessage-se ha cerrado la conexión subyacente: se ha producido un error inesperado en un envío.</span><span class="sxs-lookup"><span data-stu-id="67243-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="67243-159">Esto puede deberse a una versión anterior de la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="67243-159">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="67243-160">Para conectar este servicio, debe usar TLS 1,2 o superior.</span><span class="sxs-lookup"><span data-stu-id="67243-160">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="67243-161">Solución</span><span class="sxs-lookup"><span data-stu-id="67243-161">Solution</span></span>

<span data-ttu-id="67243-162">Actualización a TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="67243-162">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
