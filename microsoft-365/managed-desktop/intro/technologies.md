---
title: Tecnologías del Escritorio administrado de Microsoft
description: En este artículo se enumeran las tecnologías y aplicaciones usadas en el Escritorio administrado de Microsoft.
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 70e4eb442f9c0e52dbf234280205dd908c135b8d
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233113"
---
# <a name="microsoft-managed-desktop-technologies"></a>Tecnologías del Escritorio administrado de Microsoft

En este artículo se enumeran las tecnologías y aplicaciones usadas en el Escritorio administrado de Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Las licencias de Microsoft 365 Enterprise son necesarias para todos los usuarios de Escritorio administrado de Microsoft. Para obtener más información sobre los requisitos de licencia para el servicio, vea [Requisitos previos para escritorio administrado de Microsoft.](../get-ready/prerequisites.md)

En este artículo se resumen los componentes incluidos en las licencias enterprise necesarias, con una descripción de cómo el servicio usa cada componente con dispositivos de Escritorio administrado de Microsoft. Los roles y responsabilidades específicos de cada área se detallan en toda la documentación de Escritorio administrado de Microsoft. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 o E5
 |
 --- | ---
Aplicaciones de Microsoft 365 para empresas (64 bits) | Estas aplicaciones de Office se enviarán con el dispositivo: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype Empresarial y OneNote.<br><br>No se incluyen las versiones completas de 64 bits de Microsoft Project y Microsoft Visio. Sin embargo, dado que la instalación de estas aplicaciones depende de la instalación de Aplicaciones de Microsoft 365 para empresas, Escritorio administrado de Microsoft ha creado implementaciones predeterminadas de Microsoft Intune y grupos de seguridad que puede usar para implementar estas aplicaciones en usuarios con licencia. Para obtener más información, vea [Instalar Microsoft Project o Microsoft Visio en dispositivos de Escritorio administrado de Microsoft.](../get-started/project-visio.md)
OneDrive |El inicio de sesión único de Azure Active Directory está habilitado para los usuarios cuando inician sesión por primera vez en OneDrive.<br><br>Se incluye la redirección de carpetas conocidas para las carpetas "Escritorio", "Documento" e "Imágenes"; habilitado y configurado por escritorio administrado de Microsoft.
Aplicaciones de la Tienda |    Microsoft Sway y Power BI no se envían con el dispositivo. Estas aplicaciones están disponibles para su descarga desde Microsoft Store.
Aplicaciones de Win32 |    Teams no se envía con el dispositivo, pero microsoft los empaqueta y proporciona para los dispositivos de escritorio administrado de Microsoft. El cliente de Azure Information Protection no se incluye con el dispositivo, pero se puede empaquetar para su implementación.
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se envían con el dispositivo. Los usuarios pueden acceder a la versión web de estas aplicaciones con un explorador.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender para endpoint
Se recomienda que los administradores de TI configuren las siguientes opciones. Esta configuración no se incluye ni se administra como parte del Escritorio administrado de Microsoft.

 |
 --- | ---
