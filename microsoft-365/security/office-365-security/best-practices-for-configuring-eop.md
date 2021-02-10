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
description: Siga estos procedimientos recomendados para Exchange Online Protection (EOP) independiente con el fin de configurarse para el éxito y evitar errores de configuración comunes.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1a38454ceaba7f95dff172335dc374530efca20a
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165936"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Procedimientos recomendados para configurar EOP independiente

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
-  [Exchange Online Protection independiente](https://go.microsoft.com/fwlink/?linkid=2148611)

Siga estos procedimientos recomendados para Exchange Online Protection (EOP) independiente con el fin de configurarse para el éxito y evitar errores de configuración comunes. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.

## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si su organización tiene cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizar esas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configuración recomendada

Los administradores de seguridad pueden personalizar su configuración de seguridad para satisfacer las necesidades de su organización. Aunque, como regla general, hay dos niveles de seguridad en EOP y Microsoft Defender para Office 365 que recomendamos: Estándar y Estricto. Estas opciones se enumeran en la [configuración recomendada para EOP y Microsoft Defender para la seguridad de Office 365.](recommended-settings-for-eop-and-office365-atp.md)

### <a name="miscellaneousnon-policy-settings"></a>Configuración de varios o no directivas

Estas opciones de configuración cubren una serie de características que están fuera de las directivas de seguridad.

****

|Nombre de la característica de seguridad|Estándar|Estricto|Comentario|
|---|---|---|---|
|[Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sí|Sí||
|[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)|Sí|Sí||
|[Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)|Sí|Sí|Se `action=quarantine` usa para Standard y `action=reject` Strict.|
|Implementar el complemento de mensaje [](enable-the-report-phish-add-in.md) de informe [o](enable-the-report-message-add-in.md) el complemento de suplantación de identidad de informe para mejorar los informes de correo electrónico sospechoso para el usuario final|Sí|Sí||
|Programar informes de malware y correo no deseado|Sí|Sí||
|El reenvío automático a dominios externos debe no estar permitido o supervisarse|Sí|Sí||
|Se debe habilitar la auditoría unificada|Sí|Sí||
|[Conectividad IMAP al buzón](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|[Conectividad POP al buzón](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|Envío SMTP autenticado|Deshabilitado|Deshabilitado|El envío SMTP del cliente autenticado (también conocido como envío SMTP de cliente o AUTENTICACIÓN SMTP) es necesario para que los clientes POP3 e IMAP4 envíen correo electrónico.|
|Conectividad de EWS al buzón|Deshabilitado|Deshabilitado||
|[Conectividad de PowerShell](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)|Deshabilitado|Deshabilitado|Disponible para usuarios de buzones de correo o usuarios de correo (objetos de usuario devueltos por el cmdlet [Get-User).](https://docs.microsoft.com/powershell/module/exchange/get-user)|
|Usar [inteligencia de suplantación](learn-about-spoof-intelligence.md) de identidad para agregar remitentes a la lista de permitidos|Sí|Sí||
|[Bloqueo perimetral basado en directorios (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Habilitado|Habilitado|Tipo de dominio = autoritativo|
|[Configurar la autenticación multifactor para todas las cuentas de administrador](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||
|

## <a name="troubleshooting"></a>Solución de problemas

Solucionar problemas generales y tendencias con los informes del centro de administración. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Obtenga más información sobre la herramienta de seguimiento de mensajes en seguimiento de mensajes en el [Centro de & cumplimiento.](message-trace-scc.md)

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Notificar falsos positivos y falsos negativos a Microsoft

Para ayudar a mejorar el filtrado de correo no deseado en el servicio para todos los usuarios, debe informar a Microsoft de falsos positivos (correo electrónico bueno marcado como negativo) y falsos negativos (correo electrónico no deseado permitido) para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo (también conocidas como reglas de transporte) o filtros personalizados para satisfacer sus necesidades empresariales.

Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.

Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción.

En entornos híbridos en los que su organización incluye Exchange local y Exchange Online, tenga en cuenta las condiciones que se usan en las reglas de flujo de correo. Si desea que las reglas se apliquen a toda la organización, asegúrese de usar condiciones disponibles tanto en Exchange local como en Exchange Online. Aunque la mayoría de las condiciones están disponibles en ambos entornos, hay algunas que solo están disponibles en un entorno u otro. Obtenga más información [en Reglas de flujo de correo (reglas de transporte) en Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
