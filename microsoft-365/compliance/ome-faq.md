---
title: Preguntas más frecuentes sobre el cifrado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: ¿Tiene alguna pregunta sobre cómo funcionan las nuevas capacidades de protección de mensajes? Busca una respuesta aquí.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4be3ff4be1d5bf8b81d06ea17a8345e4c843b150
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058543"
---
# <a name="message-encryption-faq"></a>Preguntas más frecuentes sobre el cifrado de mensajes

¿Tiene alguna pregunta sobre cómo funcionan las nuevas capacidades de protección de mensajes? Busca una respuesta aquí. Además, echa un vistazo a las preguntas más frecuentes sobre la protección de datos en [Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) para obtener respuestas a preguntas sobre el servicio de protección de datos, Azure Rights Management, en Azure Information Protection.

## <a name="what-is-office-365-message-encryption-ome"></a>¿Qué es el cifrado de mensajes de Office 365 (OME)?

OME combina el cifrado de correo electrónico y las capacidades de administración de derechos. Las funcionalidades de administración de derechos funcionan con Azure Information Protection.

## <a name="who-can-use-ome"></a>¿Quién puede usar OME?

Puede usar las nuevas funcionalidades para OME en las siguientes condiciones:
  
- Si nunca ha configurado OME o IRM para Exchange Online en Office 365.

- Si ha configurado OME e IRM, puede seguir estos pasos si usa el servicio Azure Rights Management desde Azure Information Protection.

