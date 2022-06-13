---
title: Visualización de los roles de Azure Active Directory en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: magarlan, chrigreen
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolib
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los técnicos del proveedor de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo ver los roles de Azure Active Directory (Azure AD) en los distintos inquilinos de clientes que administra su organización.
ms.openlocfilehash: 6f12bef7a1e7958b345a86dbc9d0e2ee76534885
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2022
ms.locfileid: "66011825"
---
# <a name="view-your-azure-active-directory-roles-in-microsoft-365-lighthouse"></a>Visualización de los roles de Azure Active Directory en Microsoft 365 Lighthouse

En este artículo se proporcionan instrucciones sobre cómo ver los roles de Azure Active Directory (Azure AD) en los distintos inquilinos de clientes que administra la organización. El rol determina qué acciones puede realizar en Lighthouse.

## <a name="before-you-begin"></a>Antes de empezar

Debe tener acceso a un inquilino de asociado que se haya incorporado al servicio Microsoft 365 Lighthouse.

## <a name="view-your-roles"></a>Visualización de los roles

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione cualquier nombre de inquilino para abrir la página **Información general** del inquilino.

3. Junto a **Roles**, seleccione el vínculo que indica el número de roles que tiene en el inquilino. Se abre **la página Roles** .

    Si tiene uno o varios roles en un inquilino de cliente, verá una marca de verificación verde en la columna **Habilitado** para ese inquilino, junto con el número de roles que tiene. Si no tiene ningún rol en un inquilino, verá una **X** roja.
 
4. En el caso de los inquilinos de clientes con una marca de verificación verde junto a ellos, expanda el inquilino para ver la lista de roles que tiene en ese inquilino. Para obtener más información sobre los roles de Azure AD y los permisos que conceden, consulte [Roles integrados de Azure AD](/azure/active-directory/roles/permissions-reference).

    La página **Roles** también muestra las etiquetas personalizadas que se han aplicado a los inquilinos. Puede filtrar los datos de la página por roles o etiquetas asignados.

## <a name="next-steps"></a>Siguientes pasos

Si no tiene permiso para realizar una acción que necesita realizar en Lighthouse, póngase en contacto con un administrador del inquilino del asociado que pueda asignarle el rol adecuado para la acción que intenta realizar.

## <a name="related-content"></a>Contenido relacionado

[Introducción a los permisos en Microsoft 365 Lighthouse](m365-lighthouse-overview-of-permissions.md) (artículo)\
[Administración de la lista de inquilinos en Microsoft 365 Lighthouse](m365-lighthouse-manage-tenant-list.md) (artículo)
