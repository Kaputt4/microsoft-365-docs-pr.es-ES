---
title: Administrar la autenticación multifactor
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
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo administrar la autenticación multifactor.
ms.openlocfilehash: 4587dffbe45eacaf62c49d0c84aeef86455980e1
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2021
ms.locfileid: "60557279"
---
# <a name="manage-multifactor-authentication"></a>Administrar la autenticación multifactor

> [!NOTE]
> Las características descritas en este artículo están en Versión preliminar, están sujetas a cambios y solo están disponibles para los partners que cumplen los [requisitos](m365-lighthouse-requirements.md). Si su organización no tiene Microsoft 365 Lighthouse, vea [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).

Azure Active Directory (Azure AD) Multi-Factor Authentication (MFA) ayuda a proteger el acceso a datos y aplicaciones, proporcionando otra capa de seguridad mediante una segunda forma de autenticación. La pestaña Autenticación multifactor proporciona información detallada sobre el estado de habilitación de MFA en todos los inquilinos. Seleccione cualquier inquilino de la lista para ver más detalles sobre ese espacio empresarial, incluidas las directivas de acceso condicional que requieren MFA ya configuradas y qué usuarios aún no se han registrado para MFA.

Para los clientes de pequeñas y medianas empresas (SMB), Microsoft recomienda habilitar los valores predeterminados [de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) como mínimo. Para escenarios más complejos, puede usar [el acceso condicional](/azure/active-directory/conditional-access/overview) para configurar directivas específicas.

## <a name="before-you-begin"></a>Antes de empezar

Se deben cumplir las siguientes condiciones antes de que un inquilino aparezca en la lista:

- El inquilino del cliente debe tener una Azure AD Premium licencia para cada usuario. Para obtener más información sobre qué licencias admiten MFA, vea Características y licencias [para Azure AD multifactor authentication](/azure/active-directory/authentication/concept-mfa-licensing).

- El inquilino del cliente debe estar activo dentro de Microsoft 365 Lighthouse. Para obtener información sobre cómo determinar si un inquilino está activo, [consulte Microsoft 365 Lighthouse de lista de inquilinos](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview).

## <a name="enable-mfa-for-a-tenant"></a>Habilitar MFA para un inquilino

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Usuarios**.

2. Seleccione la **pestaña Autenticación multifactor.**

3. En la lista de inquilinos, seleccione un espacio empresarial para abrir el panel de detalles.

4. En la **pestaña Habilitación de MFA,** en MFA con valores predeterminados **de seguridad,** seleccione **Habilitar valores predeterminados de seguridad**.

5. Seleccione **Guardar cambios**.

Para habilitar MFA a través del acceso condicional, vea Tutorial: Proteger los eventos de inicio de sesión de usuario [con Azure AD multifactor authentication](/azure/active-directory/authentication/tutorial-enable-azure-mfa).

## <a name="notify-users-who-arent-registered-for-mfa"></a>Notificar a los usuarios que no están registrados para MFA

1. En el panel izquierdo de Faro, seleccione **Usuarios**.

2. Seleccione la **pestaña Autenticación multifactor.**

3. En la lista de inquilinos, seleccione un espacio empresarial para abrir el panel de detalles.

4. En la **pestaña Usuario no registrado para MFA,** seleccione los usuarios que desea notificar.

5. Seleccione **Crear correo** electrónico .

Lighthouse abre el cliente de correo electrónico predeterminado y rellenar previamente el mensaje de correo electrónico con instrucciones para registrarse en MFA. Todos los usuarios seleccionados se incluirán en la línea CCO. Si prefiere enviar un correo electrónico individualmente a los usuarios, puede seleccionar el icono de correo electrónico junto al nombre de usuario.

Si desea usar una cuenta de correo electrónico diferente, puede exportar la lista de usuarios a un archivo. También puede descargar plantillas de correo electrónico de ejemplo que puede personalizar con la personalización de marca de su empresa.

## <a name="next-steps"></a>Siguientes pasos

Una vez habilitada la MFA, puede habilitar Azure Active Directory (Azure AD) restablecimiento de contraseñas de autoservicio. Esta característica ofrece a los usuarios la capacidad de cambiar o restablecer su contraseña sin intervención del administrador ni del departamento de ayuda. Para obtener más información, vea [Manage self-service password reset](m365-lighthouse-manage-sspr.md).

## <a name="related-content"></a>Contenido relacionado

[Planear una Azure Active Directory multifactor authentication](/azure/active-directory/authentication/howto-mfa-getstarted) (artículo)\
[¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) (artículo)\
[¿Qué es el acceso condicional?](/azure/active-directory/conditional-access/overview) (artículo)\
[Obtenga información sobre cómo convertir usuarios de MFA por usuario a acceso condicional](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) (artículo)
