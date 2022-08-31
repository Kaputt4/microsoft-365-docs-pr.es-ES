---
title: Administración del autoservicio de restablecimiento de contraseña en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo administrar el autoservicio de restablecimiento de contraseña.
ms.openlocfilehash: 2b530b7f0d2d8707a0876788fd22132a5cb998c5
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67471640"
---
# <a name="manage-self-service-password-reset-in-microsoft-365-lighthouse"></a>Administración del autoservicio de restablecimiento de contraseña en Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite a los asociados administrar el autoservicio de restablecimiento de contraseña (SSPR) de Azure Active Directory (Azure AD). SSPR ofrece a los usuarios la posibilidad de cambiar o restablecer su contraseña sin la participación del administrador o del departamento de soporte técnico. Si la cuenta de un usuario está bloqueada o olvida su contraseña, puede seguir las indicaciones para desbloquearse y volver a trabajar. Esta capacidad reduce las llamadas del departamento de soporte técnico y la pérdida de productividad cuando un usuario no puede iniciar sesión en su dispositivo o una aplicación.

## <a name="before-you-begin"></a>Antes de empezar

Se deben cumplir las condiciones siguientes antes de que aparezca un inquilino en la lista:

- El inquilino del cliente debe tener una licencia de Azure AD Premium para cada usuario. Para obtener más información sobre qué licencias admiten SSPR, consulte [Requisitos de licencias para el autoservicio de restablecimiento de contraseña de Azure Active Directory](/azure/active-directory/authentication/concept-sspr-licensing).

- El inquilino del cliente debe estar activo en Lighthouse. Para obtener información sobre cómo determinar si un inquilino está activo, consulte [Información general de la página Windows 365 (PC en la nube) en Microsoft 365 Lighthouse](m365-lighthouse-tenants-page-overview.md).

## <a name="view-sspr-tenant-status"></a>Visualización del estado del inquilino de SSPR

- En el panel de navegación izquierdo de Lighthouse, seleccione **Restablecimiento de contraseña** **de los usuarios** > .

La página Restablecimiento de contraseña proporciona información general sobre los inquilinos que han habilitado SSPR a través de la configuración recomendada, el número de usuarios que no se han registrado para SSPR y un desglose detallado por inquilino del progreso de la implementación de SSPR en las organizaciones que administra.

## <a name="enable-sspr-for-a-tenant"></a>Habilitación de SSPR para un inquilino

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Restablecimiento de contraseña** **de los usuarios** > .

2. En la página **Restablecimiento de contraseña** , seleccione un inquilino de la lista para abrir el panel de detalles.

3. Seleccione **Editar configuración de SSPR en Azure Active Directory** para ir a Azure Active Directory (Azure AD).

4. En Azure AD, habilite SSPR para todos los usuarios o seleccionados. Para más información, consulte [Tutorial: Permitir que los usuarios desbloqueen su cuenta o restablezcan contraseñas mediante el autoservicio de restablecimiento de contraseña de Azure Active Directory](/azure/active-directory/authentication/tutorial-enable-sspr).

## <a name="notify-users-to-register-for-sspr"></a>Notificar a los usuarios que se registren para SSPR

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Restablecimiento de contraseña** **de los usuarios** > .

2. En la página **Restablecimiento de contraseña** , seleccione un inquilino de la lista para abrir el panel de detalles.

3. Seleccione los usuarios a los que desea notificar.

4. Seleccione **Crear correo electrónico**.

Lighthouse abre el cliente de correo electrónico predeterminado y rellena previamente el mensaje de correo electrónico con instrucciones para registrarse en SSPR. Todos los usuarios seleccionados se incluirán en la línea BCC. Si prefiere enviar un correo electrónico individualmente a los usuarios, puede seleccionar el icono de correo electrónico junto al nombre de usuario.

Si desea usar una cuenta de correo electrónico diferente, puede exportar la lista de usuarios a un archivo. También puede descargar plantillas de correo electrónico de ejemplo que puede personalizar con la personalización de marca de su empresa.

## <a name="related-content"></a>Contenido relacionado

[Planear una implementación de autoservicio de restablecimiento de contraseña de Azure Active Directory](/azure/active-directory/authentication/howto-sspr-deployment) (artículo)\
[Tutorial: Permitir que los usuarios desbloqueen su cuenta o restablezcan contraseñas mediante el autoservicio de restablecimiento de contraseña de Azure Active Directory](/azure/active-directory/authentication/tutorial-enable-sspr) (artículo)\
[Habilitación y configuración de SSPR en Azure AD](https://www.youtube.com/watch?v=rA8TvhNcCvQ) (vídeo)\
[Administración de la autenticación multifactor en Microsoft 365 Lighthouse](m365-lighthouse-manage-mfa.md) (artículo)
