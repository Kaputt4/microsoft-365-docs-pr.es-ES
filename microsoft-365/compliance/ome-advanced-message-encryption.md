---
title: Cifrado avanzado de mensajes de Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/16/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: El cifrado de mensajes avanzado en Office 365 ayuda a las organizaciones a cumplir sus obligaciones de cumplimiento al permitir que los administradores hagan incluso más cosas con los mensajes protegidos.
ms.openlocfilehash: 3b7f4d595b8c3592530b107dd7f71aeb8d0dc57e
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "43106178"
---
# <a name="office-365-advanced-message-encryption"></a>Cifrado avanzado de mensajes de Office 365

Office 365 Advanced Message Encryption se incluye en [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (precio de personal sin ánimo de lucro), Office 365 Enterprise E5 (precio de personal sin ánimo de lucro) y Office 365 Education A5. Si su organización tiene una suscripción que no incluye el cifrado avanzado de mensajes de Office 365, puede comprarlo con el complemento de SKU de cumplimiento de Microsoft 365 E5 para Microsoft 365 E3, Microsoft 365 E3 (precio del personal sin ánimo de lucro), o el complemento de SKU de Office 365 Advanced Compliance para Microsoft 365 E3, Microsoft 365 E3 (precios para empleados sin ánimo de lucro), SKU de Office 365 o el complemento de protección de información y de administración de la información de Microsoft 365 E5/A5 para Microsoft 365 a3/E3.

El cifrado de mensajes avanzado en Office 365 ayuda a los clientes a cumplir las obligaciones de cumplimiento que necesitan controles más flexibles sobre los destinatarios externos y su acceso a los correos electrónicos cifrados. Con el cifrado de mensajes avanzado en Office 365, puede controlar los mensajes de correo electrónico confidenciales que se comparten fuera de la organización con directivas automáticas. Estas directivas se configuran para identificar los tipos de información confidencial, como los identificadores de PII, financieros o de mantenimiento, o se pueden usar palabras clave para mejorar la protección. Una vez que haya configurado las directivas, empareja las directivas con plantillas de correo electrónico personalizadas y, a continuación, agrega una fecha de expiración para el control adicional de los correos electrónicos que se ajustan a la Directiva. Además, los administradores pueden controlar más los correos electrónicos cifrados a los que se accede externamente a través de un portal web seguro al revocar el acceso al correo en cualquier momento.

Solo puede revocar y establecer una fecha de caducidad para los correos electrónicos enviados a destinatarios externos.

## <a name="get-started-with-office-365-advanced-message-encryption"></a>Introducción a Office 365 Advanced Message Encryption

En los artículos siguientes se describe cómo configurar y usar el cifrado de mensajes avanzado.

La organización debe tener una suscripción que incluya el cifrado de mensajes avanzado de Office 365. Para obtener información detallada acerca de las suscripciones admitidas, consulte la [Descripción del servicio de cumplimiento y directivas de mensajes](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).

Si no tiene ya configurado el cifrado de mensajes de Office 365, vea [configurar las nuevas capacidades de cifrado de mensajes de office 365](set-up-new-message-encryption-capabilities.md).

Con el cifrado de mensajes avanzado, no está limitado a una sola plantilla de personalización de marca. En su lugar, puede crear y usar varias plantillas de personalización de marca. Para obtener más información, vea [Agregar la marca de la organización a los mensajes cifrados](add-your-organization-brand-to-encrypted-messages.md).

[Establezca una fecha de caducidad para el correo electrónico cifrado por el cifrado de mensajes avanzado de Office 365](ome-advanced-expiration.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización con directivas automáticas que mejoran la protección al expirar el acceso a través de un portal web seguro a los correos electrónicos cifrados.

[Revocar correo electrónico cifrado por el cifrado de mensajes avanzado de Office 365](revoke-ome-encrypted-mail.md). Controle los correos electrónicos confidenciales compartidos fuera de la organización y mejore la protección al revocar el acceso a través de un portal web seguro a los correos electrónicos cifrados.  

Con Office 365 Advanced Message Encryption, siempre que aplique una plantilla de personalización de marca personalizada, Office 365 aplica un contenedor al correo electrónico que se ajusta a la regla de flujo de correo a la que se aplica la plantilla. Solo puede revocar mensajes y aplicar fechas de caducidad a los mensajes que reciben los usuarios a través del portal. Es decir, se aplica un correo electrónico con una plantilla de personalización de marca personalizada. Para obtener más información y un ejemplo, consulte la guía en [Asegúrese de que todos los destinatarios externos usan el portal OME para leer correo cifrado](manage-office-365-message-encryption.md#ensure-all-external-recipients-use-the-ome-portal-to-read-encrypted-mail).
