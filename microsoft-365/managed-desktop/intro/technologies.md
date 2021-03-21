---
title: Tecnologías del Escritorio administrado de Microsoft
description: En este artículo se enumeran las tecnologías y aplicaciones usadas en El escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920581"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías del Escritorio administrado de Microsoft

En este artículo se enumeran las tecnologías y aplicaciones usadas en El escritorio administrado de Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Las licencias de Microsoft 365 Enterprise son necesarias para todos los usuarios de Escritorio administrado de Microsoft. Para obtener más información sobre los requisitos de licencia para el servicio, vea [Prerequisites for Microsoft Managed Desktop](../get-ready/prerequisites.md).

En este artículo se resumen los componentes incluidos en las licencias enterprise necesarias, con una descripción de cómo el servicio usa cada componente con dispositivos de Escritorio administrado de Microsoft. Las funciones y responsabilidades específicas de cada área se detallan en toda la documentación de Escritorio administrado de Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5
 |
 --- | ---
Aplicaciones de Microsoft 365 para empresas (64 bits) | Estas aplicaciones de Office se enviarán con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial, OneNote.<br><br>No se incluyen las versiones completas de 64 bits de Microsoft Project y Microsoft Visio. Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación de Aplicaciones de Microsoft 365 para empresas, Microsoft Managed Desktop ha creado implementaciones predeterminadas de Microsoft Intune y grupos de seguridad que luego puede usar para implementar estas aplicaciones para usuarios con licencia. Para obtener más información, vea [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).
OneDrive |El inicio de sesión único de Azure Active Directory está habilitado para los usuarios cuando inician sesión por primera vez en OneDrive.<br><br>Se incluye la redirección de carpetas conocidas para las carpetas "Escritorio", "Documento" e "Imágenes"; habilitado y configurado por Microsoft Managed Desktop.
Aplicaciones de la Tienda |    Microsoft Sway y Power BI no se envían con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones de Win32 |    Teams no se envía con el dispositivo, pero Microsoft lo empaqueta y proporciona para dispositivos de Escritorio administrado de Microsoft. El cliente de Azure Information Protection no se incluye con el dispositivo, pero puede empaquetar para su implementación.
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se envían con el dispositivo. Los usuarios pueden acceder a la versión web de estas aplicaciones con un explorador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender para endpoint
Se recomienda que los administradores de TI configuren las siguientes opciones. Esta configuración no se incluye ni se administra como parte de Microsoft Managed Desktop.

 |
 --- | ---
