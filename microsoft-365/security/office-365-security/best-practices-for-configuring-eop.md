---
title: Procedimientos recomendados para configurar EOP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estas recomendaciones de procedimientos recomendados para la protección independiente de Exchange Online (EOP) con el fin de establecer el éxito y evitar errores de configuración habituales.
ms.openlocfilehash: 69b0789612d6490305ff31d89954bc1d9258ac01
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587539"
---
# <a name="best-practices-for-configuring-standalone-eop"></a>Procedimientos recomendados para configurar EOP independiente

Siga estas recomendaciones de procedimientos recomendados para la protección independiente de Exchange Online (EOP) con el fin de establecer el éxito y evitar errores de configuración habituales. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.

## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si la organización cuenta con cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizar esas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configuración recomendada

Habilitamos a los administradores de seguridad para que personalicen la configuración de seguridad para satisfacer las necesidades de su organización. Aunque, como regla general, hay dos niveles de seguridad en EOP y Office 365 ATP que se recomiendan: estándar y estricta. Esta configuración se muestra en la [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Configuraciones varias/sin directivas

Esta configuración cubre una variedad de características que se encuentran fuera de las directivas de seguridad.

|||||
|---|---|---|---|
|**Nombre de la característica de seguridad**|**Estándar**|**Estricta**|**Comment**|
|[Configurar SPF para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sí|Sí||
|[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)|Sí|Sí||
|[Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)|Sí|Sí|Se usa `action=quarantine` para Standard y `action=reject` para STRICT.|
|Implementar el [complemento de mensajes de informe](enable-the-report-message-add-in.md) para mejorar los informes de usuarios finales de correo electrónico sospechoso|Sí|Sí||
|Programar informes de malware y correo no deseado|Sí|Sí||
|No se debe permitir ni supervisar el reenvío automático a dominios externos|Sí|Sí||
|La auditoría unificada debe estar habilitada|Sí|Sí||
|[Conectividad IMAP a buzón de correo](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|[Conectividad POP al buzón de correo](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|Envío SMTP autenticado|Deshabilitado|Deshabilitado|El envío SMTP de cliente autenticado (también conocido como envío SMTP de cliente o autenticación SMTP) es necesario para que los clientes POP3 e IMAP4 puedan enviar correo electrónico.|
|Conectividad de EWS al buzón de correo|Deshabilitado|Deshabilitado||
|[Conectividad de PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Deshabilitado|Deshabilitado|Disponible para usuarios de buzones de correo o usuarios de correo (objetos de usuario devueltos por el cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/get-user) ).|
|Usar [inteligencia simulada](learn-about-spoof-intelligence.md) para los remitentes de listas blancas siempre que sea posible|Sí|Sí||
|[Bloqueo perimetral basado en directorios (DBEB)](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-directory-based-edge-blocking)|Habilitado|Habilitado|Tipo de dominio = autoritario|
|[Configurar la autenticación multifactor para todas las cuentas de administrador](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||
|

## <a name="troubleshooting"></a>Solución de problemas

Solucionar problemas generales y tendencias mediante el uso de los informes del centro de administración. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Obtenga más información sobre la herramienta de seguimiento de mensajes en [el seguimiento de mensajes en el centro de seguridad & cumplimiento](message-trace-scc.md).

## <a name="report-false-positives-and-false-negatives-to-microsoft"></a>Informar sobre falsos positivos y falsos negativos a Microsoft

Para ayudar a mejorar el filtrado de correo no deseado en el servicio para todos los usuarios, debe informar de falsos positivos (correo electrónico bueno marcado como incorrecto) y falsos negativos (se permite correo electrónico incorrecto) a Microsoft para su análisis. Para obtener más información, consulte [Notificar mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo (también conocidas como reglas de transporte) o filtros personalizados para satisfacer las necesidades de su empresa.

Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.

Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción.

En entornos híbridos donde la organización incluya Exchange local y Exchange Online, tenga en cuenta las condiciones que se usan en las reglas de flujo de correo. Si desea que las reglas se apliquen a toda la organización, asegúrese de usar las condiciones que están disponibles en Exchange local y en Exchange Online. Aunque la mayoría de las condiciones están disponibles en ambos entornos, hay algunas que solo están disponibles en un entorno o en la otra. Obtenga más información en [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
