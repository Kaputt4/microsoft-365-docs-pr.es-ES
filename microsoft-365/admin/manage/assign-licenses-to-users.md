---
title: Asignar licencias a los usuarios
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Obtenga información sobre cómo asignar las licencias a los usuarios.
ms.date: 08/14/2020
ms.openlocfilehash: fc5f9112a22d56abb9c11d61f4108586487b4986
ms.sourcegitcommit: 806536f859ac864228797f1f2f23b8f41040a6b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/28/2020
ms.locfileid: "49735803"
---
# <a name="assign-licenses-to-users"></a>Asignar licencias a los usuarios

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Puede asignar licencias a los usuarios en la página **usuarios activos** o en la página **licencias**. El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.

::: moniker-end

[Obtenga información sobre cómo agregar un usuario y asignar una licencia al mismo tiempo](../add-users/add-users.md).

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser un administrador global, de licencia o de usuarios para asignar licencias. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).
- Puede [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://go.microsoft.com/fwlink/p/?linkid=850410).
- Para usar las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Algunos servicios, como Sway, se asignan automáticamente a los usuarios y no es necesario que los asigne individualmente.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Use la página de licencias para asignar licencias a los usuarios

Al usar la página de **licencias** de para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios. En la página de **licencias**, verá una lista de todos los productos para los que tiene suscripciones. También verá el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.

1. En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.
2. Seleccione un producto.
3. En la página de detalles del producto, seleccione **Asignar licencias**.
4. En el panel **asignar licencias a usuarios**, empiece a escribir un nombre y elíjalo en los resultados para agregarlo a la lista. Puede agregar hasta 20 usuarios a la vez.
5. Seleccione **activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos.
6. Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.

Si hay un conflicto, se muestra un mensaje que indica cuál es el problema y cómo corregirlo. Por ejemplo, si seleccionó licencias que contienen servicios en conflicto, el mensaje de error indica que debe revisar los servicios incluidos en cada licencia y volver a intentarlo.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Cambiar las aplicaciones y los servicios a los que tiene acceso un usuario

1. En el centro de administración, vaya a la página de **Facturación** ><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.
2. En la página **Licencias**, seleccione la fila para un usuario específico.
3. En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.
4. Cuando haya terminado, seleccione **guardar** y haga clic en **cerrar**.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>Use la página Usuarios activos para asignar licencias

Cuando usa la página **Usuarios activos** para asignar licencias, asigna licencias de usuarios a los productos.

### <a name="assign-licenses-to-multiple-users"></a>Asignar licencias a varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione los círculos que se encuentran junto a los nombres de los usuarios a los que quiere asignarles licencias.
3. En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.
4. En el panel **administrar licencias de producto**, seleccione **agregar a las asignaciones de licencias de producto existentes** \> **siguiente**.
5. En el panel **Agregar a los productos existentes**, cambie el botón a la posición de **Activado** para la licencia que quiere que tengan los usuarios seleccionados.\
    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.
6. En la parte inferior del panel, seleccione **agregar** \> **cerrar**.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>Asignar licencias a varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
2. Seleccione los cuadros junto a los nombres de los usuarios a los que quiere asignar licencias.
3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.
4. En el panel **Asignar productos**, seleccione **Agregar a las asignaciones de licencias de producto existentes** \> **Siguiente**.
5. Sitúe el botón en la posición **Activado** para las licencias que quiere que tengan los usuarios seleccionados.\
    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.
6. En la parte inferior del panel **Agregar a los productos existentes**, seleccione **Agregar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>Asignar licencias a varios usuarios

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
2. Seleccione los cuadros junto a los nombres de los usuarios a los que quiere asignar licencias.
3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.
4. En el panel **Asignar productos**, seleccione **Agregar a las asignaciones de licencias de producto existentes** \> **Siguiente**.
5. Sitúe el botón en la posición **Activado** para las licencias que quiere que tengan los usuarios seleccionados.\
    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.
6. En la parte inferior del panel **Agregar a los productos existentes**, seleccione **Agregar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>Asignar licencias a un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.
2. Seleccione la fila del usuario al que quiere asignar una licencia.
3. En el panel derecho, seleccione **licencias y aplicaciones**.
4. Expanda la sección **licencias**, active las casillas de las licencias que quiera asignar y seleccione **guardar los cambios**.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>Asignar licencias a un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.
2. Seleccione el cuadro junto al nombre del usuario al que quiere asignar una licencia.
3. En el panel derecho, en la fila **licencias de producto**, seleccione **editar**.
4. En el panel **Licencias de producto**, sitúe el botón en la posición **Activada** para la licencia que quiera asignar a este usuario.\
    De manera predeterminada, todos los servicios asociados a esa licencia se asignan automáticamente al usuario. Puede limitar los servicios que están disponibles para el usuario. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario.
5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>Asignar licencias a un usuario

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.
2. Seleccione el cuadro junto al nombre del usuario al que quiere asignar una licencia.
3. En el panel derecho, en la fila **licencias de producto**, seleccione **editar**.
4. En el panel **Licencias de producto**, sitúe el botón en la posición **Activada** para la licencia que quiera asignar a este usuario.\
    De manera predeterminada, todos los servicios asociados a esa licencia se asignan automáticamente al usuario. Puede limitar los servicios que están disponibles para el usuario. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario.
5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>Asignar una licencia a un usuario invitado

Puede invitar a usuarios para colaborar con su organización en el centro de administración de Azure Active Directory. Para obtener más información sobre los usuarios invitados, vea [¿Qué es el acceso de usuarios invitados en Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b). Si no tiene usuarios invitados, vea [Inicio rápido: agregar usuarios invitados al directorio de Azure Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

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

Si los usuarios aún no tienen aplicaciones de Office instaladas, puede compartir la [Guía de inicio rápido para empleados](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) con los usuarios para que configuren todo, como [cómo descargar e instalar Microsoft 365 u Office 2019 en un equipo Windows o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y [cómo configurar las aplicaciones de Office y el correo electrónico en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenido relacionado

[Entender las suscripciones y las licencias](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)\
[Cancelar asignación a licencias de usuarios](remove-licenses-from-users.md) (artículo)\
[Comprar o quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)