Windows Hello para empresas | Debes implementar Windows Hello para empresas para reemplazar las contraseñas con una autenticación segura en dos fases para dispositivos de Escritorio administrado de Microsoft. Para obtener más información, [consulta Windows Hello para empresas](/windows/security/identity-protection/hello-for-business/hello-identity-verification).
Virtualización de aplicaciones | Puedes implementar paquetes de virtualización de aplicaciones (App-V) con el cliente de administración de aplicaciones de Intune Win32. Para obtener más información, vea [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Prevención de pérdida de datos de Microsoft 365 | Debe implementar la prevención de pérdida de datos de Microsoft 365 para supervisar las acciones que se están haciendo en los elementos que ha determinado que son confidenciales y ayudar a evitar el uso compartido involuntario de esos elementos. Para obtener más información, vea Prevención de pérdida de datos [de Microsoft 365](../../compliance/endpoint-dlp-learn-about.md).


Características incluidas y administradas como parte de Microsoft Managed Desktop:

 |
 --- | ---
Cifrado de unidad BitLocker | El cifrado de unidad BitLocker se usa para cifrar todas las unidades del sistema. Para obtener más información, [consulta Cifrado de unidad BitLocker](/windows/security/information-protection/bitlocker/bitlocker-overview).
Windows Defender System Guard | Protege la integridad del sistema al iniciarse y valida que la integridad del sistema se haya mantenido realmente. Para obtener más información, [vea Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Credential Guard de Windows Defender | Windows Defender Credential Guard usa la seguridad basada en virtualización para aislar secretos de modo que solo el software del sistema con privilegios pueda tener acceso a ellos. Para obtener más información, [vea Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Microsoft Defender para endpoint: detección y respuesta de puntos de conexión | Las operaciones de seguridad de escritorio administrado de Microsoft responden a las alertas y toma medidas para corregir las amenazas mediante la detección y respuesta de puntos de conexión. Para obtener más información, vea [Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender para endpoint: expertos en amenazas | Microsoft Managed Desktop se integra con información y datos de expertos en amenazas a través de notificaciones de ataques dirigidos. Tendrá que proporcionar un consentimiento adicional antes de habilitar este servicio. Para obtener más información, vea [Microsoft Defender for Endpoint - Threat Experts](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender para endpoint: administración de amenazas y vulnerabilidades | Necesario para su uso futuro en el plan de servicio de Escritorio administrado de Microsoft. Para obtener más información, vea [Microsoft Defender for Endpoint - Threat and Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).
Microsoft Defender para endpoint: reducción de superficie de ataque | La reducción de superficie de ataque se dirige a comportamientos de software arriesgados que suelen ser abusados por los atacantes. Para obtener más información, consulta [Microsoft Defender for Endpoint - Attack Surface Reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).
Microsoft Defender para endpoint: Protección contra vulnerabilidades de seguridad | Protege contra malware que usa exploits para infectar dispositivos y propagarse aplicando automáticamente técnicas de mitigación de vulnerabilidades a procesos y aplicaciones del sistema operativo. Para obtener más información, vea [Microsoft Defender for Endpoint - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).
Microsoft Defender para endpoint: Protección de red | La protección de red expande el ámbito de SmartScreen de Microsoft Defender para bloquear todo el tráfico HTTP y HTTPS saliente que intente conectarse a orígenes de baja reputación. Para obtener más información, vea [Microsoft Defender for Endpoint - Network Protection](/windows/security/threat-protection/microsoft-defender-atp/network-protection).
Protección contra manipulaciones de Microsoft Defender | Windows Tamper Protection se usa para evitar que se cambie la configuración de seguridad, como la protección antivirus. Para obtener más información, vea [Protección contra manipulaciones de Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Protección antivirus basada en comportamiento de Antivirus de Microsoft Defender, heurística y en tiempo real | Siempre en busca de amenazas de archivos y procesos que pueden no detectarse como malware. Para obtener más información, vea Protección antivirus basada en comportamiento de Antivirus de [Microsoft Defender, heurística y en tiempo real.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Protección de entrega en la nube de Antivirus de Microsoft Defender | Proporciona protección dinámica casi instantánea y automatizada contra amenazas nuevas y emergentes. Para obtener más información, vea Protección de [entrega en la nube de Antivirus de Microsoft Defender.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
"Bloquear a primera vista" de Microsoft Defender | Proporciona detección y bloqueo de nuevo malware cuando Windows detecta un archivo sospechoso o desconocido. Para obtener más información, vea [Bloqueo de Microsoft Defender a primera vista.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Aplicaciones potencialmente no deseadas de Antivirus de Microsoft Defender | Las aplicaciones potencialmente no deseadas se usan para bloquear aplicaciones que pueden hacer que el equipo se ejecute lentamente, mostrar anuncios inesperados o, en el peor de los casos, instalar otro software que pueda ser inesperado o no deseado. Para obtener más información, vea [Microsoft Defender AV Potentially Unwanted Applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).
Windows Defender firewall con seguridad avanzada | El filtrado de tráfico de red de dos direcciones basado en host para un dispositivo, Windows Defender firewall bloquea el tráfico de red no autorizado que entra o sale del dispositivo local. Para obtener más información, [vea Windows Defender Firewall with Advanced Security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).
Control de cuentas de usuario | El control de cuentas de usuario cambia al Escritorio seguro cuando una tarea o una acción requiere el acceso de tipo de cuenta de administrador. A los usuarios de Escritorio administrado de Microsoft se les asigna acceso de usuario estándar en la inscripción. Para obtener más información, vea [User Account Control](/windows/security/identity-protection/user-account-control/how-user-account-control-works).


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puedes usar todas las características de Enterprise Mobility + Security E3 y Azure Active Directory Premium P2 para administrar dispositivos MDM.
Microsoft Cloud App Security |  Puedes usar esta característica opcional con Microsoft Managed Desktop.
Azure Information Protection P2  | Puedes usar esta característica opcional con Microsoft Managed Desktop.