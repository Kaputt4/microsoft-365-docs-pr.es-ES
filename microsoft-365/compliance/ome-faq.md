---
title: Preguntas más frecuentes sobre cifrado de mensajes
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
description: ¿Tiene alguna pregunta sobre cómo funcionan las nuevas funcionalidades de protección de mensajes? Busca una respuesta aquí.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13d4181482bf8ad7460480a70c762fe60fd28ad0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051752"
---
# <a name="message-encryption-faq"></a>Preguntas más frecuentes sobre cifrado de mensajes

¿Tiene alguna pregunta sobre cómo funcionan las nuevas funcionalidades de protección de mensajes? Busca una respuesta aquí. Además, echa un vistazo a las preguntas más frecuentes sobre la protección de datos en [Azure Information Protection](/information-protection/get-started/faqs-rms) para obtener respuestas a preguntas sobre el servicio de protección de datos, Azure Rights Management, en Azure Information Protection.

## <a name="what-is-office-365-message-encryption-ome"></a>¿Qué es el cifrado de mensajes (OME) de Office 365?

OME combina el cifrado de correo electrónico y las capacidades de administración de derechos. Las capacidades de administración de derechos están basadas en Azure Information Protection.

## <a name="who-can-use-ome"></a>¿Quién puede usar OME?

Puede usar las nuevas funcionalidades para OME en las siguientes condiciones:
  
- Si nunca ha configurado OME o IRM para Exchange Online en Office 365.

- Si ha configurado OME e IRM, puede usar estos pasos si usa el servicio Azure Rights Management de Azure Information Protection.

