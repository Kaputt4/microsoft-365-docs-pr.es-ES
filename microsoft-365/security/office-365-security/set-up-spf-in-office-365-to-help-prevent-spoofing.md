---
title: Configurar SPF para ayudar a evitar la suplantación de identidad
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Aprenda a actualizar un registro de Servicio de nombres de dominio (DNS) para usar el marco de directivas de remitente (SPF) con su dominio personalizado en Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c4369cafece2d0a7c7a27890cbedf35eca2b90a7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157523"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a>Configurar SPF para ayudar a evitar la suplantación de identidad

- [Requisitos previos](#prerequisites)
- [Crear o actualizar el registro TXT de SPF](#create-or-update-your-spf-txt-record)
- [¿Cómo se tratan los subdominios?](#how-to-handle-subdomains)
- [Solución de problemas con SPF](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

En este artículo se describe cómo actualizar un registro del servicio de nombres de dominio (DNS) para que pueda usar la autenticación de correo electrónico del Marco de directivas de remitente (SPF)  con su dominio personalizado en Office 365.

SPF ayuda a *validar* el correo electrónico saliente enviado desde su dominio personalizado (si proviene de quien dice ser). Es un primer paso para configurar los métodos completos de autenticación de correo electrónico recomendados de SPF, [DKIM](use-dkim-to-validate-outbound-email.md)y [DMARC](use-dmarc-to-validate-email.md).

- [Requisitos previos](#prerequisites)
- [Crear o actualizar el registro TXT de SPF](#create-or-update-your-spf-txt-record)
  - [¿Cómo se tratan los subdominios?](#how-to-handle-subdomains)
- [¿Qué hace realmente la autenticación de correo electrónico SPF?](#what-does-spf-email-authentication-actually-do)
  - [Solucionar problemas relacionados con SPF](#troubleshooting-spf)
- [Más información sobre SPF](#more-information-about-spf)

## <a name="prerequisites"></a>Requisitos previos

> [!IMPORTANT]
> Si es administrador de una **pequeña empresa** o está familiarizado con las direcciones IP o la configuración de DNS, llame a su registrador de dominios de Internet (p. ej. GoDaddy, Bluehost,web.com) y solicitar ayuda con la *configuración de DNS de SPF* (y cualquier otro método de autenticación de correo electrónico). <p> **Si no usa una dirección URL personalizada** (y la dirección URL que se usa para Office 365 termina en **onmicrosoft.com**), SPF ya se ha configurado para usted en el servicio de Office 365.

Comencemos.

El registro TXT de SPF para Office 365 se hará en un DNS externo para cualquier dominio o subdominio personalizado. Necesita cierta información para realizar el registro. Recopile esta información:

- El registro TXT de SPF para su dominio personalizado, en caso de que exista uno. Para obtener instrucciones, consulte [Recopilar la información necesaria para crear registros de DNS de Office 365](../../admin/get-help-with-domains/information-for-dns-records.md).

- Vaya a los servidores de mensajería y encuentre las direcciones IP externas (necesarias en todos los servidores de mensajería locales). Por ejemplo, **131.107.2.200**.

- Nombres de dominio que se usarán para todos los dominios de terceros que necesita incluir en el registro TXT de SPF. Algunos proveedores de correo masivo tienen configurados subdominios para sus clientes. Por ejemplo, la empresa MailChimp tiene configurado **servers.mcsv.net**.

- Averigüe qué regla de cumplimiento desea usar para el registro TXT de SPF. Se recomienda la regla **-all**. Para obtener información detallada sobre otras opciones de sintaxis, consulte [Sintaxis de registro TXT de SPF para Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).

> [!IMPORTANT]
> Para poder utilizar un dominio personalizado, Office 365 requiere que agregue un registro TXT de marco de directivas de remitente (SPF) en su registro DNS para ayudar a evitar la suplantación de identidad.

## <a name="create-or-update-your-spf-txt-record"></a>Crear o actualizar el registro TXT de SPF

1. Asegúrese de que está familiarizado con la sintaxis SFP de la siguiente tabla.

   ****

   |Elemento|Si usa...|¿Es común para los clientes?|Agregue esto...|
   |---|---|---|---|
   |1|Cualquier sistema de correo electrónico (obligatorio)|Común. Todos los registros TXT de SPF comienzan con este valor|`v=spf1`|
   |2|Exchange Online|Común|`include:spf.protection.outlook.com`|
   |3|Solo Exchange Online dedicado|No es común|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |4 |Solo para Office 365 Alemania y Microsoft Cloud Alemania|No es común|`include:spf.protection.outlook.de`|
   |5|Sistema de correo electrónico de terceros|No es común|`include:<domain_name>` <p> \<domain_name\> es el dominio del sistema de correo electrónico de terceros.|
   |6 |Sistema de correo local. Por ejemplo, Exchange Online Protection y otro sistema de correo electrónico|No es común|Use uno de estos para cada sistema de correo adicional: <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> \<IP_address\> y \<domain_name\> son la dirección IP y el dominio del otro sistema de correo que envía correos en nombre de su dominio.|
   |7 |Cualquier sistema de correo electrónico (obligatorio)|Común. Todos los registros TXT de SPF acaban con este valor|`<enforcement rule>` <p> Puede ser uno de varios valores. Le recomendamos que use `-all`.|
   |

2. Si todavía no lo ha hecho, para formar el registro TXT de SPF, use la sintaxis de la tabla.

   Por ejemplo, si está hospedado por completo en Office 365, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 2 y 7, y tendría este aspecto:

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   **El ejemplo anterior es el registro TXT de SPF más común**. Este registro funciona para casi todo el mundo, independientemente de si el centro de datos de Microsoft se encuentra en Estados Unidos, en Europa (incluida Alemania) o en otra ubicación.

   Sin embargo, si ha adquirido Office 365 Alemania, parte de la nube de Microsoft Alemania, debe utilizar la instrucción incluir de la línea 4 en lugar de la línea 2. Por ejemplo, si está completamente hospedado en Office 365 Alemania, es decir, no tiene ningún servidor de correo local, el registro TXT de SPF incluiría las filas 1, 4 y 7, y tendría este aspecto:

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   Si ya ha implementado Office 365 y ha configurado sus registros TXT de SPF para su dominio personalizado y va a migrar a Office 365 Alemania, debe actualizar el registro TXT de SPF. Para ello, cambie `include:spf.protection.outlook.com` por `include:spf.protection.outlook.de`.

3. Una vez que haya formado el registro TXT de SPF, debe actualizar el registro en DNS. **Solo puede tener un registro TXT de SPF para un dominio.** Si existe un registro TXT de SPF, en vez de agregar un registro nuevo, debe actualizar el registro existente. Vaya a [Crear registros DNS para Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) y seleccione el vínculo para su host DNS.

4. Pruebe el registro TXT de SPF

## <a name="how-to-handle-subdomains"></a>¿Cómo se tratan los subdominios?

Es importante tener en cuenta que *necesita crear un registro independiente para cada subdominio, ya que los subdominios no heredan el registro SPF de su dominio de nivel superior*.

Se requiere un registro SPF comodín (`*.`) para cada dominio y subdominio con el fin de evitar que los atacantes envíen correo electrónico que dice ser de subdominios inexistentes. Por ejemplo:

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a>Solucionar problemas relacionados con SPF

¿Tiene problemas con el registro TXT de SPF? Lea [Solución de problemas: Procedimientos recomendados para SPF en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).

## <a name="what-does-spf-email-authentication-actually-do"></a>¿Qué hace realmente la autenticación de correo electrónico SPF?

SPF identifica qué servidores de correo pueden enviar correo en su nombre. Básicamente, SPF, junto con DKIM, DMARC y otras tecnologías soportadas por Office 365, ayudan a prevenir la suplantación de identidad y el phishing. SPF se agrega como un registro TXT que es usado por DNS para identificar qué servidores de correo pueden enviar correo en nombre de su dominio personalizado. Los sistemas de correo del destinatario se refieren al registro TXT de SPF para determinar si un mensaje de su dominio personalizado proviene de un servidor de mensajería autorizado.

Por ejemplo, supongamos que el dominio personalizado contoso.com usa Office 365. Le agrega un registro TXT de SPF que incluye los servidores de mensajería de Office 365 como servidores de correo legítimos para su dominio. Cuando el servidor de mensajería receptor obtiene un mensaje de joe@contoso.com, el servidor busca el registro TXT de SPF para contoso.com y averigua si el mensaje es válido. Si el servidor receptor descubre que el mensaje proviene de un servidor que no es ninguno de los servidores de mensajería de Office 365 indicados en el registro SPF, el servidor de correo receptor puede rechazar el mensaje como correo no deseado.

Además, si el dominio personalizado no tiene un registro TXT de SPF, algunos servidores de recepción pueden rechazar directamente el mensaje. Esto se debe a que el servidor de recepción no puede validar que los mensajes procedan de un servidor de mensajería autorizado.

Si ya ha configurado el correo para Office 365, ya ha incluido servidores de mensajería de Microsoft en DNS como un registro TXT de SPF. Sin embargo, en algunos casos puede que sea necesario actualizar el registro TXT de SPF en DNS. Por ejemplo:

- Antes, debía agregar un registro TXT de SPF diferente a su dominio personalizado si utilizaba SharePoint Online. Esto ya no es necesario. Este cambio debería reducir el riesgo de que los mensajes de notificación de SharePoint Online acaben en la carpeta de Correo no deseado. Actualice su registro SPF TXT si ha alcanzado el límite de 10 búsquedas y recibe errores como "Límite de búsqueda superado" y "Demasiados saltos".

- Tiene un entorno híbrido con Office 365 y Exchange local.

- Quiere configurar DKIM y DMARC (recomendado).

## <a name="more-information-about-spf"></a>Más información sobre SPF

Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, la suplantación de identidad, la solución de problemas y la manera en que Office 365 admite SPF, vea [Cómo funciona SPF para evitar la suplantación de identidad en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

## <a name="next-steps-dkim-and-dmarc"></a>Pasos siguientes: DKIM y DMARC

 SPF está diseñado para ayudar a evitar la suplantación de identidad, pero existen técnicas de suplantación de identidad contra las que SPF no puede protegerlo. Para defenderse de estos, una vez que haya configurado SPF, debe configurar DKIM y DMARC para Office 365.

El objetivo de la autenticación de correo electrónico [**DKIM**](use-dkim-to-validate-outbound-email.md) es demostrar que el contenido del correo no haya sido manipulado.

El objetivo de la autenticación de correo electrónico [**DMARC**](use-dmarc-to-validate-email.md) es asegurarse de que la información de SPF y DKIM coincida con la dirección De.

 Para obtener ejemplos avanzados y explicaciones más detalladas sobre la sintaxis admitida de SPF, consulte [Cómo funciona SPF para evitar la suplantación de identidad y el phishing en Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).

*Seleccione "Esta página" en "Comentarios" si tiene comentarios sobre esta documentación.*
