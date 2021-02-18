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
description: Los administradores de Microsoft 365 pueden aprender a recuperarse de un ataque de ransomware.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 120dd9ae71f04d6921fae95965f56f0a08f1280c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289310"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Recuperarse de un ataque de ransomware en Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Incluso si toma todas las precauciones para proteger su organización, todavía puede ser víctima de un [ataque de ransomware.](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) Ransomware es una gran empresa y los ataques son muy sofisticados.

Los pasos de este artículo le darán la mejor oportunidad de recuperar datos y detener la propagación interna de la infección. Antes de empezar, tenga en cuenta los siguientes elementos:

- No hay ninguna garantía de que al pagar el rescate se devolverá acceso a los archivos. De hecho, pagar el rescate puede convertirte en un destino de más ransomware.

  Si ya ha pagado, pero ha recuperado sin usar la solución del atacante, póngase en contacto con su banco para ver si puede bloquear la transacción.

  También le recomendamos que informe del ataque ransomware a los organismos de seguridad, a los sitios web de informes de estafas y a Microsoft, como se describe más adelante en este artículo.

- Es importante que respondas rápidamente al ataque y sus consecuencias. Cuanto más tiempo espere, menor será la probabilidad de que pueda recuperar los datos afectados.

## <a name="step-1-verify-your-backups"></a>Paso 1: Comprobar las copias de seguridad

Si tiene copias de seguridad sin conexión, probablemente puede restaurar los datos cifrados después de quitar la carga de ransomware (malware) de su entorno. 

Si no tiene copias de seguridad o si las copias de seguridad también se vieron afectadas por el ransomware, puede omitir este paso.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>Paso 2: Deshabilitar la sincronización Exchange ActiveSync y OneDrive

El punto clave aquí es detener la propagación del cifrado de datos por el ransomware.

Si sospecha que el correo electrónico es un destino del cifrado ransomware, deshabilite temporalmente el acceso de los usuarios a los buzones. Exchange ActiveSync sincroniza datos entre dispositivos y buzones de Exchange Online.

