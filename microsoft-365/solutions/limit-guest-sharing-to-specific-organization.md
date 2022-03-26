---
title: Limitar el uso compartido de invitados a organizaciones específicas
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo limitar el uso compartido de invitados a organizaciones Azure AD o Microsoft 365 específicas.
ms.openlocfilehash: 75cfe739e1cdde2e0bd959382b2444487ea726be
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716118"
---
# <a name="limit-guest-sharing-to-specific-organizations"></a>Limitar el uso compartido de invitados a organizaciones específicas

De forma predeterminada, los usuarios pueden invitar a personas fuera de la organización como invitados. Esto incluye invitarlos a equipos de Microsoft Team, SharePoint sitios y compartir archivos y carpetas individuales con ellos.

Si solo desea que los usuarios inviten invitados de organizaciones específicas Azure Active Directory, puede especificar estas organizaciones en la configuración de acceso entre inquilinos para la colaboración [B2B](/azure/active-directory/external-identities/what-is-b2b).

## <a name="configure-cross-tenant-access-settings"></a>Configurar las opciones de acceso entre inquilinos

El primer paso para limitar el uso compartido de invitados es cambiar la configuración predeterminada en el Azure AD de acceso entre inquilinos para bloquear invitados de forma predeterminada. A continuación, puede permitir invitaciones de invitado para organizaciones específicas.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en tener efecto.

### <a name="set-the-default-b2b-collaboration-settings-to-block-inviting-guests"></a>Establecer la configuración de colaboración B2B predeterminada para bloquear la invitación a invitados

Dado que invitar invitados está habilitado de forma predeterminada, limitar las invitaciones de invitado a determinadas organizaciones requiere bloquear la colaboración B2B entrante de forma predeterminada.

Para bloquear la colaboración B2B entrante de forma predeterminada
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o de administrador de seguridad.
1. Seleccione **Identidades externas y**, a continuación, **seleccione Configuración de acceso entre inquilinos (versión preliminar).**.
1. Seleccione la **pestaña Configuración predeterminada** .
1. En **Configuración de acceso entrante**, seleccione **Editar valores predeterminados de entrada**.
1. Seleccione la **pestaña colaboración B2B** y **la pestaña Usuarios y** grupos.
1. En **Estado de Acceso**, elija **Bloquear acceso**.
1. Seleccione la **pestaña Acceso** externo.
1. En **Estado de Acceso**, elija **Bloquear acceso**.
1. Seleccione **Guardar**.
1. Cierre la **hoja Configuración predeterminada** .

### <a name="add-the-organization-where-you-want-to-allow-guest-invitations"></a>Agregar la organización en la que desea permitir invitaciones de invitado

A continuación, agregue las organizaciones en las que desea permitir a los usuarios invitar invitados a la Azure AD de acceso entre inquilinos.

Para agregar una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar).**
1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el **panel Agregar organización** , escriba el nombre de dominio completo (o identificador de inquilino) de la organización.
1. Seleccione la organización en los resultados de la búsqueda y, a continuación, **seleccione Agregar**.
1. La organización aparece en la **lista Configuración de la** organización.

En este momento, todas las opciones de acceso de esta organización se heredan de la configuración predeterminada.

### <a name="configure-inbound-settings-for-the-organization-to-allow-all-users"></a>Configurar la configuración de entrada de la organización para permitir que todos los usuarios

Una vez que haya agregado la organización, debe actualizar la configuración de entrada de la organización para permitir que los usuarios de colaboración B2B puedan ser invitados como invitados. Haga esto para cada organización en la que desee permitir que los usuarios puedan invitar invitados.

1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar).**
1. Seleccione el vínculo de acceso entrante para la organización que desea modificar.
1. En la **pestaña Colaboración B2B** , elija **Personalizar configuración**.
1. En **Estado de Acceso**, elija **Permitir acceso**.
1. En **Destino**, elija permitir a todos los usuarios.
1. Seleccione **Guardar y** cerrar la **hoja Configuración de acceso saliente** .

## <a name="turn-off-one-time-passcode-authentication"></a>Desactivar la autenticación de código de acceso único

Incluso después de limitar la colaboración B2B a determinadas organizaciones, las personas aún pueden compartir archivos y carpetas con personas de otras organizaciones; simplemente, no se les dará una cuenta de invitado en el directorio.

Si desea impedir el uso compartido por completo con otras organizaciones, debe deshabilitar la característica de código de acceso único en Azure AD. Esto impedirá que se envíe un código de acceso único para la autenticación a archivos o carpetas compartidos.

Para deshabilitar la característica de código de acceso único de correo electrónico
1. Inicie sesión en [Azure Portal](https://portal.azure.com/) como administrador global de Azure AD.
1. En el panel de navegación, seleccione **Azure Active Directory**.
1. Seleccione **Identidades** >  **externasTodos proveedores de identidades**.
1. Seleccione **Email one-time passcode** y, a continuación, en **Email one-time passcode for guests**, select **Disable email one-time passcode for guests** (or **No** if the feature was previously enabled, disabled, or opted into during preview).
1. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Introducción a la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar las opciones de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar quién puede ser invitado por una organización](limit-invitations-from-specific-organization.md)

[Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado](limit-organizations-where-users-have-guest-accounts.md)