Windows Hello para empresas | Debes implementar Windows Hello para empresas para reemplazar contraseñas con autenticación segura en dos fases para dispositivos de Escritorio administrado de Microsoft. Para obtener más información, [consulta Windows Hello para empresas.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Virtualización de aplicaciones | Puedes implementar paquetes de virtualización de aplicaciones (App-V) con el cliente de administración de aplicaciones de Intune Win32. Para obtener más información, vea [Virtualización de aplicaciones.](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference)
Prevención de pérdida de datos de Microsoft 365 | Debe implementar la prevención de pérdida de datos de Microsoft 365 para supervisar las acciones que se están haciendo en los elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido no intencionado de esos elementos. Para obtener más información, consulte Prevención de pérdida de datos [de Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)


Características incluidas y administradas como parte del Escritorio administrado de Microsoft:

 |
 --- | ---
Cifrado de unidad BitLocker | El cifrado de unidad BitLocker se usa para cifrar todas las unidades del sistema. Para obtener más información, consulta [Cifrado de unidad BitLocker.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Protege la integridad del sistema en el inicio y valida que la integridad del sistema se haya mantenido realmente. Para obtener más información, [consulta Windows Defender Protección del sistema.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Credential Guard de Windows Defender | Windows Defender Credential Guard usa la seguridad basada en virtualización para aislar secretos para que solo el software del sistema con privilegios pueda acceder a ellos. Para obtener más información, [consulta Windows Defender Protección del sistema.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender para punto de conexión: detección y respuesta de puntos de conexión | Las operaciones de seguridad de escritorio administrado de Microsoft responden a las alertas y toma medidas para corregir las amenazas mediante la detección y respuesta de puntos de conexión. Para obtener más información, consulta [Microsoft Defender para Endpoint : Detección y respuesta de puntos de conexión.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender para puntos de conexión: expertos en amenazas | Escritorio administrado de Microsoft se integra con información y datos de expertos en amenazas a través de notificaciones de ataques dirigidos. Tendrá que proporcionar consentimiento adicional antes de habilitar este servicio. Para obtener más información, vea [Microsoft Defender para Endpoint - Threat Experts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender para puntos de conexión: administración de amenazas y vulnerabilidades | Necesario para su uso futuro en el plan de servicio de Escritorio administrado de Microsoft. Para obtener más información, vea [Microsoft Defender para Endpoint : Administración de amenazas y vulnerabilidades.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender para puntos de conexión: Reducción de superficie de ataque | La reducción de superficie de ataque se dirige a comportamientos de software de riesgo que a menudo son usados por atacantes. Para obtener más información, consulta [Microsoft Defender para Endpoint - Reducción de superficie de ataque.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender para endpoint: Protección contra vulnerabilidades | Protege contra el malware que usa vulnerabilidades de seguridad para infectar dispositivos y propagarse mediante la aplicación automática de técnicas de mitigación de vulnerabilidades a aplicaciones y procesos del sistema operativo. Para obtener más información, consulta [Microsoft Defender para Endpoint - Protección contra vulnerabilidades.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender para puntos de conexión: Protección de red | Protección de red amplía el ámbito de SmartScreen de Microsoft Defender para bloquear todo el tráfico HTTP y HTTPS saliente que intenta conectarse a orígenes de baja reputación. Para obtener más información, vea [Microsoft Defender para Endpoint : Protección de red.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Protección contra alteraciones de Microsoft Defender | Protección contra alteraciones de Windows se usa para evitar que se cambie la configuración de seguridad, como la protección antivirus. Para obtener más información, vea [Protección contra alteraciones de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Protección antivirus basada en comportamiento, heurística y en tiempo real de Antivirus de Microsoft Defender | Siempre en busca de amenazas de archivos y procesos que no se detecten como malware. Para obtener más información, vea Protección antivirus basada en el comportamiento del Antivirus de [Microsoft Defender, heurística y en tiempo real.]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Protección de entrega en la nube del Antivirus de Microsoft Defender | Proporciona protección dinámica casi instantánea y automatizada contra amenazas nuevas y emergentes. Para obtener más información, vea Protección de [entrega en la nube del Antivirus de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
"Bloquear a primera vista" de Microsoft Defender | Proporciona detección y bloqueo de nuevo malware cuando Windows detecta un archivo sospechoso o desconocido. Para obtener más información, vea [Bloqueo de Microsoft Defender a primera vista.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Aplicaciones potencialmente no deseadas del Antivirus de Microsoft Defender | Las aplicaciones potencialmente no deseadas se usan para bloquear aplicaciones que pueden hacer que el equipo se ejecute lentamente, muestre anuncios inesperados o, en el peor de los casos, instale otro software que podría ser inesperado o no deseado. Para obtener más información, vea [Aplicaciones potencialmente no deseadas del Antivirus de Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender Firewall con seguridad avanzada | El filtrado de tráfico de red doble basado en host para un dispositivo, Windows Defender Firewall bloquea el tráfico de red no autorizado que fluye dentro o fuera del dispositivo local. Para obtener más información, [consulte Windows Defender Firewall con seguridad avanzada.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Control de cuentas de usuario | Control de cuentas de usuario cambia al Escritorio seguro cuando una tarea o una acción requiere el acceso de tipo cuenta de administrador. A los usuarios de Escritorio administrado de Microsoft se les asigna acceso de usuario estándar durante la inscripción. Para obtener más información, vea [Control de cuentas de usuario.](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puedes usar todas las características de Enterprise Mobility + Security E3 y Azure Active Directory Premium P2 para administrar dispositivos MDM.
Microsoft Cloud App Security |  Puede usar esta característica opcional con escritorio administrado de Microsoft.
Azure Information Protection P2  | Puede usar esta característica opcional con escritorio administrado de Microsoft.
