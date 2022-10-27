---
title: Cambiar un tipo de cuenta de pc en la nube de Windows 365 Business en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: katmartin
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- Tier2
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo establecer o cambiar un tipo de cuenta de pc en la nube de Windows 365 Business.
ms.openlocfilehash: 8220027f771dbe4cdc3e08f040d281f71a84537b
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68732083"
---
# <a name="change-a-windows-365-business-cloud-pc-account-type-in-microsoft-365-lighthouse"></a>Cambiar un tipo de cuenta de pc en la nube de Windows 365 Business en Microsoft 365 Lighthouse

Los técnicos del proveedor de servicios administrados (MSP) pueden establecer el tipo de cuenta de un equipo de Business Cloud o realizar cambios en un tipo de cuenta existente. Están disponibles los siguientes tipos de cuenta:

- **Usuario estándar (recomendado):** las cuentas de usuario estándar tienen permiso para instalar software solo desde Microsoft Store.

- **Administrador local** : las cuentas de administrador local tienen permiso para instalar cualquier software y realizar cambios en cualquier parte del sistema operativo. Seleccione este tipo de cuenta solo cuando sea necesario, ya que el malware puede usar permisos de administrador para infectar o dañar archivos.

> [!NOTE]
> Puede establecer o cambiar el tipo de cuenta solo para equipos en la nube con una licencia de empresa. No se puede cambiar el tipo de cuenta de los equipos en la nube con una licencia enterprise.

## <a name="before-you-begin"></a>Antes de empezar 

Debe ser un administrador Windows 365 o un administrador global en el inquilino del asociado.

## <a name="set-or-change-a-windows-365-business-cloud-pc-account-type"></a>Establecimiento o cambio de un tipo de cuenta de pc en la nube de Windows 365 Business

1.  En el panel de navegación izquierdo de Lighthouse, seleccione **Dispositivos** >  **Windows 365**.

2.  Seleccione la pestaña **Todos los equipos en la nube** .

3.  Use la barra de anotaciones de recuento de colores para explorar en profundidad los equipos en la nube que tienen un estado **Aprovisionado** .

4.  En el menú desplegable **Filtros** , seleccione el tipo de licencia **Business** para ver una lista de todos los equipos en la nube con una licencia empresarial dentro de los inquilinos del cliente.

5.  En la lista de equipos en la nube, seleccione el equipo en la nube para el que desea cambiar el tipo de cuenta.

6.  En el panel de detalles del equipo en la nube, seleccione **Cambiar tipo de cuenta**.

7.  En el panel **Cambiar tipo de cuenta de PC** en la nube, seleccione el tipo de cuenta para el equipo en la nube y, a continuación, seleccione **Guardar**.

## <a name="next-steps"></a>Pasos siguientes

Una vez aplicada la actualización, el usuario asignado del equipo en la nube tendrá que volver a iniciar sesión en el equipo en la nube o reiniciar el dispositivo. Los nuevos cambios pueden tardar varios minutos en aparecer en Microsoft 365 Lighthouse. El administrador de PC en la nube también puede reiniciar de forma remota el equipo en la nube, pero el usuario puede perder los datos no guardados.

## <a name="related-content"></a>Contenido relacionado

[Control de acceso basado en rol de PC en la nube](/windows-365/enterprise/role-based-access) (artículo)\
[Información general de la página Windows 365 (PC en la nube) de Microsoft 365 Lighthouse](m365-lighthouse-win365-page-overview.md) (artículo)\
[Reprovisionar un PC en la nube Windows 365 en Microsoft 365 Lighthouse](m365-lighthouse-reprovision-cloudpc.md) (artículo)
