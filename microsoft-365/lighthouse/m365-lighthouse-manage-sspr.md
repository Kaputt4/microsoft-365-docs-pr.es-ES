---
title: Administrar el restablecimiento de contraseñas de autoservicio
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo administrar el restablecimiento de contraseñas de autoservicio.
ms.openlocfilehash: 0444fac94ee4a3037b4387e3ad344b374e6a3f1d
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557243"
---
# <a name="manage-self-service-password-reset"></a>Administrar el restablecimiento de contraseñas de autoservicio

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Microsoft 365 Lighthouse permite a los partners administrar Azure Active Directory (Azure AD) el restablecimiento de contraseña de autoservicio (SSPR). SSPR ofrece a los usuarios la capacidad de cambiar o restablecer su contraseña sin intervención del administrador ni del servicio de ayuda. Si la cuenta de un usuario está bloqueada o olvida su contraseña, puede seguir los mensajes para desbloquearse y volver al trabajo. Esta capacidad reduce las llamadas al servicio de ayuda y la pérdida de productividad cuando un usuario no puede iniciar sesión en su dispositivo o una aplicación.

## <a name="before-you-begin"></a>Antes de empezar

Se deben cumplir las siguientes condiciones antes de que un inquilino aparezca en la lista:

- El inquilino del cliente debe tener una Azure AD Premium licencia para cada usuario. Para obtener más información sobre las licencias compatibles con SSPR, vea [Licensing requirements for Azure Active Directory self-service password reset](/azure/active-directory/authentication/concept-sspr-licensing).

- El inquilino del cliente debe estar activo en Lighthouse. Para obtener información sobre cómo determinar si un inquilino está activo, [consulte Microsoft 365 Lighthouse de lista de inquilinos](m365-lighthouse-tenant-list-overview.md).

## <a name="view-sspr-tenant-status"></a>Ver estado del inquilino de SSPR

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Usuarios**.

2. Seleccione la **pestaña Restablecimiento de** contraseña.

La pestaña restablecimiento de contraseña proporciona información general sobre los inquilinos que han habilitado SSPR a través de la configuración recomendada, el número de usuarios que no se han registrado en SSPR y un desglose detallado por inquilino del progreso de implementación de SSPR en todas las organizaciones que administra.

## <a name="enable-sspr-for-a-tenant"></a>Habilitar SSPR para un inquilino

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Usuarios**.

2. Seleccione la **pestaña Restablecimiento de** contraseña.

3. En la lista de inquilinos, seleccione un espacio empresarial para abrir el panel de detalles.

4. Seleccione **Editar configuración de SSPR en Azure Active Directory** para ir a Azure Active Directory (Azure AD).

5. En Azure AD, habilite SSPR para todos o usuarios seleccionados. Para obtener más información, vea Tutorial: Permitir que los usuarios desbloqueen su cuenta o restablezcan contraseñas Azure Active Directory restablecimiento de [contraseñas de autoservicio.](/azure/active-directory/authentication/tutorial-enable-sspr)

## <a name="notify-users-to-register-for-sspr"></a>Notificar a los usuarios que se registren en SSPR

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Usuarios**.

2. Seleccione la **pestaña Restablecimiento de** contraseña.

3. En la lista de inquilinos, seleccione un espacio empresarial para abrir el panel de detalles.

4. Seleccione los usuarios que desea notificar.

5. Seleccione **Crear correo** electrónico .

Lighthouse abre el cliente de correo electrónico predeterminado y rellenar previamente el mensaje de correo electrónico con instrucciones para registrarse en SSPR. Todos los usuarios seleccionados se incluirán en la línea CCO. Si prefiere enviar un correo electrónico individualmente a los usuarios, puede seleccionar el icono de correo electrónico junto al nombre de usuario.

Si desea usar una cuenta de correo electrónico diferente, puede exportar la lista de usuarios a un archivo. También puede descargar plantillas de correo electrónico de ejemplo que puede personalizar con la personalización de marca de su empresa.

## <a name="related-content"></a>Contenido relacionado

[Plan an Azure Active Directory self-service password reset deployment](/azure/active-directory/authentication/howto-sspr-deployment) (article)\
[Tutorial: permitir que los usuarios desbloqueen su](/azure/active-directory/authentication/tutorial-enable-sspr) cuenta o restablezcan contraseñas Azure Active Directory restablecimiento de contraseñas de autoservicio (artículo)\
[Cómo habilitar y configurar SSPR en Azure AD](https://www.youtube.com/watch?v=rA8TvhNcCvQ) (vídeo)\
[Administrar la autenticación multifactor](m365-lighthouse-manage-mfa.md) (artículo)
