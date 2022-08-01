---
title: Limitar quién puede invitar a invitados
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
description: Obtenga información sobre cómo limitar quién puede invitar a invitados a su organización.
ms.openlocfilehash: d8eb9452abb76916940d10fa042dae479358568a
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "66997784"
---
# <a name="limit-who-can-invite-guests"></a>Limitar quién puede invitar a invitados

Puede limitar quién de su organización puede invitar a invitados. Las cuentas de invitado se pueden usar para compartir equipos, sitios de SharePoint, archivos y carpetas con personas ajenas a la organización.

Si los procesos empresariales requieren que limite quién puede compartir con invitados o si desea que los usuarios completen el entrenamiento antes de poder compartirlos con los invitados, puede limitar quién puede compartir mediante el rol invitador invitado en Azure Active Directory.

## <a name="create-a-security-group-for-people-allowed-to-invite-guests"></a>Creación de un grupo de seguridad para las personas a las que se permite invitar a invitados

El primer paso consiste en crear un grupo de seguridad para los usuarios a los que se les permitirá invitar a invitados. Asegúrese de configurar este grupo para permitir un rol de Azure AD y, a continuación, asígnele el rol invitador invitado.

Para crear un grupo de seguridad para invitados invitados
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o administrador de seguridad.
1. En la página **Active Directory** , seleccione **Grupos** y, a continuación, seleccione **Nuevo grupo**.
1. Elija **Seguridad** para el **tipo de grupo**.
1. Escriba un **nombre de grupo.** 
1. Opcionalmente, agregue una descripción para el grupo.
1. Para los **roles de Azure AD se pueden asignar al grupo**, elija **Sí**.
1. Agregar propietarios y miembros del grupo.
1. En **Roles**, seleccione **No hay roles seleccionados**.
1. Busque y seleccione el rol **Invitador** y, a continuación, elija **Seleccionar**.
1. Seleccione **Crear** y confirme que desea un grupo al que se puedan asignar roles. El grupo se crea y está listo para agregar miembros.

## <a name="configure-external-collaboration-settings"></a>Configuración de la colaboración externa

Una vez que haya creado el grupo de seguridad y agregado los usuarios a los que desea poder invitar a invitados, el siguiente paso es configurar la configuración de colaboración externa de Azure AD para permitir que solo los usuarios con el rol invitador invitador inviten a invitados.

Tenga en cuenta que los administradores globales siempre pueden invitar a invitados independientemente de esta configuración.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en surtir efecto.

Para configurar Azure AD para limitar las invitaciones de invitado al rol invitador de invitado
1. En [Azure Active Directory](https://aad.portal.azure.com/), seleccione **Identidades externas**.
1. Seleccione **Configuración de colaboración externa**.
1. En **Configuración de invitación de** invitado, elija **Solo los usuarios asignados a roles de administrador específicos pueden invitar invitados**.
1. Seleccione **Guardar**.

## <a name="related-topics"></a>Temas relacionados

[Permitir que solo los usuarios de grupos de seguridad específicos compartan externamente en SharePoint y OneDrive](/sharepoint/manage-security-groups)

[Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](/azure/active-directory/external-identities/delegate-invitations)