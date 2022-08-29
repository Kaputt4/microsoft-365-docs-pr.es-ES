---
title: Resumen de Microsoft 365 para la seguridad empresarial de Contoso Corporation
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: scotv
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo Contoso usa las características de seguridad de Microsoft 365 para empresas.
ms.openlocfilehash: 46611f5321c893466448b39a9990501d9b3fafc2
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385471"
---
# <a name="summary-of-microsoft-365-for-enterprise-security-for-the-contoso-corporation"></a>Resumen de Microsoft 365 para la seguridad empresarial de Contoso Corporation

Para obtener la aprobación para implementar Microsoft 365 para empresas, el departamento de seguridad de TI de Contoso realizó una revisión de seguridad exhaustiva. Identificaron los siguientes requisitos de seguridad para la nube:

- Use los métodos más seguros de autenticación para el acceso de los empleados a los recursos en la nube.
- Asegúrese de que los equipos y dispositivos móviles se conecten y accedan a las aplicaciones de manera segura.
- Proteja los equipos y el correo electrónico contra malware.
- Los permisos de los recursos digitales basados en la nube definen quién puede acceder a qué y qué pueden hacer, y están diseñados para el acceso con privilegios mínimos.
- Los recursos digitales confidenciales y altamente regulados se etiquetan, cifran y almacenan en ubicaciones seguras.
- Los recursos digitales altamente regulados están protegidos con cifrado y permisos adicionales.
- El personal de seguridad de TI puede supervisar la posición de seguridad actual desde los paneles centrales y recibir notificaciones de eventos de seguridad para una respuesta y mitigación rápidas.

## <a name="the-contoso-path-to-microsoft-365-security-readiness"></a>La ruta de acceso de Contoso a la preparación de seguridad de Microsoft 365

Contoso ha seguido estos pasos para preparar su seguridad para la implementación de Microsoft 365 para empresas:

1. Límite de cuentas de administrador para la nube

   Contoso realizó una amplia revisión de sus cuentas de administrador de Servicios de dominio de Active Directory (AD DS) existentes y configuró una serie de grupos y cuentas de administrador en la nube dedicados.

2. Clasificación de datos en tres niveles de seguridad

   Contoso realizó una revisión cuidadosa y determinó los tres niveles, que se usaron para identificar las características de Microsoft 365 para empresas con el fin de proteger los datos más valiosos.

3. Determinar las directivas de acceso, retención y protección de la información para los niveles de datos

   En función de los niveles de datos, Contoso determinó requisitos detallados para calificar futuras cargas de trabajo de TI que se mueven a la nube.

Para seguir los procedimientos recomendados de seguridad y Microsoft 365 para los requisitos de implementación empresarial, los administradores de seguridad de Contoso y su departamento de TI implementaron muchas características y funcionalidades de seguridad, como se describe en las secciones siguientes.

## <a name="identity-and-access-management"></a>Administración de identidad y acceso 

- Cuentas de administrador global dedicadas con MFA y PIM

  En lugar de asignar el rol de administrador global a cuentas de usuario diarias, Contoso creó tres cuentas de administrador global dedicadas con contraseñas seguras. Las cuentas están protegidas por Azure AD Multi-Factor Authentication (MFA) y Azure Active Directory (Azure AD) Privileged Identity Management (PIM). *PIM solo está disponible con Microsoft 365 E5.*

  El inicio de sesión con un administrador de Controlador de dominio de **Azure AD** o una cuenta **de administrador global** solo se realiza para tareas administrativas específicas. Las contraseñas solo son conocidas por el personal designado y solo se pueden usar en un período de tiempo configurado en PIM de Azure AD.

  Los administradores de seguridad de Contoso asignaron roles de administrador menores a las cuentas que son adecuadas para la función de trabajo del trabajador de TI.

  Para obtener más información, consulte [Acerca de los roles de administrador de Microsoft 365](/office365/admin/add-users/about-admin-roles).

- MFA para todas las cuentas de usuario

  MFA agrega una capa adicional de protección al proceso de inicio de sesión. Requiere que los usuarios confirmen una llamada telefónica, un mensaje de texto o una notificación de aplicación en su teléfono inteligente después de escribir correctamente su contraseña. Con MFA, las cuentas de usuario de Azure AD están protegidas contra el inicio de sesión no autorizado, incluso si una contraseña de cuenta está en peligro.

   - Para protegerse frente a los riesgos de la suscripción de Microsoft 365, Contoso requiere MFA en todos los **administradores de Azure AD DC** o cuentas **de administrador global** .
   - Para protegerse contra los ataques de suplantación de identidad (phishing), en los que un atacante pone en peligro las credenciales de una persona de confianza de la organización y envía mensajes de correo electrónico malintencionados, Contoso habilitó MFA en todas las cuentas de usuario, incluidos los administradores y ejecutivos.

- Acceso de dispositivos y aplicaciones más seguro con las directivas de Acceso Condicional

  Contoso usa [directivas de Acceso Condicional](../security/office-365-security/microsoft-365-policies-configurations.md) para la identidad, los dispositivos, Exchange Online y SharePoint. Las directivas de Acceso Condicional de identidad incluyen exigir cambios de contraseña para los usuarios de riesgo elevado e impedir que los clientes usen aplicaciones que no admiten la autenticación moderna. Las directivas condicionales de dispositivo incluyen la definición de aplicaciones aprobadas y la exigencia de equipos y dispositivos móviles compatibles. Las directivas de Acceso Condicional de Exchange Online incluyen el bloqueo de los clientes de ActiveSync y la configuración del cifrado de mensajes de Office 365. Las directivas de acceso condicional de SharePoint Online incluyen una protección adicional para sitios confidenciales y altamente regulados.

