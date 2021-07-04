---
title: Tecnologías del Escritorio administrado de Microsoft
description: En este artículo se enumeran las tecnologías y aplicaciones usadas en Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d70bb133904a7bcc9c30721d3f723b0fd8b88512
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287968"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías del Escritorio administrado de Microsoft

En este artículo se enumeran las tecnologías y aplicaciones usadas en Escritorio administrado de Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise se requieren licencias para todos los Escritorio administrado de Microsoft usuarios. Para obtener más información sobre los requisitos de licencia para el servicio, vea [Prerequisites for Escritorio administrado de Microsoft](../get-ready/prerequisites.md).

En este artículo se resumen los componentes incluidos en las licencias Enterprise necesarias, con una descripción de cómo el servicio usa cada componente con Escritorio administrado de Microsoft dispositivos. Las funciones y responsabilidades específicas de cada área se detallan en Escritorio administrado de Microsoft documentación. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5

| Producto |Información |
--- |--- 
Aplicaciones Microsoft 365 para empresas (64 bits) | Estas Office se enviarán con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial, OneNote.<br><br>Las versiones completas de 64 bits de Microsoft Project y Microsoft Visio no se incluyen. Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación de Aplicaciones Microsoft 365 para empresas, Escritorio administrado de Microsoft ha creado implementaciones de Microsoft Intune predeterminadas y grupos de seguridad que luego puede usar para implementar estas aplicaciones en usuarios con licencia. Para obtener más información, [vea Install Microsoft Project or Microsoft Visio on Escritorio administrado de Microsoft devices](../get-started/project-visio.md).
OneDrive |Azure Active Directory El inicio de sesión único está habilitado para los usuarios cuando inician sesión por primera vez en OneDrive.<br><br>Se incluye la redirección de carpetas conocidas para las carpetas "Escritorio", "Documento" e "Imágenes"; habilitado y configurado por Escritorio administrado de Microsoft.
Aplicaciones de la Tienda | Microsoft Sway y Power BI se envían con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones de Win32 | Teams no se incluye con el dispositivo, sino que Microsoft lo empaqueta y proporciona para Escritorio administrado de Microsoft dispositivos. El cliente de Azure Information Protection no se incluye con el dispositivo, pero puede empaquetar para su implementación.
Aplicaciones web | Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se envían con el dispositivo. Los usuarios pueden acceder a la versión web de estas aplicaciones con un explorador.

## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender para endpoint

Se recomienda que los administradores de TI configuren las siguientes opciones. Esta configuración no se incluye ni se administra como parte de Escritorio administrado de Microsoft.

