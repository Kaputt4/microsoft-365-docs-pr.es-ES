---
title: Control del acceso en grupos de Microsoft 365, Teams y SharePoint
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
description: Obtenga información sobre cómo gobernar el acceso en grupos de Microsoft 365, Teams y SharePoint.
ms.openlocfilehash: fb1bec219ef0d27c2a908f5f385185a1a70e01e1
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613471"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>Control del acceso en grupos de Microsoft 365, Teams y SharePoint

Hay muchos controles que le permiten controlar el modo en que los usuarios acceden a los recursos en grupos, equipos y SharePoint. Revise estas opciones y tenga en cuenta cómo se asignan a sus necesidades empresariales, la confidencialidad de los datos y el ámbito de las personas con las que los usuarios necesitan colaborar.

En la tabla siguiente se proporciona una referencia rápida para los controles de acceso disponibles en Microsoft 365. En las secciones siguientes se proporciona más información.

|Categoría|Description|Referencia|
|:-------|:----------|:--------|
|Pertenencia|||
||Detección de equipos privados|[Administrar la detección de equipos privados en Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||Pertenencia a grupos dinámica basada en reglas|[Crear o actualizar un grupo dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||Controlar quién puede compartir archivos, carpetas y sitios.|[Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|Acceso condicional|||
||Autenticación multifactor|[Autenticación multifactor de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||Controlar el acceso a dispositivos en función de la confidencialidad del grupo, equipo o sitio.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Limitar el acceso al sitio para dispositivos no administrados.|[Controlar el acceso de SharePoint desde dispositivos no administrados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||Controlar el acceso al sitio en función de la ubicación|[Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|Acceso de invitado|||
||Permitir o bloquear el uso compartido de SharePoint de dominios especificados.|[Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||Permitir o bloquear la pertenencia a grupos o equipos de dominios especificados.|[Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||Impedir el uso compartido anónimo.|[Desactivar vínculos de tipo Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||Controle los permisos de los vínculos de acceso anónimo.|[Establecer permisos de vínculo para vínculos de cualquiera](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||Controlar la expiración de los vínculos de uso compartido anónimo.|[Establezca una fecha de expiración de los vínculos para Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||Controlar el tipo de vínculo para compartir que se muestra a los usuarios de forma predeterminada.|[Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||Limitar el uso compartido externo a personas específicas.|[Limitar el uso compartido externo a grupos de seguridad especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||Controlar el acceso de invitado a un grupo, equipo o sitio en función de la confidencialidad de la información.|[Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||Desactivar las opciones de uso compartido.|[Limitar el uso compartido en Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|Administración de usuarios|||
||Revisar la pertenencia a grupos y equipos de forma periódica.|[¿Qué son las revisiones de acceso de Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||Automatice la administración de acceso a grupos y equipos.|[¿Qué es la administración de derechos de Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||Permitir o bloquear la creación de canales privados en Teams.|[Administrar el ciclo de vida de los canales privados en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>Pertenencia

Los propietarios controlan la pertenencia a equipos y grupos. Los miembros pueden invitar a otros usuarios, pero las invitaciones se envían a los propietarios para su aprobación. Aunque los equipos y grupos públicos son reconocibles por cualquier persona de la organización, puede controlar si los equipos y grupos privados son reconocibles:

- [Administrar la detección de equipos privados en Microsoft Teams](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

Puede administrar la pertenencia a un grupo o equipo dinámicamente en función de algunos criterios, como el departamento. En este caso, los miembros y propietarios no pueden invitar a personas al equipo.

- [Crear o actualizar un grupo dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

Los sitios de SharePoint proporcionan la capacidad de agregar propietarios, miembros y visitantes aparte de la pertenencia a grupos o equipos. Según sus requisitos, es posible que desee restringir quién puede invitar a personas al sitio. Además, según la confidencialidad de la información de un sitio determinado, es posible que desee restringir quién puede compartir archivos y carpetas. Estas restricciones las configura el equipo, grupo o propietario del sitio:

- [Configurar y administrar solicitudes de acceso](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>Acceso condicional

Con Microsoft 365, puede requerir la autenticación multifactor para personas dentro y fuera de su organización. Existen muchas opciones para las circunstancias en las que se solicita a los usuarios un segundo factor de autenticación. Le recomendamos encarecidamente que implemente la autenticación multifactor para su organización:

- [Autenticación multifactor de Azure AD](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

Si tiene información confidencial en algunos de sus grupos y equipos, puede aplicar directivas de administración de dispositivos basadas en la etiqueta de confidencialidad de un grupo o equipo. Puede bloquear el acceso por completo desde dispositivos no administrados o permitir el acceso limitado a la web:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

En SharePoint, puede restringir el acceso a los sitios desde ubicaciones de red especificadas.

- [Controlar el acceso a los datos de SharePoint y OneDrive en función de la ubicación de red](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


Recursos adicionales:

- [Planeación de una implementación de acceso condicional](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Introducción a Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [Controlar el acceso de SharePoint desde dispositivos no administrados](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>Acceso de invitado

Puede restringir a los invitados en función del dominio de su dirección de correo electrónico. SharePoint ofrece una configuración de restricción de dominio específica para toda la organización y para el sitio. Los grupos y Teams usan las listas de dominios permitidos y denegados en Azure AD. Asegúrese de configurar ambas opciones para evitar el uso compartido no deseado y garantizar una experiencia de usuario coherente:

- [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [Permitir o bloquear invitaciones a usuarios B2B de organizaciones específicas](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 permite el uso compartido anónimo de archivos y carpetas mediante el uso de *vínculos de* uso compartido cualquiera. *Cualquier* vínculo se puede reenviar y cualquier persona con el vínculo puede tener acceso al elemento compartido. En función de la confidencialidad de  los datos, considere la posibilidad de gobernar cómo se usan los vínculos cualquiera, incluida su desactivación completa, la restricción de permisos de vínculos a solo lectura o la configuración de una fecha de expiración para ellos:

- [Desactivar vínculos de tipo Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [Establecer permisos de vínculo para vínculos de cualquiera](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [Establezca una fecha de expiración de los vínculos para Cualquiera](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

Al compartir archivos o carpetas, los usuarios tienen varios tipos de vínculo entre los que elegir. Para reducir el riesgo de uso compartido inadecuado accidental, puede cambiar el tipo de vínculo predeterminado que se presenta a los usuarios cuando comparten. Por ejemplo, cambiar  el valor predeterminado de los  vínculos cualquiera (que permiten el acceso anónimo) a los vínculos de personas de su organización puede reducir el riesgo de compartir información confidencial externa no deseada:

- [Cambiar el tipo de vínculo predeterminado para un sitio](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

Si su organización tiene datos confidenciales que necesita compartir con invitados, pero le preocupa el uso compartido inapropiado, puede limitar el uso compartido externo de archivos y carpetas a los miembros de grupos de seguridad especificados. De este modo, puede restringir el uso compartido externamente a un grupo específico de personas o requerir que los usuarios tomen formación sobre el uso compartido externo adecuado antes de agregarlos al grupo de seguridad:

- [Limitar el uso compartido externo a grupos de seguridad especificados](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

Los grupos y Teams tienen una configuración de nivel de organización que permite o deniega el acceso de invitado. Aunque puede restringir el acceso de invitado a grupos o equipos específicos mediante PowerShell de [Microsoft,](per-group-guest-access.md)se recomienda hacerlo mediante una etiqueta de confidencialidad. Con las etiquetas de confidencialidad puede permitir o denegar automáticamente el acceso de invitado en función de la etiqueta aplicada:

- [Usar etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 ofrece muchos métodos diferentes para compartir información. Si tiene información confidencial y desea restringir cómo se comparte, revise las opciones para limitar el uso compartido:

- [Limitar el uso compartido en Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

Recursos adicionales:

- [Configurar la colaboración moderna con Microsoft 365](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [Crear un entorno seguro de uso compartido para invitados](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [Habilitar la colaboración externa B2B y administrar quién puede invitar a invitados](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>Administración de usuarios

A medida que los grupos y equipos evolucionan en su organización, un procedimiento recomendado es revisar la pertenencia a equipos y grupos de forma periódica. Esto puede ser especialmente útil para equipos y grupos con una pertenencia cambiante, aquellos que contienen información confidencial o aquellos que incluyen invitados. Considere la posibilidad de configurar revisiones de acceso para estos equipos y grupos:

- [¿Qué son las revisiones de acceso de Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

Muchas organizaciones tienen asociaciones empresariales con otras organizaciones o proveedores clave con quienes colaboran en profundidad. La administración de usuarios y el acceso a los recursos pueden ser difíciles de administrar en estos escenarios. Considera la posibilidad de automatizar algunas de las tareas de administración de usuarios e incluso de realizar la transición de algunas de ellas a la organización asociada:

- [¿Qué es la administración de derechos de Azure AD?](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

Los canales privados de Teams permiten conversaciones con ámbito y el uso compartido de archivos entre un subconjunto de miembros del equipo. En función de sus necesidades empresariales específicas, es posible que desee permitir o bloquear esta funcionalidad.

- [Canales privados en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [Administrar el ciclo de vida de los canales privados en Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

Recursos adicionales:

- [Azure Active Directory Identity Governance](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>Temas relacionados

[Planeación paso a paso de gobierno de colaboración](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Crear un plan de gobierno de colaboración](collaboration-governance-first.md)

[Seguridad y cumplimiento en Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Administrar la configuración de uso compartido en SharePoint](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[Crear y administrar una red externa en Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[Configurar Teams con tres niveles de protección](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