Para deshabilitar Exchange ActiveSync para un buzón de correo, consulte Cómo deshabilitar Exchange ActiveSync [para los usuarios de Exchange Online](https://support.microsoft.com/help/2795303).

Para deshabilitar otros tipos de acceso a un buzón, consulte:

- [Habilitar o deshabilitar MAPI para un buzón](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)de correo.

- [Habilitar o deshabilitar el acceso a POP3 o IMAP4 para un usuario](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

Pausar la sincronización de OneDrive le ayudará a proteger los datos de la nube de que los dispositivos potencialmente infectados se actualicen. Para obtener más información, [vea Cómo pausar y reanudar la sincronización en OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>Paso 3: Quitar el malware de los dispositivos afectados

Ejecuta un examen antivirus completo y actual en todos los equipos y dispositivos sospechosos para detectar y quitar la carga asociada con el ransomware.

No olvides examinar los dispositivos que sincronizan datos o los destinos de las unidades de red asignadas.

Puede usar [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) o (para clientes más [antiguos) Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201).

Una alternativa que también le ayudará a quitar ransomware o malware es la Herramienta de eliminación de software malintencionado [(MSRT).](https://www.microsoft.com/download/details.aspx?id=9905)

Si estas opciones no funcionan, puede probar Windows Defender [sin](https://support.microsoft.com/help/17466) conexión o solucionar problemas con la detección y [eliminación de malware.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>Paso 4: Recuperar archivos en un equipo o dispositivo limpiado

Después de completar el paso anterior para quitar la carga de ransomware del entorno (lo que impedirá que el ransomware cifre o quite los archivos), puedes usar el historial de archivos en Windows 10 y Windows 8.1 o la Protección del sistema en Windows 7 para intentar recuperar los archivos y carpetas locales. [](https://support.microsoft.com/help/17128)

**Notas**:

- Some ransomware will also encrypt or delete the backup versions, so you can't use File History or System Protection to restore files. Si esto ocurre, necesita usar copias de seguridad en unidades externas o dispositivos que no se vieron afectados por el ransomware o OneDrive, como se describe en la sección siguiente.

- Si una carpeta está sincronizada con OneDrive y no usa la versión más reciente de Windows, puede haber algunas limitaciones con el Historial de archivos.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>Paso 5: Recuperar los archivos en OneDrive para la Empresa

La restauración de archivos en OneDrive para la Empresa le permite restaurar su OneDrive completo a un punto anterior en el tiempo en los últimos 30 días. Para obtener más información, [vea Restaurar OneDrive.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>Paso 6: Recuperar correo electrónico eliminado

En el caso poco frecuente de que el ransomware haya eliminado todo el correo electrónico, es probable que pueda recuperar los elementos eliminados. Para obtener más información, vea:

- [Recuperar mensajes eliminados en el buzón de un usuario](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Recuperación de elementos eliminados en Outlook para Windows](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>Paso 7: Volver a habilitar la sincronización Exchange ActiveSync y OneDrive

Después de limpiar los equipos y dispositivos y recuperar los datos, puede volver a habilitar Exchange ActiveSync y la sincronización de OneDrive que deshabilitó anteriormente en el paso [2.](#step-2-disable-exchange-activesync-and-onedrive-sync)

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>Paso 8 (opcional): Bloquear la sincronización de OneDrive para extensiones de archivo específicas

Después de haber recuperado, puede impedir que los clientes de OneDrive para la Empresa sincronicen los tipos de archivo que se vieron afectados por este ransomware. Para obtener más información, [vea Set-SPOTenantSyncClientRestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>Informar del ataque

### <a name="contact-law-enforcement"></a>Ponerse en contacto con las fuerzas del orden

Debe ponerse en contacto con los organismos de seguridad locales o federales. Por ejemplo, si se encuentra en Estados Unidos, puede ponerse en contacto con la oficina de campo local de [THEBL,](https://www.fbi.gov/contact-us/field) [IC3](http://www.ic3.gov/complaint/default.aspx) o [el Servicio secreto.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>Enviar un informe al sitio web de informes de estafas de su país

Los sitios web de informes de estafas proporcionan información sobre cómo evitar y evitar estafas. También proporcionan mecanismos para informar si ha sido víctima de una estafa.

- Australia: [SCAMwatch](http://www.scamwatch.gov.au/)

- Canadá: [Centro de protección contra el fraude de Canadá](http://www.antifraudcentre-centreantifraude.ca/)

- Francia: [Agence nationale de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- Alemania: [Germanamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- Irlanda: [An Síochána](http://www.garda.ie/)

- Nueva Zelanda: [estafas de asuntos del consumidor](http://www.consumeraffairs.govt.nz/scams)

- Reino Unido: Fraude [de acciones](http://www.actionfraud.police.uk/)

- Estados Unidos: [On Guard Online](http://www.onguardonline.gov/)

Si su país no aparece en la lista, pregúntele a los organismos de seguridad locales o federales.

### <a name="submit-email-messages-to-microsoft"></a>Enviar mensajes de correo electrónico a Microsoft

Puede notificar mensajes de suplantación de identidad que contienen ransomware mediante uno de varios métodos. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="see-also"></a>Vea también

- [Ransomware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Respuesta ransomware: ¿pagar o no pagar?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [El norsk Despón responde al ataque de ransomware con transparencia](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [Detección de ransomware y recuperación de archivos en OneDrive](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Informe de inteligencia de seguridad de Microsoft](https://www.microsoft.com/securityinsights/)

- [Habilitar o deshabilitar macros en archivos de Office](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [Configuración recomendada para EOP y Microsoft Defender para la seguridad de Office 365](recommended-settings-for-eop-and-office365-atp.md)

- [Una actualización valiosa: la seguridad de última generación en Windows 10 demuestra resistencia frente a ataques de ransomware en 2017](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Sin más, Samas: ¿Qué hay en el modus operandi de este ransomware?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Malware de bloqueo, antimalware para evitarlo](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT julio de 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Las tres cabezas del ransomware Cerberus-like](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Ransomware Troldesh influenciado por (el) código Da Desván](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