- Si usa Exchange Online con el servicio Active Directory Rights Management (AD RMS), no puede habilitar estas nuevas funcionalidades de inmediato. En su lugar, primero [debe migrar AD RMS a Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Cuando haya terminado la migración, puede configurar correctamente OME.

  Si decide seguir usando AD RMS local con Exchange Online en lugar de migrar a Azure Information Protection, no podrá usar estas nuevas funcionalidades.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>¿Qué suscripciones necesito para usar las nuevas funcionalidades de OME?

Para usar las nuevas funcionalidades de OME, necesita uno de los siguientes planes:
  
- El cifrado de mensajes de Office 365 se ofrece como parte de Office 365 Enterprise E3 y E5, Microsoft Enterprise E3 y E5, Microsoft 365 Empresa Premium, Office 365 A1, A3 y A5, y Office 365 Administración Pública G3 y G5. Los clientes no necesitan licencias adicionales para recibir las nuevas funcionalidades de protección con tecnología de Azure Information Protection.

- También puede agregar Azure Information Protection Plan 1 a los siguientes planes para recibir las nuevas capacidades de cifrado de mensajes de Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Empresa Basic, Microsoft 365 Empresa Standard u Office 365 Enterprise E1.

- Cada usuario que se beneficie del cifrado de mensajes de Office 365 debe tener una licencia para que esté cubierto por la característica.

- Para obtener la lista completa, vea las [descripciones del](https://technet.microsoft.com/library/exchange-online-service-description.aspx) servicio de Exchange Online para el cifrado de mensajes de Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>¿Puedo usar Exchange Online con bring your own key (BYOK) en Azure Information Protection?

Sí Microsoft recomienda completar los pasos para configurar BYOK antes de configurar OME.
  
Para obtener más información acerca de BYOK, vea [Planeación e implementación de la clave](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)de inquilino de Azure Information Protection.
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿OME y BYOK con Azure Information Protection cambian el enfoque de Microsoft para las solicitudes de datos de terceros, como las citaciones?

No. OME y la opción de proporcionar y controlar sus propias claves de cifrado, denominadas BYOK, desde Azure Information Protection no se diseñaron para responder a las citaciones de las fuerzas del orden. OME, con BYOK para Azure Information Protection, se diseñó para clientes centrados en el cumplimiento. Microsoft se toma muy en serio las solicitudes de terceros para los datos de los clientes. Como proveedor de servicios en la nube, siempre estamos a favor de la privacidad de los datos de los clientes. En caso de obtener una citación, siempre intentamos redirigir al tercero al cliente para obtener la información. (Please read Brad Smith's blog: [Protecting customer data from government snooping](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos periódicamente información detallada de la solicitud que recibimos. Para obtener más información sobre las solicitudes de datos de terceros, vea Responder a solicitudes gubernamentales y de las [fuerzas](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) del orden para obtener acceso a los datos de clientes en el Centro de confianza de Microsoft. Vea también "Divulgación de datos de clientes" en los Términos [de Online Services (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>¿Cómo está relacionada esta característica con las características heredadas de Cifrado de mensajes de Office 365 (OME) e Information Rights Management (IRM)?

Las nuevas capacidades para el cifrado de mensajes de Office 365 son una evolución de las soluciones existentes de IRM y OME heredadas. En la tabla siguiente se proporcionan más detalles.
  
**Comparación de las funcionalidades OME, IRM y nuevas de OME heredadas**

|**Función**|**Versiones anteriores de OME**|**IRM**|**Nuevas funcionalidades de OME**|
|:-----|:-----|:-----|:-----|
|**Enviar un correo electrónico cifrado**|Solo a través de reglas de flujo de correo de Exchange|Usuario final iniciado desde Outlook para Windows, Outlook para Mac o Outlook en la Web; o a través de reglas de flujo de correo de Exchange|Usuario final iniciado desde Outlook para Windows, Outlook para Mac o Outlook en la Web; o a través de reglas de flujo de correo|
|**Administración de derechos**|-|Opciones no reenviar y plantillas personalizadas|Opción No reenviar, opción de solo cifrado, plantillas predeterminadas y personalizadas|
|**Tipo de destinatario admitido**|Solo destinatarios externos|Solo destinatarios internos|Destinatarios internos y externos|
|**Experiencia para el destinatario**|Los destinatarios externos recibieron un mensaje HTML que descargaron y abrieron en un explorador o en una aplicación móvil descargada.|Los destinatarios internos solo recibieron correo electrónico cifrado en Outlook para Windows, Outlook para Mac y Outlook en la Web.|Los destinatarios internos y externos reciben correo electrónico en Outlook para Windows, Outlook para Mac, Outlook en la Web, Outlook para Android y Outlook para iOS, o a través de un portal web, independientemente de si están o no en la misma organización o en cualquier organización. El portal de OME no requiere descarga independiente.|
|**Compatibilidad con Bring Your Own Key**|No disponible|No disponible| BYOK compatible|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>¿Cómo puedo habilitar las nuevas funcionalidades de OME para mi organización?

Vea Configurar las nuevas capacidades de cifrado de mensajes [de Office 365.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>¿La versión anterior de OME estará en desuso?

Todavía puedes usar la versión anterior de OME, no estará en desuso en este momento. Sin embargo, recomendamos encarecidamente a las organizaciones que usen la nueva y mejorada solución OME. Los clientes que aún no han implementado OME no pueden configurar una nueva implementación de la versión anterior de OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Mi organización usa Active Directory Rights Management, ¿puedo usar esta funcionalidad?

No. Si usa Exchange Online con el servicio Active Directory Rights Management (AD RMS), no puede habilitar estas nuevas funcionalidades de inmediato. En su lugar, primero [debe migrar AD RMS a Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Mi organización tiene una implementación híbrida de Exchange. ¿Puedo usar esta característica?

Los usuarios locales pueden enviar correo cifrado mediante reglas de flujo de correo de Exchange Online. Para ello, debe enrutar el correo electrónico a través de Exchange Online. Para obtener más información, vea la parte 2: Configurar el correo para que fluya desde el servidor de correo electrónico [a Microsoft 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>¿Qué cliente de correo electrónico necesito usar para crear un mensaje cifrado de OME? ¿Qué aplicaciones se admiten para enviar mensajes protegidos?

Puede crear mensajes protegidos desde Outlook 2016, Outlook 2013 para Windows y Mac, y desde Outlook en la Web. Para obtener más información sobre el envío de mensajes cifrados, vea Enviar, ver y responder a mensajes cifrados [en Outlook para PC.](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>¿Qué clientes de correo electrónico se admiten para leer y responder mensajes de correo electrónico protegidos?

Los usuarios de Microsoft 365 pueden leer y responder desde Outlook para Windows y Mac (2013 y 2016), Outlook en la Web y Outlook mobile (Android e iOS). También puede usar el cliente de correo nativo de iOS si su organización lo permite. Si no es un usuario de Microsoft 365, puede leer y responder mensajes cifrados en la web a través de su explorador web.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>¿Qué clientes de correo electrónico admiten los correos electrónicos protegidos de solo cifrado?

Los usuarios de Microsoft 365 pueden usar Outlook para pc versiones 2019 y Microsoft 365 para crear correo protegido con la directiva de solo cifrado.  Esto significa que los mensajes a los que se aplica la nueva directiva de solo cifrado se pueden leer directamente en Outlook en la Web, en Outlook para iOS y Android y ahora en Outlook para PC, versiones 2019 y Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>¿Hay un límite de tamaño para los mensajes que puede enviar con OME?

Sí. El tamaño máximo de mensaje que puede enviar con OME, incluidos los datos adjuntos, es de 25 MB. Para obtener más información, vea [Límites de mensajes.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>¿Qué tipos de archivo se admiten como datos adjuntos en correos electrónicos protegidos? ¿Heredan los datos adjuntos las directivas de protección asociadas con los correos electrónicos protegidos?

Puede adjuntar cualquier tipo de archivo a un correo protegido. Con una excepción, las directivas de protección se aplican solo en los formatos de archivo mencionados en los tipos de archivo [admitidos por](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types)el cliente de Azure Information Protection . OME no admite las versiones 97-2003 de los siguientes programas de Office: Word (.doc), Excel (.xls) y PowerPoint (.ppt).

Si se admite un formato de archivo, como un archivo de Word, Excel o PowerPoint, el archivo siempre está protegido, incluso después de que el destinatario haya descargado los datos adjuntos. Por ejemplo, diga que un archivo adjunto está protegido por No reenviar. El destinatario original descarga el archivo, crea un mensaje a un nuevo destinatario y adjunta el archivo. Cuando el nuevo destinatario recibe el archivo, el destinatario no podrá abrir el archivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>¿Se admiten los datos adjuntos de archivos PDF?

La respuesta breve es sí. El cifrado de PDF le permite proteger documentos PDF confidenciales a través de una comunicación segura o una colaboración segura. Al enviar correo electrónico, el servicio office 365 cifra los datos adjuntos de los archivos PDF, no el cliente de Outlook.

Para Outlook en la Web, Outlook para iOS y Outlook para Android, puede cifrar los archivos PDF que envíe sin pasos adicionales. Estos clientes admiten de forma nativa el cifrado pdf.

El escritorio de Outlook no admite de forma nativa el cifrado de datos adjuntos de archivos PDF. En su lugar, deberá configurar las reglas de flujo de correo de Exchange o DLP para aplicar primero el cifrado a los datos adjuntos de PDF. Al enviar correo desde el escritorio de Outlook con datos adjuntos en PDF, el cliente envía primero el mensaje con los datos adjuntos al servicio. Cuando el servicio recibe el archivo, el servicio aplica la protección OME de la directiva de prevención de pérdida de datos (DLP) o regla de flujo de correo en Exchange Online. A continuación, Exchange Online envía el mensaje con los datos adjuntos del archivo PDF protegido.

Para habilitar el cifrado de datos adjuntos en PDF, ejecute el siguiente comando en [Exchange Online PowerShell:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

El cifrado de PDF le permite proteger documentos PDF confidenciales a través de una comunicación segura o una colaboración segura. Para todos los clientes de Outlook, los mensajes y los datos adjuntos PDF desprotegidos heredan la protección de OME de la directiva de prevención de pérdida de datos (DLP) o regla de flujo de correo en Exchange Online. Además, si un usuario de Outlook en la web adjunta un documento PDF desprotegido y aplica protección al mensaje, el mensaje hereda la protección del mensaje. Los usuarios solo pueden abrir los datos adjuntos cifrados en aplicaciones que admiten archivos PDF protegidos (por ejemplo, el Portal de OME y el Visor de Azure Information Protection).

> [!IMPORTANT]
> El cliente de escritorio de Outlook no admite el cifrado de PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>¿Se admiten los datos adjuntos de OneDrive para la Empresa?

Not yet. No se admiten los datos adjuntos de OneDrive para la Empresa y los usuarios finales no pueden cifrar un correo que contiene datos adjuntos de OneDrive para la Empresa en la nube.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>¿Qué clientes de correo electrónico admiten la vista previa de datos adjuntos cifrados en correos electrónicos protegidos?

Cuando los datos adjuntos están protegidos con un correo protegido, los clientes de Outlook proporcionan la capacidad de obtener una vista previa del documento directamente. Outlook admite la vista previa de documentos de Office (docx, xlsx, pptx, doc, xls, ppt). Outlook en la web admite la vista previa de documentos de Office (docx, xlsx, pptx) y PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>¿Qué clientes de correo electrónico admiten la revocación de correos electrónicos protegidos?

Outlook en la web admite la revocación de correo protegido.  Consulte [Cómo revocar un mensaje cifrado que envió para](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) obtener más información.


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>¿Puedo cifrar automáticamente los mensajes configurando directivas?

Sí. Use reglas de flujo de correo en Exchange Online para cifrar automáticamente un mensaje en función de determinadas condiciones. Por ejemplo, puede crear directivas basadas en el identificador de destinatario, el dominio del destinatario o en el contenido del cuerpo o asunto del mensaje. Vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>¿Puedo quitar automáticamente el cifrado del correo entrante y saliente?

Los administradores pueden configurar una regla de flujo de correo para quitar el cifrado del correo saliente. No puede configurar una regla para quitar el cifrado del correo entrante.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>¿Puedo cifrar mensajes automáticamente configurando directivas en prevención de pérdida de datos (DLP) a través del Centro de &amp; cumplimiento de seguridad?

Sí Puede configurar reglas de flujo de correo en Exchange Online o mediante DLP en el Centro de &amp; cumplimiento de seguridad.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>¿Puedo personalizar los mensajes cifrados con la personalización de marca de mi empresa?

Sí Para obtener información sobre cómo personalizar los mensajes de correo electrónico y el portal de OME, consulte Agregar la marca de su organización a los mensajes cifrados. Vea [Agregar la marca de su organización a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>¿Hay alguna capacidad de informes o información para los correos electrónicos cifrados?

Hay un informe de cifrado en el Centro de seguridad y cumplimiento. Consulte [Ver informes de seguridad de correo electrónico en el Centro de & cumplimiento.](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>¿Puedo usar el cifrado de mensajes con características de cumplimiento como eDiscovery?

Sí. Todas las características de cumplimiento de Microsoft 365 pueden detectar todos los mensajes de correo electrónico cifrados.

## <a name="can-i-remove-encryption-from-email"></a>¿Puedo quitar el cifrado del correo electrónico?

Los administradores pueden configurar una regla de flujo de correo para quitar el cifrado del correo saliente. No puede quitar el cifrado mediante una regla de flujo de correo de los mensajes entrantes.

## <a name="is-delegated-access-supported"></a>¿Se admite el acceso delegado?

No en este momento.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>¿Puedo enviar como un buzón compartido y cifrar mensajes de correo electrónico?

Cuando alguien envía un mensaje de correo electrónico que coincide con una regla de flujo de correo de cifrado, el mensaje se cifra antes de que se envíe.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>¿Puedo abrir mensajes cifrados enviados a un buzón compartido?

Sí Los mensajes cifrados son compatibles con un buzón compartido.

- Los usuarios pueden abrir correos protegidos en un buzón compartido donde el buzón compartido recibió un correo protegido como parte de un grupo de distribución.

- Los usuarios pueden ver datos adjuntos que heredan la protección del correo electrónico cuando usan Outlook para Windows, Outlook para Mac y Outlook en la Web.

En la tabla siguiente se enumeran los clientes admitidos para buzones compartidos.

| Plataforma | Leer correo | Ver datos adjuntos de correo electrónico |
|----------|-----------|------------------------|
| Outlook en la Web | Sí | Sí                |
| Outlook para Windows| Sí | Sí                |
| Outlook para Mac    | Sí | Sí                |
| Outlook para Android| Sí | No                 |
| Outlook para iOS    | Sí | No                 |
|

Actualmente hay dos limitaciones conocidas:

- No puede abrir datos adjuntos a los correos electrónicos que recibe en dispositivos móviles con Outlook Mobile.

- No se admite la asignación a través de un grupo de seguridad habilitado para correo electrónico. Solo se admite el acceso proporcionado por la asignación directa de usuarios al buzón compartido y que la asignación automática está habilitada para Exchange Online. La automapping está habilitada de forma predeterminada para Exchange Online.

**Para asignar un usuario al buzón compartido**

1. [Conéctese a Exchange Online con PowerShell remoto.](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)

2. Ejecute el cmdlet Add-MailboxPermission con el parámetro Automapping. En este ejemplo se conceden permisos de acceso completo a Ayla a un buzón de soporte técnico.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>¿Puedo abrir los mensajes cifrados enviados al buzón de otro usuario con Fullaccess?

Los usuarios pueden abrir mensajes cifrados siempre que se les proporciona acceso directo y la automapping está activada. No se permite el acceso si el acceso se concede a través de un grupo de seguridad habilitado para correo electrónico.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>¿Qué debo hacer si no recibo el código de paso de un solo paso después de solicitarlo?

En primer lugar, compruebe la carpeta de correo no deseado o correo no deseado en el cliente de correo electrónico. La configuración de DKIM y DMARC para su organización puede hacer que estos correos electrónicos terminen filtrados como correo no deseado.

A continuación, compruebe la cuarentena en el Centro de & cumplimiento. A menudo, los mensajes que contienen un código de paso único, especialmente los primeros que recibe su organización, terminan en cuarentena.
