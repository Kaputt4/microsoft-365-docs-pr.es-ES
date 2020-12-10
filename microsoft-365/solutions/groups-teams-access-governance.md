---
title: Controlar el acceso a los grupos de Microsoft 365, Teams y SharePoint
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
description: Obtenga información sobre cómo controlar el acceso en grupos de Microsoft 365, Teams y SharePoint.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613471"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Controlar el acceso a los grupos de Microsoft 365, Teams y SharePoint

Hay muchos controles que le permiten controlar la forma en que los usuarios obtienen acceso a los recursos en grupos, equipos y SharePoint. Revise estas opciones y considere cómo se asignan a las necesidades de su empresa, la confidencialidad de sus datos y el ámbito de las personas con las que deben colaborar los usuarios.

En la tabla siguiente se proporciona una referencia rápida para los controles de acceso disponibles en Microsoft 365. En las siguientes secciones se proporciona información adicional.

|Categoría|Descripción|Referencia|
|:-------|:----------|:--------|
|Pertenencia|||
||Detección de equipos privados|[Administrar la detección de equipos privados en Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Pertenencia a grupos dinámicos basada en reglas|[Crear o actualizar un grupo dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controlar quién puede compartir archivos, carpetas y sitios.|[Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acceso condicional|||
||Autenticación multifactor|[Autenticación multifactor de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlar el acceso a los dispositivos en función de la confidencialidad del sitio, equipo o grupo.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Limitar el acceso al sitio para dispositivos no administrados.|[Controlar el acceso a SharePoint desde dispositivos no administrados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Controlar el acceso al sitio según la ubicación|[Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Acceso de invitado|||
||Permitir o bloquear el uso compartido de SharePoint desde dominios especificados.|[Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Permitir o bloquear la pertenencia al equipo o grupo de dominios especificados.|[Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Evitar el uso compartido anónimo.|[Desactivar vínculos de tipo Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Controlar los permisos de los vínculos de acceso anónimo.|[Establecer permisos de vínculo para todos los vínculos](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Controlar la expiración de vínculos de uso compartido anónimo.|[Establezca una fecha de expiración de los vínculos para Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Controlar el tipo de vínculo de uso compartido que se muestra a los usuarios de forma predeterminada.|[Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Limitar el uso compartido externo a personas específicas.|[Limitar el uso compartido externo a los grupos de seguridad especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controlar el acceso de invitado a un grupo, un equipo o un sitio en función de la confidencialidad de la información.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Desactive las opciones de uso compartido.|[Limitar el uso compartido en Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Administración de usuarios|||
||Revise la pertenencia al grupo y al equipo con regularidad.|[¿Cuáles son las revisiones de acceso a Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatizar la administración de acceso a grupos y equipos.|[¿Qué es la administración de derechos de Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Permitir o impedir que los usuarios creen canales privados en Teams.|[Administrar el ciclo de vida de los canales privados en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Pertenencia

Los propietarios controlan la pertenencia a los equipos y grupos. Los miembros pueden invitar a otros usuarios, pero las invitaciones se envían a los propietarios para su aprobación. Aunque los equipos y grupos públicos son detectables por cualquier persona de la organización, puede controlar si los grupos y equipos privados se pueden detectar:

- [Administrar la detección de equipos privados en Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Puede administrar la pertenencia de un grupo o equipo dinámicamente en función de algunos criterios, como el Departamento. En este caso, los miembros y los propietarios no pueden invitar a personas al equipo.

- [Crear o actualizar un grupo dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Los sitios de SharePoint proporcionan la capacidad de agregar propietarios, miembros y visitantes aparte de la pertenencia a grupos o equipos. En función de sus necesidades, es posible que desee restringir quién puede invitar a personas al sitio. Además, en función de la confidencialidad de la información de un sitio determinado, es posible que desee restringir quién puede compartir archivos y carpetas. Estas restricciones están configuradas por el equipo, el grupo o el propietario del sitio:

- [Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acceso condicional

Con Microsoft 365, puede requerir multi-factor Authentication para los usuarios de dentro y fuera de la organización. Hay muchas opciones para las circunstancias en las que se pide a los usuarios un segundo factor de autenticación. Se recomienda encarecidamente implementar la autenticación multifactor para su organización:

- [Autenticación multifactor de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Si tiene información confidencial en algunos de los grupos y equipos, puede aplicar directivas de administración de dispositivos en función de la etiqueta de confidencialidad de un grupo o un equipo. Puede bloquear el acceso por completo desde dispositivos no administrados o permitir el acceso limitado web solo:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

En SharePoint, puede restringir el acceso a los sitios desde ubicaciones de red especificadas.

- [Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Recursos adicionales:

- [Planeación de una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Información general de Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Controlar el acceso a SharePoint desde dispositivos no administrados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acceso de invitado

Puede restringir los invitados en función del dominio de su dirección de correo electrónico. SharePoint ofrece opciones de restricción de dominio específicas para toda la organización y para el sitio. Los grupos y los equipos usan las listas de permitidos y denegados de dominio en Azure AD. Asegúrese de configurar ambas opciones para evitar el uso compartido no deseado y garantizar una experiencia de usuario coherente:

- [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 permite el uso compartido de archivos y carpetas anónimos mediante el uso de vínculos de *uso compartido.* *Todos* los vínculos se pueden reenviar y cualquier usuario con el vínculo puede tener acceso al elemento compartido. En función de la confidencialidad de los datos, considere la posibilidad de controlar cómo se usan los vínculos de *todos* , incluidos los desactivados completamente, la restricción de permisos de vínculo a solo lectura o la configuración de un tiempo de expiración para ellos:

- [Desactivar vínculos de tipo Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Establecer permisos de vínculo para todos los vínculos](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Establezca una fecha de expiración de los vínculos para Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Al compartir archivos o carpetas, los usuarios tienen varios tipos de vínculos entre los que elegir. Para reducir el riesgo de un uso compartido accidentalmente inapropiado, puede cambiar el tipo de vínculo predeterminado que se presenta a los usuarios cuando comparten. Por ejemplo, si se cambia el valor predeterminado de *todos* los vínculos que permiten el acceso anónimo a *personas de los vínculos de la organización* , se puede reducir el riesgo del uso compartido externo no deseado de información confidencial:

- [Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Si su organización tiene datos confidenciales que necesita compartir con invitados, pero le preocupa el uso compartido inadecuado, puede limitar el uso compartido externo de archivos y carpetas a los miembros de los grupos de seguridad especificados. De este modo, puede restringir el uso compartido externamente a un grupo específico de personas o requerir a los usuarios que realicen un entrenamiento alrededor del uso compartido externo apropiado antes de agregarlos al grupo de seguridad:

- [Limitar el uso compartido externo a los grupos de seguridad especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Los grupos y los equipos tienen una configuración a nivel de la organización que permite o deniega el acceso de invitado. Aunque puede [restringir el acceso de invitado a equipos o grupos específicos mediante PowerShell de Microsoft](per-group-guest-access.md), se recomienda hacerlo mediante una etiqueta de confidencialidad. Con las etiquetas de confidencialidad puede permitir o denegar automáticamente el acceso de invitado en función de la etiqueta aplicada:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 ofrece muchos métodos diferentes para compartir información. Si tiene información confidencial y desea restringir su uso compartido, revise las opciones para limitar el uso compartido:

- [Limitar el uso compartido en Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Recursos adicionales:

- [Configurar la colaboración moderna con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Crear un entorno seguro de uso compartido para invitados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Administración de usuarios

A medida que los grupos y los equipos evolucionan en su organización, una práctica recomendada es revisar la pertenencia del equipo y del grupo de forma regular. Esto puede resultar especialmente útil para los equipos y grupos que tienen una pertenencia cambiante, que contienen información confidencial o que incluyen a los invitados. Considere la posibilidad de configurar las revisiones de acceso para estos equipos y grupos:

- [¿Cuáles son las revisiones de acceso a Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Muchas organizaciones tienen asociaciones empresariales con otras organizaciones o proveedores principales con los que colaboran en profundidad. La administración de usuarios y el acceso a los recursos pueden ser difíciles de administrar en estos escenarios. Considere la posibilidad de automatizar algunas de las tareas de administración de usuarios e incluso migrar algunas de ellas a la organización asociada:

- [¿Qué es la administración de derechos de Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Los canales privados en Microsoft Teams permiten el uso compartido de archivos y conversaciones con ámbito entre un subconjunto de miembros del equipo. En función de las necesidades específicas de su empresa, es posible que desee permitir o bloquear esta funcionalidad.

- [Canales privados en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Administrar el ciclo de vida de los canales privados en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Recursos adicionales:

- [Control de identidad de Azure Active Directory](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Temas relacionados

[Paso a paso de la planeación del gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear el plan de gobierno de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento en Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Administrar la configuración de uso compartido en SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Crear y administrar una red externa en Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurar Teams con tres niveles de protección](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
