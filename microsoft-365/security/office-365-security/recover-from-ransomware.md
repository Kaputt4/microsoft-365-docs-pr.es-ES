---
title: Recuperarse de un ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
- m365solution-ransomware
- highpri
description: Los administradores de Microsoft 365 pueden aprender a recuperarse de un ataque de ransomware.
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 6fc5aef45ab6fbced903dc46e2734a32d2dc0948
ms.sourcegitcommit: 2b89bcff547e00be3d38dc8d1e6cbcf8f41eba42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67597766"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperación de un ataque de ransomware en Microsoft 365

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Incluso si toma todas las precauciones necesarias para proteger su organización, puede ser víctima de un ataque [de ransomware](/windows/security/threat-protection/intelligence/ransomware-malware) . El ransomware es un gran negocio y, en el panorama de amenazas actual, Microsoft 365 es un objetivo cada vez mayor [para ataques sofisticados](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Cloudy-With-A-Chance-Of-APT-Novel-Microsoft-365-Attacks-In-The-Wild.pdf).

Los pasos de este artículo le proporcionarán la mejor oportunidad de recuperar datos y detener la propagación interna de la infección. Antes de empezar, tenga en cuenta los siguientes elementos:

- No hay ninguna garantía de que el pago del rescate devolverá el acceso a sus archivos. De hecho, pagar el rescate puede hacer que un objetivo para más ransomware.

  Si ya ha pagado, pero se ha recuperado sin usar la solución del atacante, póngase en contacto con su banco para ver si pueden bloquear la transacción.

  También se recomienda que informe del ataque de ransomware a la aplicación de la ley, sitios web de informes de estafa, y Microsoft como se describe más adelante en este artículo.

- Es importante que responda rápidamente al ataque y sus consecuencias. Cuanto más tiempo espere, menos probable es que pueda recuperar los datos afectados.

## <a name="step-1-verify-your-backups"></a>Paso 1: Comprobar las copias de seguridad

Si tiene copias de seguridad sin conexión, es probable que pueda restaurar los datos cifrados **después** de quitar la carga útil de ransomware (malware) de su entorno y **después** de comprobar que no hay acceso no autorizado en los entornos de Microsoft 365.

Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Paso 2: Deshabilitar Exchange ActiveSync y Sincronización de OneDrive

El punto clave aquí es detener la propagación del cifrado de datos por el ransomware.

Si sospecha que el correo electrónico es un destino del cifrado de ransomware, deshabilite temporalmente el acceso del usuario a los buzones. Exchange ActiveSync sincroniza los datos entre dispositivos y Exchange Online buzones.

