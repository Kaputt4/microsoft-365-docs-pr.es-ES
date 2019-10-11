---
title: Solución de problemas e información de soporte técnico
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
ms.assetid: 5d9f75f5-bb7f-458c-ad30-5c8eae0b0e4e
ms.collection:
- M365-security-compliance
description: En este tema se describen pasos de solución de problemas para usuarios finales y administradores, y se proporciona información acerca de cómo ponerse en contacto con el soporte técnico para obtener ayuda.
ms.openlocfilehash: c87744608930603f70e6be1132a0b405e9646b57
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441197"
---
# <a name="troubleshooting-and-support-information"></a>Solución de problemas e información de soporte técnico

En este tema se describen pasos de solución de problemas para usuarios finales y administradores, y se proporciona información acerca de cómo ponerse en contacto con el soporte técnico para obtener ayuda.

## <a name="troubleshooting-for-users"></a>Solución de problemas para usuarios

En ocasiones, puede experimentar problemas con Microsoft Outlook después de agregar el complemento de notificación de correo no deseado. A continuación, se enumeran los problemas que puede experimentar, junto con las sugerencias correspondientes para resolverlos.

- Al hacer clic en **Informar de correo electrónico no deseado**, no ocurre ninguna acción.

- Outlook deja de responder después de seleccionar un mensaje de correo electrónico.

- El correo no deseado notificado no se puede entregar debido a una respuesta de "no se puede entregar".

Para solucionar este problema, siga estos pasos:

1. Cierre y reinicie Outlook.

2. Compruebe que puede crear y enviar un mensaje de prueba. Para ello, puede enviar un mensaje de prueba a otra cuenta de correo electrónico y, a continuación, comprobar si se recibe el mensaje.

Si el problema continúa, póngase en contacto con el administrador.

> [!TIP]
> También puede enviar mensajes de correo no deseado directamente a Microsoft a la dirección de correo electrónico [junk@office365.microsoft.com](mailto:junk@office365.microsoft.com), y mensajes falsos positivos a la dirección de correo electrónico [not_junk@office365.microsoft.com](mailto: not_junk@office365.microsoft.com). Para obtener más información, vea enviar correo electrónico no deseado, mensajes de correo [no deseado y mensajes de estafa de suplantación de identidad a Microsoft para su análisis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).

## <a name="troubleshooting-for-administrators"></a>Solución de problemas para administradores

Como administrador, puede experimentar problemas con los usuarios que usan el complemento de notificación de correo no deseado para Outlook. A continuación hay algunos pasos para resolver problemas que pueda encontrar.

### <a name="problem-an-error-message-asking-users-to-contact-their-system-administrator-continually-appears"></a>Problema: un mensaje de error que pide a los usuarios que se pongan en contacto con el administrador del sistema aparece continuamente

1. Establezca el valor de la clave del Registro siguiente en "Verbose":

   - **32 bit de Outlook instalado en un sistema operativo de 32 bits**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **32 bit de Outlook instalado en un sistema operativo de 64 bits**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

   - **Outlook de 64 bits (siempre instalado en un sistema operativo de 64 bits)**:

     `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Junk Email Reporting\Addins\LoggingLevel`

2. Reinicie Outlook y pida a los usuarios que informen de nuevo cuando vean el mensaje de error.

3. Recopile la información de registro de la siguiente ubicación:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Póngase en contacto con el soporte técnico de Protección en línea de Exchange y proporcione la información de registro.

### <a name="problem-users-choose-not-to-receive-a-confirmation-when-they-submit-an-email-as-junk-and-now-they-want-the-option-back"></a>Problema: los usuarios optan por no recibir una confirmación cuando envían un correo electrónico como correo no deseado y ahora quieren volver a la opción

1. Establezca el valor de la clave del Registro siguiente en " `HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences\ConfirmReportJunk`true":.

2. Reinicie Outlook.

## <a name="support-information"></a>Información de soporte

Si necesita ayuda para instalar, configurar o desinstalar el complemento, póngase en contacto con el soporte técnico mediante el vínculo nueva solicitud de servicio de la página soporte del centro de administración de Microsoft 365. Para obtener opciones adicionales, como el envío de una solicitud de servicio a través de las opciones de teléfono y de autosoporte, consulte [ayuda y soporte técnico para EOP](help-and-support-for-eop.md).

## <a name="for-more-information"></a>Más información

[Habilitar el complemento de mensajes de informe](https://support.office.com/article/4250c4bc-6102-420b-9e0a-a95064837676)

[Informar a Microsoft sobre mensajes de correo electrónico no deseado](report-junk-email-messages-to-microsoft.md)
