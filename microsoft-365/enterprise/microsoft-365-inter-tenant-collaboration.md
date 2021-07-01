---
title: Microsoft 365 colaboración entre inquilinos
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Obtenga información sobre Microsoft 365 colaboración entre inquilinos y organizaciones, lo que permite que distintas organizaciones trabajen juntas de forma segura.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a0a9d15608e046e72ba579b77ba44092ed2ecb46
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229856"
---
# <a name="microsoft-365-inter-tenant-collaboration"></a>Microsoft 365 colaboración entre inquilinos

Supongamos que dos organizaciones, Fabrikam y Contoso, cada una de ellas tienen una Microsoft 365 empresarial y quieren trabajar juntos en varios proyectos; algunas de las cuales se ejecutan durante un tiempo limitado y otras están en curso. ¿Cómo pueden Fabrikam y Contoso permitir que sus personas y equipos colaboren de forma más eficaz en sus diferentes Microsoft 365 inquilinos de forma segura? Microsoft 365, junto con la colaboración B2B Azure Active Directory (Azure AD), proporciona varias opciones. En este artículo se describen varios escenarios clave que Fabrikam y Contoso pueden tener en cuenta.

Microsoft 365 de colaboración entre inquilinos incluyen el uso de una ubicación central para archivos y conversaciones, el uso compartido de calendarios, el uso de mensajería instantánea, llamadas de audio y vídeo para la comunicación y la protección del acceso a recursos y aplicaciones. Use las tablas siguientes para seleccionar soluciones y obtener más información.

## <a name="exchange-online-collaboration-options"></a>Exchange Online de colaboración

