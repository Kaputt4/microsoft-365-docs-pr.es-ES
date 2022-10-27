---
title: Guías de configuración de Azure Active Directory
ms.author: Kwekua
author: Kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
description: Obtenga información sobre las guías de configuración de Azure Active Directory.
ms.openlocfilehash: df54d2218e40fa6b184399c33b8e53f614b843e6
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68734261"
---
# <a name="azure-active-directory-setup-guides"></a>Guías de configuración de Azure Active Directory

Las características de Azure Active Directory (Azure AD) le ayudan a administrar y proteger su organización. Estas guías de configuración le ayudarán a integrar esas características de una manera sencilla. En las secciones siguientes, describiremos brevemente las guías de configuración y compartiremos vínculos a las guías.

## <a name="who-are-these-setup-guides-for"></a>¿Para quién son estas guías de configuración?

Estas guías de configuración están diseñadas para organizaciones pequeñas y medianas que normalmente no tienen un equipo de identidades dedicado. No es necesario ser un experto en identidades para usarlos.

## <a name="what-to-expect-and-what-youll-need"></a>Qué esperar y qué necesitará

Las guías de configuración le ayudan a configurar la funcionalidad principal de Azure AD. Si necesita configurar una configuración más avanzada, la guía de configuración le dirigirá a la ubicación adecuada en el portal de Azure AD.

### <a name="required-permissions"></a>Permisos necesarios

Debe ser miembro de los siguientes roles administrativos:

- Administrador global: permite usar herramientas integradas en las guías de configuración para realizar cambios en la organización de Microsoft 365.

- Lector global: permite ver las guías de configuración, pero no realizar cambios en el inquilino.

## <a name="identity-security-for-teams"></a>Seguridad de identidad para Teams

Azure Active Directory (Azure AD) es nuestro servicio de administración de identidades y acceso basado en la nube, que ayuda a los empleados a iniciar sesión y acceder a aplicaciones y servicios.
Este catálogo contiene algunas características de seguridad básicas que puede usar para asegurarse de que los usuarios están seguros y tienen el tiempo más productivo mediante Teams.

### <a name="licensing"></a>Licencias

Se requiere una licencia de Azure Active Directory P2 para usar las características de seguridad de este catálogo.

