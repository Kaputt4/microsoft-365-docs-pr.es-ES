---
title: Información general de Microsoft 365 Enterprise Services | Microsoft docs
description: Este contenido proporciona información general sobre las recomendaciones de uso empresarial y empresarial de Microsoft 365.
author: jeffgilb
manager: femila
ms.prod: microsoft-365-business
ms.topic: article
ms.date: 08/23/2017
ms.author: jeffgilb
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 7772421a32abd863f4301a4bc3d8264d8fe44242
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290165"
---
# <a name="microsoft-365-enterprise-services-and-concepts"></a>Conceptos y servicios empresariales de Microsoft 365

Microsoft 365 Enterprise está diseñado para organizaciones grandes e incorpora Office 365 Enterprise, Windows 10 Enterprise y Enterprise Mobility + Security (EMS) para ofrecer la posibilidad a todos los usuarios de ser creativos y trabajar juntos de forma segura. Microsoft 365 Enterprise incluye una edición empresarial de las aplicaciones de Windows 10 y Office a través de Office 365 ProPlus.

Tanto Windows 10 como Office 365 ProPlus proporcionan nuevas versiones de características a la empresa en marzo y septiembre a través del Canal semianual. Una versión de características del Canal semianual se admite durante 18 meses. Microsoft Intune y System Center Configuration Manager proporcionan funcionalidades para implementar y actualizar Windows 10 y Office 365 ProPlus.

Estas son las versiones más recientes de Windows 10, Office 365 ProPlus, Microsoft Intune y System Center Configuration Manager:

|     |**Canal semianual (dirigido)**|**Canal semianual**|
|:-----|:-----|:-----|
|**Windows 10**|Windows 10 Fall Creators Update (próximamente)|Versión 1703|
|**Office 365 ProPlus**|Versión 1803|Versión 1708|
|**Intune**|No aplicable|Versión 1708|
|**System Center Configuration Manager**|Technical Preview versión 1708|Versión 1706<sup>*</sup>|

<sup>*</sup> La actualización 1706 para la rama actual de System Center Configuration Manager está disponible como actualización en consola para sitios instalados previamente que ejecutan la versión 1606, 1610 o 1702.

