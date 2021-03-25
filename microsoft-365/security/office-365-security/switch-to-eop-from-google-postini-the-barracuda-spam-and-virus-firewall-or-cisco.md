---
title: Cambiar a EOP desde otro servicio de protección
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 81b75194-3b04-48da-8b81-951afbabedde
ms.custom:
- seo-marvel-apr2020
description: En este artículo, aprenderá a cambiar a Exchange Online Protection (EOP) desde un dispositivo de higiene de correo electrónico local o un servicio de protección basado en la nube.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e1a5df0b11c258ebe633868bb5abca5b20552a33
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2021
ms.locfileid: "51207346"
---
# <a name="switch-to-eop-from-google-postini-the-barracuda-spam-and-virus-firewall-or-cisco-ironport"></a>Cambiar a EOP desde Google Postini, Barracuda Spam y Virus Firewall o Cisco IronPort

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Se aplica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Plan 1 y Plan 2 de Microsoft Defender para Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

 El objetivo de este tema consiste en proporcionar los detalles sobre el proceso para cambiar a Protección en línea de Exchange (EOP) desde una aplicación de higiene de correo electrónico local o desde un servicio de protección basado en la nube, así como suministrar los recursos de ayuda necesarios para comenzar. Existen muchas soluciones de filtrado de correo no deseado, aunque el proceso para cambiar a EOP es similar en la mayoría de los casos.

Si es nuevo en EOP y desea leer una introducción a sus características antes de decidir cambiar, comience con el tema Información general de [Exchange Online Protection.](exchange-online-protection-overview.md)

Antes de cambiarse a EOP, es importante que piense si desea hospedar los buzones de correo protegidos por EOP en la nube, con Exchange Online, de forma local o en un escenario híbrido. (Por "híbrido" se entiende que algunos buzones de correo están hospedados de forma local y otros en Exchange Online). Los pasos de configuración necesarios para cada uno de estos escenarios de hospedaje (en la nube, en local o híbrido) pueden ser diferentes. Estas son algunas consideraciones que le pueden ayudar a elegir la implementación adecuada:

- Protección **de EOP** con buzones locales: este escenario es adecuado si tiene una infraestructura de hospedaje de correo existente que desea usar o tiene requisitos empresariales para mantener los buzones locales y desea usar EOP como protección de correo electrónico basada en la nube. En [Cambiar a EOP independiente](#switch-to-eop-standalone) se describe este escenario con más detalle.

- **Protección de EOP con** buzones de Exchange Online: este escenario es adecuado si desea la protección de EOP y todos los buzones hospedados en la nube. Además, le ayudará a reducir la complejidad, ya que no es necesario mantener servidores de mensajería locales. Este escenario se describe en [Cambiar a Exchange Online](#switch-to-exchange-online).

- **Protección de EOP con** buzones híbridos: quizás quiera buzones en la nube, pero debe mantener los buzones de algunos usuarios locales. Elija este escenario si desea hospedar algunos buzones de correo en local y otros en Exchange Online. En [Cambiar a una solución híbrida](#switch-to-a-hybrid-solution) se describe este escenario.

## <a name="switch-to-eop-standalone"></a>Cambiar a EOP independiente

Si actualmente hospeda sus buzones de correo en local y usa una aplicación de protección local o un servicio de protección de mensajería en la nube, puede cambiar a EOP para beneficiarse de sus características de protección y disponibilidad. Para configurar EOP en un escenario independiente, es decir, para hospedar los buzones de correo de forma local y usar EOP para proteger el correo electrónico, siga los pasos detallados en [Configurar un servicio de EOP](set-up-your-eop-service.md). En este tema se describen los pasos que hay que seguir para configurar la protección EOP. Entre ellos se incluye registrarse, agregar el dominio y configurar el flujo del correo con conectores.

## <a name="switch-to-exchange-online"></a>Cambiar a Exchange Online

Tal vez tenga buzones locales protegidos por una aplicación local y desee saltar a buzones hospedados en la nube de Exchange Online y protección EOP para aprovechar las características de protección y mensajería en la nube de Microsoft 365. Para empezar, puede registrarse en Microsoft 365 y agregar su dominio. Este escenario no requiere configurar conectores, ya que no hay ningún enrutamiento a buzones locales. Comience en [Obtener las últimas características avanzadas con Microsoft 365](https://www.microsoft.com/microsoft-365/business/compare-more-office-365-for-business-plans) para registrarse y familiarizarse con sus características.

Durante el proceso de instalación de Microsoft 365, creará los usuarios de buzones basados en la nube.

## <a name="switch-to-a-hybrid-solution"></a>Cambiar a una solución híbrida

Puede que desee mover solo una parte de los buzones de correo a la nube debido a los requisitos de su compañía o a consideraciones reglamentarias. Al implementar un escenario híbrido, los buzones de correo se pueden mover a la nube en función de las necesidades del negocio. La migración a un escenario híbrido con la protección EOP resulta más complicada que cambiar a un escenario en la nube. No obstante, Microsoft ofrece diversos recursos y un completo soporte para escenarios híbridos a fin de facilitar la conversión.

El mejor lugar para empezar, si está considerando una implementación híbrida, es Exchange Server [implementaciones híbridas.](/exchange/exchange-hybrid) Además, es importante comprender las diversas formas de enrutar el correo en un escenario híbrido. [El enrutamiento de transporte en implementaciones híbridas de Exchange](/exchange/transport-routing) explica cada tipo, por lo que puede elegir el mejor escenario de enrutamiento, en función de los requisitos empresariales.

## <a name="migration-planning"></a>Diseño de la migración

Cuando decida cambiar a EOP, asegúrese de considerar las siguientes áreas:

- **Reglas de** filtrado personalizadas: si tiene reglas de filtrado personalizadas o directivas empresariales para detectar correo no deseado específico, le recomendamos que pruebe EOP con la configuración predeterminada durante un período de tiempo antes de migrar las reglas. EOP ofrece protección contra correo no deseado a nivel empresarial con la configuración predeterminada, por lo que quizá no sea necesario migrar todas sus reglas a EOP. Evidentemente, si tiene reglas que ejecutan ciertas directivas empresariales personalizadas, podrá crearlas. [Las reglas de flujo de correo (reglas de transporte) de Exchange Online Protection](mail-flow-rules-transport-rules-0.md) proporcionan instrucciones detalladas para crear reglas de flujo de correo en EOP.

- **Listas de** direcciones IP permitidos y listas de direcciones IP bloqueados: si tiene listas de permisos por usuario y listas de bloqueo, espere un poco de tiempo para copiar las listas en EOP como parte del proceso de configuración. Para obtener más información acerca de la lista de direcciones IP permitidos y la lista de direcciones IP bloqueados, vea [Configure the connection filter policy](configure-the-connection-filter-policy.md).

- **Comunicación segura:** si tiene un partner que requiere mensajería cifrada, le recomendamos que lo configure en el Centro de administración de Exchange. Para configurar este escenario, vea Configurar conectores para el flujo de [correo seguro con una organización asociada.](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

> [!TIP]
> Al cambiar de una aplicación local a EOP, se puede dejar la aplicación o un servidor para que realice las comprobaciones de reglas de negocio. Por ejemplo, si el dispositivo realiza un filtrado personalizado en el correo saliente y desea que siga haciéndolo, puede configurar EOP para que envíe correo directamente al dispositivo para filtrarlo adicionalmente antes de enrutar a Internet.