---
title: Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado
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
description: Obtenga información sobre cómo especificar las organizaciones en las que los usuarios pueden tener cuentas de invitado.
ms.openlocfilehash: 00db14560c491461435e41e30c106c2554d9ad61
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716097"
---
# <a name="limit-organizations-where-users-can-have-guest-accounts"></a>Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado

De forma predeterminada, otras Microsoft 365 y Azure Active Directory pueden invitar a los usuarios a participar en su organización como invitados. Esto incluye invitarlos a equipos de Microsoft Team, SharePoint sitios y compartir archivos y carpetas individuales con ellos.

Si solo desea que los usuarios participen como invitados con organizaciones específicas, puede especificar estas organizaciones en la configuración de acceso entre inquilinos Azure Active Directory la colaboración [B2B](/azure/active-directory/external-identities/what-is-b2b).

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en tener efecto.

## <a name="set-the-default-b2b-collaboration-settings-to-block-users-from-being-guests"></a>Establecer la configuración de colaboración B2B predeterminada para impedir que los usuarios sean invitados

Dado que participar como invitados está habilitado de forma predeterminada, limitar la participación de invitados a determinadas organizaciones requiere bloquear la colaboración B2B saliente de forma predeterminada.

Para bloquear la colaboración B2B saliente de forma predeterminada
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o de administrador de seguridad.
1. Seleccione **Identidades externas y**, a continuación, **seleccione Configuración de acceso entre inquilinos (versión preliminar).**.
1. Seleccione la **pestaña Configuración predeterminada** .
1. En **Configuración de acceso saliente**, seleccione **Editar valores predeterminados de salida**.
1. Seleccione la **pestaña colaboración B2B** y **la pestaña Usuarios y** grupos.
1. En **Estado de Acceso**, elija **Bloquear acceso**.
1. Seleccione la **pestaña Acceso** externo.
1. En **Estado de Acceso**, elija **Bloquear acceso**.
1. Seleccione **Guardar**.
1. Cierre la **hoja Configuración predeterminada** .

## <a name="add-an-organization"></a>Agregar una organización

A continuación, agregue las organizaciones en las que desea permitir que los usuarios colaboren como invitados en la Azure AD de acceso entre inquilinos.

Para agregar una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar).**
1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el **panel Agregar organización** , escriba el nombre de dominio completo (o identificador de inquilino) de la organización.
1. Seleccione la organización en los resultados de la búsqueda y, a continuación, **seleccione Agregar**.
1. La organización aparece en la **lista Configuración de la** organización.

En este momento, todas las opciones de acceso de esta organización se heredan de la configuración predeterminada.

## <a name="configure-the-organizations-outbound-setting-to-allow-all-users"></a>Configurar la configuración de salida de la organización para permitir que todos los usuarios

Una vez que haya agregado la organización, debe actualizar la configuración de salida de la organización para permitir que los usuarios de colaboración B2B se agregó como invitados. Haga esto para cada organización en la que desee permitir que los usuarios se agregó como invitados.

Para permitir que los usuarios puedan colaborar con invitados de colaboración B2B en una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar).**
1. Seleccione el vínculo de acceso saliente para la organización que desea modificar.
1. En la **pestaña Colaboración B2B** , elija **Personalizar configuración**.
1. En **Estado de Acceso**, elija **Permitir acceso**.
1. En **Destino**, elija permitir a todos los usuarios.
1. Seleccione **Guardar y** cerrar la **hoja Configuración de acceso saliente** .

## <a name="related-topics"></a>Temas relacionados

[Introducción a la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar las opciones de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar quién puede ser invitado por una organización](limit-invitations-from-specific-organization.md)

[Limitar el uso compartido de invitados a organizaciones específicas](limit-guest-sharing-to-specific-organization.md)