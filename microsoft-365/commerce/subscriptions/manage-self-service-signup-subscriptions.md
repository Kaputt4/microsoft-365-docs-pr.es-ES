---
title: Administrar suscripciones de registro de autoservicio
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: Obtenga información sobre cómo administrar suscripciones de registro de autoservicio gratuitas para su organización.
ms.date: 03/17/2021
ms.openlocfilehash: b469515a649399c71ef64ba2567dfa376f21e9a7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333223"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Administrar suscripciones de registro de autoservicio

## <a name="what-are-self-service-sign-up-subscriptions"></a>¿Qué son las suscripciones de registro de autoservicio?

Hay un número limitado de suscripciones de registro de autoservicio gratuitas disponibles para que los usuarios de su organización puedan registrarse. Un usuario solo puede registrarse y usar una suscripción de registro de autoservicio por sí mismo. Las suscripciones de registro de autoservicio se administran bloqueando la suscripción de los usuarios y eliminando las suscripciones gratuitas para las que los usuarios se han registrado. Para obtener más información sobre el registro de autoservicio y las suscripciones disponibles, vea [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Ver una lista de suscripciones de registro de autoservicio

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Libre**. Se muestra una lista de todas las suscripciones de registro de autoservicio.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>¿En qué se diferencian estas suscripciones de las suscripciones de compra sin servicio?

Las suscripciones de registro de autoservicio son gratuitas y están disponibles para una lista más grande de productos que las suscripciones de compra de autoservicio. Cuando un usuario se inscribe en una suscripción de compra de autoservicio, es responsable de pagar por ella. Las suscripciones de compra de autoservicio solo están disponibles para productos de Power Platform (Power BI, Power Apps y Power Automate), Project y Visio. Para obtener más información, consulta Preguntas más frecuentes [sobre la compra de autoservicio.](self-service-purchase-faq.md)

## <a name="block-users-from-signing-up"></a>Impedir que los usuarios se inscriba

Use el cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) con el parámetro **AllowAdHocSubscriptions** para controlar si los usuarios pueden registrarse en suscripciones de registro de autoservicio. Para obtener más información, [vea How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminar una suscripción de registro de autoservicio

> [!IMPORTANT]
> Al eliminar una suscripción de registro de autoservicio, se bloquea a todos los usuarios el acceso a sus datos y correo electrónico y se eliminan todos los datos y el correo electrónico.

1. En el centro de administración, vaya a la página **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la **pestaña Productos,** seleccione el icono de filtro y, a continuación, **seleccione Libre**.
3. Seleccione la suscripción de registro de autoservicio que desea eliminar. 
4. En la página detalles de la suscripción, en la sección **Suscripciones y configuración de pago,** seleccione Eliminar **suscripción**.
5. En el **panel Eliminar suscripción,** active la casilla y, a continuación, **seleccione Eliminar suscripción.**

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Tengo una suscripción de registro de autoservicio que bloquea la eliminación de directorios

Los productos de registro de autoservicio para los que los usuarios individuales pueden registrarse también crean un usuario invitado para la autenticación en el directorio de Azure AD. Para evitar la pérdida de datos, estos productos de autoservicio bloquean las eliminaciones de directorios hasta que se eliminan completamente del directorio. El administrador de Azure AD solo las puede eliminar. Para obtener más información, vea [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).
