---
title: Asignar licencias a los usuarios
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce_licensing
search.appverid: MET150
description: Asigne licencias dependiendo de si quiere asignar licencias de producto a usuarios específicos o asignar licencias de usuarios a un producto específico.
ms.date: 04/26/2021
ms.openlocfilehash: 707c1c952aa737f0aa91d886e9fa304eabe26321
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537540"
---
# <a name="assign-licenses-to-users"></a>Asignar licencias a los usuarios

Puede asignar licencias a los usuarios en la página **usuarios activos** o en la página **licencias**. El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.

> [!NOTE]
> Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización. Puede [apoderarse de una suscripción de compra de autoservicio](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.

[Obtenga información sobre cómo agregar un usuario y asignar una licencia al mismo tiempo](../add-users/add-users.md).

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global, de licencia o de usuarios para asignar licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).
- Puede [asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Para usar las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Algunos servicios, como Sway, se asignan automáticamente a los usuarios y no es necesario que los asigne individualmente.


## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Use la página de licencias para asignar licencias a los usuarios

Al usar la página de **licencias** de para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios. En la página de **licencias**, verá una lista de todos los productos para los que tiene suscripciones. También verá el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end


2. Seleccione un producto.
3. En la página de detalles del producto, seleccione **Asignar licencias**.
4. En el panel **asignar licencias a usuarios**, empiece a escribir un nombre y elíjalo en los resultados para agregarlo a la lista. Puede agregar hasta 20 usuarios a la vez.
4. Seleccione **activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos.
6. Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.

Si hay un conflicto, se muestra un mensaje que indica cuál es el problema y cómo corregirlo. Por ejemplo, si seleccionó licencias que contienen servicios en conflicto, el mensaje de error indica que debe revisar los servicios incluidos en cada licencia y volver a intentarlo.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Cambiar las aplicaciones y los servicios a los que tiene acceso un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end


2. En la página **Licencias**, seleccione la fila para un usuario específico.
3. En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.
4. Cuando haya terminado, seleccione **guardar** y haga clic en **cerrar**.

## <a name="use-the-active-users-page-to-assign-licenses"></a>Use la página Usuarios activos para asignar licencias

Cuando usa la página **Usuarios activos** para asignar licencias, asigna licencias de usuarios a los productos.

### <a name="assign-licenses-to-multiple-users"></a>Asignar licencias a varios usuarios

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end


2. Seleccione los círculos que se encuentran junto a los nombres de los usuarios a los que quiere asignarles licencias.
3. En la parte superior, seleccione los tres puntos (Más acciones) y, después, seleccione **Administrar licencias de producto**.
4. En el panel **administrar licencias de producto**, seleccione **agregar a las asignaciones de licencias de producto existentes** \> **siguiente**.
5. En el panel **Agregar a los productos existentes**, cambie el botón a la posición de **Activado** para la licencia que quiere que tengan los usuarios seleccionados.\
    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.
6. En la parte inferior del panel, seleccione **agregar** \> **cerrar**.  


> [!NOTE]
> Si quiere asignar licencias para un gran número de usuarios, use la opción [Asignar licencias a usuarios por pertenencia a grupos en Azure Active Directory.](/azure/active-directory/enterprise-users/licensing-groups-assign)

### <a name="assign-licenses-to-one-user"></a>Asignar licencias a un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-germany"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

::: moniker-end

::: moniker range="o365-21vianet"

 1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end


2. Seleccione la fila del usuario al que quiere asignar una licencia.
3. En el panel derecho, seleccione **licencias y aplicaciones**.
4. Expanda la sección **licencias**, active las casillas de las licencias que quiera asignar y seleccione **guardar los cambios**.

## <a name="assign-a-license-to-a-guest-user"></a>Asignar una licencia a un usuario invitado

Puede invitar a usuarios para colaborar con su organización en el centro de administración de Azure Active Directory. Para obtener más información sobre los usuarios invitados, vea [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b). Si no tiene usuarios invitados, vea [Inicio rápido: agregar usuarios invitados al directorio de Azure Portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

> [!IMPORTANT]
> Para poder realizar estos pasos, debe ser un administrador global.

1. Vaya al <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Centro de administración de Azure Active Directory</a>.
2. En el panel de navegación, seleccione **Usuarios**.
3. En la página **Usuarios | Todos los usuarios (vista previa)**, seleccione **Agregar filtros**.
4. En el menú **Elegir un campo**, seleccione **Tipo de usuario** y, después, seleccione **Aplicar**.
5. En el menú siguiente, seleccione **Invitado**.
6. En la lista de resultados, seleccione el usuario que necesita una licencia.
7. En **Administrar**, seleccione **Licencias**.
8. Seleccione **Asignaciones**.
9. En la página **Actualizar asignaciones de licencia**, seleccione el producto al que quiere asignar una licencia.
10. En la parte derecha, desactive las casillas de los servicios a los que no quiere que el usuario invitado tenga acceso.
11. Seleccione **Guardar**.

## <a name="next-steps"></a>Pasos siguientes

Si los usuarios aún no tienen aplicaciones de Office instaladas, puede compartir la [Guía de inicio rápido para empleados](../../business-video/employee-quick-setup.md) con los usuarios para que configuren todo, como [cómo descargar e instalar Microsoft 365 u Office 2019 en un equipo Windows o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y [cómo configurar las aplicaciones de Office y el correo electrónico en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenido relacionado

[Entender las suscripciones y las licencias](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)\
[Cancelar asignación a licencias de usuarios](remove-licenses-from-users.md) (artículo)\
[Comprar o quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)
