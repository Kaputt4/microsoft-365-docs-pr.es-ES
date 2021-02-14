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
description: Obtenga información sobre cómo usar el cmdlet allowSelfServicePurchase de PowerShell para activar o desactivar la compra de autoservicio.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653718"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce

El **módulo de PowerShell MSCommerce** ya está disponible en la [Galería de PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery) El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que permite controlar si los usuarios de la organización pueden realizar compras de autoservicio.

Puede usar el módulo **de PowerShell MSCommerce** para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase(** si está habilitado o deshabilitado)
- Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

## <a name="requirements"></a>Requirements

Para usar el **módulo de PowerShell MSCommerce,** necesita:

- Un dispositivo con Windows 10
- Permiso de administrador para el dispositivo
- Rol De administrador global o de facturación para su espacio empresarial

## <a name="install-the-mscommerce-powershell-module"></a>Instalar el módulo de PowerShell MSCommerce

Instale el módulo **de PowerShell MSCommerce** en el dispositivo Windows 10 una vez y, a continuación, impórlo en cada sesión de PowerShell que inicie. Descargue el **módulo de PowerShell MSCommerce** de la [Galería de PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)

Para instalar el **módulo de PowerShell MSCommerce** con **PowerShellGet,** ejecute el siguiente comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importar MSCommerce a la sesión de PowerShell

Después de instalar el módulo en el dispositivo Windows 10, luego lo importas en cada sesión de PowerShell que inicies. Para importarlo en una sesión de PowerShell, ejecute el siguiente comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conectarse a MSCommerce con sus credenciales

Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.

```powershell
Connect-MSCommerce
```

Este comando conecta la sesión actual de PowerShell a un inquilino de Azure Active Directory. El comando le pide un nombre de usuario y una contraseña para el inquilino al que desea conectarse. Si la autenticación multifactor está habilitada para sus credenciales, use la opción interactiva para iniciar sesión.

## <a name="view-details-for-allowselfservicepurchase"></a>Ver detalles de AllowSelfServicePurchase

Para ver una descripción del valor del parámetro **AllowSelfServicePurchase** y el estado predeterminado, en función de la organización, ejecute el siguiente comando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Ver una lista de productos de compra de autoservicio y su estado

Para ver una lista de todos los productos de compra de autoservicio disponibles y el estado de cada uno de ellos, ejecute el siguiente comando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

En la tabla siguiente se enumeran los productos disponibles y **su ProductId**.

| Producto | ProductId |
|-----------------------------|--------------|
| Power Apps por usuario | CFQ7TTC0KP0P |
| Power Automate por usuario | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Plan de proyecto 1 | CFQ7TTC0KXND |
| Plan de proyecto 3 | CFQ7TTC0KXNC |
| Visio Plan 1 | CFQ7TTC0KXN9 |
| Visio Plan 2 | CFQ7TTC0KXN8 |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Ver o establecer el estado de AllowSelfServicePurchase

Después de ver la lista de productos disponibles para la compra de autoservicio, puede ver o modificar la configuración de un producto específico.

Para obtener la configuración de directiva de un producto específico, ejecute el siguiente comando:

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

Para habilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

Para deshabilitar la configuración de directiva de un producto específico, ejecute el siguiente comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Script de ejemplo para deshabilitar AllowSelfServicePurchase

En el siguiente ejemplo se explica cómo importar el módulo **MSCommerce,** iniciar sesión con su cuenta, obtener **ProductId** para Power Automate y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="problem"></a>Problema

Verá el siguiente mensaje de error:

> HandleError : No se pudo recuperar la directiva con PolicyId 'AllowSelfServicePurchase', ErrorMessage : se cerró la conexión subyacente: se produjo un error inesperado en un envío.

Esto puede deberse a una versión anterior de Seguridad de la capa de transporte (TLS). Para conectar este servicio, debe usar TLS 1.2 o superior

### <a name="solution"></a>Solución

Actualizar a TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
