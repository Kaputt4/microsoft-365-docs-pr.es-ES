---
title: Crear indicadores para direcciones IP y URL/dominios
ms.reviewer: ''
description: Cree indicadores para direcciones IP y direcciones URL/dominios que definan la detección, prevención y exclusión de entidades.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0b28d4088b8475794989d777bf58ccc7550b3f7c
ms.sourcegitcommit: d016e3bd30c0dd73c4cd3d804c0b6941b5eb3e87
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2021
ms.locfileid: "58683557"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Crear indicadores para direcciones IP y URL/dominios

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Desea experimentar Defender for Endpoint? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Defender for Endpoint puede bloquear lo que Microsoft considera direcciones IP o direcciones URL malintencionadas, a través de Windows Defender SmartScreen para exploradores de Microsoft y a través de Network Protection para exploradores que no son de Microsoft o llamadas realizadas fuera de un explorador.

Microsoft ha administrado el conjunto de datos de inteligencia de amenazas para esto.

Al crear indicadores para direcciones IP y direcciones URL o dominios, ahora puede permitir o bloquear direcciones IP, direcciones URL o dominios basados en su propia inteligencia de amenazas. También puedes advertir a los usuarios con un mensaje si abren una aplicación arriesgada. El mensaje no les impedirá usar la aplicación, pero puedes proporcionar un mensaje personalizado y vínculos a una página de empresa que describe el uso adecuado de la aplicación. Los usuarios aún pueden omitir la advertencia y seguir usando la aplicación si lo necesitan.


Puedes hacerlo a través de la página de configuración o por grupos de máquinas si consideras que determinados grupos están más o menos en riesgo que otros.

> [!NOTE]
> No se admite Inter-Domain de enrutamiento sin clases (CIDR) para direcciones IP.

## <a name="before-you-begin"></a>Antes de empezar
Es importante comprender los siguientes requisitos previos antes de crear indicadores para IPS, direcciones URL o dominios:

- La dirección URL/IP permiten y bloquean la protección de red del componente Defender for Endpoint para habilitarse en modo de bloqueo. Para obtener más información sobre la protección de red y las instrucciones de configuración, vea [Enable network protection](enable-network-protection.md).
- La versión del cliente Antimalware debe ser 4.18.1906.x o posterior.
- Compatible con máquinas en Windows 10, versión 1709 o posterior.
- Asegúrese de **que los indicadores de red personalizados** están **habilitados Microsoft 365 Defender > Configuración > endpoints > características avanzadas**. Para obtener más información, vea [Características avanzadas](advanced-features.md).
- Para obtener compatibilidad con indicadores en iOS, vea [Configure custom indicators](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).

> [!IMPORTANT]
> Solo se pueden agregar direcciones IP externas a la lista de indicadores. Los indicadores no se pueden crear para ip internas.
> Para escenarios de protección web, se recomienda usar las funciones integradas en Microsoft Edge. Microsoft Edge aprovecha [Network Protection para](network-protection.md) inspeccionar el tráfico de red y permite bloques para TCP, HTTP y HTTPS (TLS).
> Si hay directivas de indicador de dirección URL en conflicto, se aplica la ruta de acceso más larga. Por ejemplo, la directiva de indicador de dirección URL `https:\\support.microsoft.com/office` tiene prioridad sobre la directiva de indicador de dirección URL `https:\\support.microsoft.com` .

> [!NOTE]
> Para todos los demás procesos, los escenarios de protección web aprovechan la protección de red para la inspección y la aplicación:
>
> - La IP es compatible con los tres protocolos
> - Solo se admiten direcciones IP únicas (sin bloques CIDR ni intervalos IP)
> - Las direcciones URL cifradas (ruta de acceso completa) solo se pueden bloquear en exploradores de terceros (Internet Explorer, Edge)
> - Las direcciones URL cifradas (solo FQDN) se pueden bloquear fuera de los exploradores de terceros (Internet Explorer, Edge)
> - Los bloques de ruta de acceso url completos se pueden aplicar en el nivel de dominio y todas las direcciones URL sin cifrar
>
> Puede haber hasta 2 horas de latencia (normalmente menos) entre el momento en que se realiza la acción y la dirección URL e IP bloqueadas.

Al usar el modo de advertencia, puede configurar los siguientes controles:

**Capacidad de omisión**:

- Botón Permitir en edge
- Botón Permitir en notificaciones del sistema (exploradores que no son de Microsoft)
- Parámetro de duración de omisión en el indicador
- Omitir la aplicación en exploradores de Microsoft y no microsoft

**Dirección URL de redireccionamiento:**

- Parámetro de dirección URL de redireccionamiento en el indicador
- Dirección URL de redireccionamiento en el perímetro
- Dirección URL de redireccionamiento en notificaciones del sistema (exploradores que no son de Microsoft)

Para obtener más información, vea [Govern apps discovered by Microsoft Defender for Endpoint](/cloud-app-security/mde-govern).

## <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Crear un indicador de direcciones IP, direcciones URL o dominios desde la página de configuración

1. En el panel de navegación, **seleccione Configuración** \> **indicadores** de puntos de \> **conexión** (en **Reglas**).

2. Seleccione la **pestaña Direcciones IP o DIRECCIONES URL/Dominios.**

3. Seleccione **Agregar elemento**.

4. Especifique los siguientes detalles:
   - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
   - Action: especifique la acción que se va a realizar y proporcione una descripción.
   - Ámbito: defina el ámbito del grupo de máquinas.

5. Revise los detalles de la pestaña Resumen y, a continuación, haga clic **en Guardar**.

## <a name="related-topics"></a>Temas relacionados

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para los archivos](indicator-file.md)
- [Crear indicadores basados en certificados](indicator-certificates.md)
- [Administrar indicadores](indicator-manage.md)
