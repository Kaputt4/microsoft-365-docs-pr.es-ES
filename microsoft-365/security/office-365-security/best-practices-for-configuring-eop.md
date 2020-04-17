---
title: Procedimientos recomendados para configurar EOP y Office 365 ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas.
ms.openlocfilehash: 9bddb736d41b4fd56790b8bbe9dbb00d07e75553
ms.sourcegitcommit: 9ed3283dd6dd959faeca5c22613f9126261b9590
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "43528622"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp"></a>Procedimientos recomendados para configurar EOP y Office 365 ATP

Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.

## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si la organización cuenta con cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizar esas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configuración recomendada

Habilitamos a los administradores de seguridad para que personalicen la configuración de seguridad para satisfacer las necesidades de su organización. Aunque, como regla general, hay dos niveles de seguridad en EOP y Office 365 ATP que se recomiendan: estándar y estricta. Esta configuración se muestra en la [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md).

### <a name="miscellaneousnon-policy-settings"></a>Configuraciones varias/sin directivas

Esta configuración cubre una variedad de características que se encuentran fuera de las directivas de seguridad.

|Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|[Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sí|Sí||
|[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)|Sí|Sí||
|[Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)|Sí|Sí|Use Action = Quarantine para Standard y Action = Reject para STRICT.|
|Implementar el complemento de mensajes de informe para mejorar los informes de usuarios finales de correos sospechosos|Sí|Sí||
|Programar informes de malware y correo no deseado|Sí|Sí||
|No se debe permitir ni supervisar el reenvío automático a dominios externos|Sí|Sí||
|La auditoría unificada debe estar habilitada|Sí|Sí||
|[Conectividad IMAP a buzón de correo](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|[Conectividad POP al buzón de correo](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)|Deshabilitado|Deshabilitado||
|Envío autenticado mediante SMTP al buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad de EWS al buzón de correo|Deshabilitado|Deshabilitado||
|[Conectividad de PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)|Deshabilitado|Deshabilitado|Disponible para usuarios de buzones de correo o usuarios de correo (objetos de usuario devueltos por el cmdlet [Get-User](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-user) ).|
|Usar [inteligencia simulada](learn-about-spoof-intelligence.md) para los remitentes de listas blancas siempre que sea posible|Sí|Sí||
|Bloqueo perimetral basado en directorios (DBEB)|Habilitado|Habilitado|Tipo de dominio = autoritario|
|[Configurar la autenticación multifactor para todas las cuentas de administrador](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||

## <a name="troubleshooting"></a>Solución de problemas

Solucionar problemas generales y tendencias mediante el uso de los informes del centro de administración. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Obtenga más información sobre la herramienta de seguimiento de mensajes en [el seguimiento de mensajes en el centro de seguridad & cumplimiento](message-trace-scc.md).

## <a name="report-false-positive-and-false-negatives-to-microsoft"></a>Informar sobre falsos positivos y falsos negativos a Microsoft

Para ayudar a mejorar el filtrado de correo no deseado en el servicio para todos los usuarios, debe informar de falsos positivos (correo electrónico bueno marcado como incorrecto) y falsos negativos (se permite correo electrónico incorrecto) a Microsoft para su análisis. Para obtener más información, vea [informar de mensajes y archivos a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo o filtros personalizados para satisfacer las necesidades de su empresa.

Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.

Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción.

En entornos híbridos donde la organización incluya tanto Exchange como Office 365, tenga en cuenta las condiciones que se usan en las reglas de flujo de correo. Si desea que las reglas se apliquen a toda la organización, asegúrese de usar las condiciones que están disponibles en Exchange local y en Office 365. Aunque la mayoría de las condiciones están disponibles en ambos entornos, hay algunas que solo están disponibles en un entorno o en la otra. Obtenga más información en [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