- Si usa Exchange Online con el servicio de Administración de derechos de Active Directory (AD RMS), no puede habilitar estas nuevas funcionalidades de inmediato. En su lugar, primero debe [migrar AD RMS a Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Cuando haya terminado la migración, puede configurar OME correctamente.

  Si decide seguir usando AD RMS local con Exchange Online en lugar de migrar a Azure Information Protection, no podrá usar estas nuevas funcionalidades.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>¿Qué suscripciones necesito para usar las nuevas funcionalidades de OME?

Para usar las nuevas funcionalidades de OME, necesita uno de los siguientes planes:
  
- El cifrado de mensajes de Office 365 se ofrece como parte de Office 365 Enterprise E3 y E5, Microsoft Enterprise E3 y E5, Microsoft 365 Empresa Premium, Office 365 A1, A3 y A5, y Office 365 Government G3 y G5. Los clientes no necesitan licencias adicionales para recibir las nuevas funcionalidades de protección con tecnología de Azure Information Protection.

- También puede agregar Azure Information Protection Plan 1 a los siguientes planes para recibir las nuevas funcionalidades de cifrado de mensajes de Office 365: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Empresa Basic, Microsoft 365 Empresa Standard o Office 365 Enterprise E1.

- Cada usuario que se beneficie del cifrado de mensajes de Office 365 debe tener una licencia para que la característica la pueda cubrir.

- Para obtener la lista completa, vea las descripciones del servicio [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) para cifrado de mensajes de Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>¿Puedo usar Exchange Online con su propia clave (BYOK) en Azure Information Protection?

Sí Microsoft recomienda completar los pasos para configurar BYOK antes de configurar OME.
  
Para obtener más información acerca de BYOK, vea [Planning and implementing your Azure Information Protection tenant key](/information-protection/plan-design/plan-implement-tenant-key).
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>¿OME y BYOK con Azure Information Protection cambian el enfoque de Microsoft para solicitudes de datos de terceros, como citaciones?

No. La OME y la opción de proporcionar y controlar sus propias claves de cifrado, denominadas BYOK, de Azure Information Protection no se diseñaron para responder a las citaciones de las fuerzas del orden. OME, con BYOK para Azure Information Protection, se diseñó para clientes centrados en el cumplimiento. Microsoft se toma muy en serio las solicitudes de datos de clientes de terceros. Como proveedor de servicios en la nube, siempre defendemos la privacidad de los datos de los clientes. En caso de obtener una citación, siempre intentamos redirigir al tercero al cliente para obtener la información. (Lea el blog de Brad Smith: Proteger los datos de los clientes [del espionaje gubernamental](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Publicamos información detallada periódicamente de la solicitud que recibimos. Para obtener más información acerca de las solicitudes de datos de terceros, vea [Responder](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) a solicitudes gubernamentales y de cumplimiento de la ley para obtener acceso a los datos de los clientes en el Centro de confianza de Microsoft. Además, vea "Divulgación de datos del cliente" en los [Términos de servicios en línea (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>¿Cómo está relacionada esta característica con las características heredadas de Cifrado de mensajes (OME) de Office 365 y Information Rights Management (IRM)

Las nuevas funcionalidades del cifrado de mensajes de Office 365 son una evolución de las soluciones existentes de IRM y OME heredadas. En la tabla siguiente se proporcionan más detalles.
  
**Comparación de funcionalidades heredadas de OME, IRM y nuevas OME**

| Funcionalidad | Versiones anteriores de OME | IRM | Nuevas funcionalidades de OME |
|:-----|:-----|:-----|:-----|
|**Enviar un correo electrónico cifrado**|Solo a través de reglas de flujo de correo de Exchange|Usuario final iniciado desde Outlook para Windows, Outlook para Mac o Outlook en la web; o a través de reglas de flujo de correo de Exchange|Usuario final iniciado desde Outlook para Windows, Outlook para Mac o Outlook en la web; o a través de reglas de flujo de correo|
|**Administración de derechos**|-|Opción No reenviar y plantillas personalizadas|Opción No reenviar, opción de solo cifrado, plantillas predeterminadas y personalizadas|
|**Tipo de destinatario admitido**|Solo destinatarios externos|Solo destinatarios internos|Destinatarios internos y externos|
|**Experiencia para el destinatario**|Los destinatarios externos recibieron un mensaje HTML que descargaron y abrieron en un explorador o en una aplicación móvil descargada.|Los destinatarios internos solo recibieron correo electrónico cifrado en Outlook para Windows, Outlook para Mac y Outlook en la web.|Los destinatarios internos y externos reciben correo electrónico en Outlook para Windows, Outlook para Mac, Outlook en la web, Outlook para Android y Outlook para iOS, o a través de un portal web, independientemente de si están o no en la misma organización o en cualquier organización. El portal de OME no requiere descarga independiente.|
|**Traer su propia clave de soporte técnico**|No disponible|No disponible| BYOK compatible|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>¿Cómo puedo habilitar las nuevas funcionalidades de OME para mi organización?

Consulte Configurar nuevas capacidades de cifrado de mensajes [de Office 365.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>¿La versión anterior de OME estará en desuso?

Todavía puede usar la versión anterior de OME, no estará en desuso en este momento. Sin embargo, recomendamos encarecidamente a las organizaciones que usen la nueva y mejorada solución de OME. Los clientes que aún no han implementado OME no pueden configurar una nueva implementación de la versión anterior de OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>Mi organización usa Active Directory Rights Management, ¿puedo usar esta funcionalidad?

No. Si usa Exchange Online con el servicio de Administración de derechos de Active Directory (AD RMS), no puede habilitar estas nuevas funcionalidades de inmediato. En su lugar, primero debe [migrar AD RMS a Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>Mi organización tiene una implementación híbrida de Exchange. ¿Puedo usar esta característica?

Los usuarios locales pueden enviar correo cifrado mediante reglas de flujo de correo de Exchange Online. Para ello, debe enrutar el correo electrónico a través de Exchange Online. Para obtener más información, vea [Part 2: Configure mail to flow from your email server to Microsoft 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>¿Qué cliente de correo electrónico necesito usar para crear un mensaje cifrado de OME? ¿Qué aplicaciones se admiten para enviar mensajes protegidos?

Puede crear mensajes protegidos desde Outlook 2016, Outlook 2013 para Windows y Mac, y desde Outlook en la web. Para obtener más información sobre el envío de mensajes cifrados, vea [Enviar, ver y responder](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)a mensajes cifrados en Outlook para PC .
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>¿Qué clientes de correo electrónico se admiten para leer y responder a correos electrónicos protegidos?

Los usuarios de Microsoft 365 pueden leer y responder desde Outlook para Windows y Mac (2013 y 2016), Outlook en la web y Outlook mobile (Android e iOS). También puedes usar el cliente de correo nativo de iOS si tu organización lo permite. Si no es un usuario de Microsoft 365, puede leer y responder a mensajes cifrados en la web a través del explorador web.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>¿Qué clientes de correo electrónico admiten los correos electrónicos protegidos de solo cifrado?

Los usuarios de Microsoft 365 pueden usar las versiones de Outlook para PC 2019 y Microsoft 365 para crear correo protegido con la directiva de solo cifrado.  Esto significa que los mensajes que tienen aplicada la nueva directiva de solo cifrado se pueden leer directamente en Outlook en la web, en Outlook para iOS y Android, y ahora outlook para pc versiones 2019 y Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>¿Hay un límite de tamaño para los mensajes que puede enviar con OME?

Sí. El tamaño máximo de mensaje que puede enviar con OME, incluidos los datos adjuntos, es de 25 MB. Para obtener más información, vea [Límites de mensajes](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1).

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>¿Qué tipos de archivo se admiten como datos adjuntos en correos electrónicos protegidos? ¿Los datos adjuntos heredan las directivas de protección asociadas con los correos electrónicos protegidos?

Puede adjuntar cualquier tipo de archivo a un correo protegido. Con una excepción, las directivas de protección se aplican solo en los formatos de archivo mencionados en Tipos de [archivo admitidos por el](/information-protection/rms-client/client-admin-guide-file-types)cliente de Azure Information Protection . OME no admite las versiones 97-2003 de los siguientes programas de Office: Word (.doc), Excel (.xls) y PowerPoint (.ppt).

Si se admite un formato de archivo, como un archivo de Word, Excel o PowerPoint, el archivo siempre está protegido, incluso después de que el destinatario haya descargado los datos adjuntos. Por ejemplo, diga que los datos adjuntos están protegidos por Do Not Forward. El destinatario original descarga el archivo, crea un mensaje a un nuevo destinatario y adjunta el archivo. Cuando el nuevo destinatario recibe el archivo, el destinatario no podrá abrir el archivo protegido.
  
## <a name="are-pdf-file-attachments-supported"></a>¿Se admiten los datos adjuntos de archivos PDF?

La respuesta corta es sí. El cifrado de PDF le permite proteger documentos PDF confidenciales mediante una comunicación segura o una colaboración segura. Al enviar correo electrónico, el servicio de Office 365 cifra los datos adjuntos de archivos PDF, no el cliente de Outlook.

Para Outlook en la web, Outlook para iOS y Outlook para Android, puede cifrar los archivos PDF que envíe sin ningún paso adicional. Estos clientes admiten de forma nativa el cifrado de PDF.

El escritorio de Outlook no admite de forma nativa el cifrado de datos adjuntos de archivos PDF. En su lugar, deberá configurar primero las reglas de flujo de correo de Exchange o DLP para aplicar el cifrado a los datos adjuntos de PDF. Cuando envía correo desde El escritorio de Outlook con datos adjuntos de PDF, el cliente envía primero el mensaje con los datos adjuntos al servicio. Cuando el servicio recibe el archivo, el servicio aplica la protección OME de la directiva de prevención de pérdida de datos (DLP) o la regla de flujo de correo en Exchange Online. A continuación, Exchange Online envía el mensaje con los datos adjuntos del archivo PDF protegido.

Para habilitar el cifrado para los datos adjuntos de PDF, ejecute el siguiente comando en [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

El cifrado de PDF le permite proteger documentos PDF confidenciales mediante una comunicación segura o una colaboración segura. Para todos los clientes de Outlook, los mensajes y los datos adjuntos de PDF sin protección heredan la protección OME de la directiva de prevención de pérdida de datos (DLP) o la regla de flujo de correo en Exchange Online. Además, si un usuario de Outlook en la web adjunta un documento PDF desprotegido y aplica protección al mensaje, el mensaje hereda la protección del mensaje. Los usuarios solo pueden abrir los datos adjuntos cifrados en aplicaciones que admiten ARCHIVOS PDF protegidos (por ejemplo, el Portal de OME y el Visor de Azure Information Protection).

> [!IMPORTANT]
> El cliente de escritorio de Outlook no admite el cifrado de PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>¿Se admiten los datos adjuntos de OneDrive para la Empresa?

Not yet. Los datos adjuntos de OneDrive para la Empresa no son compatibles y los usuarios finales no pueden cifrar un correo que contiene datos adjuntos de OneDrive para la Empresa en la nube.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>¿Qué clientes de correo electrónico admiten la vista previa de datos adjuntos cifrados en correos electrónicos protegidos?

Cuando los datos adjuntos están protegidos con un correo protegido, los clientes de Outlook proporcionan la capacidad de obtener una vista previa del documento directamente. Outlook admite la vista previa de documentos de Office (docx, xlsx, pptx, doc, xls, ppt). Outlook en la web admite una vista previa de documentos de Office (docx, xlsx, pptx) y PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>¿Qué clientes de correo electrónico admiten la revocación de correos electrónicos protegidos?

Outlook en la web admite la revocación de correo protegido.  Consulte [How to revoke an encrypted message that you sent](revoke-ome-encrypted-mail.md#how-to-revoke-an-encrypted-message-that-you-sent) for details.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>¿Puedo cifrar automáticamente los mensajes configurando directivas?

Sí. Use reglas de flujo de correo en Exchange Online para cifrar automáticamente un mensaje en función de determinadas condiciones. Por ejemplo, puede crear directivas basadas en el identificador de destinatario, el dominio del destinatario o en el contenido del cuerpo o asunto del mensaje. Vea [Definir reglas de flujo de correo para cifrar mensajes de correo electrónico en Office 365](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>¿Puedo quitar automáticamente el cifrado en el correo entrante y saliente?

Los administradores pueden configurar una regla de flujo de correo para quitar el cifrado del correo saliente. No puede configurar una regla para quitar el cifrado del correo entrante.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>¿Puedo cifrar automáticamente los mensajes configurando directivas en Prevención de pérdida de datos (DLP) a través del Centro de &amp; cumplimiento de seguridad?

Sí Puede configurar reglas de flujo de correo en Exchange Online o mediante DLP en el Centro de &amp; seguridad y cumplimiento.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>¿Puedo personalizar los mensajes cifrados con la personalización de marca de mi empresa?

Sí Para obtener información sobre la personalización de mensajes de correo electrónico y el portal de OME, vea Agregar la marca de la organización a los mensajes cifrados. Consulta [Agregar la marca de la organización a los mensajes cifrados.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>¿Hay capacidades de informes o información para correos electrónicos cifrados?

Hay un informe de cifrado en el Centro de seguridad y cumplimiento. Vea [Ver informes de seguridad de correo electrónico en el Centro de seguridad & cumplimiento](../security/defender-365-security/view-email-security-reports.md).
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>¿Puedo usar el cifrado de mensajes con características de cumplimiento como eDiscovery?

Sí. Todas las características de cumplimiento de Microsoft 365 pueden detectar todos los mensajes de correo electrónico cifrados.

## <a name="can-i-remove-encryption-from-email"></a>¿Puedo quitar el cifrado del correo electrónico?

Los administradores pueden configurar una regla de flujo de correo para quitar el cifrado. No puede quitar el cifrado mediante una regla de flujo de correo del correo que aplica otra organización, a menos que el correo se enrutíce con protección de solo cifrado.

## <a name="is-delegated-access-supported"></a>¿Se admite el acceso delegado?

No en este momento.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>¿Puedo enviar como buzón compartido y cifrar correos electrónicos?

Cuando alguien envía un mensaje de correo electrónico que coincide con una regla de flujo de correo de cifrado, el mensaje se cifra antes de que se envíe.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>¿Puedo abrir los mensajes cifrados enviados a un buzón compartido?

Sí Los mensajes cifrados son compatibles con un buzón compartido.

- Los usuarios pueden abrir correos protegidos en un buzón compartido donde el buzón compartido recibió un correo protegido como parte de un grupo de distribución.

- Los usuarios pueden ver datos adjuntos que heredan la protección del correo electrónico cuando usan Outlook para Windows, Outlook para Mac y Outlook en la web.

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

- No puede abrir datos adjuntos a los correos electrónicos que reciba en dispositivos móviles mediante Outlook mobile.

- No se admite la asignación a través de un grupo de seguridad habilitado para correo electrónico. Solo se admite el acceso proporcionado por la asignación directa de usuarios al buzón compartido y que la asignación automática está habilitada para Exchange Online. La automapping está habilitada de forma predeterminada para Exchange Online.

**Para asignar un usuario al buzón compartido**

1. [Conectarse a Exchange Online con PowerShell remoto](/powershell/exchange/connect-to-exchange-online-powershell?v=exchg.150).aspx).

2. Ejecute el cmdlet Add-MailboxPermission con el parámetro Automapping. En este ejemplo se proporciona a Ayla permisos de acceso completo a un buzón de soporte técnico.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```

## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>¿Puedo abrir los mensajes cifrados enviados al buzón de otro usuario con Fullaccess?

Los usuarios pueden abrir mensajes cifrados siempre que se les proporciona acceso directo y la automapping está activada. No se permite el acceso si el acceso se concede a través de un grupo de seguridad habilitado para correo electrónico.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>¿Qué hago si no recibo el código de paso de una sola vez después de solicitarlo?

En primer lugar, compruebe la carpeta de correo no deseado o correo no deseado en el cliente de correo electrónico. La configuración de DKIM y DMARC para su organización puede hacer que estos correos electrónicos terminen filtrados como correo no deseado.

A continuación, compruebe la cuarentena en el Centro de seguridad & cumplimiento. A menudo, los mensajes que contienen un código de paso único, especialmente los primeros que recibe la organización, terminan en cuarentena.