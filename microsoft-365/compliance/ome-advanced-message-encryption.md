---
title: Cifrado avanzado de mensajes
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 05/12/2022
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Advanced Message Encryption ayuda a las organizaciones a cumplir sus obligaciones de cumplimiento al permitir que los administradores hagan aún más con los mensajes protegidos.
ms.openlocfilehash: 077a17921c456ddff30e7490611dd4e78aaa5232
ms.sourcegitcommit: 54bc063818779e351ca24f04ba571f762d85751d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/13/2022
ms.locfileid: "65393294"
---
# <a name="advanced-message-encryption"></a>Cifrado avanzado de mensajes

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Microsoft Purview Cifrado avanzado de mensajes se incluye en [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precios del personal sin ánimo de lucro), Office 365 Enterprise E5 (Personal sin ánimo de lucro) Precios) y Office 365 Educación A5. Si su organización tiene una suscripción que no incluye Microsoft Purview cifrado avanzado de mensajes, puede comprarlo con el complemento de SKU de Cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro) o el Cumplimiento avanzado de Office 365 complemento de SKU para Microsoft 365 E3, Microsoft 365 E3 (precios del personal sin ánimo de lucro), SKU de Office 365 o Microsoft 365 E5/A5 complemento Information Protection y SKU de gobernanza para Microsoft 365 A3/E3.

Advanced Message Encryption ayuda a los clientes a cumplir las obligaciones de cumplimiento que requieren controles más flexibles sobre los destinatarios externos y su acceso a correos electrónicos cifrados. Con Advanced Message Encryption en Office 365, puede controlar los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas y realizar un seguimiento de esas actividades a través de los registros de acceso del portal de mensajes cifrados. Configure estas directivas para identificar tipos de información confidencial, como PII, Financial o Health, o bien puede usar palabras clave para mejorar la protección. Una vez que haya configurado las directivas, empareja las directivas con plantillas de correo electrónico personalizadas de marca y, a continuación, agrega una fecha de expiración para el control adicional de los correos electrónicos que se ajustan a la directiva. Además, los administradores pueden controlar aún más los correos electrónicos cifrados a los que se accede externamente a través de un portal web seguro revocando el acceso al correo en cualquier momento.

Solo puede revocar y establecer una fecha de expiración para los correos electrónicos enviados a destinatarios externos.

## <a name="get-started-with-microsoft-purview-advanced-message-encryption"></a>Comenzar con Microsoft Purview cifrado avanzado de mensajes

En los artículos siguientes se describe cómo configurar y usar el cifrado avanzado de mensajes.

Su organización debe tener una suscripción que incluya Microsoft Purview Cifrado avanzado de mensajes. Para obtener información detallada sobre las suscripciones admitidas, consulte la [descripción de la directiva de mensajes y del servicio de cumplimiento](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Si aún no tiene Office 365 cifrado de mensajes configurado, consulte [Configuración de nuevas funcionalidades de cifrado de mensajes Office 365](set-up-new-message-encryption-capabilities.md).

Con Advanced Message Encryption, no se limita a una sola plantilla de personalización de marca. En su lugar, puede crear y usar varias plantillas de personalización de marca. Agregar personalización de marca también permite habilitar el seguimiento de una revocación de mensajes cifrados. Para obtener información, consulte [Incorporación de la marca de su organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md). Cuando se usa la personalización de marca, los destinatarios externos reciben un correo electrónico de notificación que contiene un vínculo al portal de OME. La regla de flujo de correo determina qué plantilla de personalización de marca usan el correo electrónico de notificación y el portal de OME. De este modo, el contenido seguro no se envía fuera de la organización.

Solo puede revocar mensajes y aplicar fechas de expiración a los mensajes que los usuarios reciben a través del portal. En otras palabras, el correo electrónico que tiene una plantilla de personalización de marca aplicada. Para obtener más información y un ejemplo, consulte las instrucciones [de Asegúrese de que todos los destinatarios externos usen el portal de OME para leer el correo cifrado](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).

[Establezca una fecha de expiración para el correo electrónico cifrado mediante Microsoft Purview Cifrado avanzado de mensajes](ome-advanced-expiration.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que mejoren la protección al expirar el acceso a través de un portal web seguro a correos electrónicos cifrados.

[Revoque el correo electrónico cifrado mediante Microsoft Purview Cifrado avanzado de mensajes](revoke-ome-encrypted-mail.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización y mejore la protección mediante la revocación del acceso a través de un portal web seguro a los correos electrónicos cifrados.

[Registro de actividad del portal de mensajes cifrado mediante Microsoft Purview cifrado avanzado de mensajes](ome-message-access-logs.md). Supervise los correos electrónicos confidenciales compartidos fuera de la organización en el portal de mensajes cifrados.
