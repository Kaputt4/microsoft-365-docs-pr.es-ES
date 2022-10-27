---
title: Administración de suscripciones de registro de autoservicio
f1.keywords:
- NOCSH
author: cmcatee-MSFT
ms.author: cmcatee
manager: scotv
ms.reviewer: mijeffer, jmueller
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier1
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- commerce_subscriptions
- AdminSurgePortfolio
search.appverid: MET150
description: Obtenga información sobre cómo administrar suscripciones de registro de autoservicio gratuitas para su organización.
ms.date: 03/17/2021
ms.openlocfilehash: 3710cd1baefba3d11cfeec0da8bd7a47f38e8160
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68725263"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Administración de suscripciones de registro de autoservicio

## <a name="what-are-self-service-sign-up-subscriptions"></a>¿Qué son las suscripciones de registro de autoservicio?

Hay un número limitado de suscripciones de registro de autoservicio gratuitas disponibles para que los usuarios de su organización se registren. Un usuario solo puede registrarse y usar una suscripción de registro de autoservicio por sí mismo. Las suscripciones de registro de autoservicio se administran mediante el bloqueo de la suscripción de los usuarios y la eliminación de las suscripciones gratuitas para las que se han registrado los usuarios. Para obtener más información sobre el registro de autoservicio y las suscripciones disponibles, consulte [Uso del registro de autoservicio en su organización](../../admin/misc/self-service-sign-up.md).

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a>Ver una lista de suscripciones de registro de autoservicio

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la pestaña **Productos** , seleccione el icono de filtro y, a continuación, seleccione **Gratis**. Se muestra una lista de todas las suscripciones de registro de autoservicio.

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>¿En qué se diferencian estas suscripciones de las suscripciones de compra de autoservicio?

Las suscripciones de registro de autoservicio son gratuitas y están disponibles para una lista mayor de productos que las suscripciones de compra de autoservicio. Cuando un usuario se registra para obtener una suscripción de compra de autoservicio, es responsable de pagarla. Las suscripciones de compra de autoservicio solo están disponibles para productos de Power Platform (Power BI, Power Apps y Power Automate), Project y Visio. Para obtener más información, consulte [Preguntas más frecuentes sobre compras de autoservicio](self-service-purchase-faq.yml).

## <a name="block-users-from-signing-up"></a>Impedir que los usuarios se registren

Use el cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) con el parámetro **AllowAdHocSubscriptions** para controlar si los usuarios pueden registrarse para suscripciones de registro de autoservicio. Para obtener más información, consulte [Cómo controlar la configuración de autoservicio?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminación de una suscripción de registro de autoservicio

> [!IMPORTANT]
> Al eliminar una suscripción de registro de autoservicio, se impide que todos los usuarios accedan a sus datos y correo electrónico, y se eliminan todos los datos y el correo electrónico.

1. En el centro de administración, vaya a la página de **Facturación** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Sus productos</a>.
2. En la pestaña **Productos** , seleccione el icono de filtro y, a continuación, seleccione **Gratis**.
3. Seleccione la suscripción de registro de autoservicio que desea eliminar. 
4. En la página de detalles de la suscripción, en la sección **Suscripciones y configuración de pago** , seleccione **Eliminar suscripción**.
5. En el panel **Eliminar suscripción** , active la casilla y, a continuación, seleccione **Eliminar suscripción**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Tengo una suscripción de registro de autoservicio que bloquea la eliminación de directorios

Los productos de registro de autoservicio para los que los usuarios individuales pueden registrarse también crean un usuario invitado para la autenticación en el directorio de Azure AD. Para evitar la pérdida de datos, estos productos de autoservicio bloquean las eliminaciones de directorios hasta que se eliminan por completo del directorio. Solo los puede eliminar el administrador de Azure AD. Para más información, consulte [Eliminación de un directorio en Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).
