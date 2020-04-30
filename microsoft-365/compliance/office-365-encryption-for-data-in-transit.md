---
title: Cifrado de datos en tránsito
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Una breve explicación de cómo Microsoft cifra los datos en tránsito en sus centros de datos.
ms.openlocfilehash: 645294522185a631012c1654fbad96ba0a21b33e
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943309"
---
# <a name="encryption-for-data-in-transit"></a>Cifrado de datos en tránsito

Además de proteger los datos de los clientes en reposo, Microsoft usa tecnologías de cifrado para proteger los datos de los clientes en tránsito. 

Los datos están en tránsito:

- Cuando un equipo cliente se comunica con un servidor de Microsoft;
- Cuando un servidor de Microsoft se comunica con otro servidor de Microsoft; y
- Cuando un servidor de Microsoft se comunica con un servidor que no es de Microsoft (por ejemplo, Exchange online que entrega el correo electrónico a un servidor de correo electrónico de terceros).

Las comunicaciones entre los servidores de Microsoft se realizan a través de TLS o IPsec y todos los servidores orientados a clientes negocian una sesión segura mediante TLS con los equipos cliente (por ejemplo, Exchange online usa TLS 1,2 con la intensidad de cifrado de 256 bits se usa (FIPS 140-2 nivel 2-validado). (Vea los [detalles de referencia técnica sobre el cifrado](technical-reference-details-about-encryption.md) para obtener una lista de los conjuntos de cifrado de TLS compatibles con Office 365). Esto se aplica a los protocolos que usan los clientes como Outlook, Skype empresarial, Microsoft Teams y Outlook en la web (por ejemplo, HTTP, POP3, etc.).

Los certificados públicos los emite SSL de Microsoft IT con SSLAdmin, una herramienta interna de Microsoft para proteger la confidencialidad de la información transmitida. Todos los certificados emitidos por Microsoft IT tienen un mínimo de 2048 bits de longitud y el cumplimiento de WebTrust requiere SSLAdmin para asegurarse de que los certificados solo se emiten para las direcciones IP públicas que pertenecen a Microsoft. Las direcciones IP que no cumplan este criterio se enrutan a través de un proceso de excepción.

Todos los detalles de implementación, como la versión de TLS que se usa, si la confidencialidad directa (FS) está habilitada, el orden de los conjuntos de cifrado, etc., están disponibles públicamente. Una forma de ver estos detalles es usar un sitio web de otro fabricante, como los [laboratorios de SSL de Qualys](https://www.ssllabs.com). A continuación se muestran los vínculos a páginas de prueba automatizadas desde Qualys que muestran información para los siguientes servicios:

- [Portal de Office 365](https://www.ssllabs.com/ssltest/analyze.html?d=portal.office.com&hideResults=on)
- [Exchange Online](https://www.ssllabs.com/ssltest/analyze.html?d=outlook.office365.com&hideResults=on)
- [SharePoint Online](https://www.ssllabs.com/ssltest/analyze.html?d=microsoft-my.sharepoint.com&hideResults=on)
- [Skype empresarial (SIP)](https://www.ssllabs.com/ssltest/analyze.html?d=sipdir.online.lync.com)
- [Skype empresarial (Web)](https://www.ssllabs.com/ssltest/analyze.html?d=webdir.online.lync.com&hideResults=on)
- [Exchange Online Protection](https://ssl-tools.net/mailservers/microsoft-com.mail.protection.outlook.com)
- [Microsoft Teams](https://www.ssllabs.com/ssltest/analyze.html?d=teams.microsoft.com&latest)

Para la protección en línea de Exchange, las direcciones URL varían según los nombres de los inquilinos; sin embargo, todos los clientes pueden probar Microsoft 365 con **Microsoft-com.mail.Protection.Outlook.com**.