[Abrir el catálogo seguridad de identidades para Teams](https://portal.office.com/AdminPortal/home?Q=azuredocs#/teamsidentity)

## <a name="identity-governance"></a>Gobernanza de identidades

Este catálogo de asistentes está diseñado para ayudar a los clientes con la funcionalidad de Azure Active Directory P2, incluidas las revisiones de acceso (AR), Privileged Identity Management (PIM) y la administración de derechos (ELM). Para PIM y ELM, ofrecemos una lista seleccionada de documentos y un puntero al Centro de administración de Azure Active Directory, donde el administrador puede configurar esta funcionalidad. Para AR, ofrecemos una experiencia totalmente automatizada que permite a los administradores elegir entre dos plantillas. Estas plantillas incluyen una que permite a los propietarios del grupo aprobar el uso de invitados en todos los grupos de Microsoft 365. Esta es una directiva principal que los clientes usan hoy en día.  

A continuación, ofrecemos una plantilla de prueba, donde el administrador es el revisor de invitados para un grupo específico que elijan. Si el inquilino ya tiene una revisión que abarca todos los usuarios invitados de grupos de Microsoft 365, el administrador se dirigirá al Centro de administración de Azure Active Directory para administrar la revisión existente y no habrá ninguna experiencia automatizada.

[Abra la guía de configuración de Identity Governance](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/identitygovernance)

> [!NOTE]
> Se requiere una licencia de Azure Active Directory P2 para usar las características de seguridad de este catálogo.

## <a name="azure-active-directory-deployment"></a>Implementación de Azure Active Directory  

La guía de configuración de Azure Active Directory le ayudará a configurar las características más comunes de Azure AD en un orden recomendado. La guía de configuración se divide en tres secciones: **Inicial**, **Núcleo** y **Avanzadas**. Cada sección recomienda un conjunto de características que debe activar.

Las guías de configuración contienen una lista de comprobación de las tareas que necesita completar y puede realizar un seguimiento del progreso a medida que vaya a través de las guías. Las guías también se vincularán a las demás guías de configuración cuando sea necesario.

[Abra la guía de instalación de Azure Active Directory](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/azureadsetup).

## <a name="add-or-sync-users-to-your-microsoft-account"></a>Adición o sincronización de usuarios a su cuenta de Microsoft  

Esta guía le ayuda a configurar las cuentas de usuario en Azure y Microsoft 365. En función del entorno y las necesidades, puede elegir agregar usuarios individualmente, migrar el directorio local con Azure AD Cloud Sync o Azure AD Connect o solucionar problemas de sincronización existentes.

### <a name="licensing"></a>Licencias

El uso de las herramientas de sincronización de Azure Active Directory es gratuito e incluye todas las suscripciones de Microsoft 365.

[Abra la guía de configuración Agregar o sincronizar usuarios](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/identitywizard).

## <a name="secure-your-cloud-apps-with-single-sign-on-sso"></a>Protección de las aplicaciones en la nube con el inicio de sesión único (SSO)

Esta guía está diseñada para ayudarle a agregar aplicaciones en la nube a Microsoft 365. En nuestra guía, puede agregar una aplicación al inquilino, agregar usuarios a la aplicación, asignar roles, etc.  Si la aplicación admite Single Sign-On (SSO), también le guiaremos por esa configuración.

### <a name="licensing"></a>Licencias

Cada suscripción de pago a Microsoft 365 incluye una suscripción gratuita a Azure AD. Puede usar Azure AD para administrar las aplicaciones y crear y administrar cuentas de usuario y grupo.

[Abra la guía de instalación Agregar una aplicación en la nube a Microsoft 365](https://portal.office.com/AdminPortal/home?Q=azuredocs#/azureadappintegration)

## <a name="azure-self-service-password-reset-sspr-guide"></a>Guía de restablecimiento de contraseña de Azure Self-Service (SSPR)

Esta guía de configuración está diseñada para ayudarle a habilitar y configurar el autoservicio de restablecimiento de contraseña. La guía de configuración le guiará por las opciones recomendadas, incluidas la escritura diferida de contraseñas y las notificaciones de administrador.

### <a name="licensing"></a>Licencias

SSPR requiere una de las siguientes licencias:

- Azure Active Directory P1 o P2

- Microsoft 365 Empresa Premium

- Microsoft 365 Enterprise E3 o E5  

- Enterprise Mobility and Security E3 o E5

[Abra la guía de configuración de autoservicio de restablecimiento de contraseña](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/ssprsetup).

## <a name="multi-factor-authentication-mfa"></a>Autenticación multifactor (MFA)

Esta guía proporciona el estado de MFA actual y ayuda a los administradores de TI a seleccionar la mejor opción de MFA que cumpla los requisitos de su organización. A continuación, ayudamos a configurar y aplicar el método MFA seleccionado para la organización.

### <a name="licensing"></a>Licencias

El acceso condicional requiere una licencia P1 o P2 de Azure Active Directory, los valores predeterminados de seguridad y MFA por usuario son gratuitos e se incluyen con todas las suscripciones de Microsoft 365.

[Abra la guía multifactor authentication (MFA)](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/mfasetupguide)

## <a name="the-passwordless-setup-guide"></a>Guía de configuración sin contraseña

La guía de configuración sin contraseña está diseñada para ayudarle a determinar el mejor método sin contraseña para su entorno. Los métodos incluyen claves de seguridad, Windows Hello para empresas y la aplicación Microsoft Authenticator. Si la recomendación está Windows Hello para empresas, hay una sección que le guiará por las distintas opciones. La guía le hace preguntas para ayudarle a crear un plan paso a paso.

### <a name="licensing"></a>Licencias

Cada suscripción de pago a Microsoft 365 incluye una suscripción gratuita a Azure AD. Puede usar Azure AD para administrar las aplicaciones y crear y administrar cuentas de usuario y grupo.

[Abra la guía de configuración sin contraseña](https://admin.microsoft.com/adminportal/home?Q=azuredocs#/modernonboarding/passwordlesssetup).
