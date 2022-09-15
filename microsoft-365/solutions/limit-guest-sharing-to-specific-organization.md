---
title: Limitar el uso compartido de invitados a organizaciones específicas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.collection:
- highpri
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Aprenda a limitar el uso compartido de invitados a organizaciones específicas de Azure AD o Microsoft 365.
ms.openlocfilehash: baad796304090844d379d9c924f10b94245c7796
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67727268"
---
# <a name="limit-guest-sharing-to-specific-organizations"></a>Limitar el uso compartido de invitados a organizaciones específicas

De forma predeterminada, los usuarios pueden invitar a personas ajenas a la organización como invitados. Esto incluye invitarlos a equipos de Microsoft Team, sitios de SharePoint y compartir archivos y carpetas individuales con ellos.

Si solo quiere que los usuarios inviten a invitados de organizaciones específicas, puede especificar estas organizaciones en la configuración de acceso entre inquilinos de Azure Active Directory para la [colaboración B2B](/azure/active-directory/external-identities/what-is-b2b).

## <a name="configure-cross-tenant-access-settings"></a>Configuración de los valores de acceso entre inquilinos

El primer paso para limitar el uso compartido de invitados es cambiar la configuración predeterminada en la configuración de acceso entre inquilinos de Azure AD para bloquear la invitación a invitados de forma predeterminada. A continuación, puede permitir invitaciones de invitados para organizaciones específicas.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en surtir efecto.

### <a name="set-the-default-b2b-collaboration-settings-to-block-inviting-guests"></a>Establecer la configuración de colaboración B2B predeterminada para bloquear la invitación de invitados

Dado que la invitación a invitados está habilitada de forma predeterminada, limitar las invitaciones de invitado a determinadas organizaciones requiere bloquear la colaboración B2B entrante de forma predeterminada.

Para bloquear la colaboración B2B de entrada de forma predeterminada
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. Seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione la pestaña **Configuración predeterminada** .
1. En **Configuración de acceso de entrada**, seleccione **Editar valores predeterminados de entrada**.
1. Seleccione la pestaña **colaboración B2B** y la pestaña **Usuarios y grupos** .
1. En **Estado de acceso**, elija **Bloquear acceso**.
1. Seleccione la pestaña **Acceso externo** .
1. En **Estado de acceso**, elija **Bloquear acceso**.
1. Haga clic en **Guardar**.
1. Cierre la hoja **Configuración predeterminada** .

### <a name="add-the-organization-where-you-want-to-allow-guest-invitations"></a>Agregue la organización en la que desea permitir invitaciones de invitado.

A continuación, agregue las organizaciones donde desea permitir que los usuarios inviten a invitados a la lista de acceso entre inquilinos de Azure AD.

Para agregar una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el panel **Agregar organización**, escriba el nombre de dominio completo (o id. de inquilino) de la organización.
1. Seleccione la organización en los resultados de la búsqueda y, a continuación, seleccione **Agregar**.
1. La organización aparece en la lista **Configuración de la organización**.

En este momento, toda la configuración de acceso de esta organización se hereda de la configuración predeterminada.

### <a name="configure-inbound-settings-for-the-organization-to-allow-all-users"></a>Configuración de las opciones de entrada de la organización para permitir a todos los usuarios

Una vez que haya agregado la organización, debe actualizar la configuración de entrada de la organización para permitir que se invite a los usuarios de colaboración B2B como invitados. Haga esto para cada organización en la que quiera permitir que los usuarios puedan invitar a invitados.

1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione el vínculo de acceso de entrada para la organización que desea modificar.
1. En la pestaña **Colaboración B2B** , elija **Personalizar configuración**.
1. En **Estado de acceso**, elija **Permitir acceso**.
1. En **Destino**, elija permitir a todos los usuarios.
1. Seleccione **Guardar** y cierre la hoja **Configuración de acceso de salida**.

## <a name="turn-off-one-time-passcode-authentication"></a>Desactivar la autenticación de código de acceso de un solo uso

Incluso después de que haya limitado la colaboración B2B a ciertas organizaciones, las personas todavía pueden compartir archivos y carpetas con personas de otras organizaciones; simplemente no se les proporcionará una cuenta de invitado en el directorio.

Si desea evitar el uso compartido por completo con otras organizaciones, debe deshabilitar la característica de código de acceso de un solo uso en Azure AD. Esto impedirá que a las personas ajenas a la organización se les envíe un código de acceso único para la autenticación en archivos o carpetas compartidos.

Para deshabilitar la característica de código de acceso de un solo uso de correo electrónico
1. Inicie sesión en [Azure Portal](https://portal.azure.com/) como administrador global de Azure AD.
1. En el panel de navegación, seleccione **Azure Active Directory**.
1. Seleccione **Identidades externas** > **Todos los proveedores de identidades**.
1. Seleccione **Email código de acceso único** y, a continuación, en **Email código de acceso único para invitados**, seleccione **Deshabilitar código de acceso de un solo uso de correo electrónico para invitados** (o **No** si la característica se ha habilitado, deshabilitado o optado anteriormente durante la versión preliminar).
1. Haga clic en **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Información general sobre la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar la configuración de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar a quién puede invitar una organización](limit-invitations-from-specific-organization.md)

[Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado](limit-organizations-where-users-have-guest-accounts.md)