Para deshabilitar Exchange ActiveSync de un buzón de correo, consulte [Cómo deshabilitar Exchange ActiveSync para los usuarios de Exchange Online](https://support.microsoft.com/help/2795303).

Para deshabilitar otros tipos de acceso a un buzón de correo, consulte:

- [Habilite o deshabilite MAPI para un buzón](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Habilitar o deshabilitar el acceso POP3 o IMAP4 para un usuario](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Pausar Sincronización de OneDrive ayudará a proteger los datos en la nube de que los dispositivos potencialmente infectados actualicen los datos en la nube. Para obtener más información, vea [Pausar y reanudar la sincronización en OneDrive](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Paso 3: Quitar el malware de los dispositivos afectados

Ejecute un examen antivirus completo y actual en todos los equipos y dispositivos sospechosos para detectar y quitar la carga que está asociada con el ransomware.

No olvide examinar los dispositivos que sincronizan datos o los destinos de las unidades de red asignadas.

Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes anteriores) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Una alternativa que también le ayudará a eliminar ransomware o malware es la [herramienta de eliminación de software malintencionado (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Si estas opciones no funcionan, puede intentar [Windows Defender sin conexión](https://support.microsoft.com/help/17466) o [solucionar problemas con la detección y eliminación de malware](https://support.microsoft.com/help/4466982).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Paso 4: Recuperar archivos en un equipo o dispositivo limpio

Después de completar el paso anterior para quitar la carga útil de ransomware de su entorno (lo que impedirá que el ransomware cifre o quite los archivos), puede usar [el historial](https://support.microsoft.com/help/17128) de archivos en Windows 11, Windows 10, Windows 8.1 y mediante Protección del sistema en Windows 7 para intentar recuperar los archivos y carpetas locales.

**Notas**:

- Algunos ransomware también cifrarán o eliminarán las versiones de copia de seguridad, por lo que no puede usar el historial de archivos o protección del sistema para restaurar archivos. Si esto sucede, necesita usar copias de seguridad en unidades externas o dispositivos que no se vieron afectados por el ransomware o OneDrive, como se describe en la sección siguiente.

- Si una carpeta está sincronizada con OneDrive y no usa la versión más reciente de Windows, puede haber algunas limitaciones mediante el historial de archivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Paso 5: Recuperar los archivos en el OneDrive para la Empresa

Restauración de archivos en OneDrive para la Empresa permite restaurar todo onedrive a un momento dado anterior en los últimos 30 días. Para obtener más información, consulte [Restaurar su OneDrive](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Paso 6: Recuperación del correo electrónico eliminado

En el raro caso de que el ransomware eliminó todo el correo electrónico, es probable que pueda recuperar los elementos eliminados. Para obtener más información, consulte:

- [Recuperar mensajes eliminados en el buzón de un usuario](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperación de elementos eliminados en Outlook para Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Paso 7: Volver a habilitar Exchange ActiveSync y Sincronización de OneDrive

Después de limpiar los equipos y dispositivos y recuperar los datos, puede volver a habilitar Exchange ActiveSync y Sincronización de OneDrive que deshabilitó anteriormente en el [paso 2](#step-2-disable-exchange-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Paso 8 (opcional): Bloquear Sincronización de OneDrive para extensiones de archivo específicas

Después de recuperarse, puede evitar que OneDrive para la Empresa clientes sincronicen los tipos de archivo que se vieron afectados por este ransomware. Para obtener más información, vea [Set-SPOTenantSyncClientRestriction](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Notificar el ataque

### <a name="contact-law-enforcement"></a>Ponerse en contacto con el cumplimiento de la ley

Debe ponerse en contacto con sus agencias de cumplimiento de la ley locales o federales. Por ejemplo, si está en la Estados Unidos puede ponerse en contacto con la [oficina local del FBI](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) o [el Servicio Secreto](http://www.secretservice.gov/).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar un informe al sitio web de informes de estafas de su país

Sitios web de informes de estafas proporcionan información sobre cómo prevenir y evitar estafas. También proporcionan mecanismos para informar si usted fue víctima de estafa.

- Australia: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [Centro canadiense de lucha contra el fraude](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Alemania: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [a Garda Síochána](http://www.garda.ie/)

- Nueva Zelanda: [Estafas de asuntos de consumo](http://www.consumeraffairs.govt.nz/scams)

- Suiza [Nationales Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- Reino Unido: [Fraude de acción](http://www.actionfraud.police.uk/)

- Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)

Si su país no aparece en la lista, pregúntele a las agencias de cumplimiento de la ley locales o federales.

### <a name="submit-email-messages-to-microsoft"></a>Envío de mensajes de correo electrónico a Microsoft

Puede notificar mensajes de suplantación de identidad (phishing) que contengan ransomware mediante uno de varios métodos. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="additional-ransomware-resources"></a>Recursos adicionales de ransomware

Información clave de Microsoft:

- [La creciente amenaza de ransomware](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), entrada de blog de Microsoft On the Issues del 20 de julio de 2021
- [Ransomware operado por humanos](/security/compass/human-operated-ransomware)
- [Protéjase contra ransomware y extorsión de manera rápida](/security/compass/protect-against-ransomware)
- [Informe de Microsoft Digital Defense 2021](https://www.microsoft.com/security/business/microsoft-digital-defense-report) (vea las páginas 10-19)
- [Ransomware: informe de análisis de amenazas generalizado y continuo](https://security.microsoft.com/threatanalytics3/05658b6c-dc62-496d-ad3c-c6a795a33c27/overview) en el portal de Microsoft 365 Defender

Microsoft 365:

- [Implementar la protección contra ransomware para el inquilino de Microsoft 365](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Maximizar la resistencia de ransomware con Azure y Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Protección de malware y ransomware](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [Proteger su PC Windows de ransomware](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [Control de ransomware en SharePoint Online](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)
- [Informes de análisis de amenazas para ransomware](https://security.microsoft.com/threatanalytics3?page_size=30&filters=tags%3DRansomware&ordering=-lastUpdatedOn&fields=displayName,alertsCount,impactedEntities,reportType,createdOn,lastUpdatedOn,tags,flag) en el portal de Microsoft 365 Defender

Microsoft 365 Defender:

- [Buscar ransomware con la búsqueda avanzada de amenazas](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure:

- [Defensas de Azure para los ataques de ransomware](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Maximizar la resistencia de ransomware con Azure y Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [Plan de restauración y copia de seguridad para la protección contra ransomware](/security/compass/backup-plan-to-protect-against-ransomware)
- [Ayuda para protegerse de ransomware con Microsoft Azure Backup](https://www.youtube.com/watch?v=VhLOr2_1MCg) (vídeo de 26 minutos)
- [Recuperación de una identidad en peligro](/azure/security/fundamentals/recover-from-identity-compromise)
- [Detección avanzada de ataques de varias fases en Microsoft Sentinel](/azure/sentinel/fusion#ransomware)
- [Detección de difusión para ransomware en Microsoft Sentinel](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Defender for Cloud Apps:

-  [Crear directivas de detección de anomalías en Defender para aplicaciones en la nube](/cloud-app-security/anomaly-detection-policy)

Entradas de blog del equipo de Seguridad de Microsoft:

- [3 pasos para evitar y recuperarse del ransomware (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [Una guía para combatir el ransomware operado por personas: Parte 1 (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/20/a-guide-to-combatting-human-operated-ransomware-part-1/)

  Pasos clave sobre cómo el equipo de detección y respuesta de Microsoft (DART) lleva a cabo investigaciones de incidentes de ransomware.

- [Una guía para combatir el ransomware operado por personas: Parte 2 (septiembre de 2021)](https://www.microsoft.com/security/blog/2021/09/27/a-guide-to-combatting-human-operated-ransomware-part-2/)

  Recomendaciones y procedimientos recomendados.

- [Camino a la resistencia al comprender los riesgos de ciberseguridad: Parte 4 — Navegación por las amenazas actuales (mayo de 2021)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  Consulte la sección **Ransomware**.

- [Ataques de ransomware operados por humanos: Un desastre evitable (marzo de 2020)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  Incluye análisis de cadenas de ataques, de ataques reales.

- [Respuesta frente a ransomware: ¿pagar o no pagar? (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro responde ante ataques de ransomware con transparencia (diciembre de 2019)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
