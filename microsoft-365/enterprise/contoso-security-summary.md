---
title: Resumen de Microsoft 365 para la seguridad empresarial de Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo contoso usa las características de seguridad de Microsoft 365 para empresas.
ms.openlocfilehash: 635336b70318acdd4ed013a2705691d160926e84
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649706"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Resumen de Microsoft 365 para la seguridad empresarial de Contoso Corporation

Para obtener la aprobación para implementar Microsoft 365 for Enterprise, el Departamento de seguridad de TI de Contoso realizó una revisión de seguridad exhaustiva. Identificaron los siguientes requisitos de seguridad para la nube:

- Use los métodos de autenticación más seguros para el acceso de los empleados a los recursos de la nube.
- Asegurarse de que los equipos y dispositivos móviles se conectan y tienen acceso a las aplicaciones de manera segura.
- Proteger los equipos y el correo electrónico del malware.
- Los permisos en activos digitales basados en la nube definen quién puede tener acceso a qué y qué pueden hacer y están diseñados para el acceso con privilegios mínimos
- Los activos digitales confidenciales y altamente regulados se etiquetan, cifran y almacenan en ubicaciones seguras.
- Los activos digitales altamente regulados están protegidos con cifrado y permisos adicionales.
- El personal de seguridad de ti puede supervisar la postura de seguridad actual de los paneles centrales y recibir notificaciones de eventos de seguridad para una rápida respuesta y mitigación.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>La ruta de acceso de Contoso a Microsoft 365 Security Readiness

Contoso siguió estos pasos para preparar su seguridad para su implementación de Microsoft 365 para empresas:

1. Limitar las cuentas de administrador para la nube

   Contoso realizó una revisión exhaustiva de sus cuentas de administrador existentes de servicios de dominio de Active Directory (AD DS) y ha configurado una serie de cuentas y grupos de administradores de nube dedicados.

2. Clasificación de datos en tres niveles de seguridad

   Contoso realizó una revisión minuciosa y determinó los tres niveles, que se usaron para identificar las características de Microsoft 365 para empresas con el fin de proteger los datos más valiosos.

3. Determinar las directivas de acceso, retención y protección de la información para los niveles de datos

   En función de los niveles de datos, contoso determinó los requisitos detallados para calificar las cargas de trabajo de ti futuras que se muevan a la nube.

Para seguir los procedimientos recomendados de seguridad y Microsoft 365 para los requisitos de implementación de la empresa, los administradores de seguridad de Contoso y su Departamento de ti implementaron muchas características y capacidades de seguridad, tal como se describe en las secciones siguientes.

## <a name="identity-and-access-management"></a>Administración de identidad y acceso 

- Cuentas de administrador global dedicadas con MFA y PIM

  En lugar de asignar el rol de administrador global a las cuentas de usuario diarias, contoso ha creado tres cuentas de administrador global dedicadas con contraseñas seguras. Las cuentas están protegidas por Azure multi-factor Authentication (MFA) y Azure Active Directory (Azure AD) privileged Identity Management (PIM). *PIM solo está disponible con Microsoft 365 E5.*

  El inicio de sesión con una cuenta de administrador global solo se realiza para tareas administrativas específicas. Las contraseñas solo las conoce el personal designado y solo se pueden usar en un período de tiempo configurado en el PIM de Azure AD.

  Los administradores de seguridad de Contoso tienen asignados menos roles de administrador en las cuentas apropiadas para la función de trabajo del trabajador de ti.

  Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- MFA para todas las cuentas de usuario

  MFA agrega una capa adicional de protección al proceso de inicio de sesión. Requiere que los usuarios acepten una llamada de teléfono, un mensaje de texto o una notificación de la aplicación en el smartphone después de escribir correctamente su contraseña. Con MFA, las cuentas de usuario de Azure AD están protegidas contra el inicio de sesión no autorizado, incluso si la contraseña de la cuenta está en peligro.

   - Para protegerse contra la intromisión de la suscripción de Microsoft 365, contoso requiere MFA en todas las cuentas de administrador global.
   - Para protegerse contra los ataques de suplantación de identidad (phishing), en los que un atacante pone en peligro las credenciales de una persona de confianza de la organización y envía mensajes de correo electrónico malintencionados, Contoso habilitó MFA en todas las cuentas de usuario, incluidos los administradores y ejecutivos.

