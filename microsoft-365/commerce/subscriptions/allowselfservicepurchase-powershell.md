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
ms.openlocfilehash: fbba7f4385684a8a34f9feebc28a27e8e867bacb
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227480"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Usar AllowSelfServicePurchase para el módulo de PowerShell de MSCommerce

El módulo de PowerShell de **MSCommerce** ya está disponible en la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery). El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras de autoservicio.

Puede usar el módulo **MSCommerce** PowerShell para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase,** independientemente de si está habilitado o deshabilitado.
- Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

## <a name="requirements"></a>Requisitos

Para usar el **módulo de PowerShell de MSCommerce,** necesita:

- Un Windows 10 móvil
- PowerShell 5 o inferior. Actualmente, PowerShell 6.x/7.x no es compatible con este módulo.
- Permiso de administrador para el dispositivo
- Rol de administrador global o de facturación para el inquilino

## <a name="install-the-mscommerce-powershell-module"></a>Instalar el módulo de PowerShell de MSCommerce

El módulo **de PowerShell de MSCommerce** se instala en el dispositivo Windows 10 una vez y, a continuación, se importa en cada sesión de PowerShell que inicie. Descargue el **módulo MSCommerce** PowerShell de la [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Para instalar el **módulo de PowerShell de MSCommerce** con **PowerShellGet,** ejecute el siguiente comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importar MSCommerce a la sesión de PowerShell

Después de instalar el módulo en el dispositivo Windows 10, luego lo importa en cada sesión de PowerShell que inicie. Para importarlo en una sesión de PowerShell, ejecute el siguiente comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conectar a MSCommerce con sus credenciales

Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.

```powershell
Connect-MSCommerce
```

Este comando conecta la sesión actual de PowerShell a un Azure Active Directory inquilino. El comando le pide un nombre de usuario y una contraseña para el espacio empresarial al que desea conectarse. Si la autenticación multifactor está habilitada para sus credenciales, use la opción interactiva para iniciar sesión.

## <a name="view-details-for-allowselfservicepurchase"></a>Ver detalles de AllowSelfServicePurchase

Para ver una descripción del valor del parámetro **AllowSelfServicePurchase** y el estado predeterminado, según la organización, ejecute el siguiente comando:

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a>Ver una lista de productos de compra de autoservicio y su estado

Para ver una lista de todos los productos de compra de autoservicio disponibles y el estado de cada uno, ejecute el siguiente comando:

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

En la tabla siguiente se enumeran los productos disponibles y **su ProductId**.

| Producto | ProductId |
|-----------------------------|--------------|
| Power Apps por usuario | CFQ7TTC0KP0P |
| Power Automate por usuario | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (independiente) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1 | CFQ7TTC0KXND |
| Project Plan 3 | CFQ7TTC0KXNC |
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

En el siguiente ejemplo se explica cómo importar el módulo **MSCommerce,** iniciar sesión con su cuenta, obtener **el ProductId** para Power Automate y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="problem"></a>Problema

Verá el siguiente mensaje de error:

> HandleError: no se pudo recuperar la directiva con PolicyId 'AllowSelfServicePurchase', ErrorMessage: se cerró la conexión subyacente: se produjo un error inesperado en un envío.

Esto puede deberse a una versión anterior de Seguridad de la capa de transporte (TLS). Para conectar este servicio, debe usar TLS 1.2 o posterior

### <a name="solution"></a>Solución

Actualización a TLS 1.2: (/mem/configmgr/core/plan-design/security/enable-tls-1-2)

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>Contenido relacionado

[Administrar compras de autoservicio (administrador)](manage-self-service-purchases-admins.md) (artículo)

[Preguntas más frecuentes sobre la compra de](self-service-purchase-faq.yml) autoservicio (artículo)
