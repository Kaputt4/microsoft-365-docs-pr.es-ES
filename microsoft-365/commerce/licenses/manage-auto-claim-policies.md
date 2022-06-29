---
title: Administrar directivas de reclamación automática
f1.keywords:
- CSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: yinggiy, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_licensing
- AdminSurgePortfolio
description: Obtenga información sobre cómo crear y administrar directivas de notificaciones automáticas que asignan automáticamente licencias a los usuarios para determinadas aplicaciones.
search.appverid: MET150
ms.date: 04/06/2021
ms.openlocfilehash: 76f2742dc97f880c8044def269e3e9517ea4605c
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/29/2022
ms.locfileid: "66493794"
---
# <a name="manage-microsoft-teams-auto-claim-policies"></a>Administración de directivas de notificaciones automáticas de Microsoft Teams

Una directiva de notificación automática permite a los usuarios reclamar automáticamente una licencia para un producto la primera vez que inician sesión en una aplicación. Como administrador, normalmente se asignan licencias a los usuarios manualmente o mediante licencias basadas en grupos. Mediante el uso de directivas de notificación automática, se administran los productos para los que los usuarios pueden reclamar automáticamente licencias. También puede controlar de qué productos proceden esas licencias.

> [!IMPORTANT]
> Actualmente, las directivas de notificaciones automáticas solo están disponibles para Microsoft Teams. Más productos estarán disponibles para su uso en el futuro.

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global, de usuario o de licencia para crear y administrar directivas de notificaciones automáticas. Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](../../admin/add-users/about-admin-roles.md).

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>Activar o desactivar la característica de directiva de notificación automática

De forma predeterminada, la característica de directiva de notificación automática está desactivada. Para poder usar la característica, primero debe activarla. Después de activar la característica, puede crear una directiva de notificación automática.

### <a name="turn-on-auto-claim-policies"></a>Activar directivas de notificación automática

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. En el centro de la página, seleccione el botón **Activar configuración** .

### <a name="turn-off-auto-claim-policies"></a>Desactivar las directivas de notificación automática

Solo un administrador global puede desactivar una configuración de directiva de notificación automática.

1. En el centro de administración, vaya a la página **Configuración** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">de la organización</a> .
2. Cerca de la parte inferior de la tabla, seleccione **Aplicaciones y servicios propiedad del usuario**.
3. En el panel derecho, desactive la casilla **Permitir a los usuarios reclamar automáticamente licencias la primera vez que inicien sesión**.

