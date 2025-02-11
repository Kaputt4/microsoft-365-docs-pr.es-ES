---
title: Colaboración entre inquilinos de Microsoft 365
ms.author: kvice
author: kelleyvice-msft
manager: scotv
audience: Admin
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Obtenga información sobre cómo funciona la colaboración de Microsoft 365 entre inquilinos y organizaciones, lo que permite que distintas organizaciones trabajen juntas de forma segura.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5dc6879e724ecca2ba25f8dc95d260cc46817e66
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68196125"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Colaboración entre inquilinos de Microsoft 365

Supongamos que dos organizaciones, Fabrikam y Contoso, tienen un inquilino de Microsoft 365 para empresas y quieren trabajar juntos en varios proyectos; algunos de los cuales se ejecutan durante un tiempo limitado y otros están en curso. ¿Cómo pueden Fabrikam y Contoso permitir que sus personas y equipos colaboren de forma más eficaz en sus diferentes inquilinos de Microsoft 365 de forma segura? Microsoft 365, junto con la colaboración B2B de Azure Active Directory (Azure AD), proporciona varias opciones. En este artículo se describen varios escenarios clave que Fabrikam y Contoso pueden tener en cuenta.

Las opciones de colaboración entre inquilinos de Microsoft 365 incluyen el uso de una ubicación central para archivos y conversaciones, el uso compartido de calendarios, el uso de mensajería instantánea, llamadas de audio y vídeo para la comunicación y la protección del acceso a recursos y aplicaciones. Use las tablas siguientes para seleccionar soluciones y obtener más información.

## <a name="exchange-online-collaboration-options"></a>opciones de colaboración Exchange Online

