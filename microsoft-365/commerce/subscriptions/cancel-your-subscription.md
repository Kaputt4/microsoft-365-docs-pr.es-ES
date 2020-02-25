---
title: Cancelar la suscripción
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: b1bc0bef-4608-4601-813a-cdd9f746709a
description: Obtenga información sobre cómo cancelar la suscripción de prueba o de pago de Office 365 para empresas o Microsoft 365.
ms.openlocfilehash: d3590f224757265af3107566023413d276443c46
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/24/2020
ms.locfileid: "42245992"
---
# <a name="cancel-your-subscription"></a>Cancelar la suscripción

*Elegibilidad:* Si tiene menos de 25 licencias asignadas a usuarios, puede cancelar la suscripción de prueba de Office 365 para empresas o pago en línea en el centro de administración en cualquier momento. Si tiene más de 25 licencias asignadas a usuarios, [llame al soporte técnico para cancelar la suscripción](../../admin/contact-support-for-business-products.md).

*Reembolso:* Se le devolverá cualquier crédito prorrateado dentro del siguiente ciclo de facturación.

> [!NOTE]
> Si tiene varias suscripciones al mismo producto, como Office 365 Enterprise E3, cancelar una de ellas no afectará a las licencias o los servicios adquiridos dentro de las demás suscripciones.

## <a name="steps-to-cancel-your-subscription"></a>Pasos para cancelar la suscripción

Si agregó su propio nombre de dominio para usarlo con la suscripción, debe quitar el dominio antes de cancelar la suscripción. Para obtener más información, consulte [Quitar dominios de Office 365](../../admin/get-help-with-domains/remove-a-domain.md).

::: moniker range="o365-worldwide"

> [!NOTE]
> Si no usa el nuevo Centro de administración de Microsoft 365, puede activarlo seleccionando **Probar el nuevo centro de administración** ubicado en la parte superior de la página de inicio.

1. En el centro de administración, vaya a **Facturación** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Productos y servicios</a>.

2. Busque la suscripción que desea cancelar y, en **configuración & acciones**, seleccione **Cancelar suscripción**.

3. Revise las fechas importantes, envíe comentarios sobre el motivo de la cancelación y, después, seleccione **Cancelar suscripción**.

    La suscripción ahora aparece en estado **deshabilitado** y se ha reducido la funcionalidad hasta que se elimina. Para obtener más información acerca de lo que puede esperar cuando se cancela una suscripción de pago de Office 365 para empresas, vea [¿Qué pasa con mis datos y mi acceso cuando termina mi suscripción a office 365 para empresas?](what-if-my-subscription-expires.md)

::: moniker-end

::: moniker range="o365-germany"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">suscripciones</a> de **facturación** \> .

2. En la página **suscripciones** , seleccione una suscripción.

3. En el menú **más acciones** , seleccione **Cancelar suscripción**.

    ![Se cierra el menú más acciones.](../../admin/media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)

4. Revise las fechas importantes, envíe comentarios sobre el motivo de la cancelación y, después, seleccione **Cancelar suscripción**.

    La suscripción ahora aparece en estado **deshabilitado** y se ha reducido la funcionalidad hasta que se elimina. Para obtener más información acerca de lo que puede esperar cuando se cancela una suscripción de pago de Office 365 para empresas, vea [¿Qué pasa con mis datos y mi acceso cuando termina mi suscripción a office 365 para empresas?](what-if-my-subscription-expires.md)

::: moniker-end

::: moniker range="o365-21vianet"

1. En el centro de administración, vaya a la página <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">suscripciones</a> de **facturación** \> .

2. En la página **suscripciones** , seleccione una suscripción.

3. En el menú **más acciones** , seleccione **Cancelar suscripción**.

    ![Se cierra el menú más acciones.](../../admin/media/befa74b7-62c1-42a3-a38e-db76a1c97dba.png)

4. Revise las fechas importantes, envíe comentarios sobre el motivo de la cancelación y, después, seleccione **Cancelar suscripción**.

    La suscripción ahora aparece en estado **deshabilitado** y se ha reducido la funcionalidad hasta que se elimina. Para obtener más información acerca de lo que puede esperar cuando se cancela una suscripción de pago de Office 365 para empresas, vea [¿Qué pasa con mis datos y mi acceso cuando termina mi suscripción a office 365 para empresas?](what-if-my-subscription-expires.md)

