---
title: Cómo evitar los falsos positivos en Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Aprenda cómo evitar los falsos positivos y evite que correos electrónicos reales sean marcados como correo no deseado en Office 365, Exchange Online y Exchange Online Protection (EOP).
ms.openlocfilehash: 483bad168aa421e3fba4b0cc51e0b2e286f5701d
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2019
ms.locfileid: "40809410"
---
# <a name="how-to-prevent-good-email-messages-from-being-marked-as-spam-in-office-365"></a>Cómo evitar que los mensajes de correo electrónico adecuados se marquen como correo no deseado en Office 365

 **¿Se está marcando el correo electrónico real como correo no deseado en Office 365? Siga este procedimiento.**

Si un mensaje de correo electrónico entrante está marcado como correo no deseado (_falso positivo_) en Office 365, Exchange Online o Exchange Online Protection (EOP), debe informar del mensaje a Microsoft mediante el [Uso del complemento de mensajes de informe](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2). Asimismo, puede enviar el mensaje mediante el [explorador de envíos](admin-submission.md).

## <a name="determine-why-the-message-was-marked-as-spam"></a>Determinar el motivo por el que un mensaje se marcó como correo no deseado

Para resolver problemas con falsos positivos, puede ver el encabezado del mensaje de correo electrónico para determinar por qué el mensaje se marcó como correo no deseado. Para ver el encabezado del mensaje, consulte [Ver los encabezados de mensajes de Internet en Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

En concreto, tiene que buscar un campo de encabezado denominado **X-Forefront-Antispam-Report**. Los valores importantes que debe buscar son:

- **SFV:SPM**: el mensaje se marcó como correo no deseado por el filtro de correo no deseado (también conocido como _filtro de contenido_). Para obtener más información, consulte [Protección del correo electrónico de Office 365 contra correo no deseado](anti-spam-protection.md).

- **SFV:BLK**: el mensaje se marcó como correo no deseado porque la dirección de correo electrónico del remitente se encuentra en la lista de **remitentes** bloqueados del destinatario. Para obtener más información, consulte [filtrar correo no deseado en Outlook en la Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) e [información general sobre el filtro de correo no deseado](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089).

- **SFV:SKS**: el mensaje se marcó como correo electrónico no deseado **antes** de que pudiera ser examinado por el filtro correo no deseado. Por ejemplo, una regla de flujo de correo (también denominada regla de transporte) define el nivel de confianza de correo no deseado (SCL) del mensaje en un valor alto (9) que indica que el mensaje era de correo no deseado. Para obtener más información sobre el SCL, consulte [niveles de confianza del correo no deseado](spam-confidence-levels.md).

  Ejecutar un seguimiento de mensajes para ver si una regla de flujo de correo es la responsable del valor SCL alto. Para obtener más información, consulte [seguimiento de mensajes en el centro de cumplimiento y de seguridad](message-trace-scc.md).

- **SFV:SKB**: el mensaje se marcó como correo no deseado porque coincidía con una entrada de bloque en una directiva de filtro de correo no deseado (por ejemplo, remitentes bloqueados o dominios bloqueados de remitentes). Para obtener más información, consulte [Configure sus políticas de filtro de correo no deseado](configure-your-spam-filter-policies.md).

- **SFV:BULK**: el filtro de correo no deseado identificó el mensaje como correo electrónico masivo en lugar de correo no deseado. Esto sucede cuando el valor del nivel de queja masiva (BCL) del mensaje es **mayor que** el umbral masivo definido en la configuración de la Directiva contra correo no deseado (un valor de BCL inferior indica que el mensaje es más probable que sea correo no deseado). Puede ver el valor BCL en el campo de encabezado **X-Microsoft-Antispam**.

  El correo electrónico masivo (también conocido como _correo gris_) es un correo electrónico de marketing o publicidad indeseable pero no malicioso que fue solicitado intencionalmente o no por el usuario. Cada usuario tiene distintas expectativas sobre cómo se debe administrar el correo electrónico masivo, por lo que puede crear directivas o reglas diferentes que permitan o bloqueen correo electrónico masivo en consecuencia. Para obtener más información, vea los siguientes temas:

  - [¿Cuál es la diferencia entre correo electrónico no deseado y correo electrónico masivo?](what-s-the-difference-between-junk-email-and-bulk-email.md)

  - [Valores de nivel de queja de correo masivo](bulk-complaint-level-values.md)

- **CAT:SPOOF** o **CAT:PHISH**: Indican que el ﻿mensaje parece suplantado, lo que significa que el origen del mensaje no se puede validar y podría ser sospechoso.

  Si el mensaje proviene de un remitente falso, el correspondiente remitente legítimo tendrá que comprobar los registros SPF y DKIM del dominio de correo electrónico en su DNS público. Para obtener más información, consulte el campo de encabezado **Resultados de autenticación**. Aunque puede resultar complicado conseguir que todos los remitentes usen métodos de autenticación de correo electrónico adecuados, omitir estas comprobaciones puede ser muy peligroso y es una de las principales causas de amenazas y suplantación de identidad.

> [!NOTE]
> • Para obtener más información sobre otros encabezados y valores de mensajes de correo no deseado, consulte [Encabezados de mensajes de correo no deseado](anti-spam-message-headers.md). <br/><br/>• Otros valores y campos de encabezado que no se hayan descrito específicamente se usan exclusivamente por el equipo de correo no deseado de Microsoft para propósitos de diagnóstico. <br/><br/>• Un campo de encabezado **X-CustomSpam** en el encabezado del mensaje indica que el mensaje se marcó como correo no deseado por el filtro de correo no deseado avanzado (ASF). Estamos en el proceso de mover la funcionalidad de ASF a otras partes de la pila de filtrado y le recomendamos **desactivar** la configuración de ASF que está disponible actualmente en las directivas de correo no deseado. Para obtener más información, consulte [opciones avanzadas de filtrado de correo no deseado](advanced-spam-filtering-asf-options.md).

## <a name="solutions-for-too-much-spam"></a>Soluciones para demasiado correo no deseado

Para que el filtrado de correo no deseado sea el más eficaz, un administrador debe configurar algunas opciones en la organización. Si no es administrador, puede ir directamente a la sección usuarios.

### <a name="for-admins"></a>Para administradores

- **Apunte el registro MX del dominio de correo electrónico a Office 365**: para que Office 365 pueda ofrecer protección, el registro MX para todos los dominios de correo electrónico en Office 365 debe apuntar a Office 365, y solo a Office 365 (es decir, el correo electrónico para los destinatarios en esos dominios siempre se entrega primero a Office 365). Si el registro MX apunta a alguna otra ubicación (por ejemplo, una solución o dispositivo de correo no deseado de terceros), Office 365 no puede proporcionar filtrado de correo no deseado para sus usuarios. En este escenario, considere la posibilidad de crear una regla de flujo de correo para omitir el filtrado de correo no deseado para todos los mensajes (establecer el valor SCL de todos los mensajes entrantes en -1). Si, posteriormente, decide apuntar el registro MX a Office 365 en primer lugar, asegúrese de quitar la regla.

- **Activar el complemento de mensaje para los usuarios**: le recomendamos encarecidamente que habilite el complemento de mensajes de informe para sus usuarios. Para obtener instrucciones, consulte [Habilitar el complemento de mensajes de informe](enable-the-report-message-add-in.md).

- **Usar el explorador de envíos**: los administradores ahora pueden enviar mensajes de correo electrónico para que Microsoft los analice. Como administrador, es posible que también pueda ver los comentarios que han enviado los usuarios. Puede usar patrones en sus informes de falsos positivos para ajustar la configuración de filtrado de correo no deseado. Para obtener más información, consulte [Cómo enviar correo no deseado sospechoso, suplantar identidad, URL y archivos a Microsoft para escanear Office 365](admin-submission.md).

- **Compruebe que los usuarios se encuentran dentro de los límites autorizados**, tal y como se describe en [límites de envío y recepción](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) en la descripción del servicio Exchange Online.

- **Compruebe que los niveles de BCL de las directivas de correo no deseado** se han descrito anteriormente en este tema.

### <a name="for-users"></a>Para los usuarios

- **Agregue el remitente a la lista de remitentes seguros** en [Outlook](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) o [Outlook en la Web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d).

  Office 365 utilizará la lista de remitentes seguros y la lista de destinatarios seguros, pero no la lista de dominios seguros. Esto es válido independientemente de cómo agregue el dominio a la lista (en Outlook, en Outlook en la Web o en Outlook y, a continuación, se sincroniza por la sincronización de directorio).

- **Deshabilitar el filtrado SmartScreen en Outlook**: en los clientes antiguos de escritorio de Outlook, no habilite el filtro SmartScreen en las **opciones de correo electrónico no deseado**. Las actualizaciones al filtrado SmartScreen finalizaron en noviembre de 2016. Si habilita la protección contra correo electrónico no deseado en **baja** o **alta** en Outlook, usará el filtrado SmartScreen y podría obtener falsos positivos. Tenga en cuenta que el filtrado SmartScreen no está disponible en los clientes modernos de escritorio de Outlook. Para obtener más información, consulte la [compatibilidad para SmartScreen en Outlook y Exchange](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/Deprecating-support-for-SmartScreen-in-Outlook-and-Exchange/ba-p/605332).

## <a name="troubleshooting-a-message-is-delivered-to-the-junk-email-folder-after-passing-anti-spam-filtering"></a>Solución de problemas: se entrega un mensaje a la carpeta correo no deseado tras pasar el filtrado de correo no deseado

Si un usuario tiene seleccionada la opción **solo listas seguras** en las opciones de correo electrónico no deseado de Outlook, todos los mensajes de las personas que no están en la lista de remitentes seguros del usuario o en la lista de destinatarios seguros irán a su carpeta de **correo electrónico no deseado**, independientemente de si el mensaje ha pasado el filtrado de correo no deseado de la organización, o si una regla de flujo de correo marcó el mensaje como no es correo no deseado (un valor SCL de -1).

En Outlook en la Web, el destinatario verá una sugerencia de seguridad amarilla que indica que el mensaje está en la carpeta **correo electrónico no deseado** porque el remitente no se encuentra en la lista de remitentes seguros o en la lista de destinatarios seguros.

El encabezado del mensaje incluirá el valor del campo de encabezado **X-Forefront-Antispam-Report** `SFV:SKN` (el mensaje fue marcado como no es correo no deseado antes de ser procesado por el filtro de correo no deseado) o `SFV:NSPM` (el filtro de correo no deseado determinó que el mensaje no era correo no deseado), pero el mensaje aún se entrega a la carpeta de **correo no deseado** del usuario.

Nada en el encabezado del mensaje indicará que el mensaje se entregó como basura debido a la configuración de **solo listas seguras**. Pero puede usar el cmdlet **Get-MailboxJunkEmailConfiguration** en Exchange Online PowerShell para ver si un usuario solo permite recibir mensajes de remitentes de confianza en la bandeja de entrada.

Reemplace \<MailboxIdentity\> por el nombre, el alias o la dirección de correo electrónico del buzón y ejecute el siguiente comando en [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```PowerShell
Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List TrustedListsOnly,ContactsTrusted,TrustedSendersAndDomains
```

- Si el valor de la propiedad *TrustedListsOnly* es `True`: los mensajes que no provienen de remitentes o destinatarios de confianza (es decir, las personas que no están en la lista de remitentes seguros del usuario y la lista de destinatarios seguros) irán a su carpeta de **correo no deseado**.

- Si el valor de la propiedad *ContactsTrusted* es `True`: los contactos del usuario también se identifican como remitentes de confianza. Si el valor de la propiedad *TrustedListsOnly* también es `True`, los mensajes de personas que no están en la lista de remitentes seguros, la lista de destinatarios seguros o los contactos del usuario se mostrarán en su carpeta de **correo no deseado**.

- El valor de la propiedad *TrustedSendersAndDomains* contiene la lista de remitentes seguros del usuario.

Para cambiar esta configuración en el buzón, reemplace \<MailboxIdentity\> por el nombre, el alias o la dirección de correo electrónico del buzón y ejecute el siguiente comando:

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" -TrustedListsOnly $false -ContactsTrusted $false
```

Para obtener información detallada sobre la sintaxis, el parámetro y los permisos necesarios, vea los temas [Get-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-mailboxjunkemailconfiguration) y [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration).

## <a name="directory-synchronization-for-standalone-eop-customers"></a>Sincronización de directorios para clientes de EOP independientes

Si usa un EOP independiente para ayudar a proteger su organización de Exchange local, debe sincronizar la configuración de usuario con el servicio con la sincronización de directorios. De esta forma, se asegura de que EOP respeta las listas de remitentes seguros de los usuarios. Para obtener más información, consulte [utilizar la sincronización de directorios para administrar usuarios de correo](manage-mail-users-in-eop.md#use-directory-synchronization-to-manage-mail-users).
