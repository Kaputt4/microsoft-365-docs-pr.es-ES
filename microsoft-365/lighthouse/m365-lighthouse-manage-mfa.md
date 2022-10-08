---
title: Administración de la autenticación multifactor en Microsoft 365 Lighthouse
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: ragovind
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo administrar la autenticación multifactor.
ms.openlocfilehash: d3b25356f4d1588b3d0dc3b40f143fa5424fea44
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68178413"
---
# <a name="manage-multifactor-authentication-in-microsoft-365-lighthouse"></a>Administración de la autenticación multifactor en Microsoft 365 Lighthouse

Multi-Factor Authentication (MFA) de Azure Active Directory (Azure AD) ayuda a proteger el acceso a datos y aplicaciones, lo que proporciona otra capa de seguridad mediante una segunda forma de autenticación. La página Autenticación multifactor proporciona información detallada sobre el estado de la habilitación de MFA en los inquilinos. Seleccione cualquier inquilino de la lista para ver más detalles para ese inquilino, incluidas las directivas de acceso condicional que requieren MFA ya configuradas y qué usuarios aún no se han registrado para MFA.

Para los clientes de pequeñas y medianas empresas (SMB), Microsoft recomienda habilitar [los valores predeterminados de seguridad](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) como mínimo. Para escenarios más complejos, puede usar [el acceso condicional](/azure/active-directory/conditional-access/overview) para configurar directivas específicas.

## <a name="before-you-begin"></a>Antes de empezar

Se deben cumplir las condiciones siguientes antes de que aparezca un inquilino en la lista:

- El inquilino del cliente debe tener una licencia de Azure AD Premium para cada usuario. Para obtener más información sobre qué licencias admiten MFA, consulte [Características y licencias para Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/concept-mfa-licensing).

- El inquilino del cliente debe estar activo dentro de Microsoft 365 Lighthouse. Para obtener información sobre cómo determinar si un inquilino está activo, consulte [introducción a Microsoft 365 Lighthouse lista de inquilinos](/microsoft-365/lighthouse/m365-lighthouse-tenant-list-overview).

## <a name="enable-mfa-for-a-tenant"></a>Habilitación de MFA para un inquilino

1. En el panel de navegación izquierdo de Lighthouse, seleccione Autenticación **multifactor** **de usuarios** > .

2. En la página **Autenticación multifactor** , busque un inquilino que no use MFA y, a continuación, seleccione ese inquilino para abrir el panel de detalles del inquilino.

3. En la pestaña **Habilitación de MFA** , en **MFA con valores predeterminados de seguridad**, seleccione **Habilitar valores predeterminados de seguridad**.

4. Seleccione **Guardar cambios**.

Para habilitar MFA a través del acceso condicional, consulte [Tutorial: Protección de eventos de inicio de sesión de usuario con Azure AD Multi-Factor Authentication](/azure/active-directory/authentication/tutorial-enable-azure-mfa).

## <a name="notify-users-who-arent-registered-for-mfa"></a>Notificar a los usuarios que no están registrados para MFA

1. En el panel de navegación izquierdo de Lighthouse, seleccione Autenticación **multifactor** **de usuarios** > .

2. En la página **Autenticación multifactor** , busque inquilinos con usuarios no registrados para MFA y, a continuación, seleccione el inquilino para abrir el panel de detalles del inquilino.

3. Seleccione **Usuarios no registrados para la pestaña MFA** .

4. Seleccione todos los demás usuarios de la lista que necesiten registrarse para MFA y, a continuación, seleccione **Crear correo electrónico**.

> [!TIP]
> Si alguna de las cuentas de usuario de la lista son cuentas de acceso de emergencia o cuentas de servicio para las que no desea requerir MFA, seleccione esas cuentas de usuario y, a continuación, seleccione **Excluir usuarios**. Las cuentas de usuario excluidas ya no aparecerán en la lista de usuarios no registrados para MFA.

> [!NOTE]
> Si aparecen cuentas de buzón de correo compartidas o cuentas de usuario inactivas en la lista de usuarios no registrados para MFA, se recomienda bloquear el inicio de sesión de esas cuentas para que ya no aparezcan en esta lista.


Lighthouse abre el cliente de correo electrónico predeterminado y rellena previamente el mensaje de correo electrónico con instrucciones para registrarse en MFA. Todos los usuarios seleccionados se incluirán en la línea BCC. Si prefiere enviar un correo electrónico individualmente a los usuarios, puede seleccionar el icono de correo electrónico junto al nombre de usuario.

Si desea usar una cuenta de correo electrónico diferente, puede exportar la lista de usuarios a un archivo. También puede descargar plantillas de correo electrónico de ejemplo que puede personalizar con la personalización de marca de su empresa.

## <a name="next-steps"></a>Pasos siguientes

Una vez habilitada MFA, puede habilitar el autoservicio de restablecimiento de contraseña de Azure Active Directory (Azure AD). Esta característica ofrece a los usuarios la posibilidad de cambiar o restablecer su contraseña sin la participación del administrador o del departamento de soporte técnico. Para obtener más información, vea [Administrar el autoservicio de restablecimiento de contraseña en Microsoft 365 Lighthouse](m365-lighthouse-manage-sspr.md).

## <a name="related-content"></a>Contenido relacionado

[Planeamiento de una implementación de Azure Active Directory Multi-Factor Authentication](/azure/active-directory/authentication/howto-mfa-getstarted) (artículo)\
[¿Qué son los valores predeterminados de seguridad?](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) (artículo)\
[¿Qué es el acceso condicional?](/azure/active-directory/conditional-access/overview) (artículo)\
[Obtenga información sobre cómo convertir usuarios de MFA por usuario a acceso condicional](/azure/active-directory/authentication/howto-mfa-getstarted#convert-users-from-per-user-mfa-to-conditional-access-based-mfa) (artículo)
