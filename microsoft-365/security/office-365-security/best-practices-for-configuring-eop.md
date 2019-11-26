---
title: Procedimientos recomendados para configurar EOP y Office 365 ATP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: faf1efd1-3b0c-411a-804d-17f37292eac0
description: Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas.
ms.openlocfilehash: ccc312d6e3e9954ea38b10ebe9b4c8877a85b925
ms.sourcegitcommit: e292e9f0181d722a11398fbd012bb84589aef052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2019
ms.locfileid: "39257295"
---
# <a name="best-practices-for-configuring-eop"></a>Procedimientos recomendados para configurar EOP

Siga estos procedimientos recomendados para Exchange Online Protection (EOP) con el fin de evitar errores comunes de configuración y prepararse para usar esta característica sin problemas. En este tema se supone que ya completó el proceso de configuración. Si no completó la configuración de EOP, vea [Configurar un servicio de EOP](set-up-your-eop-service.md).

## <a name="use-a-test-domain"></a>Usar un dominio de prueba

Recomendamos usar un dominio, subdominio o dominio de bajo volumen de prueba para probar las características del servicio antes de implementarlas en los dominios de producción de mayor volumen.

## <a name="synchronize-recipients"></a>Sincronizar destinatarios

Si la organización cuenta con cuentas de usuario existentes en un entorno local de Active Directory, puede sincronizar esas cuentas con Azure Active Directory en la nube. Se recomienda usar la sincronización de directorios. Para más información sobre los beneficios de usar la sincronización de directorios y los pasos para configurarla, vea [Administrar usuarios de correo en EOP](manage-mail-users-in-eop.md).

## <a name="recommended-settings"></a>Configuración recomendada

Habilitamos a los administradores de seguridad para personalizar la configuración de seguridad que satistfy las necesidades de sus entornos. Aunque, como regla general, hay dos niveles de seguridad en EOP y Office 365 ATP que se recomiendan: estándar y estricta. Esta configuración se muestra en la [configuración recomendada para EOP y Office 365 ATP Security](recommended-settings-for-eop-and-office365-atp.md). 

### <a name="miscellaneousnon-policy-settings"></a>Configuraciones varias/sin directivas

Esta configuración cubre una variedad de características que se encuentran fuera de las directivas de seguridad.

Nombre de la característica de seguridad|Estándar|Estricta|Comentario|
|---------|---------|---------|---------|
|[Configurar SPF en Office 365 para ayudar a evitar la suplantación de identidad](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sí|Sí||
|[Usar DKIM para validar el correo electrónico saliente enviado desde su dominio personalizado en Office 365](use-dkim-to-validate-outbound-email.md)|Sí|Sí||
|[Usar DMARC para validar el correo electrónico en Office 365](use-dmarc-to-validate-email.md)|Sí|Sí|Use Action = Quarantine para Standard y Action = Reject para STRICT.|
|Implementar el complemento de mensajes de informe para mejorar los informes de usuarios finales de correos sospechosos|Sí|Sí||
|Programar informes de malware y correo no deseado|Sí|Sí||
|No se debe permitir ni supervisar el reenvío automático a dominios externos|Sí|Sí||
|La auditoría unificada debe estar habilitada|Sí|Sí||
|Conectividad IMAP a buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad POP al buzón de correo|Deshabilitado|Deshabilitado||
|Envío autenticado mediante SMTP al buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad de EWS al buzón de correo|Deshabilitado|Deshabilitado||
|Conectividad de PowerShell|Deshabilitado|Deshabilitado||
|Usar inteligencia simulada para los remitentes de listas blancas siempre que sea posible|Sí|Sí||
|Bloqueo perimetral basado en directorios (DBEB)|Habilitado|Habilitado|Tipo de dominio = autoritario|
|[Configurar la autenticación multifactor para todas las cuentas de administrador](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Habilitado|Habilitado||

## <a name="troubleshooting"></a>Solución de problemas

Solucionar problemas generales y tendencias mediante el uso de los informes del centro de administración. Para encontrar datos específicos en un punto único sobre un mensaje, use la herramienta de seguimiento de mensajes. Para más información sobre informes, vea [Informes y seguimiento de mensajes en Exchange Online Protection](reporting-and-message-trace-in-exchange-online-protection.md). Para más información sobre la herramienta de seguimiento de mensajes, vea [Trace an Email Message](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/trace-an-email-message).

## <a name="reporting-false-positive-and-false-negatives-to-microsoft"></a>Informar sobre falsos positivos y falsos negativos a Microsoft

Los administradores deben enviar falsos negativos (correo no deseado) y falsos positivos (correo no deseado) a Microsoft a través de nuestro portal de envíos de administración. Los correos electrónicos, archivos y direcciones URL pueden enviarse para ayudar a los administradores a determinar por qué nosotros entregamos o no entregamos mensajes a los usuarios finales. Para obtener más información, consulte [Cómo enviar sospechoso correo no deseado, phish, direcciones URL y archivos a Microsoft para el análisis de Office 365](admin-submission.md).

Los usuarios finales también pueden informar directamente de falsos negativos (correo no deseado) y falsos positivos (correo no deseado) a Microsoft para su análisis cuando no están de acuerdo con los veredictos dados. Para obtener más información, consulte [Enviar correo electrónico no deseado, mensajes sin correo no deseado y mensajes de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).


## <a name="create-mail-flow-rules"></a>Crear reglas de flujo de correo

Cree reglas de flujo de correo o filtros personalizados para satisfacer las necesidades de su empresa.

Al implementar una regla nueva en producción, seleccione primero uno de los modos de prueba para ver su efecto. Cuando tenga la seguridad de que la regla funciona como se espera, cambie el modo de la regla a **Exigir**.

Al implementar reglas nuevas, considere la posibilidad de agregar la acción adicional de **Generar informe de incidentes** para supervisar la regla en acción.

En entornos híbridos donde la organización incluya tanto Exchange como Office 365, tenga en cuenta las condiciones que se usan en las reglas de flujo de correo. Si desea que las reglas se apliquen a toda la organización, asegúrese de usar las condiciones que están disponibles en Exchange local y en Office 365. Aunque la mayoría de las condiciones están disponibles en ambos entornos, hay algunas que solo están disponibles en un entorno o en la otra. Obtenga más información en [reglas de flujo de correo (reglas de transporte) en Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).


