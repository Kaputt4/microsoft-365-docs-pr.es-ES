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
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094872"
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
Aplicaciones de Win32 |    Teams no se incluye con el dispositivo, pero microsoft los empaqueta y proporciona para los dispositivos de escritorio administrado de Microsoft. El cliente de Azure Information Protection no se incluye con el dispositivo, pero se puede empaquetar para su implementación.
Aplicaciones web |  Yammer, Office en un explorador, Delve, Flow, StaffHub, PowerApps y Planner no se envían con el dispositivo. Los usuarios pueden acceder a la versión web de estas aplicaciones con un explorador.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 o E3 con Microsoft Defender para endpoint
Recomendado
 |
 --- | ---
[Windows Hello para empresas](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | Se recomienda a los clientes implementar Windows Hello para empresas para reemplazar contraseñas con autenticación segura en dos fases que se usa en dispositivos de Escritorio administrado de Microsoft.
[Virtualización de aplicaciones](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | Los clientes pueden implementar paquetes de virtualización de aplicaciones (App-V) con el cliente de administración de aplicaciones de Intune Win32.
[Prevención de pérdida de datos de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | Se recomienda a los clientes implementar la prevención de pérdida de datos (DLP) de Microsoft 365 para supervisar las acciones que se están haciendo en los elementos que ha determinado que son confidenciales y para ayudar a evitar el uso compartido no intencionado de esos elementos.   

Incluido y administrado en el servicio
 |
 --- | ---
[Cifrado de unidad BitLocker](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | El cifrado de unidad BitLocker se usa para cifrar todas las unidades del sistema. 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | Protege la integridad del sistema al iniciarse y valida que la integridad del sistema se haya mantenido realmente.
[Credential Guard de Windows Defender]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard usa la seguridad basada en virtualización para aislar secretos para que solo el software del sistema con privilegios pueda acceder a ellos.
[Microsoft Defender para punto de conexión | Detección y respuesta de puntos de conexión](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Las operaciones de seguridad de escritorio administrado de Microsoft responden a las alertas y toma medidas para corregir las amenazas mediante la detección y respuesta de puntos de conexión.
[Microsoft Defender para punto de conexión | Expertos en amenazas](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Escritorio administrado de Microsoft se integra con información y datos de expertos en amenazas a través de notificaciones de ataques dirigidos. Los clientes deben proporcionar consentimiento adicional antes de habilitar este servicio.  
[Microsoft Defender para punto de conexión | Administración de amenazas y vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Necesario para su uso futuro en el plan de servicio de Escritorio administrado de Microsoft.
[Microsoft Defender para punto de conexión | Reducción de superficie de ataque](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | La reducción de superficie de ataques se dirige a comportamientos de software de riesgo que suelen ser usados por atacantes.
[Microsoft Defender para punto de conexión | Protección contra vulnerabilidades](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | Protege contra el malware que usa vulnerabilidades de seguridad para infectar dispositivos y propagarse mediante la aplicación automática de técnicas de mitigación de vulnerabilidades a aplicaciones y procesos del sistema operativo.
[Microsoft Defender para punto de conexión | Protección de red](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | Protección de red amplía el ámbito de SmartScreen de Microsoft Defender para bloquear todo el tráfico HTTP saliente que intenta conectarse a orígenes de baja reputación.
[Protección contra alteraciones de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Protección contra alteraciones de Windows se usa para evitar que se cambie la configuración de seguridad, como la protección antivirus.
[Protección antivirus basada en comportamiento, heurística y en tiempo real de Antivirus de Microsoft Defender]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Siempre en busca de amenazas de archivos y procesos que no se detecten como malware.
[Protección de entrega en la nube del Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | Proporciona protección dinámica casi instantánea y automatizada contra amenazas nuevas y emergentes.
[Bloqueo de Microsoft Defender a primera vista](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Proporciona detección y bloqueo de nuevo malware cuando Windows detecta un archivo sospechoso o desconocido.
[Aplicaciones potencialmente no deseadas del Antivirus de Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | Las aplicaciones potencialmente no deseadas (PUA) se usan para bloquear aplicaciones que pueden hacer que el equipo se ejecute lentamente, muestre anuncios inesperados o, en el peor de los casos, instale otro software que podría ser inesperado o no deseado.
[Windows Defender Firewall con seguridad avanzada](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | El filtrado de tráfico de red doble basado en host para un dispositivo, Windows Defender Firewall bloquea el tráfico de red no autorizado que fluye dentro o fuera del dispositivo local.
[Control de cuentas de usuario](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | Control de cuentas de usuario cambia al Escritorio seguro cuando una tarea o una acción requiere el acceso de tipo de cuenta de administrador. A los usuarios de Escritorio administrado de Microsoft se les asigna acceso de usuario estándar durante la inscripción. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Puedes usar todas las características de Enterprise Mobility + Security E3 y Azure Active Directory Premium P2 para administrar dispositivos MDM.
Microsoft Cloud App Security |  Puede usar esta característica opcional con escritorio administrado de Microsoft.
Azure Information Protection P2  | Puede usar esta característica opcional con escritorio administrado de Microsoft.