| Finalidad del uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Compartir calendarios con otra organización de Microsoft 365 |Los administradores pueden configurar diferentes niveles de acceso al calendario en Exchange Online para permitir a las empresas colaborar con otras empresas y permitir que los usuarios compartan las programaciones (información de disponibilidad) con otros usuarios. | <ul><li>[Uso compartido](/exchange/sharing/sharing) </li><li> [Relaciones de la organización](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [Crear una relación de la organización](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Modificar una relación de la organización](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [Quitar una relación de la organización](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [Compartir calendarios con usuarios externos](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Controlar cómo los usuarios comparten sus calendarios con personas ajenas a la organización | Los administradores aplican directivas de uso compartido a los buzones de los usuarios para controlar con quién se puede compartir y el nivel de acceso concedido |  <ul><li> [Directivas de uso compartido](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [Crear una directiva de uso compartido](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [Aplicar una directiva de uso compartido a buzones](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [Modificar, desactivar o quitar una directiva de uso compartido](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|Configuración de canales de correo electrónico seguros y control del flujo de correo con organizaciones asociadas | Los administradores crean conectores para aplicar la seguridad a los intercambios de correo con una organización o proveedor de servicios asociados. Los conectores aplican el cifrado a través de la seguridad de la capa de transporte (TLS), así como permiten restricciones en los nombres de dominio o intervalos de direcciones IP desde los que los asociados envían correo electrónico. |  <ul><li> [Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [Configurar un flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [Dominios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [Configuración del conector para un flujo de correo seguro con una organización asociada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [Procedimientos recomendados de flujo de correo (información general)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>Opciones de colaboración de SharePoint Online y OneDrive para la Empresa

| Objetivos de uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Uso compartido de sitios y documentos con usuarios externos | Los administradores configuran el uso compartido en el nivel de inquilino o de colección de sitios para cuentas microsoft autenticadas, profesionales o educativas autenticadas o cuentas de invitado |  <ul><li> [Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](/sharepoint/restricted-domains-sharing) </li><li> [Uso de SharePoint Online como solución de extranet de negocio a negocio (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Seguimiento y control del uso compartido externo para los usuarios finales | OneDrive para la Empresa propietarios de archivos y usuarios finales de SharePoint Online configuran el uso compartido de sitios y documentos y establecen notificaciones para realizar un seguimiento del uso compartido |  <ul><li> [Configuración de notificaciones para el uso compartido externo para OneDrive para la Empresa](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Compartir archivos o carpetas de SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>Skype Empresarial opciones de colaboración

| Finalidad del uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Skype Empresarial Online: mensajería instantánea, llamadas y presencia con otros usuarios de Skype Empresarial | Los administradores pueden habilitar sus Skype Empresarial usuarios en línea para la mensajería instantánea, realizar llamadas de audio y vídeo y ver la presencia con los usuarios en otro inquilino de Microsoft 365. | [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|Skype Empresarial Online: mensajería instantánea, llamadas y presencia con usuarios de Skype (consumidor) | Los administradores pueden habilitar sus usuarios de Skype Empresarial Online para la mensajería instantánea, realizar llamadas y ver la presencia con usuarios de Skype (consumidor). | [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Opciones de Colaboración B2B de Azure AD

| Finalidad del uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Colaboración B2B de Azure AD: uso compartido de contenido mediante la adición de usuarios externos a un grupo en el directorio de una organización | Un administrador de Controlador de dominio de **Azure AD**, **Administración de seguridad**, **Administración de usuario**, **Administración de aplicaciones** en la nube o **administrador global** de un inquilino de Microsoft 365 puede invitar a personas de otro inquilino de Microsoft 365 a unirse a su directorio, agregar esos usuarios externos a un grupo y conceder acceso al contenido, como sitios y bibliotecas de SharePoint para el grupo. |  <ul><li> [¿Qué es la versión preliminar de colaboración B2B de Azure AD?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: las nuevas actualizaciones facilitan la integración entre empresas](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Uso compartido externo y colaboración B2B de Azure Active Directory](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Personalización y API de colaboración B2B de Azure Active Directory](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD e Identity Show: Azure AD Colaboración B2B (Empresa a Empresa)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Opciones de colaboración de Microsoft 365

| Finalidad del uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Grupos de Microsoft 365: Email, calendario, OneNote y archivos compartidos en un lugar central | Los grupos se admiten en los planes Business Essentials, Business Premium, Education y Enterprise E1, E3 y E5. Personas en un inquilino de Microsoft 365 puede crear un grupo e invitar a personas de otro inquilino de Microsoft 365 como usuarios invitados. También se aplica a Dynamics CRM. |  <ul><li> [Obtener información sobre los grupos de Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Acceso de invitado en Grupos de Microsoft 365](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Implementación de Grupos de Microsoft 365](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Opciones de colaboración de Yammer

| Finalidad del uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Yammer: colaboración a través de un medio social empresarial | A menos que un administrador de Yammer deshabilite la capacidad de crear grupos externos, los usuarios pueden crear grupos externos para colaborar en Yammer a través de conversaciones, la capacidad de gustar y seguir publicaciones, compartir archivos y chatear en línea. | [Crear y administrar grupos externos en Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Opciones de colaboración de Teams

|Finalidad del uso compartido|Acción administrativa|Información de procedimientos|
|:-----|:-----|:-----|
|Colaborar en Teams con usuarios externos a la organización | Un **usuario Administración** o **un administrador global** para el inquilino de Microsoft 365 que invita necesita habilitar la colaboración externa en Teams. Ahora, los administradores globales y los propietarios del equipo podrán invitar a cualquier persona con una dirección de correo electrónico para colaborar en Teams.  <br/> Los administradores también pueden administrar y editar invitados que ya están presentes en su inquilino. |  <ul><li> [Autorización del acceso de invitado](/microsoftteams/teams-dependencies) </li><li> [Activar o desactivar el acceso de invitado en Teams](/microsoftteams/set-up-guests) </li><li> [Uso de PowerShell para controlar el acceso de invitado](/microsoftteams/guest-access-powershell) </li><li> [Lista de comprobación de acceso de invitado](/microsoftteams/guest-access-checklist) </li><li> [Ver usuarios invitados](/microsoftteams/view-guests) </li><li> [Editar información del usuario invitado](/microsoftteams/edit-guests-information) </li></ul> |
|Los propietarios del equipo pueden invitar y administrar la forma en que los invitados colaboran dentro de sus equipos.  |Los propietarios del equipo tienen controles adicionales sobre lo que los invitados pueden hacer dentro de sus equipos. |  <ul><li> [Agregar invitados](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Agregar un invitado a un equipo](/microsoftteams/add-guests) </li><li> [Administración del acceso de invitado en Teams](/microsoftteams/manage-guests) </li><li> [Ver quién está en un equipo o en un canal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Los invitados de otros inquilinos pueden ver el contenido en Teams y colaborar con otros miembros | Ninguno. | [La experiencia de acceso de invitado](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Opciones de colaboración de Power BI

| Finalidad del uso compartido | Acción administrativa | Información de procedimientos |
|:-----|:-----|:-----|
|Power BI permite a los usuarios invitados externos consumir contenido compartido con ellos a través de vínculos. Esto permite a los usuarios de la organización distribuir contenido de forma segura entre organizaciones.<br/> | El Administración de Power BI puede controlar si los usuarios pueden invitar a usuarios externos a ver contenido dentro de la organización.| [Distribución de contenido de Power BI a usuarios invitados externos con Azure AD B2B](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Puntos a tener en cuenta sobre la colaboración entre inquilinos de Microsoft 365

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Uso compartido de cuentas de usuario, licencias, suscripciones y almacenamiento

Cada organización mantiene sus propias cuentas de usuario, identidades, grupos de seguridad, suscripciones, licencias y almacenamiento. Personas usar las características de colaboración de Microsoft 365 junto con las directivas de uso compartido y la configuración de seguridad para proporcionar acceso a la información necesaria mientras se mantiene el control de los recursos de la empresa.

- **Cuentas de usuario:** Las cuentas no se pueden compartir ni duplicar entre los inquilinos o particiones de Active Directory local Domain Services.

- **Suscripciones de licencias &amp; :** en Microsoft 365, las licencias de planes de licencia (también denominadas SKU o planes de Microsoft 365) proporcionan a los usuarios acceso a los servicios de Microsoft 365 definidos para esos planes.

- **Almacenamiento:** En los planes de licencias de Microsoft 365, los límites y límites de software para SharePoint Online se administran por separado de los límites de almacenamiento de buzones. Los límites de almacenamiento de buzones de correo se configuran y administran mediante Exchange Online. En ambos escenarios, el almacenamiento no se puede compartir entre inquilinos.

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>¿Podemos compartir espacios de nombres de dominio entre inquilinos de Microsoft 365?

No. Los nombres de dominio de la organización, como fabrikam.com o tailspintoys.com, solo se pueden asociar y usar con un único inquilino de Microsoft 365. Cada inquilino debe tener su propio espacio de nombres. Los espacios de nombres UPN, SMTP y SIP no se pueden compartir entre inquilinos.

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>¿Qué ocurre con los componentes híbridos y la colaboración entre inquilinos de Microsoft 365?

Los componentes híbridos locales, como una organización de Exchange y Azure AD Connect, no se pueden dividir entre varios inquilinos.