- Windows Hello para empresas

  Contoso implementó [Windows Hello para empresas](/windows/security/identity-protection/hello-for-business/hello-identity-verification) para eliminar eventualmente la necesidad de contraseñas mediante la autenticación en dos fases segura en equipos y dispositivos móviles que ejecutan Windows 10 Enterprise.

- Credential Guard de Windows Defender

  Para bloquear ataques dirigidos y malware que se ejecutan en el sistema operativo con privilegios administrativos, Contoso ha habilitado [Windows Defender Credential Guard](/windows/security/identity-protection/credential-guard/credential-guard) a través de la directiva de grupo de AD DS.

## <a name="threat-protection"></a>Protección contra amenazas

- Protección contra malware con antivirus de Microsoft Defender

  Contoso usa [el Antivirus de Microsoft Defender](/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) para la protección contra malware y la administración contra malware para equipos y dispositivos que ejecutan Windows 10 Enterprise.

- Proteger el flujo de correo electrónico y el registro de auditoría de buzones con Microsoft Defender para Office 365 

  Contoso usa Exchange Online Protection y [Defender para Office 365](/office365/securitycompliance/office-365-atp) para protegerse contra malware desconocido, virus y direcciones URL malintencionadas transmitidas a través de correos electrónicos.

  Contoso también ha habilitado el registro de auditoría de buzones para identificar quién inicia sesión en buzones de usuario, envía mensajes y realiza otras actividades realizadas por el propietario del buzón, un usuario delegado o un administrador.

- Supervisión y prevención de ataques con la investigación y respuesta ante amenazas de Office 365

  Contoso usa [Office 365 investigación y respuesta de amenazas](/office365/securitycompliance/office-365-ti) para proteger a los usuarios, facilitando la identificación y la dirección de ataques, y para evitar ataques futuros.

- Protección contra ataques más complejos con Advanced Threat Analytics

  Contoso usa [Advanced Threat Analytics (ATA)](/advanced-threat-analytics/what-is-ata) para protegerse de ataques dirigidos avanzados. De forma automática, ATA analiza, aprende e identifica el comportamiento de entidades normales e irregulares (usuarios, dispositivos y recursos).

## <a name="information-protection"></a>Protección de la información

- Protección de los activos digitales confidenciales y altamente regulados con etiquetas de Azure Information Protection

  Contoso determinó tres niveles de protección de datos e implementó [etiquetas de confidencialidad de Microsoft 365](../compliance/sensitivity-labels.md) que los usuarios aplican a los recursos digitales. Por sus secretos comerciales y otras propiedades intelectuales, Contoso usa subetiquetas de confidencialidad para datos altamente regulados. Este proceso cifra el contenido y restringe el acceso a cuentas de usuario y grupos específicos.

- Evitar filtraciones de datos de la intranet con Prevención de pérdida de datos

  Contoso configuró [directivas de Prevención de pérdida de datos de Microsoft Purview](../compliance/dlp-learn-about-dlp.md) para Exchange Online, SharePoint y OneDrive para la Empresa para evitar que los usuarios compartan información confidencial accidental o intencionadamente.

- Evitar pérdidas de datos de dispositivo con Windows Information Protection

  Contoso usa [Windows Information Protection (WIP)](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) para protegerse frente a la pérdida de datos a través de aplicaciones y servicios basados en Internet y aplicaciones empresariales y datos en dispositivos de propiedad empresarial y dispositivos personales que los empleados traen al trabajo.

- Supervisión en la nube con Microsoft Defender for Cloud Apps

  Contoso usa [Microsoft Defender for Cloud Apps](/cloud-app-security/what-is-cloud-app-security) para asignar su entorno en la nube, supervisar su uso y detectar eventos e incidentes de seguridad. *Microsoft Defender for Cloud Apps solo está disponible con Microsoft 365 E5.*

- Administración de dispositivos con Microsoft Intune

  Contoso usa [Microsoft Intune](/intune/introduction-intune) para inscribir, administrar, y configurar el acceso a los dispositivos móviles y las aplicaciones que se ejecutan en ellos. Los dispositivos basados en políticas de Acceso Condicional también requieren aplicaciones autorizadas, PCs y dispositivos móviles compatibles.

## <a name="security-management"></a>Administración de seguridad

- Panel de seguridad central para TI con Microsoft Defender for Cloud

  Contoso usa [Microsoft Defender for Cloud](https://azure.microsoft.com/services/security-center/) para presentar una visión unificada de la seguridad y la protección contra amenazas, para administrar directivas de seguridad en sus cargas de trabajo y para responder a ciberataques.

- Panel de seguridad central para los usuarios con Seguridad de Windows

  Contoso implementó la [aplicación Seguridad de Windows](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) en sus equipos y dispositivos que ejecutan Windows 10 Enterprise para que los usuarios puedan ver su posición de seguridad de un vistazo y tomar medidas.