::: moniker-end


## <a name="other-steps-you-might-have-to-take"></a>Otros pasos que puede que tenga que realizar

### <a name="change-custom-domain-settings"></a>Cambiar la configuración de dominio personalizado

Si usa un dominio personalizado con su suscripción, debe realizar algunos pasos adicionales antes de poder cancelar la suscripción. Si no tiene un dominio personalizado, puede continuar para [guardar los datos](#save-your-data).

#### <a name="change-your-domain-nameserver-records-if-needed"></a>Cambiar los registros del servidor de nombres de dominio (si es necesario)

Si configura un dominio personalizado, agregó registros DNS para que el dominio funcione con los servicios de Office 365. Antes de quitar el dominio, asegúrese de actualizar los registros DNS (por ejemplo, el registro MX del dominio) en el host DNS.

Por ejemplo, cambie el registro MX en su host DNS. El correo electrónico enviado a su dominio deja de ir a su dirección de Office 365 y va a su nuevo proveedor de correo electrónico. (Un registro MX determina dónde se envía el correo electrónico del dominio).

- Si los registros de servidor de nombres (NS) [señalan a Office 365 servidores de nombres](../../admin/setup/add-domain.md), los cambios en el registro mx no surtirán efecto hasta que cambie los registros NS para que apunten a su nuevo host DNS (vea el paso 2).

- Antes de actualizar el registro MX, informe a los usuarios de la fecha en la que planea cambiar el correo electrónico y el nuevo proveedor de correo electrónico que planea usar. Además, si los usuarios quieren migrar su correo electrónico de Office 365 existente al nuevo proveedor, deben realizar pasos adicionales.

- El día en que cambie el registro MX, siga el resto de los pasos de este artículo.

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>Actualizar el dominio MX y otros registros DNS (si está usando un dominio personalizado)

Si ha cambiado los registros de servidor de nombres (NS) a Office 365 al configurar el dominio, debe configurar o actualizar el registro MX y otros registros DNS en el host DNS que va a usar y, a continuación, cambiar el registro NS a ese host DNS.

Si no ha cambiado los registros NS cuando configuró el dominio, al cambiar el registro MX, el correo empieza a ir directamente a la nueva dirección.

Para obtener más información, vea [¿Cómo administra Office 365 mis registros DNS?](../../admin/setup/domains-faq.md#how-does-office-365-manage-my-dns-records). Para cambiar los registros NS, vea [quitar un dominio de Office 365](../../admin/get-help-with-domains/remove-a-domain.md).

### <a name="save-your-data"></a>Guardar los datos

Cuando la cancelación sea efectiva, los usuarios perderán el acceso a sus datos. Antes de cancelar la suscripción, pídale que guarde los archivos de OneDrive para la empresa o de SharePoint Online en otra ubicación. Es posible que los datos de los clientes que se dejen se eliminen transcurridos 30 días y que se eliminen a más tardar de 180 días después de la cancelación.

- Para mover el correo electrónico, los contactos, las tareas y la información de calendario a otra cuenta, vea [Exportar o realizar copias de seguridad de correo electrónico, contactos y calendario en un archivo .pst de Outlook](https://support.office.com/article/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx).

- Para guardar una biblioteca de documentos o el contenido de una lista (como los contactos) de un entorno de SharePoint Online (sitios de grupo o OneDrive para la Empresa) en recursos compartidos de archivos o en un equipo local, consulte [Migración manual del contenido de SharePoint Online](https://support.microsoft.com/kb/2783484).

### <a name="uninstall-office-optional"></a>Desinstalar Office (opcional)

Si ha cancelado la suscripción y no ha trasladado a los usuarios a otra suscripción que incluya Office, Office 365 se ejecuta en modo de funcionalidad reducida. Cuando esto ocurre, los usuarios solo pueden leer e imprimir documentos y las aplicaciones de Office 365 muestran [notificaciones de producto sin licencia](https://support.office.com/article/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx). Para evitar confusiones, solicite a los usuarios que [desinstalen Office](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx) de sus equipos.

## <a name="related-articles"></a>Artículos relacionados

[Renovar la suscripción](renew-your-subscription.md)

[Reactivar la suscripción](reactivate-your-subscription.md)

[Cambiar a un plan o una suscripción diferentes](switch-to-a-different-plan.md)
