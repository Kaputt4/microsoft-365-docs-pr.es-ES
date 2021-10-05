---
title: Recuperarse de un ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 administradores pueden aprender a recuperarse de un ataque de ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9659a68e69f732203a20853320b2e35cd268a7c8
ms.sourcegitcommit: d1eb1c26609146ff5a59b2a1b005dd7ac43ae64e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2021
ms.locfileid: "60099758"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperarse de un ataque de ransomware en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Incluso si toma todas las precauciones para proteger su organización, todavía puede ser víctima de un [ataque de ransomware.](/windows/security/threat-protection/intelligence/ransomware-malware) Ransomware es una gran empresa y en el panorama de amenazas actual Microsoft 365 es un objetivo cada vez mayor [para ataques sofisticados.](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Cloudy-With-A-Chance-Of-APT-Novel-Microsoft-365-Attacks-In-The-Wild.pdf)

Los pasos de este artículo le darán la mejor oportunidad de recuperar datos y detener la propagación interna de la infección. Antes de empezar, tenga en cuenta los siguientes elementos:

- No hay ninguna garantía de que el pago del rescate devolverá el acceso a los archivos. De hecho, pagar el rescate puede convertirte en un objetivo para más ransomware.

  Si ya pagó, pero se recuperó sin usar la solución del atacante, póngase en contacto con su banco para ver si pueden bloquear la transacción.

  También recomendamos que informe del ataque de ransomware a las fuerzas del orden, a los sitios web de informes de estafas y a Microsoft, tal como se describe más adelante en este artículo.

- Es importante que respondas rápidamente al ataque y sus consecuencias. Cuanto más tiempo espere, menos probable es que pueda recuperar los datos afectados.

## <a name="step-1-verify-your-backups"></a>Paso 1: Comprobar las copias de seguridad

Si tiene copias de seguridad sin conexión, probablemente pueda restaurar los datos cifrados  después de quitar la carga de ransomware (malware) del entorno y después de comprobar que no hay acceso no autorizado en los entornos de Microsoft 365. 

Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Paso 2: Deshabilitar Exchange ActiveSync y Sincronización de OneDrive

El punto clave aquí es detener la propagación del cifrado de datos por el ransomware.

Si sospecha que el correo electrónico es un destino del cifrado ransomware, deshabilite temporalmente el acceso de los usuarios a los buzones. Exchange ActiveSync sincroniza los datos entre dispositivos y Exchange Online buzones de correo.

Para deshabilitar Exchange ActiveSync para un buzón, vea [How to disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303).

Para deshabilitar otros tipos de acceso a un buzón, vea:

- [Habilitar o deshabilitar MAPI para un buzón](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Habilitar o deshabilitar el acceso POP3 o IMAP4 para un usuario](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

La pausa Sincronización de OneDrive ayudará a proteger los datos de la nube de que los dispositivos potencialmente infectados actualicen los datos de la nube. Para obtener más información, [vea How to Pause and Resume sync in OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Paso 3: Quitar el malware de los dispositivos afectados

Ejecute un examen antivirus completo y actual en todos los equipos y dispositivos sospechosos para detectar y quitar la carga que está asociada con el ransomware.

No olvide examinar los dispositivos que sincronizan datos o los destinos de las unidades de red asignadas.

Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes más [antiguos) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Una alternativa que también le ayudará a eliminar ransomware o malware es la Herramienta de eliminación de software malintencionado [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Si estas opciones no funcionan, puedes probar Windows Defender [sin](https://support.microsoft.com/help/17466) conexión o solucionar problemas con la detección [y eliminación de malware](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Paso 4: Recuperar archivos en un equipo o dispositivo limpiado

Después de completar el paso anterior para quitar la carga de ransomware del entorno (lo que impedirá que el ransomware cifre o quite los archivos), puede usar el Historial de archivos en Windows 11, Windows 10, Windows 8.1 y mediante System Protection en Windows 7 para intentar recuperar los archivos y carpetas locales. [](https://support.microsoft.com/help/17128)

**Notas**:

- Algunos ransomware también cifrarán o eliminarán las versiones de copia de seguridad, por lo que no puede usar el historial de archivos o la protección del sistema para restaurar archivos. Si esto sucede, necesitas usar copias de seguridad en unidades externas o dispositivos que no se vieron afectados por el ransomware o OneDrive como se describe en la sección siguiente.

- Si una carpeta está sincronizada OneDrive y no está usando la versión más reciente de Windows, puede haber algunas limitaciones con el Historial de archivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Paso 5: Recuperar los archivos en el OneDrive para la Empresa

Restaurar archivos en OneDrive para la Empresa permite restaurar toda la OneDrive a un punto anterior en el tiempo en los últimos 30 días. Para obtener más información, consulte [Restaurar su OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Paso 6: Recuperar correo electrónico eliminado

En el caso excepcional de que el ransomware eliminó todo el correo electrónico, probablemente puede recuperar los elementos eliminados. Para más información vea:

- [Recuperar mensajes eliminados en el buzón de un usuario](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperación de elementos eliminados en Outlook para Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Paso 7: Volver a habilitar Exchange ActiveSync y Sincronización de OneDrive

Después de limpiar los equipos y dispositivos y recuperar los datos, puede volver a habilitar Exchange ActiveSync y Sincronización de OneDrive que deshabilitó anteriormente en el paso [2](#step-2-disable-exchange-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Paso 8 (opcional): Bloquear Sincronización de OneDrive para extensiones de archivo específicas

Después de recuperarse, puede impedir que los OneDrive para la Empresa sincronicen los tipos de archivo que se vieron afectados por este ransomware. Para obtener más información, [vea Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Informar del ataque

### <a name="contact-law-enforcement"></a>Póngase en contacto con las fuerzas del orden

Debe ponerse en contacto con las agencias de seguridad locales o federales. Por ejemplo, si se encuentra en Estados Unidos, puede ponerse en contacto con la oficina de campo local del [FBI,](https://www.fbi.gov/contact-us/field) [ic3](http://www.ic3.gov/complaint/default.aspx) o [servicio secreto](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar un informe al sitio web de informes de estafas de su país

Los sitios web de informes de estafas proporcionan información sobre cómo evitar y evitar estafas. También proporcionan mecanismos para informar si fue víctima de una estafa.

- Australia: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [Centro canadiense de lucha contra el fraude](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Alemania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [Una Síochána de Garda](http://www.garda.ie/)

- Nueva Zelanda: [estafas de asuntos de consumidores](http://www.consumeraffairs.govt.nz/scams)

- Suiza [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- Reino Unido: [fraude de acción](http://www.actionfraud.police.uk/)

- Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)

Si su país no aparece en la lista, pregúntele a las agencias de seguridad locales o federales.

### <a name="submit-email-messages-to-microsoft"></a>Enviar mensajes de correo electrónico a Microsoft

Puede notificar mensajes de suplantación de identidad que contienen ransomware mediante uno de varios métodos. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="additional-ransomware-resources"></a>Recursos adicionales de ransomware

Información clave de Microsoft:

- [La creciente amenaza de ransomware](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), entrada de blog de Microsoft On the Issues del 20 de julio de 2021
- [Ransomware operado por humanos](/security/compass/human-operated-ransomware)
- [Protéjase contra ransomware y extorsión de manera rápida](/security/compass/protect-against-ransomware)
- [El informe de inteligencia de seguridad de Microsoft más reciente](https://www.microsoft.com/securityinsights/) (vea las páginas 22-24)
- **Ransomware: Un informe de amenazas generalizado y continuo** en el nodo del **Análisis de amenazas** del portal de Microsoft 365 Defender (consulte estos [requisitos de licencia](/microsoft-365/security/defender/prerequisites#licensing-requirements))

Microsoft 365:

- [Implementar la protección contra ransomware para el inquilino de Microsoft 365](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Protección de malware y ransomware](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Proteger el equipo Windows de ransomware](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [Control de ransomware en SharePoint Online](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)

Microsoft 365 Defender:

- [Buscar ransomware con la búsqueda avanzada de amenazas](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure:

- [Defensas de Azure para los ataques de ransomware](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Plan de restauración y copia de seguridad para la protección contra ransomware](/security/compass/backup-plan-to-protect-against-ransomware)
- [Ayudar a proteger contra ransomware con Microsoft Azure copia de seguridad](https://www.youtube.com/watch?v=VhLOr2_1MCg) (vídeo de 26 minutos)
- [Recuperación de una identidad en peligro](/azure/security/fundamentals/recover-from-identity-compromise)
- [Detección de ataques de varias fases en Azure Sentinel](/azure/sentinel/fusion#ransomware)
- [Detección de fusión para ransomware en Azure Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Cloud App Security:

-  [Crear directivas de detección de anomalías en Cloud App Security](/cloud-app-security/anomaly-detection-policy)

Entradas de blog del equipo de Seguridad de Microsoft:

- [3 pasos para evitar y recuperarse del ransomware (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [Camino a la resistencia al comprender los riesgos de ciberseguridad: Parte 4 — Navegación por las amenazas actuales (mayo de 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  Consulte la sección **Ransomware**.

- [Ataques de ransomware operados por humanos: Un desastre evitable (marzo de 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  Incluye análisis de cadenas de ataques, de ataques reales.

- [Respuesta frente a ransomware: ¿pagar o no pagar? (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro responde ante ataques de ransomware con transparencia (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
