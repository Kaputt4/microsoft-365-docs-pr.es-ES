---
title: Tecnologías del Escritorio administrado de Microsoft
description: En este artículo se enumeran las tecnologías y aplicaciones que se usan en Microsoft Managed Desktop.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: d7a7b6889451d83aaa6c2b53c1dce6ed035f9916
ms.sourcegitcommit: 52eea2b65c0598ba4a1b930c58b42dbe62cdaadc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/19/2022
ms.locfileid: "64945635"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías del Escritorio administrado de Microsoft

En este artículo se enumeran las tecnologías y aplicaciones que se usan en Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise se requieren licencias para todos los usuarios Microsoft Managed Desktop. Para obtener más información sobre los requisitos de licencia para el servicio, consulte [Requisitos previos para Microsoft Managed Desktop](../get-ready/prerequisites.md).

En este artículo se resumen los componentes incluidos en las licencias de Enterprise necesarias y cómo el servicio usa cada componente con Microsoft Managed Desktop dispositivos. Los roles y responsabilidades específicos de cada área se detallan a lo largo de Microsoft Managed Desktop documentación.

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5

| Producto | Información |
| ----- | ----- |
| Aplicaciones Microsoft 365 para empresas (64 bits) | Las siguientes aplicaciones Office se enviarán con el dispositivo:<br><ul><li>Word</li><li>Excel</li><li>PowerPoint</li><li>Outlook</li><li>Publisher</li><li>Access</li><li>Skype Empresarial</li><li>OneNote</li></ul><br>No se incluyen las versiones completas de 64 bits de Microsoft Project y Microsoft Visio. Sin embargo, dado que la instalación de estas aplicaciones depende de la Aplicaciones Microsoft 365 para la instalación de Enterprise, Microsoft Managed Desktop ha creado implementaciones de Microsoft Intune predeterminadas y grupos de seguridad en los que puede usar para implementar estas aplicaciones. usuarios con licencia. Para obtener más información, vea [Instalar Microsoft Project o Microsoft Visio en dispositivos Microsoft Managed Desktop](../get-started/project-visio.md). |
| OneDrive | Azure Active Directory inicio de sesión único está habilitado para los usuarios cuando inician sesión por primera vez en OneDrive.<br><br>Se incluyen las carpetas Redirección de carpetas conocidas para escritorio, Documento e Imágenes. Estas carpetas están habilitadas y configuradas por Microsoft Managed Desktop. |
| Aplicaciones de la Tienda | Microsoft Sway y Power BI no se incluyen con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store. |
| Aplicaciones Win32 | Teams no se incluye con el dispositivo, pero microsoft lo empaqueta y proporciona para dispositivos Microsoft Managed Desktop. El cliente de Azure Information Protection no se incluye con el dispositivo, pero puede empaquetarlo para la implementación. |
| Aplicaciones web | Las siguientes aplicaciones web no se incluyen con el dispositivo: <ul><li>Yammer</li><li>Office en un explorador</li><li>Delve</li><li>Flow</li><li>StaffHub</li><li>Power Apps</li><li>Planner</li></ul> <br>Los usuarios pueden acceder a la versión web de estas aplicaciones con un explorador. |

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender para punto de conexión

Se recomienda que los administradores de TI configuren las siguientes opciones.

> [!NOTE]
> Esta configuración no se incluye ni administra como parte de Microsoft Managed Desktop.

| Producto | Información |
| ----- | ----- |
| Windows Hello para empresas | Debe implementar Windows Hello para empresas para reemplazar contraseñas por autenticación segura en dos fases para dispositivos Microsoft Managed Desktop. Para obtener más información, consulte [Windows Hello para empresas](/windows/security/identity-protection/hello-for-business/hello-identity-verification). |
| Virtualización de aplicaciones | Puede implementar paquetes de Virtualización de aplicaciones (App-V) mediante el cliente de administración de aplicaciones Intune Win32. Para obtener más información, consulte [Virtualización de aplicaciones](/windows/application-management/app-v/appv-technical-reference). |
| Prevención de pérdida de datos de Microsoft Purview | Debe implementar la prevención de pérdida de datos para supervisar las acciones realizadas en los elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido involuntario de esos elementos. Para obtener más información, consulte [Prevención de pérdida de datos](../../compliance/endpoint-dlp-learn-about.md). |

Características incluidas y administradas como parte de Microsoft Managed Desktop:

| Producto | Información |
| ----- | ----- |
| Cifrado de unidad bitlocker | El cifrado de unidad bitlocker se usa para cifrar todas las unidades del sistema. Para obtener más información, vea [Cifrado de unidad BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview). |
| Protección del sistema de Windows Defender | Protege la integridad del sistema en el inicio y valida que la integridad del sistema se ha mantenido realmente. Para obtener más información, consulte [Protección del sistema de Windows Defender](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows). |
| Credential Guard de Windows Defender | Windows Defender Credential Guard usa la seguridad basada en virtualización para aislar los secretos de modo que solo el software del sistema con privilegios pueda acceder a ellos. Para obtener más información, consulte [Protección del sistema de Windows Defender](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows). |
| Microsoft Defender para punto de conexión: detección y respuesta de puntos de conexión | Microsoft Managed Desktop Security Operations responde a las alertas y toma medidas para corregir amenazas mediante la detección y respuesta de puntos de conexión. Para obtener más información, consulte [Microsoft Defender para punto de conexión: Detección y respuesta de puntos de conexión](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response). |
| Microsoft Defender para punto de conexión: expertos en amenazas | Microsoft Managed Desktop se integra con información y datos de expertos en amenazas a través de notificaciones de ataque dirigidas. Debe proporcionar consentimiento adicional antes de habilitar este servicio. Para obtener más información, vea [Microsoft Defender para punto de conexión - Expertos en amenazas](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts). |
| Microsoft Defender para punto de conexión: Administración de amenazas y vulnerabilidades | Necesario para su uso futuro en el plan de servicio de Microsoft Managed Desktop. Para obtener más información, consulte [Microsoft Defender para punto de conexión: Administración de amenazas y vulnerabilidades](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt). |
| Microsoft Defender para punto de conexión: Reducción de superficie expuesta a ataques | Se dirige a comportamientos de software de riesgo que suelen ser objeto de abuso por parte de los atacantes. Para obtener más información, consulta [Microsoft Defender para punto de conexión: Reducción de superficie expuesta a ataques](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction). |
| Microsoft Defender para punto de conexión: Protección contra vulnerabilidades de seguridad | Protege contra malware que usa vulnerabilidades de seguridad para infectar dispositivos y se propaga mediante la aplicación automática de técnicas de mitigación de vulnerabilidades de seguridad a procesos y aplicaciones del sistema operativo. Para obtener más información, consulte [Microsoft Defender para punto de conexión - Protección contra vulnerabilidades de seguridad](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection). |
| Microsoft Defender para punto de conexión: Protección de red | Expande el ámbito de SmartScreen de Microsoft Defender para bloquear todo el tráfico HTTP y HTTPS saliente que intenta conectarse a orígenes de baja reputación. Para obtener más información, consulte [Microsoft Defender para punto de conexión - Protección de red](/windows/security/threat-protection/microsoft-defender-atp/network-protection). |
| Protección contra alteraciones de Microsoft Defender | Windows Protección contra alteraciones se usa para evitar que se cambie la configuración de seguridad, como la protección antivirus. Para obtener más información, consulte [Protección contra alteraciones de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection). |
| Antivirus de Microsoft Defender protección antivirus basada en comportamientos, heurística y en tiempo real | Siempre activado para buscar amenazas de archivos y procesos que pueden no detectarse como malware. Para obtener más información, consulte [Antivirus de Microsoft Defender protección antivirus basada en comportamientos, heurística y en tiempo real](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md). |
| Antivirus de Microsoft Defender protección entregada en la nube | Proporciona protección dinámica casi instantánea y automatizada contra amenazas nuevas y emergentes. Para obtener más información, consulte [Antivirus de Microsoft Defender Protección entregada en la nube](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus). |
| Microsoft Defender para punto de conexión : "Bloquear a primera vista" | Proporciona detección y bloqueo de malware nuevo cuando Windows detecta un archivo sospechoso o desconocido. Para obtener más información, consulte [Microsoft Defender para punto de conexión - Bloquear a primera vista](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus). |
| Antivirus de Microsoft Defender aplicaciones potencialmente no deseadas | Se usa para bloquear aplicaciones que pueden hacer que el equipo se ejecute lentamente, mostrar anuncios inesperados o, en el peor de los casos, instalar otro software que pueda ser inesperado o no deseado. Para obtener más información, vea [Antivirus de Microsoft Defender aplicaciones potencialmente no deseadas](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus). |
| firewall de Windows Defender con seguridad avanzada | El filtrado de tráfico de red bidireccional basado en host para un dispositivo, Windows Defender Firewall bloquea el tráfico de red no autorizado que entra o sale del dispositivo local. Para obtener más información, consulte [Windows Defender Firewall con seguridad avanzada](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security). |
| Control de cuentas de usuario | El Control de cuentas de usuario cambia a Secure Desktop cuando una tarea o acción requiere el acceso de tipo cuenta de administrador. Microsoft Managed Desktop a los usuarios se les asigna acceso de usuario estándar en la inscripción. Para obtener más información, consulte [Control de cuentas de usuario](/windows/security/identity-protection/user-account-control/how-user-account-control-works). |

## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

| Producto | Información |
| ----- | ----- |
| Enterprise Mobility + Security E3<br><br>Azure Active Directory Premium P2 | Puede usar todas las características de Enterprise Mobility + Security E3 para administrar dispositivos MDM.<br><br>Puede usar Azure Active Directory Premium P2 como una característica opcional con Microsoft Managed Desktop. |
| Microsoft Defender for Cloud Apps | Puede usar esta característica opcional con Microsoft Managed Desktop.
| Azure Information Protection P2  | Puede usar esta característica opcional con Microsoft Managed Desktop.