- Acceso de dispositivos y aplicaciones más seguro con las directivas de Acceso Condicional

  Contoso usa [directivas de Acceso Condicional](../security/office-365-security/microsoft-365-policies-configurations.md) para la identidad, los dispositivos, Exchange Online y SharePoint. Las directivas de Acceso Condicional de identidad incluyen exigir cambios de contraseña para los usuarios de riesgo elevado e impedir que los clientes usen aplicaciones que no admiten la autenticación moderna. Las directivas condicionales de dispositivo incluyen la definición de aplicaciones aprobadas y la exigencia de equipos y dispositivos móviles compatibles. Las directivas de Acceso Condicional de Exchange Online incluyen el bloqueo de los clientes de ActiveSync y la configuración del cifrado de mensajes de Office 365. Las directivas de acceso condicional de SharePoint Online incluyen una protección adicional para sitios confidenciales y altamente regulados.

- Windows Hello para empresas

  Contoso implementó [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) para eliminar la necesidad de contraseñas mediante una autenticación en dos fases sólida en equipos PC y dispositivos móviles que ejecutan Windows 10 Enterprise.

- Credential Guard de Windows Defender

  Para bloquear el malware y los ataques de malware que se ejecutan en el sistema operativo con privilegios administrativos, contoso habilitó la [protección de credenciales de Windows Defender](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) mediante la Directiva de grupo de AD DS.

## <a name="threat-protection"></a>Protección contra amenazas

- Protección contra malware con Antivirus de Windows Defender

  Contoso usa [Antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) para la protección contra malware y la administración antimalware en los equipos y dispositivos que ejecutan Windows 10 Enterprise.

- Flujo de correo electrónico seguro y registro de auditoría del buzón de correo con Protección contra amenazas avanzada de Office 365 

  Contoso usa Exchange Online Protection y [Protección contra amenazas avanzada (ATP) de Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) para protegerse contra el malware desconocido, los virus y las direcciones URL malintencionadas que se transmiten a través de los mensajes de correo electrónico.

  Contoso también habilitó el registro de auditoría de buzones para identificar quién inicia sesión en buzones de usuario, envía mensajes y realiza otras actividades realizadas por el propietario del buzón, un usuario delegado o un administrador.

- Supervisión y prevención de ataques con la investigación y respuesta ante amenazas de Office 365

  Contoso usa la [investigación y respuesta de las amenazas de Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) para proteger a los usuarios al facilitar la identificación y el direccionamiento de los ataques, y para evitar futuros ataques.

- Protección contra ataques más complejos con Advanced Threat Analytics

  Contoso usa [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) para protegerse de ataques dirigidos avanzados. De forma automática, ATA analiza, aprende e identifica el comportamiento de entidades normales e irregulares (usuarios, dispositivos y recursos).

## <a name="information-protection"></a>Protección de la información

- Protección de los activos digitales confidenciales y altamente regulados con etiquetas de Azure Information Protection

  Contoso determinó tres niveles de protección de datos e implementó las [etiquetas de confidencialidad de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) que los usuarios aplican a los activos digitales. Para sus secretos comerciales y otra propiedad intelectual, contoso usa subetiquetas de distinción para datos altamente regulados. Este proceso cifra el contenido y restringe el acceso a grupos y cuentas de usuario específicos.

- Evitar filtraciones de datos de la intranet con Prevención de pérdida de datos

  Las directivas de [prevención de pérdida de datos](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) configuradas de Contoso para Exchange Online, SharePoint y OneDrive para la empresa para evitar que los usuarios compartan datos confidenciales de forma accidental o intencionada.

- Evitar pérdidas de datos de dispositivo con Windows Information Protection

  Contoso usa [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) para protegerse contra la filtración de datos a través de aplicaciones y servicios basados en Internet y de aplicaciones empresariales y datos de dispositivos de propiedad de empresa y dispositivos personales que los empleados trabajan.

- Supervisión en la nube con Microsoft Cloud App Security

  Contoso usa [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para asignar su entorno de nube, supervisar el uso y detectar los incidentes y eventos de seguridad. *Microsoft Cloud App Security solo está disponible con Microsoft 365 E5.*

- Administración de dispositivos con Microsoft Intune

  Contoso usa [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) para inscribir, administrar, y configurar el acceso a los dispositivos móviles y las aplicaciones que se ejecutan en ellos. Los dispositivos basados en políticas de Acceso Condicional también requieren aplicaciones autorizadas, PCs y dispositivos móviles compatibles.

## <a name="security-management"></a>Administración de seguridad

- Panel central de seguridad para TI con Azure Security Center

  Contoso usa el [centro de seguridad de Azure](https://azure.microsoft.com/services/security-center/) para presentar una vista unificada de la seguridad y la protección contra amenazas, para administrar las directivas de seguridad en sus cargas de trabajo y responder a cyberattacks.

- Panel de seguridad central para los usuarios con Seguridad de Windows

  Contoso implementó la [aplicación de seguridad de Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) en sus equipos y dispositivos que ejecutan Windows 10 Enterprise para que los usuarios puedan ver su postura de seguridad de un vistazo y emprender acciones.
