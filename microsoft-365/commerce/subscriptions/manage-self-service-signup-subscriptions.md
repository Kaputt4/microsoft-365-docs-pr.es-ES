---
title: Administrar suscripciones de registro de autoservicio
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo administrar suscripciones gratuitas de suscripción de autoservicio para su organización.
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376310"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Administrar suscripciones de registro de autoservicio

## <a name="what-are-self-service-sign-up-subscriptions"></a>¿Qué son las suscripciones de registro de autoservicio?

Hay un número limitado de suscripciones gratuitas de registro de autoservicio disponibles para que los usuarios de su organización puedan registrarse. Un usuario solo puede registrarse y usar una suscripción de registro de autoservicio por sí mismo. Las suscripciones de registro de autoservicio se administran bloqueando el registro de los usuarios y eliminando las suscripciones gratuitas para las que los usuarios se han registrado. Para obtener más información sobre el registro de autoservicio y las suscripciones disponibles, vea Usar el registro de autoservicio [en su organización.](../../admin/misc/self-service-sign-up.md)

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Ver una lista de suscripciones de suscripción de autoservicio

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Libre**. Se muestra una lista de todas las suscripciones de registro de autoservicio.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>¿En qué se diferencian estas suscripciones de las suscripciones de compra de autoservicio?

Las suscripciones de suscripción de autoservicio son gratuitas y están disponibles para una lista más grande de productos que las suscripciones de compra de autoservicio. Cuando un usuario se suscribe a una suscripción de compra de autoservicio, es responsable de pagar por ella. Las suscripciones de compra de autoservicio solo están disponibles para productos de power platform (Power BI, Power Apps y Power Automate), Project y Visio. Para obtener más información, vea [preguntas más frecuentes sobre la compra de autoservicio.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Impedir que los usuarios se suscriba

Use el cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) con el parámetro **AllowAdHocSubscriptions** para controlar si los usuarios pueden registrarse para suscripciones de registro de autoservicio. Para obtener más información, [vea ¿Cómo controlo la configuración de autoservicio?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminar una suscripción de registro de autoservicio

> [!IMPORTANT]
> Al eliminar una suscripción de suscripción de autoservicio, se bloquea el acceso de todos los usuarios a sus datos y correos electrónicos y se eliminan todos los datos y el correo electrónico.

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Libre**.
3. Seleccione la suscripción de registro de autoservicio que desea eliminar. 
4. En la página de detalles de la suscripción, en la sección Suscripciones y configuración **de pago,** seleccione **Eliminar suscripción.**
5. En el **panel Eliminar suscripción,** active la casilla y, a continuación, **seleccione Eliminar suscripción.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Tengo una suscripción de registro de autoservicio que bloquea la eliminación de directorios

Los productos de registro de autoservicio para los que los usuarios individuales pueden registrarse también crean un usuario invitado para la autenticación en el directorio de Azure AD. Para evitar la pérdida de datos, estos productos de autoservicio bloquean la eliminación de directorios hasta que se eliminan completamente del directorio. Solo el administrador de Azure AD los puede eliminar. Para obtener más información, [vea Eliminar un directorio en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)