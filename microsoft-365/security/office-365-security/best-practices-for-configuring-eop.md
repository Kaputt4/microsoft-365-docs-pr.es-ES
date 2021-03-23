---
title: Procedimientos recomendados para configurar EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estas recomendaciones de procedimiento recomendado para Exchange Online Protection (EOP) independiente para configurarse correctamente y evitar errores de configuración comunes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e968316e23fe2d8e68795318f8e0785a662c8aea
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994563"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Procedimientos recomendados para configurar EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](exchange-online-protection-overview.md)

Siga estas recomendaciones de procedimiento recomendado para Exchange Online Protection (EOP) independiente para configurarse correctamente y evitar errores de configuración comunes. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.

## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si su organización tiene cuentas de usuario existentes en un entorno de Active Directory local, puede sincronizar esas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configuración recomendada

Ofrecemos a los administradores de seguridad la capacidad de personalizar su configuración de seguridad para satisfacer las necesidades de su organización. Aunque, como regla general, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que recomendamos: Estándar y Estricto. Esta configuración se muestra en [la configuración recomendada para EOP y Microsoft Defender para la seguridad de Office 365](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Configuración de varios o no directivas

Esta configuración cubre una serie de características que están fuera de las directivas de seguridad.

<br>

****

|Nombre de la característica de seguridad|Estándar|Estricto|Comentario|
|---|---|---|---|
|[Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sí|Sí||
|[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)|Sí|Sí||
|[Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)|Sí|Sí|Use `action=quarantine` para Standard y Para `action=reject` Strict.|
|Implementar el [complemento Mensaje de informe o](enable-the-report-message-add-in.md) el complemento [Detección](enable-the-report-phish-add-in.md) de suplantación de identidad de informes para mejorar los informes de usuario final de correo electrónico sospechoso|Sí|Sí||
|Programar informes de malware y correo no deseado|Sí|Sí||
|El reenvío automático a dominios externos debe no estar permitido o supervisarse|Sí|Sí||
|La auditoría unificada debe estar habilitada|Sí|Sí||
|[Conectividad IMAP al buzón](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|[Conectividad POP al buzón](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|Envío SMTP autenticado|Deshabilitado|Deshabilitado|El envío SMTP de cliente autenticado (también conocido como envío SMTP de cliente o AUTH SMTP) es necesario para clientes POP3 e IMAP4 y aplicaciones y dispositivos que generan y envían correo electrónico. <p> Para obtener instrucciones para habilitar y deshabilitar LA AUTENTICACIÓN SMTP de forma global o selectiva, vea Habilitar o deshabilitar el envío SMTP de [cliente autenticado en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/authenticated-client-smtp-submission).|
|Conectividad de EWS al buzón|Deshabilitado|Deshabilitado|Outlook usa Exchange Web Services para la disponibilidad, la configuración fuera de la oficina y el uso compartido de calendarios. Si no puede deshabilitar EWS globalmente, tiene las siguientes opciones: <ul><li>Use [directivas de autenticación](/exchange/clients-and-mobile-in-exchange-online/disable-basic-authentication-in-exchange-online) para evitar que EWS use la autenticación básica si sus clientes admiten la autenticación moderna (autenticación moderna).</li><li>Use [reglas de acceso de cliente](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules) para limitar EWS a usuarios específicos o direcciones IP de origen.</li><li>Controlar el acceso de EWS a aplicaciones específicas globalmente o por usuario. Para obtener instrucciones, vea [Control access to EWS in Exchange](/exchange/client-developer/exchange-web-services/how-to-control-access-to-ews-in-exchange).</li></ul> <p> El [complemento Report message y](enable-the-report-message-add-in.md) report [phishing add-in](enable-the-report-phish-add-in.md) usa REST de forma predeterminada en entornos compatibles, pero volverá a EWS si REST no está disponible. Los entornos compatibles que usan REST son:<ul><li>Exchange en línea</li><li>Exchange 2019 o Exchange 2016</li><li>Outlook actual para Windows desde una suscripción de Microsoft 365 o una compra única de Outlook 2019.</li><li>Outlook actual para Mac desde una suscripción de Microsoft 365 o una compra única de Outlook para Mac 2016 o posterior.</li><li>Outlook para iOS y Android</li><li>Outlook en la Web</li></ul>|
|[Conectividad de PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)|Deshabilitado|Deshabilitado|Disponible para usuarios de buzones o usuarios de correo (objetos de usuario devueltos por el cmdlet [Get-User).](/powershell/module/exchange/get-user)|
|Usar [la inteligencia de suplantación](learn-about-spoof-intelligence.md) de identidad para agregar remitentes a la lista de permitidos|Sí|Sí||
|[Bloqueo perimetral basado en directorios (DBEB)](/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Habilitado|Habilitado|Tipo de dominio = Autoritativo|
|[Configurar la autenticación multifactor para todas las cuentas de administración](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)|Habilitado|Habilitado||
|

## <a name="troubleshooting"></a>Solución de problemas

Solucionar problemas generales y tendencias mediante los informes del Centro de administración. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Obtenga más información sobre la herramienta de seguimiento de mensajes en Seguimiento de mensajes en [el Centro de seguridad & cumplimiento](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Notificar falsos positivos y falsos negativos a Microsoft

Para ayudar a mejorar el filtrado de correo no deseado en el servicio para todos, debe informar a Microsoft de falsos positivos (correo electrónico bueno marcado como malo) y falsos negativos (correo electrónico no permitido) para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo (también conocidas como reglas de transporte) o filtros personalizados para satisfacer sus necesidades empresariales.

Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.

Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción.

En entornos híbridos donde su organización incluye Exchange local y Exchange Online, tenga en cuenta las condiciones que se usan en las reglas de flujo de correo. Si desea que las reglas se apliquen a toda la organización, asegúrese de usar condiciones disponibles tanto en Exchange local como en Exchange Online. Aunque la mayoría de las condiciones están disponibles en ambos entornos, hay algunas que solo están disponibles en un entorno u otro. Obtenga más información en Reglas de flujo de correo [(reglas de transporte) en Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).