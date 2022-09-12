---
title: Uso de AllowSelfServicePurchase para el módulo de PowerShell MSCommerce
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: ''
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_ssp
- AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo usar el cmdlet AllowSelfServicePurchase de PowerShell para activar o desactivar la compra de autoservicio.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 4/7/2022
ms.openlocfilehash: 193aa64216e1ee49822b61a7ac918c2e844dd822
ms.sourcegitcommit: a6cbc057e757771cc0e7b53b184fab9fa53a658a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "67648645"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a>Uso de AllowSelfServicePurchase para el módulo de PowerShell MSCommerce

El módulo **de PowerShell MSCommerce** ya está disponible en [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery). El módulo incluye un valor de parámetro **PolicyID** para **AllowSelfServicePurchase** que le permite controlar si los usuarios de su organización pueden realizar compras de autoservicio.

Puede usar el módulo de PowerShell **MSCommerce** para:

- Ver el estado predeterminado del valor del parámetro **AllowSelfServicePurchase** , independientemente de si está habilitado o deshabilitado.
- Ver una lista de productos aplicables y si la compra de autoservicio está habilitada o deshabilitada
- Ver o modificar la configuración actual de un producto específico para habilitarlo o deshabilitarlo

## <a name="requirements"></a>Requisitos

Para usar el módulo de PowerShell **MSCommerce** , necesita:

- Un dispositivo Windows 10
- PowerShell 5 o posterior. Actualmente, PowerShell 6.x/7.x no es compatible con este módulo.
- Permiso de administrador para el dispositivo
- Rol de Administración global o de facturación para el inquilino

## <a name="install-the-mscommerce-powershell-module"></a>Instalación del módulo de PowerShell MSCommerce

Instale el módulo de PowerShell **MSCommerce** en el dispositivo Windows 10 una vez y, a continuación, impórtelo en cada sesión de PowerShell que inicie. Descargue el módulo **de PowerShell MSCommerce** desde el [Galería de PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).

Para instalar el módulo **de PowerShell MSCommerce** con **PowerShellGet**, ejecute el siguiente comando:

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a>Importación de MSCommerce en la sesión de PowerShell

Después de instalar el módulo en el dispositivo Windows 10, lo importa en cada sesión de PowerShell que inicie. Para importarlo en una sesión de PowerShell, ejecute el siguiente comando:

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a>Conexión a MSCommerce con sus credenciales

Para conectarse al módulo de PowerShell con sus credenciales, ejecute el siguiente comando.

```powershell
Connect-MSCommerce
```

Este comando conecta la sesión actual de PowerShell a un inquilino de Azure Active Directory. El símbolo del sistema le pide un nombre de usuario y una contraseña para el inquilino al que desea conectarse. Si la autenticación multifactor está habilitada para sus credenciales, use la opción interactiva para iniciar sesión.

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

En la tabla siguiente se enumeran los productos disponibles y su **ProductId**.

| Producto | Productid |
|-----------------------------|--------------|
| Power Apps por usuario* | CFQ7TTC0LH2H |
| Power Automate por usuario | CFQ7TTC0KP0N |
| Power Automate RPA | CFQ7TTC0KXG6  |
| Power BI Premium (independiente) | CFQ7TTC0KXG7  |
| Power BI Pro | CFQ7TTC0L3PB |
| Project Plan 1* | CFQ7TTC0HDB1 |
| Project Plan 3* | CFQ7TTC0HDB0 |
| Visio Plan 1* | CFQ7TTC0HD33 |
| Visio Plan 2* | CFQ7TTC0HD32 |
| Windows 365 Enterprise | CFQ7TTC0HHS9 |
| Windows 365 Business | CFQ7TTC0J203 |
| Windows 365 Business con Ventaja híbrida de Windows | CFQ7TTC0HX99 |
| Microsoft 365 F3 | CFQ7TTC0LH05 |
| Dynamics 365 Marketing | CFQ7TTC0LH3N |
| Asociación de marketing de Dynamics 365 | CFQ7TTC0LHWP | 
| Aplicación adicional de marketing de Dynamics 365 | CFQ7TTC0LHVK |
| Aplicación adicional no producción de Dynamics 365 Marketing | CFQ7TTC0LHWM |

*Estos identificadores han cambiado. Si anteriormente bloqueó productos con los identificadores antiguos, se bloquearán automáticamente mediante los nuevos identificadores. No se requiere ningún trabajo adicional.

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a>Ver o establecer el estado de AllowSelfServicePurchase

Después de ver la lista de productos disponibles para la compra de autoservicio, puede ver o modificar la configuración de un producto específico.

Para obtener la configuración de directiva para un producto específico, ejecute el siguiente comando:

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

En el ejemplo siguiente se explica cómo importar el módulo **MSCommerce** , iniciar sesión con su cuenta, obtener **productid** para Power Automate por usuario y, a continuación, deshabilitar **AllowSelfServicePurchase** para ese producto.

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate per user'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

Si hay varios valores para el producto, puede ejecutar el comando individualmente para cada valor, como se muestra en el ejemplo siguiente:

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[0].ProductID -Enabled $false
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product[1].ProductID -Enabled $false
```

## <a name="troubleshooting"></a>Solución de problemas

### <a name="problem"></a>Problema

Verá el siguiente mensaje de error:

> HandleError: no se pudo recuperar la directiva con PolicyId "AllowSelfServicePurchase", ErrorMessage: se cerró la conexión subyacente: se produjo un error inesperado en un envío.

Esto puede deberse a una versión anterior de Seguridad de la capa de transporte (TLS). Para conectar este servicio, debe usar TLS 1.2 o posterior

### <a name="solution"></a>Solución

Actualice a TLS 1.2. La sintaxis siguiente actualiza el protocolo de seguridad ServicePointManager para permitir TLS1.2:

```powershell
 [Net.ServicePointManager]::SecurityProtocol = [Net.ServicePointManager]::SecurityProtocol -bor [Net.SecurityProtocolType]::Tls12
```

Para más información, consulte [Habilitación de TLS 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2).

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a>Contenido relacionado

[Administración de compras de autoservicio (Administración)](manage-self-service-purchases-admins.md) (artículo)

[Preguntas más frecuentes sobre compras de autoservicio](self-service-purchase-faq.yml) (artículo)
