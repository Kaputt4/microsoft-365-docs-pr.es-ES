---
title: Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Obtenga información sobre cómo usar el cmdlet de PowerShell AllowSelfServicePurchase para activar o desactivar la compra de autoservicio.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 5149a07daeedae3c28bc4326b92bb20881faebe2
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594671"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="a5e66-103">Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce</span><span class="sxs-lookup"><span data-stu-id="a5e66-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="a5e66-104">El módulo de PowerShell **MSCommerce** ahora está disponible en la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="a5e66-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="a5e66-105">El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras sin servicio de asistencia.</span><span class="sxs-lookup"><span data-stu-id="a5e66-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="a5e66-106">Puede usar el módulo de PowerShell **MSCommerce** para:</span><span class="sxs-lookup"><span data-stu-id="a5e66-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="a5e66-107">Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase** (si está habilitado o deshabilitado)</span><span class="sxs-lookup"><span data-stu-id="a5e66-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="a5e66-108">Ver una lista de los productos aplicables y si la compra de servicios automáticos está habilitada o deshabilitada</span><span class="sxs-lookup"><span data-stu-id="a5e66-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="a5e66-109">Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo</span><span class="sxs-lookup"><span data-stu-id="a5e66-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="a5e66-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a5e66-110">Requirements</span></span>

<span data-ttu-id="a5e66-111">Para usar el módulo de PowerShell **MSCommerce** , necesita:</span><span class="sxs-lookup"><span data-stu-id="a5e66-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="a5e66-112">Un dispositivo con Windows 10</span><span class="sxs-lookup"><span data-stu-id="a5e66-112">A Windows 10 device</span></span>
- <span data-ttu-id="a5e66-113">Permisos de administrador para el dispositivo</span><span class="sxs-lookup"><span data-stu-id="a5e66-113">Administrator permission for the device</span></span>
- <span data-ttu-id="a5e66-114">Rol de administrador global o de facturación para su espacio empresarial</span><span class="sxs-lookup"><span data-stu-id="a5e66-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="a5e66-115">Instalar el módulo de PowerShell MSCommerce</span><span class="sxs-lookup"><span data-stu-id="a5e66-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="a5e66-116">Instale el módulo de PowerShell **MSCommerce** en su dispositivo con Windows 10 y, a continuación, impórtelo en cada sesión de PowerShell que inicie.</span><span class="sxs-lookup"><span data-stu-id="a5e66-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="a5e66-117">Descargue el módulo de PowerShell **MSCommerce** de la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="a5e66-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="a5e66-118">Para instalar el módulo de PowerShell **MSCommerce** con **PowerShellGet**, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="a5e66-119">Importar MSCommerce en la sesión de PowerShell</span><span class="sxs-lookup"><span data-stu-id="a5e66-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="a5e66-120">Después de instalar el módulo en el dispositivo con Windows 10, se importa a cada sesión de PowerShell que se inicie.</span><span class="sxs-lookup"><span data-stu-id="a5e66-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="a5e66-121">Para importarla en una sesión de PowerShell, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="a5e66-122">Conectarse a MSCommerce con sus credenciales</span><span class="sxs-lookup"><span data-stu-id="a5e66-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="a5e66-123">Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="a5e66-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="a5e66-124">Este comando conecta la sesión actual de PowerShell con un inquilino de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a5e66-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="a5e66-125">El comando le pedirá un nombre de usuario y una contraseña para el inquilino al que desea conectarse.</span><span class="sxs-lookup"><span data-stu-id="a5e66-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="a5e66-126">Si está habilitada la autenticación multifactor para sus credenciales, puede usar la opción interactiva para iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="a5e66-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="a5e66-127">Ver detalles de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="a5e66-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="a5e66-128">Para ver una descripción del valor del parámetro **AllowSelfServicePurchase** y el estado predeterminado, en función de la organización, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="a5e66-129">Ver una lista de productos de compra de autoservicio y su estado</span><span class="sxs-lookup"><span data-stu-id="a5e66-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="a5e66-130">Para ver una lista de todos los productos de compra de autoservicio disponibles y el estado de cada uno, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="a5e66-131">En la siguiente tabla se enumeran los productos disponibles y su **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="a5e66-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="a5e66-132">Producto</span><span class="sxs-lookup"><span data-stu-id="a5e66-132">Product</span></span> | <span data-ttu-id="a5e66-133">Cuyo</span><span class="sxs-lookup"><span data-stu-id="a5e66-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="a5e66-134">Power apps por usuario</span><span class="sxs-lookup"><span data-stu-id="a5e66-134">Power Apps per user</span></span> | <span data-ttu-id="a5e66-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="a5e66-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="a5e66-136">Potencia automatizada por usuario</span><span class="sxs-lookup"><span data-stu-id="a5e66-136">Power Automate per user</span></span> | <span data-ttu-id="a5e66-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="a5e66-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="a5e66-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="a5e66-138">Power BI Pro</span></span> | <span data-ttu-id="a5e66-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="a5e66-139">CFQ7TTC0L3PB</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="a5e66-140">Ver o establecer el estado de AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="a5e66-140">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="a5e66-141">Después de ver la lista de productos disponibles para la compra de autoservicio, puede ver o modificar la configuración de un producto específico.</span><span class="sxs-lookup"><span data-stu-id="a5e66-141">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="a5e66-142">Para obtener la configuración de directiva de un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-142">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="a5e66-143">Para habilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-143">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="a5e66-144">Para deshabilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="a5e66-144">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="a5e66-145">Script de ejemplo para deshabilitar AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="a5e66-145">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="a5e66-146">En el ejemplo siguiente se explica cómo importar el módulo **MSCommerce** , iniciar sesión con su cuenta, obtener el **ProductID** para la automatización automática y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.</span><span class="sxs-lookup"><span data-stu-id="a5e66-146">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="a5e66-147">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="a5e66-147">Troubleshooting</span></span>

<span data-ttu-id="a5e66-148">**Problema**</span><span class="sxs-lookup"><span data-stu-id="a5e66-148">**Problem**</span></span>

<span data-ttu-id="a5e66-149">Verá el siguiente mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="a5e66-149">You see the following error message:</span></span>

    HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying
    connection was closed: An unexpected error occurred on a send.

<span data-ttu-id="a5e66-150">Esto puede deberse a una versión anterior de la seguridad de la capa de transporte (TLS).</span><span class="sxs-lookup"><span data-stu-id="a5e66-150">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="a5e66-151">Para conectar este servicio, debe usar TLS 1,2 o superior.</span><span class="sxs-lookup"><span data-stu-id="a5e66-151">To connect this service you need to use TLS 1.2 or greater</span></span>

<span data-ttu-id="a5e66-152">**Solución**</span><span class="sxs-lookup"><span data-stu-id="a5e66-152">**Solution**</span></span>

<span data-ttu-id="a5e66-153">Actualización a TLS 1,2:[https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="a5e66-153">Upgrade to TLS 1.2: [https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->