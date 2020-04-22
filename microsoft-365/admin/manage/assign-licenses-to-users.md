---
title: Asignar licencias a los usuarios
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
search.appverid:
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 997596b5-4173-4627-b915-36abac6786dc
description: Obtenga información sobre cómo asignar licencias a usuarios o mover usuarios a una suscripción nueva.
ms.openlocfilehash: 2019aeef0d802e92489b09bbddb564c4ecded8c0
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628249"
---
# <a name="assign-licenses-to-users"></a>Asignar licencias a los usuarios

::: moniker range="o365-worldwide"

Puede asignar licencias a los usuarios en la página **usuarios activos** o en la página **licencias**. El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>Asignar licencias a los usuarios en la página licencias

Al usar la página de **licencias** de para asignar licencias, asigna licencias para un producto específico a un máximo de 20 usuarios. En la página **licencias**, verá una lista de todos los productos para los que tiene suscripciones, junto con el número total de licencias de cada producto, cuántas licencias están asignadas y cuántas están disponibles.

1. En el centro de administración de, vaya a la página de **facturación**><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licencias</a>.
2. Seleccione un producto para el que quiera asignar licencias.
3. Seleccione **asignar licencias**.
4. En el panel **asignar licencias a usuarios**, empiece a escribir un nombre y elíjalo en los resultados para agregarlo a la lista. Puede agregar hasta 20 usuarios a la vez.
5. Seleccione **activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos.
6. Cuando termine, seleccione **Asignar** y haga clic en **Cerrar**.

Si hay un conflicto, se muestra un mensaje que indica cuál es el problema y cómo corregirlo. Por ejemplo, si seleccionó licencias que contienen servicios en conflicto, el mensaje de error indica que debe revisar los servicios incluidos en cada licencia y volver a intentarlo.

Para cambiar las aplicaciones y los servicios a los que tiene acceso un usuario:

1. Seleccione la fila que contiene el usuario.
2. En el panel derecho, active o desactive las aplicaciones y servicios a los que quiere dar o quitar acceso.
3. Cuando haya terminado, seleccione **guardar** y haga clic en **cerrar**.

::: moniker-end

## <a name="assign-licenses-to-multiple-users-on-the-active-users-page"></a>Asignar licencias a varios usuarios en la página usuarios activos

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione los círculos que se encuentra junto a los nombres de los usuarios a los que quiere asignar licencias.

3. En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.

4. En el panel **administrar licencias de producto**, seleccione **agregar a las asignaciones de licencias de producto existentes** \> **siguiente**.

5. En el panel **agregar a los productos existentes**, cambie el botón de alternancia a la posición de **activado** para la licencia que quiere que tengan los usuarios seleccionados.

    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.

6. En la parte inferior del panel, seleccione **agregar** \> **cerrar**.  

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione las casillas situadas junto a los nombres de los usuarios a los que quiere asignar licencias.

3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.

4. En el panel **Asignar productos**, seleccione **Agregar a las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Sitúe el botón de alternancia en la posición **Activado** para las licencias que quiere que tengan los usuarios seleccionados.

    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.

6. En la parte inferior del panel **Agregar a los productos existentes**, seleccione **Agregar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione las casillas situadas junto a los nombres de los usuarios a los que quiere asignar licencias.

3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.

4. En el panel **Asignar productos**, seleccione **Agregar a las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Sitúe el botón de alternancia en la posición **Activado** para las licencias que quiere que tengan los usuarios seleccionados.

    De forma predeterminada, todos los servicios asociados con esas licencias se asignan automáticamente a los usuarios. Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios.

6. En la parte inferior del panel **Agregar a los productos existentes**, seleccione **Agregar** \> **Cerrar** \> **Cerrar**.

::: moniker-end


## <a name="assign-licenses-to-one-user-on-the-active-users-page"></a>Asignar licencias a un usuario en la página usuarios activos

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. En la página **usuarios activos**, seleccione la fila del usuario al que quiere asignar una licencia.

3. En el panel derecho, seleccione **licencias y aplicaciones**.

4. Expanda la sección **licencias**, active las casillas de las licencias que quiera asignar y seleccione **guardar los cambios**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Seleccione el cuadro junto al nombre del usuario al que quiere asignar una licencia.

