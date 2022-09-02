---
title: Registros DNS para Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
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
ms.openlocfilehash: a0b7c08805e5cdd07c798da3c45b3af82ceddd1d
ms.sourcegitcommit: 62368e5a48e569c8e475b07d194d7d8ff7d167ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2022
ms.locfileid: "67556356"
---
# <a name="dns-records-for-office-365-dod"></a>Registros DNS para Office 365 DoD

*Este artículo se aplica a Office 365 DoD y DoD de Microsoft 365*

Como parte de la incorporación a Office 365 DoD, deberá agregar los dominios SMTP y SIP al inquilino de Online Services.  Para ello, usará el cmdlet New-MsolDomain en PowerShell de Azure AD o el [Portal de Azure Government](https://portal.azure.us) para iniciar el proceso de agregar el dominio y probar la propiedad.

Una vez que haya agregado los dominios al inquilino y validado, use las instrucciones siguientes para agregar los registros DNS adecuados para los servicios siguientes.  Es posible que tenga que modificar la tabla siguiente para satisfacer las necesidades de su organización con respecto a los registros MX entrantes y a los registros de detección automática de Exchange existentes que tenga en vigor.  Se recomienda coordinar estos registros DNS con el equipo de mensajería para evitar interrupciones o entregas incorrectas de correo electrónico.

## <a name="exchange-online"></a>Exchange Online

| Tipo | Prioridad | Nombre de host | Apuntar a dirección o valor | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant.mail.protection.office365.us* (consulte a continuación para obtener más información) | Una hora |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | Una hora |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | Una hora |

### <a name="exchange-autodiscover-record"></a>Registro de detección automática de Exchange

Si tiene Exchange Server local, se recomienda dejar el registro existente en su lugar mientras se migra a Exchange Online y actualizar ese registro una vez que haya completado la migración.

### <a name="exchange-online-mx-record"></a>registro MX de Exchange Online

El valor de registro MX de los dominios aceptados sigue un formato estándar como se indicó anteriormente: *tenant.mail.protection.office365.us*, reemplazando el *inquilino* por la primera parte del nombre de inquilino predeterminado.

Por ejemplo, si el nombre del inquilino está contoso.onmicrosoft.us, usaría **contoso.mail.protection.office365.us** como valor para el registro MX.

## <a name="skype-for-business-online"></a>Skype Empresarial Online

### <a name="cname-records"></a>Registros CNAME

| Tipo | Nombre de host | Apuntar a dirección o valor | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | Una hora |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | Una hora | 

### <a name="srv-records"></a>Registros SRV

| Tipo | Servicio | Protocolo | Puerto | Peso | Prioridad | Nombre | Target | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | Una hora |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | Una hora |

## <a name="other-dns-records"></a>Otros registros DNS

> [!IMPORTANT]
> Si tiene un registro *CNAME msoid* existente en la zona DNS, debe **quitar** el registro de DNS en este momento.  El registro msoid no es compatible con Microsoft 365 Enterprise Apps *(anteriormente Office 365 ProPlus)* y evitará que la activación se realice correctamente.
