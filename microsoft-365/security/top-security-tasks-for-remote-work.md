---
title: Las 12 principales tareas para que los equipos de seguridad admitan el trabajo desde casa
f1.keywords:
- CSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: o365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- remotework
description: Proteja el correo electrónico y los datos de la empresa de las amenazas para el ciberespacio, incluidos los datos adjuntos malintencionados y de ransomware.
ms.openlocfilehash: 04f59d4f87bda9460930b54818d2ab43933d11e5
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943548"
---
# <a name="top-12-tasks-for-security-teams-to-support-working-from-home"></a>Las 12 principales tareas para que los equipos de seguridad admitan el trabajo desde casa

Si es como [Microsoft](https://www.microsoft.com/microsoft-365/blog/2020/03/10/staying-productive-while-working-remotely-with-microsoft-teams/) y, repentinamente, se da soporte a un personal de trabajo basado principalmente en el hogar, queremos ayudarle a asegurarse de que su organización funciona de la forma más segura posible. En este artículo se priorizan las tareas para ayudar a los equipos de seguridad a implementar las capacidades de seguridad más importantes lo antes posible. 

Si es una organización pequeña o mediana que usa uno de los planes de negocio de Microsoft, consulte estos recursos en su lugar:
- [Las diez formas principales de proteger los planes de Office 365 y Microsoft 365 para empresas](../admin/security-and-compliance/secure-your-business-data.md) 
- [Microsoft 365 para campañas](https://docs.microsoft.com/microsoft-365/campaigns/?view=o365-worldwide) (incluye una configuración de seguridad recomendada para la empresa de Microsoft 365)

  
Para los clientes que usen nuestros planes de empresa, Microsoft le recomienda completar las tareas que se indican en la siguiente tabla que se aplican a su plan de servicio. Si, en lugar de comprar un plan para empresas de Microsoft 365, está combinando suscripciones, tenga en cuenta lo siguiente:
- Microsoft 365 E3 incluye Enterprise Mobility + Security (EMS) E3 y Azure AD P1
- Microsoft 365 E5 incluye EMS E5 y Azure AD P2
  
||**Tarea**| Todos los planes de Office 365 Enterprise|**Microsoft 365 E3** |**Microsoft 365 E5**|
|:-----|:-----|:-----|:-----|:-----|
|1      |[Habilitar Azure multi-factor Authentication (MFA)](#1-enable-azure-multi-factor-authentication-mfa)   |   ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)   | ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|segundo     | [Protección contra amenazas](#2-protect-against-threats) |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png) |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)       | ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|3      |  [Configuración de la protección contra amenazas avanzada de Office 365](#3-configure-office-365-advanced-threat-protection)  |   |      |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|4       | [Configurar la protección contra amenazas avanzada de Azure (ATP)](#4-configure-azure-advanced-threat-protection)   |   |      |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)     | 
|5      |   [Activar la protección contra amenazas avanzada de Microsoft](#5-turn-on-microsoft-advanced-threat-protection)  |  |      | ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|6       | [Configurar la protección de aplicaciones móviles de Intune para teléfonos y tabletas](#6-configure-intune-mobile-app-protection-for-phones-and-tablets) |    |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)       |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)       | 
|7      | [Configurar MFA y el acceso condicional para invitados, incluida la protección de aplicaciones de Intune](#7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection)  |    |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)     | ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|8       |  [Inscribir equipos en administración de dispositivos y requerir equipos compatibles](#8-enroll-pcs-into-device-management-and-require-compliant-pcs)   |  | ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)        | ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|9       | [Optimizar la red para la conectividad en la nube](#9-optimize-your-network-for-cloud-connectivity)  |  ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)        | 
|10     | [Entrenar a los usuarios](#10-train-users) |    ![Included](../media/d238e041-6854-4a78-9141-049224df0795.png) |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)      |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)      | 
|11  |[Introducción a Microsoft Cloud App Security](#11-get-started-with-microsoft-cloud-app-security) |  |  |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)   |
|12  |[Supervisar las amenazas y emprender acciones](#12-monitor-for-threats-and-take-action) |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)   |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)  |![Included](../media/d238e041-6854-4a78-9141-049224df0795.png)  |
| | | |


   
Antes de empezar, Compruebe la [puntuación segura de microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score) en el centro de seguridad de Microsoft 365. Desde un panel centralizado, puede supervisar y mejorar la seguridad de las identidades, los datos, las aplicaciones, los dispositivos y la infraestructura de Microsoft 365. Se le proporcionan puntos para configurar las características de seguridad recomendadas, realizar tareas relacionadas con la seguridad (como ver informes) o dirigir recomendaciones con una aplicación o software de terceros. Las tareas recomendadas de este artículo aumentarán su puntuación.
  
![Captura de pantalla de la puntuación segura de Microsoft](../media/secure-score.png)
  
## <a name="1-enable-azure-multi-factor-authentication-mfa"></a>1: habilitar Azure multi-factor Authentication (MFA)
Lo mejor que puede hacer para mejorar la seguridad de los empleados desde casa es activar la MFA. Si aún no tiene procesos en su ubicación, trate esto como una prueba piloto de emergencia y asegúrese de que el personal de soporte técnico está preparado para ayudar a los empleados que se bloquean. Como probablemente no pueda distribuir dispositivos de seguridad de hardware, use aplicaciones de autenticación de smartphone y Windows Hello como Microsoft Authenticator.

Normalmente, Microsoft recomienda que los usuarios tengan 14 días para registrar el dispositivo para la autenticación multifactor antes de requerir la MFA. Sin embargo, si su personal está trabajando repentinamente desde casa, siga adelante y requiera MFA como prioridad de seguridad y prepárese para ayudar a los usuarios que la necesiten. 

La aplicación de estas directivas tardará solo unos minutos, pero estará preparada para admitir a los usuarios en los próximos días.  


|Plan  |Recomendación  |
|---------|---------|
|Planes de 365 de Microsoft (sin Azure AD P1 o P2)     |[Habilitar los valores predeterminados de seguridad en Azure ad](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults). Los valores predeterminados de seguridad en Azure AD incluyen MFA para los usuarios y administradores.   |
|Microsoft 365 E3 (con Azure AD P1)     | Use [directivas de acceso condicional comunes](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common) para configurar las siguientes directivas: <br>- [Requerir MFA para los administradores](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa) <br>- [Requerir MFA para todos los usuarios](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa) <br> - [Bloquear la autenticación heredada](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)       |
|Microsoft 365 E5 (con Azure AD P2)     | Aprovechando las ventajas de la protección de identidades de Azure AD, comience a implementar el [conjunto recomendado de Microsoft de acceso condicional y las directivas relacionadas](../enterprise/identity-access-policies.md) mediante la creación de estas dos directivas:<br> - [Requerir MFA cuando el riesgo de inicio de sesión sea medio o alto](../enterprise/identity-access-policies.md#require-mfa-based-on-sign-in-risk) <br>- [Bloquear clientes que no admitan la autenticación moderna](../enterprise/identity-access-policies.md#block-clients-that-dont-support-modern-authentication)<br>- [Los usuarios de riesgo alto deben cambiar la contraseña](../enterprise/identity-access-policies.md#high-risk-users-must-change-password)       |
| | |


  
## <a name="2-protect-against-threats"></a>2: protección contra amenazas

Todos los planes de Microsoft 365 incluyen una variedad de características de protección contra amenazas. La protección frente a la protección de estas características tarda solo unos minutos.
- Protección antimalware
- Protección frente a direcciones URL y archivos malintencionados
- Protección contra phishing
- Protección contra correo no deseado

Consulte [proteger contra amenazas en Office 365](office-365-security/protect-against-threats.md) para obtener instrucciones que puede usar como punto de partida.
    

## <a name="3-configure-office-365-advanced-threat-protection"></a>3: configurar la protección contra amenazas avanzada de Office 365

La protección contra amenazas avanzada de Office 365 (ATP), que se incluye con Microsoft 365 E5 y Office 365 E5, protege a su organización de las amenazas dañinas que plantean los mensajes de correo electrónico, los vínculos (URL) y las herramientas de colaboración. Esto puede tardar varias horas en configurarse.

Office 365 ATP:
- Protege su organización de las amenazas de correo electrónico desconocidas en tiempo real mediante sistemas inteligentes que inspeccionan los datos adjuntos y los vínculos en busca de contenido malintencionado. Estos sistemas automatizados incluyen una plataforma de detonación sólida, heurística y modelos de aprendizaje de la máquina. 
- Protege la organización cuando los usuarios colaboran y comparten archivos mediante la identificación y el bloqueo de archivos malintencionados en los sitios de grupo y las bibliotecas de documentos. 
- Aplica modelos de aprendizaje de la máquina y algoritmos de detección de suplantación avanzada a ataques de suplantación de identidad AVERT. 

Para obtener información general, como un resumen de los planes, consulte [Office 365 Advanced Threat Protection](office-365-security/office-365-atp.md).

El administrador global puede configurar estas protecciones:
- [Configurar vínculos seguros ATP](office-365-security/set-up-atp-safe-links-policies.md)
- [Configurar directivas de datos adjuntos seguros de ATP](office-365-security/set-up-atp-safe-attachments-policies.md)
- [Configurar una lista personalizada de URL con "no reescribir"](office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp.md)
- [Configurar una lista personalizada de URL bloqueadas](office-365-security/set-up-a-custom-blocked-urls-list-wtih-atp.md)

Tendrá que trabajar con el administrador de Exchange Online y el administrador de SharePoint Online para configurar ATP para estas cargas de trabajo:
- [Activar ATP para SharePoint, OneDrive y Microsoft Teams](office-365-security/turn-on-atp-for-spo-odb-and-teams.md)

## <a name="4-configure-azure-advanced-threat-protection"></a>4: configurar la protección contra amenazas avanzada de Azure

[Azure Advanced Threat Protection](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) (Azure ATP) es una solución de seguridad basada en la nube que aprovecha las señales locales de Active Directory para identificar, detectar e investigar las amenazas avanzadas, las identidades en peligro y las acciones de Insider malintencionadas dirigidas a la organización. Céntrese en este siguiente porque protege su infraestructura local y de nube, no tiene dependencias o requisitos previos y puede proporcionar ventajas inmediatas.


- Ver [QuickStarts de Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) para obtener el programa de instalación rápidamente 
- Ver [vídeo: Introducción a ATP de Azure](https://www.youtube.com/watch?reload=9&v=EGY2m8yU_KE)
- Revisar las [tres fases de la implementación de ATP de Azure](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp#whats-next)

## <a name="5-turn-on-microsoft-advanced-threat-protection"></a>5: activar la protección contra amenazas avanzada de Microsoft

Ahora que tiene Office 365 ATP y Azure ATP configurados, puede ver las señales combinadas de estas funcionalidades en un panel. [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection) (MTP) reúne las alertas, los incidentes, la investigación automatizada y la respuesta, y la búsqueda avanzada de cargas de trabajo (ATP de Azure, Office 365 ATP, Microsoft defender ATP y Microsoft Cloud App Security) en un solo panel en [Security.Microsoft.com](https://security.microsoft.com). 
<br>

![Ilustración del panel MTP](../media/top-ten-security-remote-work-mtp-dashboard.png)
<br><br>
Una vez que haya configurado uno o varios de los servicios de protección contra amenazas avanzada, Active MTP. Las nuevas características se agregan de forma continua a MTP; considere la posibilidad de optar por recibir características de vista previa.

- [Obtener más información acerca de MTP](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Activar MTP](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide)
- [Participar en las características de vista previa](https://docs.microsoft.com/microsoft-365/security/mtp/preview?view=o365-worldwide)


## <a name="6-configure-intune-mobile-app-protection-for-phones-and-tablets"></a>6: configurar la protección de aplicaciones móviles de Intune para teléfonos y tabletas

La administración de aplicaciones móviles (MAM) de Microsoft Intune le permite administrar y proteger los datos de su organización en teléfonos y tabletas sin administrar estos dispositivos. Aquí se muestra cómo funciona:
- Cree una directiva de protección de aplicaciones (APP) que determine qué aplicaciones de un dispositivo se administran y qué comportamientos se permiten (por ejemplo, impedir que los datos de una aplicación administrada se copien en una aplicación no administrada). Puede crear una directiva para cada platorm (iOS, Android).
- Después de crear las directivas de protección de aplicaciones, puede aplicarlas mediante la creación de una regla de acceso condicional en Azure AD para requerir aplicaciones aprobadas y protección de datos de la aplicación.

Las directivas de protección de aplicaciones incluyen muchas opciones de configuración. Afortunadamente, no es necesario obtener más información sobre cada configuración y sopesar las opciones. Microsoft hace que sea fácil aplicar una configuración de opciones mediante la recomendación de puntos de inicio. El [marco de protección de datos con directivas de protección de aplicaciones](https://docs.microsoft.com/mem/intune/apps/app-protection-framework) incluye tres niveles entre los que puede elegir. 

Incluso mejor, Microsoft coordina este marco de protección de aplicaciones con un conjunto de acceso condicional y directivas relacionadas que se recomienda que todas las organizaciones usen como punto de partida. Si ha implementado la MFA siguiendo las instrucciones de este artículo, tiene la mitad de camino.

Para configurar la protección de aplicaciones móviles, siga las instrucciones de [directivas comunes de identidad y acceso a dispositivos](../enterprise/identity-access-policies.md):
 1. Use las directrices de [aplicar directivas de protección de datos de aplicaciones](../enterprise/identity-access-policies.md#apply-app-data-protection-policies) para crear directivas para iOS y Android. Se recomienda el nivel 2 (protección de datos mejorada) para la protección de línea base. 
 2. Cree una regla de acceso condicional que [requiera aplicaciones aprobadas y protección](../enterprise/identity-access-policies.md#require-approved-apps-and-app-protection)de aplicaciones. 

## <a name="7-configure-mfa-and-conditional-access-for-guests-including-intune-mobile-app-protection"></a>7: configurar la MFA y el acceso condicional para invitados, incluida la protección de aplicaciones móviles de Intune

A continuación, vamos a garantizar que puede seguir colaborando y trabajando con los invitados. Si está usando el plan E3 365 de Microsoft y ha implementado MFA para todos los usuarios, está configurado. 

Si está usando el plan 365 E5 de Microsoft y está aprovechando Azure Identity Protection para MFA basada en riesgos, debe realizar un par de ajustes (porque Azure AD Identity Protection no se extiende a los invitados):
- Cree una nueva regla de acceso condicional para requerir que MFA siempre para invitados y usuarios externos.
- Actualice la regla de acceso condicional de MFA basada en riesgos para excluir los invitados y los usuarios externos.

Use las instrucciones de [actualización de las directivas comunes para permitir y proteger el acceso de invitados y externos](../enterprise/identity-access-policies-guest-access.md) para comprender cómo funciona el acceso de invitado con Azure ad y para actualizar las directivas afectadas. 

Las directivas de protección de aplicaciones móviles de Intune que ha creado, junto con la regla de acceso condicional para requerir la protección de aplicaciones y aplicaciones aprobadas, se aplican a las cuentas de invitados y ayudarán a proteger los datos de su organización. 

**Nota**: Si ya ha inscrito equipos en la administración de dispositivos para requerir equipos conformes, también tendrá que excluir las cuentas de invitado de la regla de acceso condicional que aplica el cumplimiento de dispositivos. 


## <a name="8-enroll-pcs-into-device-management-and-require-compliant-pcs"></a>8: inscriba equipos en la administración de dispositivos y requiera equipos compatibles

Hay varios métodos para inscribir los dispositivos del personal. Cada método depende de la propiedad del dispositivo (personal o corporativo), el tipo de dispositivo (iOS, Windows o Android), y los requisitos de administración (restablecimientos, afinidad, bloqueo). Esto puede tardar un poco de tiempo en ordenarse. Consulte: [inscribir dispositivos en Microsoft Intune](https://docs.microsoft.com/mem/intune/enrollment/). 

La forma más rápida de empezar es configurar la [inscripción automática para dispositivos con Windows 10](https://docs.microsoft.com/mem/intune/enrollment/quickstart-setup-auto-enrollment). 

También puede aprovechar estos tutoriales:
- [Usar AutoPilot para inscribir dispositivos Windows en Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-autopilot-enroll-devices)
- [Usar las características de inscripción de dispositivos corporativos de Apple en Apple Business Manager (ABM) para inscribir dispositivos iOS/iPados en Intune](https://docs.microsoft.com/mem/intune/enrollment/tutorial-use-device-enrollment-program-enroll-ios)

Después de inscribir dispositivos, use las directrices de [las directivas comunes de identidad y acceso a dispositivos](../enterprise/identity-access-policies.md) para crear estas directivas:
- [Definir directivas de cumplimiento de dispositivos](../enterprise/identity-access-policies.md#define-device-compliance-policies) : la configuración recomendada para Windows 10 incluye la necesidad de protección antivirus. Si tiene Microsoft 365 E5, use la protección contra amenazas avanzada de Microsoft defender para supervisar el estado de los dispositivos de los empleados. Asegúrese de que las directivas de cumplimiento para otros sistemas operativos incluyen el software de protección antivirus y de punto final. 
- [Requerir equipos compatibles](../enterprise/identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets) : esta es la regla de acceso condicional en Azure ad que aplica las directivas de cumplimiento de dispositivos.

Solo una organización puede administrar un dispositivo, por lo que debe asegurarse de excluir las cuentas de invitado de la regla de acceso condicional en Azure AD. Si no excluye a los usuarios externos y invitados de las directivas que requieran el cumplimiento de dispositivos, estas directivas bloquearán a estos usuarios. Para obtener más información, consulte [actualización de las directivas comunes para permitir y proteger el acceso de invitados y externos](../enterprise/identity-access-policies-guest-access.md).

## <a name="9-optimize-your-network-for-cloud-connectivity"></a>9: optimizar la red para la conectividad en la nube

Si va a permitir que la mayoría de los empleados trabajen desde casa rápidamente, este cambio repentino de patrones de conectividad puede tener un impacto significativo en la infraestructura de la red corporativa. Muchas redes se escalaron y diseñaron antes de la adopción de los servicios en la nube. En muchos casos, las redes son tolerantes de los trabajadores remotos, pero no están diseñadas para que todos los usuarios los usen de forma remota.

Los elementos de red como concentradores de VPN, el equipo de salida de red central (como los servidores proxy y los dispositivos de prevención de pérdida de datos), el ancho de banda central de Internet, los circuitos MPLS de backhaul, la funcionalidad NAT, etc., se colocan repentinamente con una gran presión debido a la carga de toda la empresa con ellos. El resultado final es un rendimiento deficiente y la productividad junto con una mala experiencia del usuario para los usuarios que se están adaptando al trabajo desde casa.

Algunas de las protecciones que tradicionalmente se han proporcionado mediante el enrutamiento de tráfico a través de una red corporativa las proporcionan las aplicaciones de nube a las que tienen acceso los usuarios. Si ha llegado a este paso en este artículo, ha implementado un conjunto de controles sofisticados de seguridad en la nube para los servicios y los datos de Microsoft 365. Con estos controles en su ubicación, puede que esté listo para enrutar el tráfico de los usuarios remotos directamente a Office 365. Si aún necesita un vínculo VPN para el acceso a otras aplicaciones, puede mejorar considerablemente el rendimiento y la experiencia del usuario mediante la implementación de túneles divididos. Una vez que haya logrado el acuerdo en su oganization, esto se puede lograr en un día mediante un equipo de red bien coordinado.


Consulte estos recursos en docs para obtener más información:
- [Información general: optimizar la conectividad para usuarios remotos mediante tunelización dividida de VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
- [Implementación de túnel dividido de VPN en Office 365](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-implement-split-tunnel)

Artículos de blog recientes en este tema:
- [Cómo optimizar rápidamente el tráfico de personal remoto & reducir la carga de la infraestructura](https://techcommunity.microsoft.com/t5/office-365-blog/how-to-quickly-optimize-office-365-traffic-for-remote-staff-amp/ba-p/1214571#)
- [Formas alternativas para profesionales de la seguridad y TI puede conseguir controles de seguridad modernos en los escenarios de trabajo remoto únicos de hoy en día.](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)


## <a name="10-train-users"></a>10: entrenar a los usuarios

Los usuarios de aprendizaje pueden ahorrar a los usuarios y al equipo de operaciones de seguridad mucho tiempo y frustraciones. Es menos probable que los usuarios más experimentados abran datos adjuntos o hagan clic en vínculos en mensajes de correo electrónico dudosos, por lo que es más probable que se eviten sitios Web sospechosos. 

El manual Harvard Kennedy School [Cybersecurity Campaign Handbook](https://go.microsoft.com/fwlink/?linkid=2015598&amp;clcid=0x409) proporciona una excelente orientación sobre cómo establecer una cultura fuerte de conciencia de la seguridad dentro de la organización, incluido el aprendizaje de usuarios para identificar ataques de suplantación de identidad. 

Microsoft 365 proporciona los siguientes recursos para ayudar a informar a los usuarios de su organización:

|Concepto  |Recursos  |
|---------|---------|
|Microsoft 365     |[Caminos de aprendizaje personalizables](https://docs.microsoft.com/office365/customlearning/) <p>Estos recursos pueden ayudarle a elaborar formación para los usuarios finales de su organización        |
|Seguridad de Microsoft 365 |[Módulo de aprendizaje: Proteja su organización con seguridad integrada e integrada de Microsoft 365](https://docs.microsoft.com/learn/modules/security-with-microsoft-365) <p>Este módulo le permite describir cómo funcionan conjuntamente las características de seguridad de Microsoft 365 y cómo articular las ventajas de estas características de seguridad. |
|Autenticación multifactor     | [Verificación en dos pasos: ¿Qué es la página de comprobación adicional?](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-first-time) <p>Este artículo ayuda a los usuarios finales a comprender qué es la autenticación multifactor y por qué se usa en la organización.    |
| | |

Además de esta guía, Microsoft recomienda que los usuarios realicen las acciones descritas en este artículo: [Proteja su cuenta y sus dispositivos de hackers y malware](https://support.office.com/article/066d6216-a56b-4f90-9af3-b3a1e9a327d6.aspx). Entre estas acciones se incluyen:
  
- Uso de contraseñas seguras
    
- Protección de dispositivos 
    
- Habilitación de las características de seguridad en equipos PC con Windows 10 y Mac (para dispositivos no administrados)
    
Microsoft también recomienda que los usuarios protejan sus cuentas de correo electrónico personales llevando a cabo las acciones recomendadas en los siguientes artículos:
  
- [Ayuda para proteger su cuenta de correo electrónico de Outlook.com](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba.aspx)
    
- [Proteger la cuenta de gmail con verificación en dos pasos](https://go.microsoft.com/fwlink/?linkid=2015688&amp;clcid=0x409)


## <a name="11-get-started-with-microsoft-cloud-app-security"></a>11: Introducción a Microsoft Cloud App Security

[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security) proporciona una gran visibilidad, control sobre los recorridos de datos y análisis sofisticados para identificar y combatir ciberamenazas en todos los servicios en la nube. Una vez que empiece con Cloud App Security, las directivas de detección de anomalías se habilitan automáticamente, pero Cloud App Security tiene un período de aprendizaje inicial de siete días durante el cual no se producen todas las alertas de detección de anomalías.

Introducción a Cloud App Security ahora. Más adelante puede configurar la supervisión y los controles más sofisticados.

- [Inicio rápido: Introducción a la seguridad de aplicaciones en la nube](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)
- [Obtenga análisis de comportamiento instantánea y detección de anomalías](https://docs.microsoft.com/cloud-app-security/anomaly-detection-policy)
- [Obtenga más información sobre Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Revisión de las nuevas características y capacidades](https://docs.microsoft.com/cloud-app-security/release-notes)
- [Consulte las instrucciones básicas de configuración](https://docs.microsoft.com/cloud-app-security/general-setup)

## <a name="12-monitor-for-threats-and-take-action"></a>12: supervise las amenazas y realice acciones

Microsoft 365 incluye varias formas de supervisar el estado y tomar las medidas adecuadas. El punto de partida más adecuado es el centro de seguridad[https://security.microsoft.com](https://security.microsoft.com)de Microsoft 365 (), donde puede ver la [puntuación segura de Microsoft](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score?view=o365-worldwide)de su organización, así como las alertas o entidades que requieren su atención.

- [Introducción al centro de seguridad de Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/overview-security-center?view=o365-worldwide)
- [Supervisar y ver informes](https://docs.microsoft.com/microsoft-365/security/mtp/monitoring-and-reporting?view=o365-worldwide)
- [Consulte los portales de seguridad en Microsoft 365](https://docs.microsoft.com/microsoft-365/security/mtp/portals)

## <a name="next-steps"></a>Siguientes pasos

¡Enhorabuena! Ha implementado rápidamente algunas de las protecciones de seguridad más importantes y su organización es mucho más segura. Ahora ya puede seguir adelante con las capacidades de protección contra amenazas (incluida la protección contra amenazas avanzada de Microsoft defender), las capacidades de protección y clasificación de datos, y la protección de las cuentas administrativas. Para obtener un conjunto más profundo y metódico de recomendaciones de seguridad para Microsoft 365, vea [microsoft 365 Security para los responsables de decisiones empresariales](Microsoft-365-security-for-bdm.md). 

Visite también el nuevo centro de seguridad de Microsoft en [docs.Microsoft.com/Security](https://docs.microsoft.com/security). 