3. En el panel derecho, en la fila **licencias de producto**, seleccione **editar**.

4. En el panel **Licencias de producto**, sitúe el botón de alternancia en la posición **Activada** para la licencia que quiera asignar a este usuario.

    De manera predeterminada, todos los servicios asociados a esa licencia se asignan automáticamente al usuario. Puede limitar los servicios que están disponibles para el usuario. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario.

5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Seleccione el cuadro junto al nombre del usuario al que quiere asignar una licencia.

3. En el panel derecho, en la fila **licencias de producto**, seleccione **editar**.

4. En el panel **Licencias de producto**, sitúe el botón de alternancia en la posición **Activada** para la licencia que quiera asignar a este usuario.

    De manera predeterminada, todos los servicios asociados a esa licencia se asignan automáticamente al usuario. Puede limitar los servicios que están disponibles para el usuario. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario.

5. En la parte inferior del panel **Licencias de producto**, elija **Guardar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

## <a name="move-users-to-a-different-subscription"></a>Mover usuarios a una suscripción diferente

Si dispone de más de una suscripción y algunos usuarios ya tienen una licencia para una suscripción pero desea moverlos a otra, puede reemplazar su licencia existente por una distinta.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

2. Seleccione los círculos que se encuentra junto a los nombres de los usuarios para los que quiere reemplazar las licencias existentes.

3. En la parte superior, seleccione **más opciones (...)** y seleccione **administrar licencias de producto**.

4. En el panel **administrar licencias de producto**, seleccione **reemplazar las asignaciones de licencias de producto existentes** \> **siguiente**.

5. Sitúe el botón de alternancia en la posición **Activada** para las licencias que quiere asignar a estos usuarios.

    Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tengan los usuarios. Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Usuarios activos</a>.

2. Active las casillas junto a los nombres de los usuarios a los que quiere reemplazar las licencias existentes.

3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.

4. En el panel **Asignar productos**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Sitúe el botón de alternancia en la posición **Activada** para las licencias que quiere asignar a estos usuarios.

    Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario. Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

2. Active las casillas junto a los nombres de los usuarios a los que quiere reemplazar las licencias existentes.

3. En el panel **Acciones en masa**, elija **Editar licencias de producto**.

4. En el panel **Asignar productos**, seleccione **Reemplazar las asignaciones de licencias de producto existentes** \> **Siguiente**.

5. Sitúe el botón de alternancia en la posición **Activada** para las licencias que quiere asignar a estos usuarios.

    Puede limitar los servicios que están disponibles para los usuarios. Cambie el botón de alternancia a la posición de **desactivado** para los servicios que no quiere que tenga el usuario. Cualquier asignación de licencia anterior para los usuarios seleccionados se quitará.

6. En la parte inferior del panel **Reemplazar productos existentes**, seleccione **Reemplazar** \> **Cerrar** \> **Cerrar**.

::: moniker-end

## <a name="what-you-need-to-know-about-assigning-licenses-to-users"></a>Todo lo que debe saber sobre la asignación de licencias a usuarios

- Debe ser un administrador global, administrador de facturación, administrador de licencias o administrador de administración de usuarios. Para obtener más información, consulte [Información sobre los roles de administrador de Microsoft 365](../add-users/about-admin-roles.md).

- Puede [asignar licencias a cuentas de usuario con PowerShell de Office 365](https://go.microsoft.com/fwlink/p/?linkid=850410).

- Siga estos pasos para agregar una licencia a una cuenta de usuario existente: [Obtenga información sobre cómo agregar una cuenta de usuario y asignar una licencia al mismo tiempo](../add-users/add-users.md).

- Algunos servicios, como Sway, se asignan automáticamente a los usuarios y no es necesario que los asigne individualmente.

## <a name="related-articles"></a>Artículos relacionados

[Entender las suscripciones y licencias](../../commerce/licenses/subscriptions-and-licenses.md)

[Solucionar conflictos de licencias en Microsoft 365 para empresas](resolve-license-conflicts.md)

[Quitar licencias de usuarios](remove-licenses-from-users.md)

[Eliminar licencias de la suscripción](../../commerce/licenses/remove-licenses-from-subscription.md)

[Comprar licencias para la suscripción](../../commerce/licenses/buy-licenses.md)
