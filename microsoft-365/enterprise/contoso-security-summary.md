---
title: Resumen de seguridad de Microsoft 365 Enterprise para Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Cómo usa Contoso las características de seguridad de Microsoft 365 Enterprise.
ms.openlocfilehash: 1aade29c8a4f9348b749025818e433981ec19091
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2019
ms.locfileid: "33353112"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a>Resumen de seguridad de Microsoft 365 Enterprise para Contoso Corporation

**Resumen:** Cómo usa Contoso las características de seguridad de Microsoft 365 Enterprise.

Para obtener la aprobación de la implementación de Microsoft 365 Enterprise por parte del departamento de seguridad de TI, se realizó una revisión de seguridad completa. Estos son los requisitos de seguridad de Contoso para la nube:

- Usar los métodos de autenticación más seguros para el acceso de los empleados a los recursos en la nube.
- Asegurarse de que los equipos y dispositivos móviles se conectan y acceden a las aplicaciones de forma segura.
- El correo electrónico y los equipos están protegidos frente al malware.
- Los permisos para los activos digitales en la nube definen quién puede acceder y qué puede hacer, y están diseñados para el acceso con privilegios mínimos.
- Los activos digitales confidenciales y altamente regulados se etiquetan, cifran y almacenan en ubicaciones seguras.
- Los activos digitales altamente regulados se protegen mediante permisos.
- La seguridad de TI puede supervisar el nivel de seguridad desde paneles centrales y recibir notificaciones de eventos de seguridad para una respuesta y mitigación rápidas.

## <a name="contosos-path-to-microsoft-365-security-readiness"></a>Ruta de acceso de Contoso para la preparación de la seguridad de Microsoft 365

Contoso siguió los pasos siguientes para preparar la seguridad de su implementación de Microsoft 365 Enterprise:

1. Limitación de las cuentas de administrador para la nube

   Contoso realizó una revisión exhaustiva de las cuentas de administrador de Active Directory Domain Services (AD DS) existentes y estableció una serie de grupos y cuentas de administrador de la nube.

2. Análisis de clasificación de datos en tres niveles

   Contoso realizó una revisión esmerada y definió los tres niveles, lo que se usó para determinar las características de Microsoft 365 Enterprise para proteger los datos más valiosos de Contoso.

3. Determinó las directivas de acceso, retención y protección de la información para los niveles de datos

   Según los niveles de datos, Contoso determinó los requisitos detallados, que se usarán para calificar las cargas de trabajo de TI que en el futuro se muevan a la nube.

De acuerdo con los procedimientos recomendados de seguridad y los requisitos de implementación de Microsoft 365 Enterprise, los administradores de seguridad de Contoso y el departamento de TI han implementado muchas funciones y características de seguridad, como se describe en las secciones siguientes.

## <a name="identity--access-management"></a>Administración de identidad y acceso 

- Cuentas de administrador global dedicadas con MFA y PIM

  En lugar de asignar el rol de administrador global a cuentas de usuario convencionales, Contoso creó tres cuentas de administrador global dedicadas con contraseñas muy seguras y las protegió con la autenticación multifactor (MFA) y Azure AD Privileged Identity Management (PIM).  PIM solo está disponible con Microsoft 365 Enterprise E5.

  El inicio de sesión con una cuenta de administrador global solo se realiza para tareas administrativas específicas, las contraseñas solo las conoce el personal designado y solo se pueden usar en los plazos configurados con Azure AD PIM. 

  Los administradores de seguridad de Contoso han asignado roles de administrador inferiores a las cuentas de acuerdo con la responsabilidad y puesto laboral de esa persona de TI.

  Para obtener más información, vea [Información sobre los roles de administrador de Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).

- MFA para todas las cuentas de usuario

  MFA agrega una capa adicional de protección al proceso de inicio de sesión al requerir a los usuarios que confirmen una llamada telefónica, un mensaje de texto o una notificación de aplicación en su smartphone después de introducir correctamente su contraseña. Con MFA, las cuentas de usuario de Azure AD están protegidas contra el inicio de sesión no autorizado incluso si la contraseña de una cuenta se pone en peligro.

   - Para protegerse contra la posibilidad de que la suscripción de Microsoft 365 se ponga en peligro, Contoso requiere MFA en todas las cuentas de administrador global.
   - Para protegerse contra los ataques de suplantación de identidad (phishing), en los que un atacante pone en peligro las credenciales de una persona de confianza de la organización y envía mensajes de correo electrónico malintencionados, Contoso habilitó MFA en todas las cuentas de usuario, incluidas las de administrador y el personal ejecutivo. 

- Acceso de dispositivos y aplicaciones más seguro con directivas de acceso condicional

  Contoso usa [directivas de acceso condicional](microsoft-365-policies-configurations.md) para la identidad, los dispositivos, Exchange Online y SharePoint Online. Las directivas de acceso condicional de identidad incluyen exigir cambios de contraseña para los usuarios de riesgo elevado e impedir que los clientes usen aplicaciones que no admiten la autenticación moderna. Las directivas condicionales de dispositivo incluyen la definición de aplicaciones aprobadas y la exigencia de equipos y dispositivos móviles compatibles. Las directivas de acceso condicional de Exchange Online incluyen el bloqueo de los clientes de ActiveSync y la configuración del cifrado de mensajes de Office 365. Las directivas de acceso condicional de SharePoint Online incluyen una protección adicional para sitios confidenciales y altamente regulados.

