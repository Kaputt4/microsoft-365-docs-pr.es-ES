---
title: Administrar suscripciones de suscripción de autoservicio
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
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Obtenga información sobre cómo administrar las suscripciones de suscripción de autoservicio gratuitas para su organización.
ms.openlocfilehash: 81c67292a394c62d6057022babb88aa8796b9b3d
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403251"
---
# <a name="manage-self-service-sign-up-subscriptions"></a>Administrar suscripciones de suscripción de autoservicio

## <a name="what-are-self-service-sign-up-subscriptions"></a>¿Qué son las suscripciones de suscripción de autoservicio?

Hay un número limitado de suscripciones de suscripción de autoservicio gratuitas para las que los usuarios de su organización pueden registrarse. Un usuario solo puede suscribirse a una suscripción de inicio de sesión de autoservicio y usarla para usted mismo. Estas suscripciones aparecen en la página **sus productos** , están marcadas como **libres**y tienen una nota que dice: "esta es una suscripción gratuita activada por los usuarios de su empresa". Puede administrar las suscripciones de suscripción de autoservicio al impedir que los usuarios se registren y eliminar suscripciones gratuitas para las que se hayan registrado los usuarios. Para obtener más información acerca del registro de Self-Service y las suscripciones disponibles, consulte [using Self-Service sign up in your Organization](../../admin/misc/self-service-sign-up.md).

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a>¿En qué se diferencian estas suscripciones de las suscripciones de compra de autoservicio?

Las suscripciones de suscripción de autoservicio son gratuitas y están disponibles para obtener una lista de productos más amplia que las suscripciones de compra de autoservicio. Cuando un usuario se registra para una suscripción de compra de autoservicio, es responsable de pagar por ella. Además, las suscripciones de compra de autoservicio solo están disponibles para los productos de la plataforma de alimentación (Power BI, Power apps y Power Automate). Para obtener más información, consulte [preguntas más frecuentes sobre las compras sin ayuda](self-service-purchase-faq.md).

## <a name="block-users-from-signing-up"></a>Impedir que los usuarios inicien sesión

Use el cmdlet [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) con el parámetro **AllowAdHocSubscriptions** para controlar si los usuarios pueden suscribirse a las suscripciones de suscripción de autoservicio. Para obtener más información, vea [¿cómo se controla la configuración de Self-Service?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)

## <a name="delete-a-self-service-sign-up-subscription"></a>Eliminar una suscripción de inicio de sesión de Self-Service

> [!IMPORTANT]
> Al eliminar una suscripción de inicio de sesión de autoservicio, impide que todos los usuarios accedan a sus datos y correo electrónico, y eliminen todos los datos y el correo electrónico.

1. En el centro de administración, vaya a la página **facturación**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">de productos</a> .
2. Busque la suscripción de inicio de sesión de autoservicio que desea eliminar. En la sección **configuración & acciones** , seleccione **eliminar suscripción**.
3. En el panel **eliminar suscripción** , active la casilla de verificación y, a continuación, seleccione **eliminar suscripción**.

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a>Tengo una suscripción de suscripción de autoservicio que bloquea la eliminación de directorios

Los productos de suscripción de autoservicio a los que se pueden suscribir usuarios individuales también crean un usuario Guest para la autenticación en su directorio de Azure AD. Para evitar la pérdida de datos, estos productos de autoservicio bloquean las eliminaciones de directorio hasta que se eliminan completamente del directorio. Solo los puede eliminar el administrador de Azure AD. Para obtener más información, vea [eliminar un directorio en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).