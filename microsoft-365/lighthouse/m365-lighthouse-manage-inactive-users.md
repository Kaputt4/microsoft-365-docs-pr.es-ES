---
title: Administración de usuarios inactivos en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo administrar usuarios inactivos.
ms.openlocfilehash: 3763ed3ca8ed36ea9d944a2847a7465b73da647d
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479604"
---
# <a name="manage-inactive-users-in-microsoft-365-lighthouse"></a>Administración de usuarios inactivos en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse proporciona visibilidad sobre todos los usuarios de los inquilinos administrados que han estado inactivos durante más de seis meses. Las cuentas inactivas pueden presentar riesgos de seguridad y vincular licencias sin usar. En la página **Usuarios inactivos** , puede realizar un seguimiento y limpiar las cuentas inactivas.

Lighthouse usa la actividad de inicio de sesión para detectar cuentas de usuarios inactivos. La página **Usuarios inactivos** muestra hasta 500 cuentas inactivas para cada inquilino.

## <a name="review-inactive-users"></a>Revisión de usuarios inactivos

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración de cuentas **de usuarios** > **> usuarios inactivos**.

2. En la pestaña **Usuarios inactivos** , establezca los filtros en el resultado deseado.

3. En la lista de inquilinos, expanda cualquier inquilino para ver una lista de usuarios inactivos dentro del inquilino.

4. Seleccione cualquier usuario para abrir el panel de detalles del usuario y ver más información sobre la cuenta.

5. Una vez que haya determinado que ya no se necesita una cuenta de usuario, puede eliminarla o bloquearla. Como mínimo, debe bloquear la cuenta de usuario para reducir los riesgos de seguridad. En el panel de detalles del usuario, seleccione **Bloquear inicio de sesión** o **Eliminar usuario**.

## <a name="block-sign-in-for-multiple-user-accounts"></a>Bloquear el inicio de sesión para varias cuentas de usuario

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de cuentas** **de usuarios** >  >**usuarios inactivos**.

2. En la pestaña **Usuarios inactivos** , expanda cualquier inquilino de la lista para ver una lista de usuarios inactivos dentro del inquilino, seleccione los usuarios que desea bloquear y, a continuación, seleccione **Bloquear inicio de sesión**.

3. En el panel **Administrar estado de inicio de sesión** , seleccione **Bloquear el inicio de sesión de los usuarios**.

4. Seleccione **Guardar**.

## <a name="related-content"></a>Contenido relacionado

[Administración de cuentas de usuario inactivas en Azure AD](/azure/active-directory/reports-monitoring/howto-manage-inactive-user-accounts) (artículo)
