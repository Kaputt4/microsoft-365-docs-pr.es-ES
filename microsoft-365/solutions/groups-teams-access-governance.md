---
title: Administración del acceso en grupos de Microsoft 365, Teams y SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo gobernar el acceso en grupos de Microsoft 365, Teams y SharePoint.
ms.openlocfilehash: 7d0f49f394bb6c5408c7de98d9fe63f306b334b2
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985748"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Administración del acceso en grupos de Microsoft 365, Teams y SharePoint

Hay muchos controles que permiten controlar cómo los usuarios acceden a los recursos en grupos, equipos y SharePoint. Revise estas opciones y considere cómo se asignan a sus necesidades empresariales, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios deben colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de acceso disponibles en Microsoft 365. En las secciones siguientes se proporciona más información.

|Categoría|Descripción|Referencia|
|:-------|:----------|:--------|
|Pertenencia|||
||Detección de equipos privados|[Administración de la detección de equipos privados en Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||Pertenencia dinámica a grupos basada en reglas|[Creación o actualización de un grupo dinámico en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controlar quién puede compartir archivos, carpetas y sitios.|[Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acceso condicional|||
||Autenticación multifactor|[Autenticación multifactor de Azure AD](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlar el acceso del dispositivo en función de la confidencialidad del grupo, equipo o sitio.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Limitar el acceso al sitio para dispositivos no administrados.|[Control del acceso a SharePoint desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices)|
||Control del acceso al sitio en función de la ubicación|[Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](/sharepoint/control-access-based-on-network-location)|
|Acceso de invitado|||
||Permitir o bloquear el uso compartido de SharePoint desde dominios especificados.|[Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](/sharepoint/restricted-domains-sharing)|
||Permitir o bloquear la pertenencia a grupos o equipos de dominios especificados.|[Permitir o bloquear las invitaciones a usuarios de B2B desde organizaciones específicas](/azure/active-directory/b2b/allow-deny-list)|
||Impedir el uso compartido anónimo.|[Desactivar vínculos de tipo Cualquiera](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Controle los permisos de los vínculos de acceso anónimo.|[Establecer permisos de vínculo para vínculos cualquiera](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Controlar la expiración de vínculos de uso compartido anónimo.|[Establezca una fecha de expiración de los vínculos para Cualquiera](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Controle el tipo de vínculo de uso compartido que se muestra a los usuarios de forma predeterminada.|[Cambiar el tipo de vínculo predeterminado para un sitio](/sharepoint/change-default-sharing-link)|
||Limitar el uso compartido externo a personas específicas.|[Limitar el uso compartido externo a grupos de seguridad especificados](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controlar el acceso de invitado a un grupo, equipo o sitio en función de la confidencialidad de la información.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Desactive las opciones de uso compartido.|[Limitar el uso compartido en Microsoft 365](./microsoft-365-limit-sharing.md)|
|Administración de usuarios|||
||Revise la pertenencia al equipo y al grupo de forma periódica.|[¿Qué son las revisiones de acceso de Azure AD?](/azure/active-directory/governance/access-reviews-overview)|
||Automatice la administración de acceso a grupos y equipos.|[¿Qué es la administración de derechos de Azure AD?](/azure/active-directory/governance/entitlement-management-overview)|

## <a name="membership"></a>Pertenencia

Los propietarios controlan la pertenencia a equipos y grupos. Los miembros pueden invitar a otros, pero las invitaciones se envían a los propietarios para su aprobación. Aunque los equipos y grupos públicos son reconocibles por cualquier usuario de la organización, puede controlar si los equipos y grupos privados son reconocibles:

- [Administración de la detección de equipos privados en Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

Puede administrar la pertenencia de un grupo o equipo dinámicamente en función de algunos criterios, como el departamento. En este caso, los miembros y propietarios no pueden invitar a personas al equipo. Los grupos dinámicos usan metadatos que se definen en Azure Active Directory para controlar quién es miembro del grupo. Asegúrese de que los metadatos que usa están completos y actualizados, ya que los metadatos incorrectos pueden provocar que los usuarios se quedarán fuera de los grupos o que se agreguen usuarios incorrectos.

- [Creación o actualización de un grupo dinámico en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

Los sitios de SharePoint proporcionan la capacidad de agregar propietarios, miembros y visitantes, además de la pertenencia a grupos o equipos. En función de sus requisitos, es posible que desee restringir quién puede invitar a personas al sitio. Además, en función de la confidencialidad de la información de un sitio determinado, es posible que desee restringir quién puede compartir archivos y carpetas. Estas restricciones las configura el equipo, el grupo o el propietario del sitio:

- [Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acceso condicional

Con Microsoft 365, puede requerir la autenticación multifactor para personas dentro y fuera de su organización. Hay muchas opciones para las circunstancias en las que se solicita a las personas un segundo factor de autenticación. Se recomienda encarecidamente implementar la autenticación multifactor para su organización:

- [Autenticación multifactor de Azure AD](/azure/active-directory/authentication/concept-mfa-howitworks)

Si tiene información confidencial en algunos de los grupos y equipos, puede aplicar directivas de administración de dispositivos en función de la etiqueta de confidencialidad de un grupo o equipo. Puede bloquear el acceso por completo desde dispositivos no administrados o permitir el acceso limitado solo a la web:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

En SharePoint, puede restringir el acceso a sitios desde ubicaciones de red especificadas.

- [Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](/sharepoint/control-access-based-on-network-location)


Recursos adicionales:

- [Planeamiento de una implementación de acceso condicional](/azure/active-directory/conditional-access/plan-conditional-access)

- [Introducción a Microsoft Intune](/mem/intune/fundamentals/what-is-intune)

- [Control del acceso a SharePoint desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acceso de invitado

Puede restringir los invitados en función del dominio de su dirección de correo electrónico. SharePoint ofrece una configuración de restricción de dominio específica del sitio y de toda la organización. Los grupos y Teams usan las listas de permitidos de dominio o las listas de bloqueo en Azure AD. Asegúrese de configurar ambas opciones para evitar el uso compartido no deseado y garantizar una experiencia de usuario coherente:

- [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](/sharepoint/restricted-domains-sharing)

- [Permitir o bloquear las invitaciones a usuarios de B2B desde organizaciones específicas](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 permite el uso compartido anónimo de archivos y carpetas mediante vínculos *de uso compartido de cualquiera* . *Todos* los vínculos se pueden reenviar y cualquier persona con el vínculo puede acceder al elemento compartido. En función de la confidencialidad de los datos, considere la posibilidad de gobernar cómo se usan los vínculos *cualquiera* , incluidos desactivarlos por completo, restringir los permisos de vínculo a solo lectura o establecer un tiempo de expiración para ellos:

- [Desactivar vínculos de tipo Cualquiera](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Establecer permisos de vínculo para vínculos cualquiera](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Establezca una fecha de expiración de los vínculos para Cualquiera](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

Al compartir archivos o carpetas, los usuarios tienen varios tipos de vínculo entre los que elegir. Para reducir el riesgo de uso compartido inadecuado accidental, puede cambiar el tipo de vínculo predeterminado que se presenta a los usuarios cuando comparten. Por ejemplo, cambiar el valor predeterminado de los vínculos *Cualquiera* (que permiten el acceso anónimo) a Personas en los vínculos de *la organización* puede reducir el riesgo de compartir información confidencial externa no deseada:

- [Cambiar el tipo de vínculo predeterminado para un sitio](/sharepoint/change-default-sharing-link)

Si su organización tiene datos confidenciales que necesita compartir con los invitados, pero le preocupa el uso compartido inadecuado, puede limitar el uso compartido externo de archivos y carpetas a los miembros de grupos de seguridad especificados. De este modo, puede restringir el uso compartido externamente a un grupo específico de personas o requerir a los usuarios que realicen entrenamientos sobre el uso compartido externo adecuado antes de agregarlos al grupo de seguridad:

- [Limitar el uso compartido externo a grupos de seguridad especificados](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Los grupos y Teams tienen una configuración de nivel de organización que permite o deniega el acceso de invitado. Aunque puede [restringir el acceso de invitado a equipos o grupos específicos mediante Microsoft PowerShell](per-group-guest-access.md), se recomienda hacerlo mediante una etiqueta de confidencialidad. Con las etiquetas de confidencialidad, puede permitir o denegar automáticamente el acceso de invitado en función de la etiqueta aplicada:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

En un entorno en el que suele invitar a invitados a grupos y equipos, considere la posibilidad de configurar revisiones de acceso de invitado programadas periódicamente. Se puede pedir a los propietarios que revisen a los invitados de sus grupos y equipos y aprueben o denieguen el acceso.

- [Configurar revisiones de acceso de invitados](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 ofrece muchos métodos diferentes para compartir información. Si tiene información confidencial y quiere restringir su uso compartido, revise las opciones para limitar el uso compartido:

- [Limitar el uso compartido en Microsoft 365](./microsoft-365-limit-sharing.md)

Recursos adicionales:

- [Configurar la colaboración segura con Microsoft 365](./setup-secure-collaboration-with-teams.md)

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](./best-practices-anonymous-sharing.md)

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](./share-limit-accidental-exposure.md)

- [Crear un entorno seguro de uso compartido para invitados](./create-secure-guest-sharing-environment.md)

- [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Administración de usuarios

A medida que los grupos y equipos evolucionan en su organización, una buena práctica es revisar la pertenencia al equipo y a los grupos de forma periódica. Esto puede ser especialmente útil para equipos y grupos con una pertenencia cambiante, aquellos que contienen información confidencial o aquellos que incluyen invitados. Considere la posibilidad de configurar revisiones de acceso para estos equipos y grupos:

- [¿Qué son las revisiones de acceso de Azure AD?](/azure/active-directory/governance/access-reviews-overview)

Muchas organizaciones tienen asociaciones empresariales con otras organizaciones o proveedores clave con los que colaboran en profundidad. La administración de usuarios y el acceso a los recursos pueden ser difíciles de administrar en estos escenarios. Considere la posibilidad de automatizar algunas de las tareas de administración de usuarios e incluso realizar la transición de algunas de ellas a su organización asociada:

- [¿Qué es la administración de derechos de Azure AD?](/azure/active-directory/governance/entitlement-management-overview)

Los canales privados de Teams permiten conversaciones con ámbito y el uso compartido de archivos entre un subconjunto de miembros del equipo. En función de sus necesidades empresariales específicas, es posible que desee permitir o bloquear esta funcionalidad.

- [Canales privados en Microsoft Teams](/MicrosoftTeams/private-channels)

Los canales compartidos le permiten invitar a personas que están fuera del equipo o fuera de la organización. En función de las necesidades empresariales específicas y las directivas de uso compartido externo, es posible que quiera permitir o bloquear esta funcionalidad.

- [Canales compartidos](/MicrosoftTeams/shared-channels)

Recursos adicionales:

- [Gobernanza de identidades de Azure Active Directory](/azure/active-directory/governance)

## <a name="related-topics"></a>Temas relacionados

[Recomendaciones de planeamiento de gobernanza de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[Creación del plan de gobernanza de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento en Microsoft Teams](/microsoftteams/security-compliance-overview)

[Administración de la configuración de uso compartido en SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Crear y administrar una red externa en Yammer](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurar Teams con tres niveles de protección](./configure-teams-three-tiers-protection.md)