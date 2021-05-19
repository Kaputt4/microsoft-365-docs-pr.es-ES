---
title: Administración del acceso en Microsoft 365 grupos, Teams y SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre cómo regular el acceso en Microsoft 365 grupos, Teams y SharePoint.
ms.openlocfilehash: 3e0485813a264fe9042e0de9596ba07e50ef72a3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538152"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Administración del acceso en Microsoft 365 grupos, Teams y SharePoint

Hay muchos controles que permiten controlar la forma en que las personas acceden a los recursos en grupos, equipos y SharePoint. Revisa estas opciones y considera cómo se asignan a las necesidades de tu empresa, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios necesitan colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de acceso disponibles en Microsoft 365. Se proporciona más información en las secciones siguientes.

|Categoría|Descripción|Referencia|
|:-------|:----------|:--------|
|Pertenencia|||
||Detección de equipos privados|[Administrar la detección de equipos privados en Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||Pertenencia a grupos dinámicos basada en reglas|[Crear o actualizar un grupo dinámico en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controle quién puede compartir archivos, carpetas y sitios.|[Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acceso condicional|||
||Autenticación multifactor|[Autenticación multifactor de Azure AD](/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controle el acceso a dispositivos según la confidencialidad de grupo, equipo o sitio.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Limitar el acceso al sitio para dispositivos no administrados.|[Controlar SharePoint acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices)|
||Controlar el acceso al sitio en función de la ubicación|[Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](/sharepoint/control-access-based-on-network-location)|
|Acceso de invitado|||
||Permitir o bloquear el SharePoint compartido de dominios especificados.|[Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](/sharepoint/restricted-domains-sharing)|
||Permitir o bloquear la pertenencia a grupos o equipos de dominios especificados.|[Permitir o bloquear las invitaciones a usuarios de B2B desde organizaciones específicas](/azure/active-directory/b2b/allow-deny-list)|
||Impedir el uso compartido anónimo.|[Desactivar vínculos de tipo Cualquiera](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||Controle los permisos de los vínculos de acceso anónimo.|[Establecer permisos de vínculo para vínculos cualquiera](./best-practices-anonymous-sharing.md#set-link-permissions)|
||Controlar la expiración de los vínculos de uso compartido anónimo.|[Establezca una fecha de expiración de los vínculos para Cualquiera](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||Controla el tipo de vínculo de uso compartido que se muestra a los usuarios de forma predeterminada.|[Cambiar el tipo de vínculo predeterminado para un sitio](/sharepoint/change-default-sharing-link)|
||Limitar el uso compartido externo a personas específicas.|[Limitar el uso compartido externo a grupos de seguridad especificados](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controle el acceso de invitado a un grupo, equipo o sitio en función de la confidencialidad de la información.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)|
||Desactivar las opciones de uso compartido.|[Limitar el uso compartido en Microsoft 365](./microsoft-365-limit-sharing.md)|
|Administración de usuarios|||
||Revise la pertenencia a grupos y equipos de forma periódica.|[¿Qué son las revisiones de acceso de Azure AD?](/azure/active-directory/governance/access-reviews-overview)|
||Automatice la administración de acceso a grupos y equipos.|[¿Qué es la administración de derechos de Azure AD?](/azure/active-directory/governance/entitlement-management-overview)|
||Permitir o bloquear la creación de canales privados en Teams.|[Administrar el ciclo de vida de los canales privados en Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Pertenencia

Los propietarios controlan la pertenencia a equipos y grupos. Los miembros pueden invitar a otros, pero las invitaciones se envían a los propietarios para su aprobación. Aunque cualquier persona de la organización puede detectar grupos y equipos públicos, puede controlar si los equipos y grupos privados son reconocibles:

- [Administrar la detección de equipos privados en Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

Puede administrar la pertenencia a un grupo o equipo dinámicamente en función de algunos criterios, como el departamento. En este caso, los miembros y propietarios no pueden invitar a personas al equipo. Los grupos dinámicos usan metadatos que se definen Azure Active Directory para controlar quién es miembro del grupo. Asegúrese de que los metadatos que está usando están completos y actualizados, ya que los metadatos incorrectos pueden provocar que los usuarios no se puedan agregar a grupos o usuarios incorrectos.

- [Crear o actualizar un grupo dinámico en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint sitios proporcionan la capacidad de agregar propietarios, miembros y visitantes aparte de la pertenencia a grupos o equipos. Según sus requisitos, es posible que desee restringir quién puede invitar a personas al sitio. Además, según la confidencialidad de la información de un sitio determinado, es posible que desee restringir quién puede compartir archivos y carpetas. El propietario del equipo, grupo o sitio configura estas restricciones:

- [Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acceso condicional

Con Microsoft 365, puede requerir autenticación multifactor para personas dentro y fuera de la organización. Hay muchas opciones para las circunstancias en las que se solicita a las personas un segundo factor de autenticación. Le recomendamos encarecidamente que implemente la autenticación multifactor para su organización:

- [Autenticación multifactor de Azure AD](/azure/active-directory/authentication/concept-mfa-howitworks)

Si tienes información confidencial en algunos de tus grupos y equipos, puedes aplicar directivas de administración de dispositivos basadas en la etiqueta de confidencialidad de un grupo o equipo. Puede bloquear el acceso por completo desde dispositivos no administrados o permitir el acceso limitado y solo web:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

En SharePoint, puede restringir el acceso a los sitios desde ubicaciones de red especificadas.

- [Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](/sharepoint/control-access-based-on-network-location)


Recursos adicionales:

- [Planear una implementación de acceso condicional](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune general](/mem/intune/fundamentals/what-is-intune)

- [Controlar SharePoint acceso desde dispositivos no administrados](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acceso de invitado

Puede restringir a los invitados en función del dominio de su dirección de correo electrónico. SharePoint ofrece una configuración de restricción de dominio específica de toda la organización y del sitio. Los grupos Teams usar las listas de dominios permitir y denegar en Azure AD. Asegúrese de configurar ambas opciones para evitar el uso compartido no deseado y garantizar una experiencia de usuario coherente:

- [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](/sharepoint/restricted-domains-sharing)

- [Permitir o bloquear las invitaciones a usuarios de B2B desde organizaciones específicas](/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 permite el uso compartido anónimo de archivos y carpetas mediante vínculos *de uso* compartido de cualquier persona. *Los* vínculos de cualquier persona se pueden reenviar y cualquier persona con el vínculo puede tener acceso al elemento compartido. En función de la confidencialidad de  los datos, considere la posibilidad de regular cómo se usan los vínculos cualquiera, incluidos desactivarlos por completo, restringir los permisos de vínculos a solo lectura o establecer una hora de expiración para ellos:

- [Desactivar vínculos de tipo Cualquiera](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [Establecer permisos de vínculo para vínculos cualquiera](./best-practices-anonymous-sharing.md#set-link-permissions)

- [Establezca una fecha de expiración de los vínculos para Cualquiera](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

Al compartir archivos o carpetas, los usuarios tienen varios tipos de vínculos entre los que elegir. Para reducir el riesgo de uso compartido inadecuado accidental, puede cambiar el tipo de vínculo predeterminado que se presenta a los usuarios cuando comparten. Por ejemplo, cambiar el valor predeterminado de Los  vínculos de *cualquiera* (que permiten el acceso anónimo) a los vínculos de personas de la organización puede reducir el riesgo de uso compartido externo no deseado de información confidencial:

- [Cambiar el tipo de vínculo predeterminado para un sitio](/sharepoint/change-default-sharing-link)

Si su organización tiene datos confidenciales que necesita compartir con invitados, pero le preocupa el uso compartido inadecuado, puede limitar el uso compartido externo de archivos y carpetas a los miembros de grupos de seguridad especificados. De este modo, puede restringir el uso compartido externamente a un grupo específico de personas o requerir que los usuarios tomen formación sobre el uso compartido externo adecuado antes de agregarlos al grupo de seguridad:

- [Limitar el uso compartido externo a grupos de seguridad especificados](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Los grupos y Teams tienen opciones de configuración de nivel de organización que permiten o deniegan el acceso de invitado. Aunque puede restringir el acceso de invitado a grupos o equipos específicos mediante [Microsoft PowerShell,](per-group-guest-access.md)se recomienda hacerlo mediante una etiqueta de confidencialidad. Con las etiquetas de confidencialidad puede permitir o denegar automáticamente el acceso de invitado en función de la etiqueta aplicada:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](../compliance/sensitivity-labels-teams-groups-sites.md)

En un entorno en el que suele invitar invitados a grupos y equipos, considere la posibilidad de configurar revisiones de acceso de invitado programadas periódicamente. Se puede solicitar a los propietarios que revisen a los invitados de sus grupos y equipos y aprueben o denieguen el acceso.

- [Configurar revisiones de acceso de invitados](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365 ofrece muchos métodos diferentes para compartir información. Si tiene información confidencial y desea restringir la forma en que se comparte, revise las opciones para limitar el uso compartido:

- [Limitar el uso compartido en Microsoft 365](./microsoft-365-limit-sharing.md)

Recursos adicionales:

- [Configurar la colaboración segura con Microsoft 365](./setup-secure-collaboration-with-teams.md)

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](./best-practices-anonymous-sharing.md)

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](./share-limit-accidental-exposure.md)

- [Crear un entorno seguro de uso compartido para invitados](./create-secure-guest-sharing-environment.md)

- [Habilitar la colaboración externa B2B y gestionar quién puede invitar a los invitados](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Administración de usuarios

A medida que los grupos y los equipos evolucionan en su organización, una buena práctica es revisar la pertenencia a equipos y grupos de forma regular. Esto puede ser especialmente útil para equipos y grupos con una pertenencia cambiante, aquellos que contienen información confidencial o aquellos que incluyen invitados. Considere la posibilidad de configurar revisiones de acceso para estos equipos y grupos:

- [¿Qué son las revisiones de acceso de Azure AD?](/azure/active-directory/governance/access-reviews-overview)

Muchas organizaciones tienen asociaciones empresariales con otras organizaciones o proveedores clave con los que colaboran en profundidad. La administración de usuarios y el acceso a los recursos pueden ser difíciles de administrar en estos escenarios. Considere la posibilidad de automatizar algunas de las tareas de administración de usuarios e incluso realizar la transición de algunas de ellas a su organización asociada:

- [¿Qué es la administración de derechos de Azure AD?](/azure/active-directory/governance/entitlement-management-overview)

Los canales privados Teams permiten conversaciones con ámbito y uso compartido de archivos entre un subconjunto de miembros del equipo. Según sus necesidades empresariales específicas, es posible que desee permitir o bloquear esta funcionalidad.

- [Canales privados en Microsoft Teams](/MicrosoftTeams/private-channels)

- [Administrar el ciclo de vida de los canales privados en Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

Recursos adicionales:

- [Azure Active Directory Gobierno de identidades](/azure/active-directory/governance)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento en Microsoft Teams](/microsoftteams/security-compliance-overview)

[Administrar la configuración de uso compartido en SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[Crear y administrar una red externa en Yammer](/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurar Teams con tres niveles de protección](./configure-teams-three-tiers-protection.md)