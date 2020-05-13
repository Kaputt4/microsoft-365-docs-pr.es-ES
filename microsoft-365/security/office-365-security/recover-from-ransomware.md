---
title: Recuperarse de un ataque de ransomware
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Los administradores de Microsoft 365 pueden obtener información sobre cómo recuperarse de un ataque de ransomware.
ms.openlocfilehash: 51f5bb365fe707615444c1399479171aa72755e1
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208263"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperarse de un ataque de ransomware en Microsoft 365

Incluso si toma todas las precauciones para proteger su organización, puede seguir siendo víctima de un ataque de [ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) . Ransomware es gran empresa y los ataques se comprueban de forma sofisticada.

Los pasos de este tema le proporcionarán la mejor oportunidad para recuperar datos cifrados por ransomware y ayudarán a detener la propagación de la infección en su organización. Antes de empezar, tenga en cuenta los siguientes elementos:

- No hay ninguna garantía de que pagar el Ransom devolverá acceso a los archivos. De hecho, pagar el Ransom puede convertirle en un objetivo para obtener más ransomware. Si ya ha pagado, pero ha podido recuperar los archivos correctamente sin tener que usar la resolución del atacante, debe llamar al Banco para ver si pueden bloquear la transacción. También le recomendamos que informe sobre el ataque de ransomware a los sitios web de la ley, los informes de fraude de estafa y Microsoft, tal como se describe más adelante en este tema.

- Es muy importante que responda rápidamente al ataque y a sus consecuencias. Cuanto más tiempo espere, lo menos probable es que pueda recuperar los datos afectados.

## <a name="step-1-verify-your-backups"></a>Paso 1: comprobar las copias de seguridad

Si tiene copias de seguridad sin conexión, probablemente podrá restaurar los datos cifrados **una vez** que haya quitado la carga de ransomware (malware) de su entorno.

Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>Paso 2: deshabilitar la sincronización de ActiveSync y de OneDrive

El punto clave aquí es detener la propagación de cifrado de datos por ransomware.

Si sospecha que el correo electrónico es un objetivo, debe deshabilitar temporalmente el acceso de los usuarios a los buzones. Exchange ActiveSync se usa en dispositivos móviles para sincronizar datos entre el dispositivo y el buzón de correo de Exchange Online.

Para deshabilitar ActiveSync para un buzón de correo, consulte [How to Disable Exchange ActiveSync for users in Exchange Online](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365).

Para deshabilitar otros tipos de acceso a un buzón, consulte:

- [Habilitar o deshabilitar MAPI para un buzón de correo](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi).