Si ya tiene una directiva activa, pero no quiere que más usuarios reclame licencias, [desactive la directiva](#turn-a-policy-on-or-off). Al desactivar una directiva de notificación automática, no más usuarios pueden reclamar una licencia a partir de ese momento. Los usuarios que ya han reclamado una licencia no pierden su licencia.

## <a name="create-an-auto-claim-policy"></a>Creación de una directiva de notificación automática

En la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a> se enumeran las directivas que se crean. En esta pestaña, puede ver: el nombre de la directiva, la aplicación asociada a la directiva, el producto asignado a la directiva, el número de licencias disponibles y el estado de la directiva.

Al crear una directiva de notificación automática, puede agregarle un producto de copia de seguridad. Si el producto principal no tiene licencias, el producto de copia de seguridad se usa para asignar licencias a los usuarios. Puede agregar hasta cuatro productos de copia de seguridad y [cambiar el orden en que se usan](#change-the-assigning-order-for-backup-products). Para obtener más información, consulte [Agregar o quitar productos de copia de seguridad](#add-or-remove-backup-products).

> [!NOTE]
> Actualmente, solo puede crear una directiva de notificación automática. El número de directivas que puede crear aumentará a medida que más productos puedan usar esta característica.

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione **Agregar una directiva**.
3. En la página **Nombre de esta directiva de notificación automática** , escriba un nombre para la directiva y, a continuación, seleccione **Siguiente**.
4. En la página **Establecer una aplicación de notificación automática y un producto** , seleccione una aplicación y la suscripción desde la que asignar licencias.
5. Si desea agregar un producto de copia de seguridad, seleccione **Agregar un producto de copia de seguridad a esta directiva** y, a continuación, seleccione el producto en la lista.
6. Seleccione **Siguiente**.
7. En la página **Seleccionar aplicaciones** , desactive o seleccione los cuadros para que las aplicaciones se excluyan o incluyan con la licencia y, a continuación, seleccione **Siguiente**.
8. Si ha agregado uno o varios productos de copia de seguridad, repita el paso 7 para cada producto. De lo contrario, vaya al paso 9.
9. En la página **Revisar y finalizar** , compruebe la nueva información de directiva, realice los cambios necesarios y, a continuación, seleccione **Crear directiva**.
10. Seleccione **Cerrar**.

## <a name="turn-a-policy-on-or-off"></a>Activar o desactivar una directiva

Al desactivar una directiva, no más usuarios pueden reclamar licencias en virtud de esa directiva. El cambio no afecta a los usuarios que ya han reclamado licencias en virtud de esa directiva.

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione la directiva que desea editar.
3. En el panel de detalles, en **Activar o desactivar esta directiva**, active o desactive la casilla.
4. Seleccione **Guardar** para cerrar el panel de detalles.

## <a name="edit-the-policy-friendly-name"></a>Editar el nombre descriptivo de la directiva

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione la directiva que desea editar.
3. En el panel de detalles, en la sección **Nombre de** directiva, seleccione **Editar**.
4. Escriba un nuevo nombre de directiva y, a continuación, seleccione **Guardar**.
5. Seleccione **Guardar** para cerrar el panel de detalles.

## <a name="add-or-remove-backup-products"></a>Adición o eliminación de productos de copia de seguridad

Al crear una directiva, se agrega un producto a ella. Las licencias se asignan automáticamente a los usuarios de ese grupo de licencias. Puede agregar o quitar productos para una directiva de notificación automática en cualquier momento. Si ya tiene un producto asociado a la directiva, los productos que agregue se considerarán productos de copia de seguridad. Cuando se usa el número disponible de licencias del primer producto, la directiva usa el siguiente producto de copia de seguridad de la lista para asignar licencias. [Puede reordenar la lista de productos](#change-the-assigning-apps-and-services) como desee.

Al quitar un producto de copia de seguridad, ya no se usa para asignar licencias. Los usuarios con una licencia existente siguen teniendo esa licencia, pero ningún usuario nuevo puede recibir licencias para ese producto.

> [!NOTE]
> Una directiva de notificación automática debe contener al menos un producto. No se pueden quitar todos los productos de una directiva. Si ya no desea asignar licencias de una directiva de notificación automática específica, [desactive la directiva](#view-an-auto-claim-policy-report).

### <a name="add-a-backup-product"></a>Agregar un producto de copia de seguridad

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione la directiva que desea editar.
3. En el panel de detalles, en la parte inferior, seleccione **Agregar un producto de copia de seguridad a esta directiva**.
    > [!NOTE]
    > Si no ve este vínculo, es porque solo tiene un producto asociado a su cuenta.
4. En el panel **Agregar un producto** , use la lista desplegable para elegir un producto que agregar a la directiva y, a continuación, seleccione **Agregar**.
5. Seleccione **Guardar** para cerrar el panel de detalles.

### <a name="remove-a-backup-product"></a>Eliminación de un producto de copia de seguridad

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione la directiva que desea editar.
3. En el panel de detalles, en la parte inferior, seleccione **Quitar un producto**.
4. En el panel **Quitar un producto del panel de directivas** , seleccione el cuadro de la directiva que desea quitar y, a continuación, seleccione **Guardar**.
5. Cierre el panel de detalles.

## <a name="change-the-assigning-apps-and-services"></a>Cambiar la asignación de aplicaciones y servicios

Cada producto tiene una colección de aplicaciones y servicios asociados. Para cada producto de la directiva de notificaciones automáticas, puede especificar qué aplicaciones y servicios incluir cuando un usuario tiene asignada automáticamente una licencia a ese producto.

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione la directiva que desea editar.
3. En el panel de detalles, en **Aplicaciones y servicios**, seleccione **Editar**.
4. En el panel **Aplicaciones y servicios** , en la lista desplegable **Producto** , seleccione un solo producto o seleccione **Todos los productos**.
5. Active o desactive las casillas de las aplicaciones y servicios a los que quiere que los usuarios tengan o no acceso.
6. Cuando haya terminado, seleccione **Guardar** y cierre el panel de detalles.

## <a name="change-the-assigning-order-for-backup-products"></a>Cambiar el orden de asignación de los productos de copia de seguridad

Si tiene productos de copia de seguridad asignados a la directiva, puede cambiar el orden en el que se usan para asignar licencias cuando los usuarios inician sesión en la aplicación.

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione la directiva que desea editar.
3. En el panel de detalles, en la sección **Licencias de producto** , seleccione el cuadro situado junto al producto que desea mover y, a continuación, seleccione **Subir** o **Bajar**.
4. Repita el paso 3 para cada producto que quiera reordenar.
5. Cuando haya terminado de reordenar los productos, seleccione **Guardar** para cerrar el panel de detalles.

## <a name="view-an-auto-claim-policy-report"></a>Visualización de un informe de directiva de notificación automática

1. En el Centro de administración, vaya a la página **Licencias** de **facturación** \> y, a continuación, seleccione la pestaña <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">Directiva de notificación automática</a>.
2. Seleccione **Ver informe**. En la página **Informe de directivas de notificación automática** se enumeran todas las licencias asignadas de cada directiva en los últimos 90 días. De forma predeterminada, la página muestra los últimos 90 días.
3. Para cambiar el período de tiempo que se muestra, seleccione la lista desplegable **Últimos 30 días** . Puede ver los informes de los últimos 1, 7, 30 y 90 días.

## <a name="next-steps"></a>Pasos siguientes

Puede volver periódicamente a la pestaña **Directiva de notificación automática** para ver una lista de los usuarios que han reclamado licencias en las directivas que ha creado.

## <a name="related-content"></a>Contenido relacionado

[Asignar licencias a los usuarios](../../admin/manage/assign-licenses-to-users.md) (artículo)\
[Comprar o quitar licencias de suscripción](buy-licenses.md) (artículo)\
[Descripción de las suscripciones y licencias](subscriptions-and-licenses.md) (artículo)
