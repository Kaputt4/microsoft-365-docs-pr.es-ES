---
title: Registros DNS para Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Resumen: registros DNS para Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693839"
---
# <a name="dns-records-for-office-365-dod"></a>Registros DNS para Office 365 DoD

*Este artículo se aplica a Office 365 DoD y Microsoft 365 DoD*

Como parte de la incorporación a Office 365 DoD, tendrá que agregar los dominios SMTP y SIP a su inquilino de Servicios en línea.  Para ello, use el cmdlet New-MsolDomain azure AD PowerShell o el Portal de [Azure Government para](https://portal.azure.us) iniciar el proceso de agregar el dominio y demostrar la propiedad.

Una vez que haya agregado sus dominios a su inquilino y validado, use las siguientes instrucciones para agregar los registros DNS adecuados para los servicios siguientes.  Es posible que tenga que modificar la tabla siguiente para satisfacer las necesidades de su organización con respecto a los registros MX entrantes y los registros de Detección automática de Exchange existentes que tenga en su lugar.  Recomendamos encarecidamente coordinar estos registros DNS con el equipo de mensajería para evitar interrupciones o entregas erróneas de correo electrónico.

## <a name="exchange-online"></a>Exchange Online

| Tipo | Prioridad | Nombre de host | Apunta a dirección o valor | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (consulta a continuación para obtener más información) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 hora |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Registro de detección automática de Exchange

Si tiene una Exchange Server local, le recomendamos dejar el registro existente en su lugar mientras migra a Exchange Online y actualizar ese registro una vez que haya completado la migración.

### <a name="exchange-online-mx-record"></a>Registro MX de Exchange Online

El valor del registro MX para los dominios aceptados sigue un formato estándar  como se indicó *anteriormente:* inquilino .mail.protection.office365.us, reemplazando el inquilino por la primera parte del nombre de inquilino predeterminado.

Por ejemplo, si el nombre del inquilino es contoso.onmicrosoft.us, usaría contoso.mail.protection.office365.us **como** valor para el registro MX.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

### <a name="cname-records"></a>Registros CNAME

| Tipo | Nombre de host | Apunta a dirección o valor | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 hora |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>Registros SRV

| Tipo | Servicio | Protocolo | Puerto | Peso | Priority | Nombre | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1  | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 hora |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1  | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Registros DNS adicionales

> [!IMPORTANT]
> Si tiene un registro *CNAME msoid* existente en  la zona DNS, debe quitar el registro de DNS en este momento.  El registro msoid es incompatible con Aplicaciones de Microsoft 365 Enterprise *(anteriormente Office 365 ProPlus)* y evitará que la activación se haga correctamente.
