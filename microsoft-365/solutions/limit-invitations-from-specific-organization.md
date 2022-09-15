---
title: Limitar a quién puede invitar una organización
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
description: Obtenga información sobre cómo limitar a qué usuarios se puede invitar como invitado o participante de canal compartido a una organización específica.
ms.openlocfilehash: eac3d5d5a91a815bc8add458aceb43c849282bf6
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67728074"
---
# <a name="limit-who-can-be-invited-by-an-organization"></a>Limitar a quién puede invitar una organización

Si colabora con otra organización y desea limitar quién puede ser invitado a esa organización como invitado o miembro de canal compartido en Teams, puede especificar quién puede ser invitado en la configuración de acceso entre inquilinos de Azure Active Directory.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar seis horas en surtir efecto.

## <a name="create-a-security-group"></a>Creación de un grupo de seguridad

La manera más fácil de especificar a quién se puede invitar a otra organización es usar un grupo de seguridad. Puede usar un grupo de seguridad con una pertenencia definida o un grupo de seguridad dinámico. Puede usar un grupo de seguridad existente o crear uno nuevo para este propósito.

Para crear un grupo de seguridad
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. En la página **Active Directory** , seleccione **Grupos** y, a continuación, seleccione **Nuevo grupo**.
1. Elija **Seguridad** para el **tipo de grupo**.
1. Escriba un **nombre de grupo.** 
1. Opcionalmente, agregue una descripción para el grupo.
1. Para que **los roles de Azure AD se puedan asignar al grupo**, elija **No**.
1. Seleccione un **tipo de pertenencia predefinido (obligatorio).**
1. Agregue propietarios y miembros del grupo o una [consulta dinámica](/azure/active-directory/enterprise-users/groups-dynamic-membership) si usa la pertenencia dinámica de usuarios.
1. Seleccione **Crear**. El grupo se crea y está listo para agregar miembros.

## <a name="add-an-organization"></a>Agregar una organización

Para definir reglas de colaboración con otra organización, debe agregar esa organización a la configuración de acceso entre inquilinos de Azure AD. Si aún no ha agregado la organización, siga este procedimiento para agregarla.

Para agregar una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el panel **Agregar organización**, escriba el nombre de dominio completo (o id. de inquilino) de la organización.
1. Seleccione la organización en los resultados de la búsqueda y, a continuación, seleccione **Agregar**.
1. La organización aparece en la lista **Configuración de la organización**. En este momento, toda la configuración de acceso de esta organización se hereda de la configuración predeterminada.

## <a name="choose-who-can-be-invited-by-an-organization"></a>Elección de quién puede ser invitado por una organización

Hay dos opciones para limitar quién puede ser invitado a una organización:

- Limite quién puede ser invitado como invitado. Esto impide que los usuarios se agreguen a Azure AD de la otra organización como invitado. Impide el uso compartido de archivos, carpetas, sitios, equipos y grupos de Microsoft 365 con personas que no están en el grupo de seguridad.
- Limite quién se puede agregar a un canal compartido externo. Esto impide que las personas que no están en el grupo de seguridad se agreguen a canales compartidos de la otra organización.

En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas** y, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.

Para limitar quién puede ser invitado como invitado
1. Seleccione el vínculo de acceso de salida de la organización que desea modificar.
1. En la pestaña **Colaboración B2B** , elija **Personalizar configuración**.
1. En **Estado de acceso**, elija **Permitir acceso**.
1. En **Destino**, elija **Seleccionar usuarios y grupos externos**.
1. Seleccione el vínculo para agregar usuarios y grupos.
1. Busque y seleccione el grupo de seguridad que desea usar.
1. Elija **Seleccionar**.
1. Seleccione **Guardar** y cierre la hoja **Configuración de acceso de salida**.


Para limitar a quién se puede invitar como participante del canal compartido
1. Seleccione el vínculo de acceso de salida de la organización que desea modificar.
1. En la pestaña **Conexión directa B2B**, elija **Personalizar configuración**.
1. En **Estado de acceso**, elija **Permitir acceso**.
1. En **Destino**, elija **Seleccionar usuarios y grupos externos**.
1. Seleccione el vínculo para agregar usuarios y grupos.
1. Busque y seleccione el grupo de seguridad que desea usar.
1. Elija **Seleccionar**.
1. Seleccione **Guardar** y cierre la hoja **Configuración de acceso de salida**.

## <a name="related-topics"></a>Temas relacionados

[Información general sobre la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar la configuración de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado](limit-organizations-where-users-have-guest-accounts.md)

[Limitar el uso compartido de invitados a organizaciones específicas](limit-guest-sharing-to-specific-organization.md)
