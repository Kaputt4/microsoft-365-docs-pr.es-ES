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
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Usar AllowSelfServicePurchase para el módulo de PowerShell MSCommerce

El módulo de PowerShell **MSCommerce** ahora está disponible en la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery). El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras sin servicio de asistencia.

Puede usar el módulo de PowerShell **MSCommerce** para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase** (si está habilitado o deshabilitado)
- Ver una lista de los productos aplicables y si la compra de servicios automáticos está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

## <a name="requirements"></a>Requisitos

Para usar el módulo de PowerShell **MSCommerce** , necesita:

- Un dispositivo con Windows 10
- Permisos de administrador para el dispositivo
- Rol de administrador global o de facturación para su espacio empresarial

## <a name="install-the-mscommerce-powershell-module"></a>Instalar el módulo de PowerShell MSCommerce

Instale el módulo de PowerShell **MSCommerce** en su dispositivo con Windows 10 y, a continuación, impórtelo en cada sesión de PowerShell que inicie. Descargue el módulo de PowerShell **MSCommerce** de la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Para instalar el módulo de PowerShell **MSCommerce** con **PowerShellGet**, ejecute el siguiente comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importar MSCommerce en la sesión de PowerShell

Después de instalar el módulo en el dispositivo con Windows 10, se importa a cada sesión de PowerShell que se inicie. Para importarla en una sesión de PowerShell, ejecute el siguiente comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conectarse a MSCommerce con sus credenciales

Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.

```powershell
Connect-MSCommerce
```

Este comando conecta la sesión actual de PowerShell con un inquilino de Azure Active Directory. El comando le pedirá un nombre de usuario y una contraseña para el inquilino al que desea conectarse. Si está habilitada la autenticación multifactor para sus credenciales, puede usar la opción interactiva para iniciar sesión.

## <a name="view-details-for-allowselfservicepurchase"></a>Ver detalles de AllowSelfServicePurchase

Para ver una descripción del valor del parámetro **AllowSelfServicePurchase** y el estado predeterminado, en función de la organización, ejecute el siguiente comando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Ver una lista de productos de compra de autoservicio y su estado

Para ver una lista de todos los productos de compra de autoservicio disponibles y el estado de cada uno, ejecute el siguiente comando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

En la siguiente tabla se enumeran los productos disponibles y su **ProductID**.

| Producto | Cuyo |
|-----------------------------|--------------|
| Power apps por usuario | CFQ7TTC0KP0P |
| Potencia automatizada por usuario | CFQ7TTC0KP0N |
| Power BI Pro | CFQ7TTC0L3PB |
| Plan de proyecto 1 | CFQ7TTC0KXND |
| Plan de proyecto 3 | CFQ7TTC0KXNC |
| Visio plan 1 | CFQ7TTC0KXN9 |
| Visio plan 2 | CFQ7TTC0KXN8 |

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

Para deshabilitar la configuración de directiva para un producto específico, ejecute el siguiente comando:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a>Script de ejemplo para deshabilitar AllowSelfServicePurchase

En el ejemplo siguiente se explica cómo importar el módulo **MSCommerce** , iniciar sesión con su cuenta, obtener el **ProductID** para la automatización automática y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="problem"></a>Problema

Verá el siguiente mensaje de error:

> HandleError: no se pudo recuperar la Directiva con PolicyId ' AllowSelfServicePurchase ', ErrorMessage-se ha cerrado la conexión subyacente: se ha producido un error inesperado en un envío.

Esto puede deberse a una versión anterior de la seguridad de la capa de transporte (TLS). Para conectar este servicio, debe usar TLS 1,2 o superior.

### <a name="solution"></a>Solución

Actualización a TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
