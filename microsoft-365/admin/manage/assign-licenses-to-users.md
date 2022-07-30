---
title: Asignar licencias a usuarios en el centro de administración de Microsoft 365
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: sinakassaw, nicholak
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- VSBFY23
- commerce_licensing
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- business_assist
- okr_SMB
- manage_licenses
- AdminTemplateSet
search.appverid: MET150
description: Asigne licencias dependiendo de si quiere asignar licencias de producto a usuarios específicos o asignar licencias de usuarios a un producto específico.
ms.date: 07/12/2022
ms.openlocfilehash: e18cbae154a85f29194cd3d6c4e4f00d298a7d76
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2022
ms.locfileid: "67084771"
---
# <a name="assign-microsoft-365-licenses-to-users"></a>Asignar licencias de Microsoft 365 a usuarios

Puede asignar licencias a los usuarios en la página **usuarios activos** o en la página **licencias**. El método que use dependerá de si desea asignar licencias de producto a usuarios específicos o si quiere asignar licencias de usuarios a productos específicos.

> [!NOTE]
> 
> - Como administrador, no puede asignar o cancelar la asignación de licencias para una suscripción de compra de autoservicio adquirida por un usuario de su organización. Puede [apoderarse de una suscripción de compra de autoservicio](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) y, a continuación, asignar o cancelar la asignación de licencias.
> - Para algunas suscripciones, solo puede cancelar durante un período de tiempo limitado después de comprar o renovar la suscripción. Si la ventana de cancelación ha pasado, desactive la facturación periódica para cancelar la suscripción al final de su término.

[Obtenga información sobre cómo agregar un usuario y asignar una licencia al mismo tiempo](../add-users/add-users.md).

> [!TIP]
> Si necesita ayuda con los pasos descritos en este tema, considere la posibilidad de [trabajar con un especialista de Microsoft Small Business](https://go.microsoft.com/fwlink/?linkid=2186871). Con Business Assist, usted y sus empleados obtienen acceso de forma ininterrumpida a especialistas de pequeñas empresas a medida que hace crecer su negocio, desde la incorporación hasta el uso diario.

## <a name="before-you-begin"></a>Antes de empezar

- Debe ser administrador global, de licencia o de usuario para asignar licencias. Para obtener más información, vea [Acerca de Microsoft 365 roles de administrador](../add-users/about-admin-roles.md).
- Puede [asignar licencias de Microsoft 365 a cuentas de usuario con PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Para usar las licencias basadas en grupos, vea [Asignar licencias a usuarios por la pertenencia a grupos en Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Algunos servicios, como Sway, se asignan automáticamente a los usuarios y no es necesario que los asigne individualmente.

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Use la página de licencias para asignar licencias a los usuarios

La página **Licencias** le permite asignar o cancelar la asignación de licencias para un máximo de 20 usuarios a la vez. En la página se muestran los productos de su propiedad, el número de licencias disponibles para cada producto y el número de licencias asignadas del total de licencias disponibles.

La página de **licencias** muestra un total agregado de licencias para todas las suscripciones para el mismo nombre de producto. Por ejemplo, podría tener una suscripción para Microsoft 365 Empresa Premium que tenga 5 licencias y otra suscripción que tenga 8 licencias para el mismo producto. En la página **Licencias** se muestra que tiene un total de 13 licencias para Microsoft 365 Empresa Premium en todas sus suscripciones. Esto es diferente de lo que ve en la página **Sus productos**, que muestra una fila para cada suscripción de su propiedad, incluso si son para el mismo producto.

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank"> Licencias</a>.

::: moniker-end

2. Seleccione un producto.

3. En la página de detalles del producto, seleccione **Asignar licencias**.

4. En el panel **Asignar licencias a usuarios**, empiece a escribir un nombre y a continuación selecciónelo en los resultados para agregarlo a la lista. Puede agregar hasta 20 usuarios a la vez.

5. Seleccione **activar o desactivar aplicaciones y servicios** para asignar o quitar el acceso a elementos específicos.

6. Cuando haya terminado, seleccione **Asignar** y, a continuación, cierre el panel derecho.

Si hay un conflicto, verá un mensaje que le indica cuál es el problema y cómo corregirlo. Por ejemplo, si seleccionó licencias que contienen servicios en conflicto, el mensaje de error indica que debe revisar los servicios incluidos en cada licencia y volver a intentarlo.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Cambiar las aplicaciones y los servicios a los que tiene acceso un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página de **Facturación** \><a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank"> Licencias</a>.

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

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Usuarios activos</a>.

::: moniker-end

2. Seleccione los círculos que se encuentran junto a los nombres de los usuarios a los que quiere asignarles licencias.

3. En la parte superior, seleccione **Administrar licencias de producto**.

4. En el panel **Administrar licencias de producto**, seleccione **Asignar más: mantener las licencias existentes y asignar más** \> **Siguiente**.

5. En **Licencias**, seleccione la casilla de las licencias que desea que tengan los usuarios seleccionados.\
    De manera predeterminada, todos los servicios asociados a esas licencias se asignan automáticamente al usuario. Puede limitar los servicios disponibles para el usuario. Quite la selección de las casillas de los servicios que no quiere que tenga el usuario.

6. En la parte inferior del panel, seleccione **Guardar cambios**.  
    Es posible que tenga que comprar otras licencias si no tiene suficientes licencias para todos los usuarios.

> [!NOTE]
> Si quiere asignar licencias para un gran número de usuarios, use la opción [Asignar licencias a usuarios por pertenencia a grupos en Azure Active Directory.](/azure/active-directory/enterprise-users/licensing-groups-assign)

### <a name="assign-licenses-to-one-user"></a>Asignar licencias a un usuario

::: moniker range="o365-worldwide"

1. En el centro de administración, vaya a la página **Usuarios** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Usuarios activos</a>.

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

Si los usuarios aún no tienen aplicaciones de Office instaladas, puede compartir la [Guía de inicio rápido para empleados](../setup/employee-quick-setup.md) con los usuarios para que configuren todo, como [cómo descargar e instalar Microsoft 365 u Office 2019 en un equipo Windows o Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) y [cómo configurar las aplicaciones de Office y el correo electrónico en un dispositivo móvil](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Contenido relacionado

[Entender las suscripciones y las licencias](../../commerce/licenses/subscriptions-and-licenses.md) (artículo)\
[Cancelar asignación a licencias de usuarios](remove-licenses-from-users.md) (artículo)\
[Comprar o quitar las licencias de la suscripción](../../commerce/licenses/buy-licenses.md) (artículo)