| Finalidad del uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Compartir calendarios con otra Microsoft 365 organización |Los administradores pueden configurar diferentes niveles de acceso al calendario en Exchange Online para permitir que las empresas colaboren con otras empresas y permitir que los usuarios compartan las programaciones (información de disponibilidad) con otras personas. | <ul><li>[Uso compartido](/exchange/sharing/sharing) </li><li> [Relaciones de la organización](/exchange/sharing/organization-relationships/organization-relationships) </li><li> [Crear una relación de la organización](/exchange/sharing/organization-relationships/create-an-organization-relationship) </li><li> [Modificar una relación de la organización](/exchange/sharing/organization-relationships/modify-an-organization-relationship) </li><li> [Quitar una relación de la organización](/exchange/sharing/organization-relationships/remove-an-organization-relationship) </li><li> [Compartir calendarios con usuarios externos](https://support.office.com/article/fb00dd4e-2d5f-4e8d-8ff4-94b2cf002bdd) </li></ul> |
|Controlar cómo los usuarios comparten sus calendarios con personas ajenas a la organización | Los administradores aplican directivas de uso compartido a los buzones de los usuarios para controlar con quién se puede compartir y el nivel de acceso concedido |  <ul><li> [Directivas de uso compartido](/exchange/sharing/sharing-policies/sharing-policies) </li><li> [Crear una directiva de uso compartido](/exchange/sharing/sharing-policies/create-a-sharing-policy) </li><li> [Aplicar una directiva de uso compartido a buzones](/exchange/sharing/sharing-policies/apply-a-sharing-policy) </li><li> [Modificar, desactivar o quitar una directiva de uso compartido](/exchange/sharing/sharing-policies/modify-a-sharing-policy) </li></ul> |
|Configurar canales de correo electrónico seguros y controlar el flujo de correo con organizaciones asociadas | Los administradores crean conectores para aplicar seguridad a los intercambios de correo con una organización asociada o un proveedor de servicios. Los conectores aplican el cifrado a través de la seguridad de la capa de transporte (TLS), además de permitir restricciones en los nombres de dominio o los intervalos de direcciones IP desde los que los asociados envían correo electrónico. |  <ul><li> [Cómo Exchange Online usa TLS para proteger las conexiones del correo electrónico](../compliance/exchange-online-uses-tls-to-secure-email-connections.md) </li><li> [Configurar un flujo de correo mediante conectores](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) </li><li> [Dominios remotos](/exchange/mail-flow-best-practices/remote-domains/remote-domains) </li><li> [Configurar el conector para el flujo de correo seguro con una organización asociada](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) </li><li> [Procedimientos recomendados de flujo de correo (introducción)](/exchange/mail-flow-best-practices/mail-flow-best-practices) </li></ul> |

## <a name="sharepoint-online-and-onedrive-for-business-collaboration-options"></a>SharePoint Opciones de colaboración OneDrive para la Empresa en línea y en línea

| Objetivos de uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Compartir sitios y documentos con usuarios externos | Los administradores configuran el uso compartido en el inquilino o en el nivel de colección de sitios para cuentas autenticadas, de trabajo o educativas autenticadas o de invitados de Microsoft |  <ul><li> [Administrar el uso compartido externo en su entorno de SharePoint Online](https://support.office.com/article/Manage-external-sharing-for-your-SharePoint-Online-environment-C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85?ui=en-US&amp;rs=en-US&amp;ad=US) </li><li> [Restringir el uso compartido de contenido de SharePoint y OneDrive por dominio](/sharepoint/restricted-domains-sharing) </li><li> [Usar SharePoint Online como una solución de extranet de empresa a empresa (B2B)](https://support.office.com/article/7b087413-165a-4e94-8871-4393e0b9c037) </li></ul> |
|Seguimiento y control del uso compartido externo para usuarios finales | OneDrive para la Empresa propietarios de archivos y SharePoint usuarios finales en línea configuran el uso compartido de sitios y documentos y establecen notificaciones para realizar un seguimiento del uso compartido |  <ul><li> [Configurar notificaciones para uso compartido externo para OneDrive para la Empresa](https://support.office.com/article/Configure-notifications-for-external-sharing-for-OneDrive-for-Business-b640c693-f170-4227-b8c1-b0a7e0fa876b) </li><li> [Compartir archivos o carpetas de SharePoint](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) </li></ul> |

## <a name="skype-for-business-collaboration-options"></a>Skype Empresarial de colaboración

| Finalidad del uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Skype Empresarial Online: mensajería instantánea, llamadas y presencia con otros Skype Empresarial usuarios | Los administradores pueden habilitar sus Skype Empresarial en línea para mensajería instantánea, realizar llamadas de audio y vídeo y ver la presencia de usuarios en otro Microsoft 365 inquilino. | [Permitir a los usuarios contactar con usuarios externos de Skype Empresarial](https://support.office.com/article/b414873a-0059-4cd5-aea1-e5d0857dbc94)|
|Skype Empresarial Online: mensajería instantánea, llamadas y presencia con Skype usuarios (consumidor) | Los administradores pueden habilitar sus Skype Empresarial en línea para mensajería instantánea, realizar llamadas y ver presencia con Skype usuarios (consumidores). | [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](https://support.office.com/article/08666236-1894-42ae-8846-e49232bbc460)|

## <a name="azure-ad-b2b-collaboration-options"></a>Opciones de colaboración B2B de Azure AD

| Finalidad del uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Colaboración B2B de Azure AD: uso compartido de contenido agregando usuarios externos a un grupo en el directorio de una organización | Un administrador global de un inquilino de Microsoft 365 puede invitar Microsoft 365 los usuarios de otro inquilino de Microsoft 365 a unirse a su directorio, agregar esos usuarios externos a un grupo y conceder acceso al contenido, como sitios SharePoint y bibliotecas para el grupo. |  <ul><li> [¿Qué es azure AD B2B collaboration preview?](/azure/active-directory/active-directory-b2b-what-is-azure-ad-b2b) </li><li> [Azure AD B2B: las nuevas actualizaciones hacen que la intercalación entre empresas sea fácil](https://blogs.technet.microsoft.com/enterprisemobility/2017/02/01/azure-ad-b2b-new-updates-make-cross-business-collab-easy/) </li><li> [Uso compartido externo y Azure Active Directory colaboración B2B](/azure/active-directory/active-directory-b2b-o365-external-user) </li><li> [Azure Active Directory API y personalización de colaboración B2B](/azure/active-directory/active-directory-b2b-api) </li><li> [Azure AD e Identity Show: Colaboración B2B de Azure AD (empresa a empresa)](https://channel9.msdn.com/Series/Azure-AD-Identity/AzureADB2B) </li></ul> |

## <a name="microsoft-365-collaboration-options"></a>Microsoft 365 de colaboración

| Finalidad del uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Microsoft 365 Grupos: correo electrónico, calendario, OneNote y archivos compartidos en un lugar central | Los grupos son compatibles con Business Essentials, Business Premium, Education y los Enterprise planes E1, E3 y E5. Los usuarios de un Microsoft 365 pueden crear un grupo e invitar a personas de otro Microsoft 365 inquilino como usuarios invitados. También se aplica a Dynamics CRM. |  <ul><li> [Obtener más información sobre los grupos de Microsoft 365](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) </li><li> [Acceso de invitado en Microsoft 365 grupos](https://support.office.com/article/bfc7a840-868f-4fd6-a390-f347bf51aff6) </li><li> [Implementar Microsoft 365 grupos](/previous-versions/dynamicscrm-2016/administering-dynamics-365/dn896591(v=crm.8)) </li></ul> |

## <a name="yammer-collaboration-options"></a>Yammer de colaboración

| Finalidad del uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Yammer: colaboración a través de un medio social empresarial | A menos que un administrador de Yammer deshabilite la capacidad de crear grupos externos, los usuarios pueden crear grupos externos para colaborar en Yammer a través de conversaciones, la capacidad de gustar y seguir publicaciones, compartir archivos y chatear en línea. | [Crear y administrar grupos externos en Yammer](https://support.office.com/article/9ccd15ce-0efc-4dc1-81bc-4a424ab6f92a)|

## <a name="teams-collaboration-options"></a>Teams de colaboración

|Finalidad del uso compartido|Acción administrativa|Información sobre cómo hacerlo|
|:-----|:-----|:-----|
|Colaborar en Teams con usuarios externos a la organización | Un administrador global para la invitación Microsoft 365 inquilino debe habilitar la colaboración externa en Teams. Los administradores globales y los propietarios de equipos ahora podrán invitar a cualquier persona con una dirección de correo electrónico a colaborar en Teams.  <br/> Los administradores también pueden administrar y editar invitados que ya están presentes en su inquilino. |  <ul><li> [Autorizar el acceso de invitado](/microsoftteams/teams-dependencies) </li><li> [Activar o desactivar el acceso de invitado en Teams](/microsoftteams/set-up-guests) </li><li> [Usar PowerShell para controlar el acceso de invitado](/microsoftteams/guest-access-powershell) </li><li> [Lista de comprobación de acceso de invitado](/microsoftteams/guest-access-checklist) </li><li> [Ver usuarios invitados](/microsoftteams/view-guests) </li><li> [Editar información del usuario invitado](/microsoftteams/edit-guests-information) </li></ul> |
|Los propietarios de equipos pueden invitar y administrar cómo colaboran los invitados en sus equipos.  |Los propietarios de equipos tienen controles adicionales sobre lo que los invitados pueden hacer dentro de sus equipos. |  <ul><li> [Agregar invitados](https://support.office.com/article/teams-and-channels-df38ae23-8f85-46d3-b071-cb11b9de5499?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_addingguests&amp;ID0EAABAAA=Add_guests) </li><li> [Agregar un invitado a un equipo](/microsoftteams/add-guests) </li><li> [Administrar el acceso de invitado en Teams](/microsoftteams/manage-guests) </li><li> [Ver quién está en un equipo o en un canal](https://support.office.com/article/see-who-s-on-a-team-or-in-a-channel-5c6be9be-9c45-4a0f-a1a0-f332b23cb6b7?ui=en-US&amp;rs=en-US&amp;ad=US) </li></ul> |
|Los invitados de otros inquilinos pueden ver contenido en Teams y colaborar con otros miembros | Ninguno. | [La experiencia de acceso de invitado](/microsoftteams/guest-experience)|

## <a name="power-bi-collaboration-options"></a>Power BI de colaboración

| Finalidad del uso compartido | Acción administrativa | Información sobre cómo hacerlo |
|:-----|:-----|:-----|
|Power BI permite a los usuarios invitados externos consumir contenido compartido con ellos a través de vínculos. Esto permite a los usuarios de la organización distribuir contenido de forma segura entre organizaciones.<br/> | El Power BI puede controlar si los usuarios pueden invitar a usuarios externos a ver contenido dentro de la organización.| [Distribuir Power BI contenido a usuarios invitados externos con Azure AD B2B](/power-bi/service-admin-azure-ad-b2b) |

## <a name="points-to-be-aware-of-about-microsoft-365-inter-tenant-collaboration"></a>Puntos para tener en cuenta acerca de Microsoft 365 colaboración entre inquilinos

### <a name="sharing-of-user-accounts-licenses-subscriptions-and-storage"></a>Uso compartido de cuentas de usuario, licencias, suscripciones y almacenamiento

Cada organización mantiene sus propias cuentas de usuario, identidades, grupos de seguridad, suscripciones, licencias y almacenamiento. Las personas usan las características de colaboración en Microsoft 365 junto con las directivas de uso compartido y la configuración de seguridad para proporcionar acceso a la información necesaria mientras mantienen el control de los activos de la compañía.

- **Cuentas de usuario:** Las cuentas no se pueden compartir ni duplicar entre los inquilinos o particiones de los Servicios de dominio de Active Directory locales.

- Suscripciones de **&amp; licencias:** en Microsoft 365, las licencias de planes de licencias (también denominadas SKU o planes de Microsoft 365) dan a los usuarios acceso a los servicios de Microsoft 365 definidos para dichos planes.

- **Storage:** En Microsoft 365 de licencias, los límites y límites de software para SharePoint Online se administran de forma independiente de los límites de almacenamiento de buzones. Los límites de almacenamiento de buzones de correo se establecen y administran mediante Exchange Online. En ambos escenarios, el almacenamiento no se puede compartir entre inquilinos.

### <a name="can-we-share-domain-namespaces-across-microsoft-365-tenants"></a>¿Podemos compartir espacios de nombres de dominio entre Microsoft 365 inquilinos?

No. Los nombres de dominio de la organización, como fabrikam.com o tailspintoys.com, solo se pueden asociar y usar con un único Microsoft 365 inquilino. Cada inquilino debe tener su propio espacio de nombres. Los espacios de nombres UPN, SMTP y SIP no se pueden compartir entre inquilinos.

### <a name="what-about-hybrid-components-and-microsoft-365-inter-tenant-collaboration"></a>¿Qué sucede con los componentes híbridos Microsoft 365 colaboración entre inquilinos?

Los componentes híbridos locales, como una organización Exchange y Azure AD Conectar, no se pueden dividir entre varios inquilinos.
