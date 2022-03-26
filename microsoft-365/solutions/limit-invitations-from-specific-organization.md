---
title: Limitar quién puede ser invitado por una organización
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
description: Obtenga información sobre cómo limitar cuál de los usuarios puede invitarse como participante del canal invitado o compartido a una organización específica.
ms.openlocfilehash: 599f83a4464498f7a964f02a955f802cb8545432
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63716115"
---
# <a name="limit-who-can-be-invited-by-an-organization"></a>Limitar quién puede ser invitado por una organización

Si colabora con otra organización y desea limitar quién puede ser invitado a esa organización como invitado o miembro de un canal compartido en Teams, puede especificar quién puede ser invitado en la configuración de acceso entre inquilinos en Azure Active Directory.

> [!NOTE]
> Los cambios en la configuración de acceso entre inquilinos pueden tardar dos horas en tener efecto.

## <a name="create-a-security-group"></a>Creación de un grupo de seguridad

La forma más sencilla de especificar quién puede ser invitado a otra organización es usar un grupo de seguridad. Puede usar un grupo de seguridad con una pertenencia definida o un grupo de seguridad dinámico. Puede usar un grupo de seguridad existente o crear uno nuevo para este fin.

Para crear un grupo de seguridad
1. Inicie sesión en [Azure Active Directory](https://aad.portal.azure.com) con una cuenta de administrador global o de administrador de seguridad.
1. En la **página de Active Directory** , seleccione **Grupos** y, a continuación, **nuevo grupo**.
1. Elija **Seguridad** para el **tipo de grupo**.
1. Escriba un **nombre de grupo.** 
1. Opcionalmente, agregue una descripción para el grupo.
1. Para **Azure AD roles se pueden asignar al grupo**, elija **No**.
1. Seleccione un tipo de pertenencia predefinido **(obligatorio).**
1. Agregue propietarios y miembros de grupos o una [consulta dinámica](/azure/active-directory/enterprise-users/groups-dynamic-membership) si usa la pertenencia dinámica de usuarios.
1. Seleccione **Crear**. El grupo se crea y está listo para agregar miembros.

## <a name="add-an-organization"></a>Agregar una organización

Para definir reglas de colaboración con otra organización, debe agregar esa organización a la Azure AD de acceso entre inquilinos. Si aún no ha agregado la organización, siga este procedimiento para agregarla.

Para agregar una organización
1. En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar)**.1. Seleccione **Configuración de la organización**.
1. Seleccione **Agregar organización**.
1. En el **panel Agregar organización** , escriba el nombre de dominio completo (o identificador de inquilino) de la organización.
1. Seleccione la organización en los resultados de la búsqueda y, a continuación, **seleccione Agregar**.
1. La organización aparece en la **lista Configuración de la** organización. En este momento, todas las opciones de acceso de esta organización se heredan de la configuración predeterminada.

## <a name="choose-who-can-be-invited-by-an-organization"></a>Elegir quién puede ser invitado por una organización

Existen dos opciones para limitar quién puede ser invitado a una organización:

- Limitar a quién se puede invitar como invitado. Esto evita que los usuarios se agregó a la organización Azure AD como invitado. Impide el uso compartido de archivos, carpetas, sitios, equipos y grupos Microsoft 365 con personas que no están en el grupo de seguridad.
- Limitar quién se puede agregar a un canal compartido externo. Esto impide que las personas que no están en el grupo de seguridad se agregó a los canales compartidos de la otra organización.

En [Azure Active Directory](https://aad.portal.azure.com), seleccione **Identidades externas y**, a continuación, seleccione **Configuración de acceso entre inquilinos (versión preliminar).**

Para limitar quién puede ser invitado como invitado
1. Seleccione el vínculo de acceso saliente para la organización que desea modificar.
1. En la **pestaña Colaboración B2B** , elija **Personalizar configuración**.
1. En **Estado de Acceso**, elija **Permitir acceso**.
1. En **Destino**, elija **Seleccionar usuarios y grupos externos**.
1. Seleccione el vínculo para agregar usuarios y grupos.
1. Busque y seleccione el grupo de seguridad que desea usar.
1. Elija **Seleccionar**.
1. Seleccione **Guardar y** cerrar la **hoja Configuración de acceso saliente** .


Para limitar quién puede ser invitado como participante del canal compartido
1. Seleccione el vínculo de acceso saliente para la organización que desea modificar.
1. En la **pestaña Conexión directa B2B** , elija **Personalizar configuración**.
1. En **Estado de Acceso**, elija **Permitir acceso**.
1. En **Destino**, elija **Seleccionar usuarios y grupos externos**.
1. Seleccione el vínculo para agregar usuarios y grupos.
1. Busque y seleccione el grupo de seguridad que desea usar.
1. Elija **Seleccionar**.
1. Seleccione **Guardar y** cerrar la **hoja Configuración de acceso saliente** .

## <a name="related-topics"></a>Temas relacionados

[Introducción a la conexión directa B2B](/azure/active-directory/external-identities/b2b-direct-connect-overview)

[Configurar las opciones de acceso entre inquilinos para la conexión directa B2B](/azure/active-directory/external-identities/cross-tenant-access-settings-b2b-direct-connect)

[Limitar las organizaciones en las que los usuarios pueden tener cuentas de invitado](limit-organizations-where-users-have-guest-accounts.md)

[Limitar el uso compartido de invitados a organizaciones específicas](limit-guest-sharing-to-specific-organization.md)