- Windows Hello para empresas

  Contoso ha implementado y requiere [Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) para eliminar, con el tiempo, la necesidad de contraseñas con autenticación segura en dos fases en los equipos y dispositivos móviles con Windows 10 Enterprise.

- Credential Guard de Windows Defender

  Para bloquear los ataques dirigidos y el malware que se ejecuta en el sistema operativo con privilegios administrativos, Contoso ha habilitado [Credential Guard de Windows Defender](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) a través de la directiva de grupo de AD DS.

## <a name="threat-protection"></a>Protección contra amenazas

- Protección contra malware con Antivirus de Windows Defender

  Contoso usa [Antivirus de Windows Defender](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) para la protección contra malware y la administración antimalware en los equipos y dispositivos que ejecutan Windows 10 Enterprise.

- Flujo de correo electrónico seguro y registro de auditoría del buzón de correo con Protección contra amenazas avanzada de Office 365 

  Contoso usa Exchange Online Protection y [Protección contra amenazas avanzada (ATP) de Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) para protegerse contra el malware desconocido, los virus y las direcciones URL malintencionadas que se transmiten a través de los mensajes de correo electrónico. 

  Contoso también ha habilitado el registro de auditoría del buzón de correo para determinar quién ha iniciado sesión en los buzones de usuario, quién ha enviado mensajes y otras actividades realizadas por el propietario del buzón, un usuario delegado o un administrador.

- Supervisión y prevención de ataques con la investigación y respuesta ante amenazas de Office 365

  Contoso usa la [investigación y respuesta ante amenazas de Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) para proteger a los usuarios de Office 365 facilitando la identificación y resolución de los ataques, y para evitar ataques en el futuro.

- Protección contra ataques más complejos con Advanced Threat Analytics

  Contoso usa [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) para protegerse de ataques dirigidos avanzados. De forma automática, ATA analiza, aprende e identifica el comportamiento de entidades normales e irregulares (usuarios, dispositivos y recursos). 

## <a name="information-protection"></a>Protección de la información

- Protección de los activos digitales confidenciales y altamente regulados con etiquetas de Azure Information Protection

  Contoso determinó tres niveles de protección de datos e implementó etiquetas de [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) que los usuarios aplican a los activos digitales. Para los secretos comerciales y otra propiedad intelectual, Contoso usa subetiquetas de Azure Information Protection en una directiva con ámbito para los datos altamente regulados que cifran el contenido y restringen el acceso a grupos de seguridad específicos.

- Evitar filtraciones de datos de la intranet con Prevención de pérdida de datos de Office 365

  Contoso ha configurado directivas de [prevención de pérdida de datos](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies) para Exchange Online, SharePoint Online y OneDrive para la Empresa con el fin de evitar que los usuarios compartan datos confidenciales de forma accidental o deliberada.

- Evitar pérdidas de datos de dispositivo con Windows Information Protection

  Contoso usa [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) para protegerse contra la pérdida de datos desde aplicaciones y servicios basados en Internet, y aplicaciones empresariales y datos en los dispositivos propiedad de la empresa y personales que los empleados llevan al trabajo.

- Supervisión en la nube con Microsoft Cloud App Security

  Contoso usa [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) para asignar su entorno de nube, supervisar el uso y detectar los incidentes y eventos de seguridad. Microsoft Cloud App Security solo está disponible con Microsoft 365 Enterprise E5.

- Administración de dispositivos con Microsoft Intune

  Como parte del conjunto de aplicaciones Enterprise Management + Security (EMS), Contoso usa [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) para inscribir, administrar y configurar el acceso a los dispositivos móviles y las aplicaciones que se ejecutan en ellas. Las directivas de acceso condicional basadas en dispositivos también requieren aplicaciones autorizadas y equipos y dispositivos móviles compatibles.

## <a name="security-management"></a>Administración de seguridad

- Panel central de seguridad para TI con Azure Security Center

  Contoso usa [Azure Security Center](https://docs.microsoft.com/intune/introduction-intune) para obtener una vista unificada de la seguridad y la protección contra amenazas, administrar las directivas de seguridad en las cargas de trabajo y responder a los ciberataques.

- Panel de seguridad central para los usuarios con Seguridad de Windows

  Contoso ha implementado la [aplicación Seguridad de Windows](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) en los equipos y dispositivos con Windows 10 Enterprise para que los usuarios puedan ver su nivel de seguridad a simple vista y tomen medidas.


## <a name="next-step"></a>Siguiente paso

Obtenga [más información](contoso-sharepoint-online-site-for-highly-confidential-assets.md) sobre cómo Contoso creó un sitio de SharePoint Online para datos altamente regulados para permitir la colaboración entre sus equipos de investigación.

