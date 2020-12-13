---
title: Conectar su dominio a Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Aprenda a verificar su dominio y a crear registros DNS con Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658220"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Conectar su dominio a Microsoft 365

> [!NOTE]
> Si no agrega el dominio, los integrantes de la organización usarán el dominio onmicrosoft.com para las direcciones de correo electrónico hasta que lo agregue. Es importante que agregue el dominio antes de agregar usuarios, para evitar tener que configurarlo dos veces.

[Consulte las preguntas frecuentes sobre los dominios](../setup/domains-faq.yml) si no encuentra lo que busca debajo.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Agregar un registro MX para que el correo electrónico del dominio vaya a Microsoft

Obtendrá la información del registro MX del asistente de configuración del dominio del centro de administración.

En el sitio web del proveedor de host, agregue un nuevo registro MX.
Asegúrese de configurar los campos con los siguientes valores:

- Tipo de registro: `MX`
- Prioridad: defina la prioridad con el valor más alto posible, que suele ser `0`.
- Nombre de host: `@`
- Dirección de destino: copie el valor del centro de administración y péguelo aquí.
- TTL: `3600‎` (o el proveedor predeterminado)

Guarde el registro y, a continuación, quite cualquier otro registro MX.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>Agregar un registro CNAME para conectar a los usuarios con sus buzones
Obtendrá la información de los registros CNAME del asistente de configuración del dominio del centro de administración.

En el sitio web de su proveedor de hospedaje, agregue el siguiente registro CNAME. Asegúrese de configurar los campos con los siguientes valores para cada uno:

- Tipo de registro: `CNAME (Alias)`
- Host: pegue aquí los valores que copie del centro de administración.
- Dirección de destino: copie el valor del centro de administración y péguelo aquí.
- TTL: `3600‎` (o el proveedor predeterminado)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>Agregar un registro TXT para ayudar a evitar el correo no deseado
**Antes de empezar:** si ya tiene un registro de SPF para su dominio, no cree uno nuevo para Microsoft 365. En vez de eso, agregue los valores necesarios de Microsoft 365 para el registro actual en el sitio web de su proveedor de host, de modo que solo tenga un *único* registro de SPF que incluya ambos conjuntos de valores.

En el sitio web de su proveedor de host, edite el registro SPF existente o cree un nuevo registro SPF.
Asegúrese de configurar los campos con los siguientes valores:

- Tipo de registro: `TXT (Text)`
- Host: `@`
- Valor TXT: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (o el proveedor predeterminado)

Guarde el registro.

Para validar el registro de SPF, use una de estas[herramientas de validación de SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain).

SPF está diseñado para ayudar a evitar la suplantación de identidad, pero hay técnicas de suplantación de identidad contra las que SPF no puede proteger. Para protegerse de estos, una vez que haya configurado el SPF, también debe configurar DKIM y DMARC para Microsoft 365.

Para comenzar, consulte [Usar DKIM para validar el correo electrónico saliente enviado desde su dominio en Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) y[Usar DMARC para validar el correo electrónico en Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Por último, vuelva al asistente de configuración del dominio del centro de administración para completar la configuración.