Producto  |Información
--- | ---
Windows Hello para empresas | Debes implementar Windows Hello para empresas para reemplazar las contraseñas con autenticación segura en dos fases para Escritorio administrado de Microsoft dispositivos. Para obtener más información, [vea Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).
Virtualización de aplicaciones | Puedes implementar paquetes de virtualización de aplicaciones (App-V) con el cliente de administración de aplicaciones de Intune Win32. Para obtener más información, vea [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Microsoft 365 de pérdida de datos | Debe implementar Microsoft 365 prevención de pérdida de datos para supervisar las acciones que se están haciendo en los elementos que ha determinado que son confidenciales y ayudar a evitar el uso compartido involuntario de esos elementos. Para obtener más información, [vea Microsoft 365 prevención de pérdida de datos](../../compliance/endpoint-dlp-learn-about.md).

Características incluidas y administradas como parte de Escritorio administrado de Microsoft:

Producto |Información
--- |---
Cifrado de unidad BitLocker | El cifrado de unidad BitLocker se usa para cifrar todas las unidades del sistema. Para obtener más información, [consulta Cifrado de unidad BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).
Windows Defender System Guard | Protege la integridad del sistema al iniciarse y valida que la integridad del sistema se haya mantenido realmente. Para obtener más información, [vea Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Credential Guard de Windows Defender | Windows Defender Credential Guard usa la seguridad basada en virtualización para aislar secretos para que solo el software del sistema con privilegios pueda tener acceso a ellos. Para obtener más información, [vea Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Microsoft Defender para endpoint: detección y respuesta de puntos de conexión | Escritorio administrado de Microsoft Las operaciones de seguridad responden a las alertas y toma medidas para corregir las amenazas mediante la detección y respuesta de puntos de conexión. Para obtener más información, vea [Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender para endpoint: expertos en amenazas | Escritorio administrado de Microsoft se integra con información y datos de expertos en amenazas a través de notificaciones de ataques dirigidos. Tendrá que proporcionar un consentimiento adicional antes de habilitar este servicio. Para obtener más información, vea [Microsoft Defender for Endpoint - Threat Experts](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender para endpoint: administración de amenazas y vulnerabilidades | Necesario para su uso futuro en el plan Escritorio administrado de Microsoft de servicio. Para obtener más información, vea [Microsoft Defender for Endpoint - Threat and Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).
Microsoft Defender para endpoint: reducción de superficie de ataque | La reducción de superficie de ataque se dirige a comportamientos de software arriesgados que suelen ser abusados por los atacantes. Para obtener más información, consulta [Microsoft Defender for Endpoint - Attack Surface Reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).
Microsoft Defender para endpoint: Protección contra vulnerabilidades de seguridad | Protege contra malware que usa exploits para infectar dispositivos y propagarse aplicando automáticamente técnicas de mitigación de vulnerabilidades a procesos y aplicaciones del sistema operativo. Para obtener más información, vea [Microsoft Defender for Endpoint - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).
Microsoft Defender para endpoint: Protección de red | La protección de red expande el ámbito de SmartScreen de Microsoft Defender para bloquear todo el tráfico HTTP y HTTPS saliente que intente conectarse a orígenes de baja reputación. Para obtener más información, vea [Microsoft Defender for Endpoint - Network Protection](/windows/security/threat-protection/microsoft-defender-atp/network-protection).
Protección contra manipulaciones de Microsoft Defender | Windows La protección contra alteraciones se usa para evitar que se cambie la configuración de seguridad, como la protección antivirus. Para obtener más información, vea [Protección contra manipulaciones de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Antivirus de Microsoft Defender Protección antivirus basada en comportamiento, heurística y en tiempo real | Siempre en busca de amenazas de archivos y procesos que pueden no detectarse como malware. Para obtener más información, vea Antivirus de Microsoft Defender protección antivirus basada en [comportamiento, heurística y en tiempo real.](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)
Antivirus de Microsoft Defender Protección entregada en la nube | Proporciona protección dinámica casi instantánea y automatizada contra amenazas nuevas y emergentes. Para obtener más información, [vea Antivirus de Microsoft Defender Cloud-delivered Protection](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).
"Bloquear a primera vista" de Microsoft Defender | Proporciona detección y bloqueo de malware nuevo Windows detecta un archivo sospechoso o desconocido. Para obtener más información, vea [Bloqueo de Microsoft Defender a primera vista.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Aplicaciones potencialmente no deseadas de Antivirus de Microsoft Defender | Las aplicaciones potencialmente no deseadas se usan para bloquear aplicaciones que pueden hacer que el equipo se ejecute lentamente, mostrar anuncios inesperados o, en el peor de los casos, instalar otro software que pueda ser inesperado o no deseado. Para obtener más información, vea [Microsoft Defender AV Potentially Unwanted Applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).
Windows Defender Firewall con seguridad avanzada | El filtrado de tráfico de red de dos direcciones basado en host para un dispositivo, Windows Defender firewall bloquea el tráfico de red no autorizado que entra o sale del dispositivo local. Para obtener más información, [vea Windows Defender Firewall with Advanced Security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).
Control de cuentas de usuario | El control de cuentas de usuario cambia al Escritorio seguro cuando una tarea o una acción requiere el acceso de tipo de cuenta de administrador. Escritorio administrado de Microsoft a los usuarios se les asigna acceso de usuario estándar en la inscripción. Para obtener más información, vea [User Account Control](/windows/security/identity-protection/user-account-control/how-user-account-control-works).


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

Producto |Información
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 | Puedes usar todas las características de Enterprise Mobility + Security E3 para administrar dispositivos MDM. Puede usar Azure Active Directory Premium P2 como una característica opcional con Escritorio administrado de Microsoft.
Microsoft Cloud App Security | Puede usar esta característica opcional con Escritorio administrado de Microsoft.
Azure Information Protection P2  | Puede usar esta característica opcional con Escritorio administrado de Microsoft.
