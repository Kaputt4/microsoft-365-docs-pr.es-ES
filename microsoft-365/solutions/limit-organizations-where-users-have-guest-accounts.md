---
title: Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado
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
description: Obtenga información sobre cómo especificar en qué organizaciones pueden tener cuentas de invitado los usuarios.
ms.openlocfilehash: 65a3729b7a64c82b5d5261e92840272248f4cc42
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67731494"
---
# <a name="limit-organizations-where-users-can-have-guest-accounts"></a>Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado

De forma predeterminada, otras organizaciones de Microsoft 365 y Azure Active Directory pueden invitar a los usuarios a participar en su organización como invitados. Esto incluye invitarlos a equipos de Microsoft Team, sitios de SharePoint y compartir archivos y carpetas individuales con ellos.

Si solo desea que los usuarios participen como invitados con organizaciones específicas, puede especificar estas organizaciones en la configuración de acceso entre inquilinos de Azure Active Directory para la [colaboración B2B](/azure/active-directory/external-identities/what-is-b2b).

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en surtir efecto.

## <a name="set-the-default-b2b-collaboration-settings-to-block-users-from-being-guests"></a>Establecer la configuración de colaboración B2B predeterminada para impedir que los usuarios sean invitados

Dado que participar como invitados está habilitado de forma predeterminada, limitar la participación de invitados a determinadas organizaciones requiere bloquear la colaboración B2B saliente de forma predeterminada.

Para bloquear la colaboración B2B saliente de forma predeterminada
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. Seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione la pestaña **Configuración predeterminada** .
1. En **Configuración de acceso saliente**, seleccione **Editar valores predeterminados de salida**.
1. Seleccione la pestaña **colaboración B2B** y la pestaña **Usuarios y grupos** .
1. En **Estado de acceso**, elija **Bloquear acceso**.
1. Seleccione la pestaña **Acceso externo** .
1. En **Estado de acceso**, elija **Bloquear acceso**.
1. Haga clic en **Guardar**.
1. Cierre la hoja **Configuración predeterminada** .

## <a name="add-an-organization"></a>Agregar una organización

A continuación, agregue las organizaciones donde desea permitir que los usuarios colaboren como invitados en la lista de acceso entre inquilinos de Azure AD.

Para agregar una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el panel **Agregar organización**, escriba el nombre de dominio completo (o id. de inquilino) de la organización.
1. Seleccione la organización en los resultados de la búsqueda y, a continuación, seleccione **Agregar**.
1. La organización aparece en la lista **Configuración de la organización**.

En este momento, toda la configuración de acceso de esta organización se hereda de la configuración predeterminada.

## <a name="configure-the-organizations-outbound-setting-to-allow-all-users"></a>Configuración de la configuración de salida de la organización para permitir a todos los usuarios

Una vez que haya agregado la organización, debe actualizar la configuración de salida de la organización para permitir que los usuarios de colaboración B2B se agreguen como invitados. Haga esto para cada organización en la que quiera permitir que los usuarios se agreguen como invitados.

Para permitir que los usuarios puedan ir a invitados de colaboración B2B en una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.
1. Seleccione el vínculo de acceso de salida de la organización que desea modificar.
1. En la pestaña **Colaboración B2B** , elija **Personalizar configuración**.
1. En **Estado de acceso**, elija **Permitir acceso**.
1. En **Destino**, elija permitir a todos los usuarios.
1. Seleccione **Guardar** y cierre la hoja **Configuración de acceso de salida**.

## <a name="related-topics"></a>Temas relacionados

[Información general sobre la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar la configuración de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar a quién puede invitar una organización](limit-invitations-from-specific-organization.md)

[Limitar el uso compartido de invitados a organizaciones específicas](limit-guest-sharing-to-specific-organization.md)