- [Habilitar o deshabilitar el acceso a POP3 o IMAP4 para un usuario](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Pausar la sincronización de OneDrive le ayudará a proteger los datos de la nube para que no se actualicen mediante dispositivos potencialmente infectados. Para obtener más información, consulte [Cómo pausar y reanudar la sincronización en OneDrive](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e).

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Paso 3: quitar el malware de los dispositivos afectados

Ejecute un análisis antivirus completo con las actualizaciones más recientes en todos los equipos y dispositivos sospechosos para detectar y quitar la carga asociada con el ransomware. No olvide los dispositivos que sincronizan datos o el destino de las unidades de red asignadas (también deben examinarse los equipos y dispositivos).

Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes más antiguos) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Una alternativa que también le ayudará a quitar ransomware o malware es la [herramienta de eliminación de software malintencionado (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905).

Si estas opciones no funcionan, puedes probar [Windows Defender sin conexión](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) o [solucionar problemas de detección y eliminación de malware](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware).

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Paso 4: recuperar archivos en un equipo o dispositivo limpio

Una vez que haya completado el paso anterior para quitar la carga de ransomware del entorno (lo que impedirá que el ransomware Cifre o quite los archivos), puede usar el [historial de archivos](https://support.microsoft.com/help/17128/windows-8-file-history) en Windows 10 y Windows 8,1 o en la protección del sistema de Windows 7 para intentar recuperar los archivos y carpetas locales.

**Notas**:

- Algunos ransomware también cifrarán o eliminarán las versiones de copia de seguridad, por lo que no podrá usar el historial de archivos o la protección del sistema para restaurar archivos. Si esto ocurre, necesita usar copias de seguridad en dispositivos o dispositivos externos que no se vieron afectados por el ransomware o el OneDrive, tal como se describe en la siguiente sección.

- Si una carpeta está sincronizada en OneDrive y no usa la versión más reciente de Windows, es posible que existan algunas limitaciones al usar el historial de archivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Paso 5: recuperar los archivos en su OneDrive para la empresa

Los archivos restaurar en OneDrive para la empresa permiten restaurar todo el OneDrive a un punto anterior en el tiempo de los últimos 30 días. Para obtener más información, vea [restaurar el OneDrive](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15).

## <a name="step-6-recover-deleted-email"></a>Paso 6: recuperar el correo electrónico eliminado

En el caso poco probable de que ransomware elimine todo el correo electrónico, probablemente pueda recuperar los elementos eliminados. Para obtener más información, vea:

- [Recuperar mensajes eliminados en el buzón de un usuario](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperación de elementos eliminados en Outlook para Windows](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Paso 7: volver a habilitar Exchange ActiveSync y la sincronización de OneDrive

Una vez que haya limpiado los equipos y dispositivos y recuperado los datos, puede volver a habilitar la sincronización de ActiveSync y de OneDrive que deshabilitó anteriormente en el [paso 2](#step-2-disable-activesync-and-onedrive-sync).

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Paso 8 (opcional): bloquear la sincronización de OneDrive para extensiones de archivo específicas

Una vez que haya recuperado, puede evitar que los clientes de OneDrive para la empresa sincronicen los tipos de archivo afectados por este ransomware. Para obtener más información, vea [set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Informar del ataque

### <a name="contact-law-enforcement"></a>Aplicación de la ley de contacto

Debe ponerse en contacto con las agencias de cumplimiento normativo local o federal. Por ejemplo, si está en los Estados Unidos, puede ponerse en contacto con el servicio de oficina, [IC3](http://www.ic3.gov/complaint/default.aspx) o [Secret](http://www.secretservice.gov/)del [FBI local](https://www.fbi.gov/contact-us/field).

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar un informe al sitio web de informes de fraude de su país

Los sitios web de informes de estafa proporcionan información sobre cómo evitar y evitar estafas. También proporcionan mecanismos para informar si ha sido víctima de un timo.

- Australia: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [centro anti-fraude canadiense](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence Nationale de la Sécurité des Systèmes d'information](http://www.ssi.gouv.fr/)

- Alemania: [Bundesamt für Sicherheit en der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [una Garda Síochána](http://www.garda.ie/)

- Nueva Zelanda: [fraudes de asuntos de consumo](http://www.consumeraffairs.govt.nz/scams)

- Reino Unido: [fraude de acciones](http://www.actionfraud.police.uk/)

- Estados Unidos: [en protección en línea](http://www.onguardonline.gov/)

Si su país no aparece en la lista, pregunte a las agencias de cumplimiento normativo local o federal.

### <a name="submit-email-messages-to-microsoft"></a>Enviar mensajes de correo electrónico a Microsoft

Puede informar del mensaje de suplantación de identidad (phishing) que contiene ransomware mediante uno de varios métodos. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Vea también

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Respuesta por ransomware: ¿pagar o no pagar?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk de la anhidro responde al ataque de ransomware con transparencia](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Detección de ransomware y recuperación de los archivos en OneDrive](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Informe de inteligencia en seguridad de Microsoft](https://www.microsoft.com/securityinsights/)

- [Habilitar o deshabilitar macros en archivos de Office](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Configuración recomendada para EOP y la seguridad de ATP de Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [Una actualización que merece la pena: la seguridad de next-gen en Windows 10 prueba resistencia contra brotes de ransomware en 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [No hay mas samas: ¿Cuál es el contenido del operando de un modus de ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware de bloqueo, suerte para evitarlo](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT julio de 2016: ransomware CERBER](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Los tres cabezales del Cerberus-like CERBER ransomware](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Troldesh ransomware afectado por el código de da Vinci](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