> [!NOTE]
> Los servicios de Microsoft Azure también se actualizan de forma periódica, pero no se hace referencia a ellos mediante un número de versión. Para revisar las actualizaciones más recientes, y las que se proporcionarán próximamente, para los servicios de Azure, consulte la [guía básica de la plataforma en la nube](https://www.microsoft.com/cloud-platform/roadmap).

Para más información sobre las características disponibles en estas versiones, vea los siguientes artículos:
- [Novedades de Windows 10](https://docs.microsoft.com/windows/whats-new/)
- [Información sobre la versión de Windows 10](https://technet.microsoft.com/windows/release-info)
- [Historial de actualizaciones para Windows 10](https://support.microsoft.com/help/4018124/windows-10-update-history)
- [Versiones de canal de actualización de cliente de Office 365](https://technet.microsoft.com/office/mt465751)
- [Novedades de Microsoft Intune](https://docs.microsoft.com/intune/whats-new)
- [Novedades de System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-incremental-versions)
- [Capacidades de Technical Preview 1708 para System Center Configuration Manager](https://docs.microsoft.com/sccm/core/get-started/capabilities-in-technical-preview-1708)

## <a name="services-overview"></a>Introducción a los servicios

En esta sección se proporciona información general sobre los servicios de EMS y Office 365 que incluye Microsoft 365 Enterprise. También se presentan los conceptos básicos necesarios para entender cómo aprovechar estas herramientas con el fin de satisfacer las necesidades de su organización. Estos servicios aportan capacidades que permiten a los administradores empresariales de Microsoft Cloud proteger la identidad y los dispositivos de los empleados, además de controlar el acceso a los datos en tránsito o en reposo de la empresa.

|Servicio|Descripción|
|-------|-----------|
|[Microsoft Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)|Azure AD incluye un conjunto completo de capacidades de administración de la identidad, como la autenticación multifactor, el registro de dispositivos, la administración de contraseñas y grupos de autoservicio, el control de acceso basado en roles, la supervisión del uso de aplicaciones, la auditoría avanzada y la supervisión y los avisos de seguridad.|
|[Azure AD Identity Protection](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection)|Con este servicio, podrá detectar posibles vulnerabilidades que afecten a las identidades de su organización y configurar respuestas automáticas mediante directivas de acceso condicional para inicios de sesión y usuarios de riesgo bajo, medio o alto.|
|[Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)|Gracias a este servicio, las organizaciones pueden minimizar el número de usuarios que tiene acceso permanente a operaciones privilegiadas. Azure AD Privileged Identity Management crea la figura del administrador temporal. Los administradores temporales deberían ser usuarios que necesiten disponer de acceso privilegiado de vez en cuando, pero no constantemente. Este rol está inactivo hasta que el usuario necesita acceso. Entonces, debe completar un proceso de activación para convertirse en administrador activo durante un período de tiempo predeterminado.|
|[Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection)| Azure Information Protection es una solución basada en la nube que forma parte de EMS E5. Permite a las organizaciones clasificar, etiquetar y proteger sus documentos y correos electrónicos. Esto puede realizarse automáticamente por administradores que definen reglas y condiciones, manualmente por los usuarios o una combinación en la que los usuarios reciben recomendaciones. Use las etiquetas de Azure Information Protection para aplicar la clasificación a los documentos y correos electrónicos. Al hacer esto, la clasificación se puede identificar en cualquier momento, independientemente de dónde se almacenen los datos o con quién se compartan.<br><br>La configuración de directivas de Azure Information Protection está protegida por [Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms). De manera similar a las etiquetas que se aplican, la protección que se aplica mediante Rights Management permanece con los documentos y los correos electrónicos, independientemente de la ubicación, ya sea dentro o fuera de la organización, las redes, los servidores de archivos y las aplicaciones.|
|[Microsoft Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune es un servicio de administración de movilidad empresarial (EMM) basado en nube que ayuda a los empleados a ser productivos mientras mantiene protegidos los datos corporativos. Intune se integra estrechamente con Azure AD para controlar el acceso y la identidad. También se usa para administrar dispositivos y aplicaciones. Las capacidades de [administración de dispositivos de Intune](https://docs.microsoft.com/intune/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies) sirven para configurar y proteger los dispositivos de los usuarios, incluidos los PC Windows.<br><br>Las capacidades de administración de dispositivos de Intune admiten el método de inscripción [Bring Your Own Device (BYOD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/enable-byod), que permite a los usuarios inscribir sus teléfonos, tabletas o equipos personales. También admite el método [Corporate-owned Device (COD)](https://docs.microsoft.com/enterprise-mobility-security/solutions/issue-corp-devices), que ofrece varios escenarios de administración, como la inscripción automática, los dispositivos compartidos o las configuraciones de requisitos de inscripción con autorización previa. Para mayor seguridad, incluso puede requerir MFA para inscribir un dispositivo. Una vez inscrito en el sistema de administración, Intune puede configurar las características y las opciones del dispositivo para habilitar el acceso seguro a los recursos de la compañía.|

## <a name="important-concepts-to-understand"></a>Conceptos importantes para comprender
En la tabla siguiente se describen los conceptos básicos y las capacidades de EMS con los que debería estar familiarizado.

|Concepto principal|Descripción|
|------------|-----------|
|[Azure multi-factor Authentication (MFA)](https://docs.microsoft.com/azure/multi-factor-authentication/multi-factor-authentication-get-started-cloud)|Como solución de verificación de dos pasos de Microsoft, Azure MFA ayuda a salvaguardar el acceso a los datos y las aplicaciones, a la vez que satisface la demanda de los usuarios para un sencillo proceso de inicio de sesión. Proporciona una autenticación sólida a través de una amplia variedad de métodos de verificación, como la llamada telefónica, el mensaje de texto o la comprobación de la aplicación móvil.|
|[Acceso condicional de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)|Esta capacidad de Azure AD le permite aplicar controles en el acceso a las aplicaciones en la nube de su entorno en condiciones específicas. Con los controles, puede asociar los requisitos adicionales al acceso o puede bloquearlos. La implementación de acceso condicional se basa en las directivas.|
|[Prevención de pérdida de datos (DLP) de Exchange Online](https://support.office.com/article/Overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e)|Las directivas de prevención de pérdida de datos (DLP) de Exchange Online, disponibles como una característica premium de las suscripciones plan 2 de Exchange Online y Office 365, permiten a las organizaciones identificar, supervisar y proteger automáticamente la información confidencial en Office 365.<br><br>Con las directivas de DLP de Exchange Online, puede identificar información confidencial en varias ubicaciones, como Exchange Online, SharePoint Online y OneDrive para la empresa. Por ejemplo, estas directivas ayudan a identificar los documentos que contienen información confidencial o impedir el uso compartido accidental de información confidencial con personas de fuera de la organización.|
|[Reglas de flujo/transporte de correo de Exchange](https://support.office.com/article/Define-mail-flow-rules-to-encrypt-or-decrypt-email-messages-9B7DAF19-D5F2-415B-BC43-A0F5F4A585E8)|Las reglas de flujo de correo de Exchange, también denominadas reglas de transporte, buscan condiciones específicas en los mensajes que pasan por su organización y actúan sobre ellas. Las reglas de flujo de correo son similares a las reglas de la bandeja de entrada que están disponibles en muchos clientes de correo electrónico. La principal diferencia entre las reglas de flujo de correo y las reglas que se configurarían en una aplicación cliente como Outlook es que las reglas de flujo de correo actúan en mensajes mientras están en tránsito en lugar de después de que se entregue el mensaje. Las reglas de flujo de correo también contienen un conjunto más amplio de condiciones, excepciones y acciones, que proporcionan la flexibilidad para implementar muchos tipos de directivas de mensajería.|
|[Administración de dispositivos móviles de Intune](https://docs.microsoft.com/intune/understand-explore/introduction-to-microsoft-intune)|Intune proporciona la administración de dispositivos móviles (MDM) mediante los protocolos o las API que están disponibles en los sistemas operativos móviles. Incluye tareas como la inscripción de dispositivos en la administración, por lo que tiene un inventario de dispositivos que tienen acceso a servicios corporativos, configurando dispositivos para garantizar que cumplen los estándares de seguridad y mantenimiento de la empresa, lo que proporciona certificados y perfiles Wi-Fi/VPN a obtener acceso a los servicios corporativos, informar sobre el cumplimiento del dispositivo y medirlo con los estándares corporativos y quitar datos corporativos de los dispositivos administrados.|
|[Directivas de protección de aplicaciones de Intune](https://docs.microsoft.com/intune/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)|Las directivas de protección de aplicaciones de Intune se pueden usar para proteger los datos de su empresa en aplicaciones móviles con o sin la inscripción de dispositivos en la administración. De hecho, los dispositivos móviles de los usuarios pueden incluso ser administrados por otra solución MDM que no es de Microsoft mientras [Intune ayuda a proteger la información de Office 365](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-company-data-without-managing-devices). Mientras se asegura de que sus empleados todavía puedan ser productivos, también puede evitar la pérdida de datos (de forma intencionada e involuntaria). Mediante la implementación de directivas de nivel de aplicación, puede restringir el acceso a los recursos de la empresa y mantener los datos dentro del control del Departamento de ti.|
|[Vigencia del token de Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-configurable-token-lifetimes)|Puede especificar la duración de un token emitido por Azure Active Directory (Azure AD). Puede establecer la vigencia de tokens para todas las aplicaciones de la organización, para una aplicación multiempresa (multiorganización) o para una entidad de servicio específica de la organización.|
|Agentes de identidad de Microsoft|Microsoft proporciona aplicaciones para todas las plataformas móviles que permiten el puente de las credenciales entre aplicaciones de distintos proveedores y permite características mejoradas especiales que requieren un único lugar seguro desde el que validar las credenciales. Llamamos a estos agentes. En iOS y Android, estos agentes se proporcionan a través de las aplicaciones Microsoft Authenticator y portal de empresa de Intune. En Windows 10, esta funcionalidad se proporciona mediante un selector de cuentas integrado en el sistema operativo, conocido técnicamente como el agente de autenticación Web.|

## <a name="security-best-practices-and-recommendations"></a>Sugerencias y procedimientos recomendados de seguridad
Aunque no existe una sola recomendación ideal para todos los entornos de cliente, en el artículo [Recommended security policies and configurations](microsoft-365-policies-configurations.md) (Configuraciones y directivas de seguridad recomendadas) se presentan conceptos importantes sobre procedimientos recomendados de seguridad. En este artículo también se describen recomendaciones generales de Microsoft sobre cómo aplicar directivas y configuraciones en Microsoft Cloud para garantizar que sus empleados estén protegidos y sean productivos.

### <a name="baseline-recommended-security-policies-and-configurations"></a>Directivas y configuraciones de seguridad recomendadas de línea base
[Recomendaciones generales de directivas de identidad y acceso a dispositivos](identity-access-policies.md) describe las directivas comunes recomendadas para ayudarle a proteger Microsoft 365 Enterprise. También se tratan las configuraciones de plataforma cliente predeterminadas que se recomiendan para proporcionar la mejor experiencia de sistema operativo a los usuarios, además de los requisitos técnicos previos del acceso condicional.

### <a name="exchange-online-access-policies"></a>Directivas de acceso de Exchange Online
[Recomendaciones de directivas para ayudar a proteger el correo electrónico](secure-email-recommended-policies.md) proporciona recomendaciones de Microsoft para ayudarle a proteger el correo electrónico de la organización y los clientes de correo electrónico que admiten la autenticación moderna y el acceso condicional. Estas recomendaciones se suman a las [recomendaciones comunes sobre directivas de acceso e identidad](identity-access-policies.md).

### <a name="sharepoint-online-access-policies"></a>Directivas de acceso de SharePoint Online
Se proporcionan recomendaciones para [proteger el acceso a archivos de SharePoint Online](sharepoint-file-access-policies.md) , además de las [recomendaciones comunes de directivas de acceso y identidad](identity-access-policies.md) y las [recomendaciones de directivas para proteger el correo electrónico](secure-email-recommended-policies.md). En este artículo se describen las nuevas directivas que deben crearse y cómo deben modificarse las directivas existentes para proteger el correo electrónico de Exchange Online y el acceso a archivos de SharePoint Online.

## <a name="deploy-windows-10-and-office-365-proplus"></a>Implementación de Windows 10 y Office 365 ProPlus
Obtenga información sobre cómo implementar Windows 10 y Office 365 ProPlus e integrar en Microsoft Azure Active Directory (Azure AD) o local Active Directory Domain Services (AD DS). Implemente Windows 10, Office 365 ProPlus y el resto de aplicaciones de línea de negocio en dispositivos nuevos o actualice dispositivos existentes a Windows 10 mediante Intune, System Center Configuration Manager y directiva de grupo para administrar los dispositivos.

Para obtener más información, consulte los siguientes artículos:
- [Consideraciones de implementación para Windows 10](https://docs.microsoft.com/windows/deployment/planning/windows-10-deployment-considerations)
- [Guía de implementación para Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/deployment-guide-for-office-365-proplus)
- [Guía de procedimientos recomendados para implementar Office 365 ProPlus en un entorno empresarial](https://docs.microsoft.com/DeployOffice/best-practices/best-practices)
- [Implementación de aplicaciones de Office 365 ProPlus a dispositivos Windows 10 con Intune](https://docs.microsoft.com/intune/apps-add-office365)

Para obtener ayuda para la implementación con Microsoft 365, [póngase en contacto FastTrack](https://fasttrack.microsoft.com/microsoft365).

## <a name="manage-updates-to-windows-10-and-office-365-proplus"></a>Administración de las actualizaciones a Windows 10 y Office 365 ProPlus
Los vínculos siguientes le muestran cómo obtener el máximo control sobre la calidad y las actualizaciones de características para Windows 10 y Office 365 ProPlus. Aprenda a controlar el uso de ancho de banda de forma eficaz y a mantener Windows y Office al día con las características, funcionalidades y actualizaciones de seguridad más recientes.

Para obtener más información, vea los siguientes artículos:
- [Información general de Windows como servicio](https://docs.microsoft.com/windows/deployment/update/waas-overview)
- [Información general sobre los canales de actualización de Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)
- [Administración de actualizaciones de software con Intune](https://docs.microsoft.com/intune/windows-update-for-business-configure)
- [Implementar las actualizaciones de Windows 10 con System Center Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)<sup>*</sup>
- [Administración de Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/sccm/sum/deploy-use/manage-office-365-proplus-updates)

<sup>*</sup>Microsoft anima a las organizaciones que actualmente utilizan Configuration Manager para la administración de actualizaciones de Windows para continúen haciéndolo para equipos cliente Windows 10.

## <a name="next-steps"></a>Pasos siguientes
[Página del producto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)<br/>
[Guía básica de la plataforma en la nube](https://www.microsoft.com/cloud-platform/roadmap)
