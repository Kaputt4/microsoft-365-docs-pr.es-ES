---
title: Crear indicadores para direcciones IP y URL/dominios
ms.reviewer: ''
description: Cree indicadores para direcciones IP y direcciones URL/dominios que definan la detección, prevención y exclusión de entidades.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.subservice: mde
search.appverid: met150
ms.openlocfilehash: 317258174d193c5448353604bae81f42797e01d2
ms.sourcegitcommit: 9b133379196da2b3a4bb311b07ff274f43780f68
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67690342"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Crear indicadores para direcciones IP y URL/dominios

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Defender para punto de conexión puede bloquear lo que Microsoft considera direcciones IP o direcciones URL malintencionadas, a través de Windows Defender SmartScreen para exploradores de Microsoft y de Protección de red para exploradores que no son de Microsoft o llamadas realizadas fuera de un explorador.

Microsoft ha administrado el conjunto de datos de inteligencia sobre amenazas para esto.

Al crear indicadores para direcciones IP y direcciones URL o dominios, ahora puede permitir o bloquear direcciones IP, direcciones URL o dominios en función de su propia inteligencia sobre amenazas. También puede advertir a los usuarios con un mensaje si abren una aplicación de riesgo. El mensaje no les impedirá usar la aplicación, pero puede proporcionar un mensaje personalizado y vínculos a una página de empresa que describa el uso adecuado de la aplicación. Los usuarios pueden omitir la advertencia y seguir usando la aplicación si lo necesitan.

Puede hacerlo a través de la página de configuración o por grupos de máquinas si considera que determinados grupos están más o menos en riesgo que otros.

> [!NOTE]
> No se admite la notación de enrutamiento de Inter-Domain sin clase (CIDR) para direcciones IP.

## <a name="before-you-begin"></a>Antes de empezar

Es importante comprender los siguientes requisitos previos antes de crear indicadores para IPS, direcciones URL o dominios:

- El bloqueo y la dirección URL/IP se basan en el componente de Defender para punto de conexión Network Protection para habilitarse en modo de bloque. Para obtener más información sobre la protección de red y las instrucciones de configuración, consulte [Habilitación de la protección de red](enable-network-protection.md).
- La versión de cliente de Antimalware debe ser 4.18.1906.x o posterior. 
- Compatible con máquinas en Windows 10, versión 1709 o posterior, Windows 11, Windows Server 2016, Windows Server 2012 R2, Windows Server 2019, Windows Server 2022 y dispositivos Android e iOS.

    > [!NOTE]
    > Windows Server 2016 y Windows Server 2012 R2 tendrán que incorporarse mediante las instrucciones de [Incorporación de servidores Windows](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016) para que esta característica funcione.

- Asegúrese de que **los indicadores de red personalizados están habilitados** en **Microsoft 365 Defender** \> **Configuración** \> **Características avanzadas**. Para obtener más información, consulte [Características avanzadas](advanced-features.md).
- Para obtener compatibilidad con indicadores en iOS, consulte [Microsoft Defender para punto de conexión en iOS](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).
- Para obtener compatibilidad con indicadores en Android, consulte [Microsoft Defender para punto de conexión en Android](/microsoft-365/security/defender-endpoint/android-configure#configure-custom-indicators).

> [!IMPORTANT]
> Solo se pueden agregar direcciones IP externas a la lista de indicadores. No se pueden crear indicadores para direcciones IP internas.
> Para escenarios de protección web, se recomienda usar las funcionalidades integradas de Microsoft Edge. Microsoft Edge aprovecha [La protección de red](network-protection.md) para inspeccionar el tráfico de red y permite bloques de TCP, HTTP y HTTPS (TLS).
> Si hay directivas de indicadores de dirección URL en conflicto, se aplica la ruta de acceso más larga. Por ejemplo, la directiva `https://support.microsoft.com/office` de indicador de dirección URL tiene prioridad sobre la directiva `https://support.microsoft.com`de indicador de dirección URL .

> [!NOTE]
> En el caso de procesos distintos de Microsoft Edge e Internet Explorer, los escenarios de protección web aprovechan la protección de red para la inspección y el cumplimiento:
>
> - Ip es compatible con los tres protocolos (TCP, HTTP y HTTPS (TLS))
> - Solo se admiten direcciones IP únicas (sin bloques CIDR ni intervalos IP) en indicadores personalizados
> - Las direcciones URL cifradas (ruta de acceso completa) solo se pueden bloquear en exploradores de primera entidad (Internet Explorer, Edge)
> - Las direcciones URL cifradas (solo FQDN) se pueden bloquear en exploradores de terceros (es decir, distintas de Internet Explorer, Edge)
> - Se pueden aplicar bloques de ruta de acceso de dirección URL completa para direcciones URL sin cifrar
>
> Puede haber hasta 2 horas de latencia (normalmente menos) entre el momento en que se realiza la acción y la dirección URL y la dirección IP bloqueadas.

Al usar el modo de advertencia, puede configurar los siguientes controles:

**Omisión de la capacidad**:

- Botón Permitir en Edge
- Botón Permitir en el sistema (exploradores que no son de Microsoft)
- Omitir el parámetro duration en el indicador
- Omisión de la aplicación en exploradores de Microsoft y que no son de Microsoft

**Dirección URL de redireccionamiento**:

- Parámetro url de redireccionamiento en el indicador
- Dirección URL de redireccionamiento en Edge
- Dirección URL de redireccionamiento en el sistema (exploradores que no son de Microsoft)

Para obtener más información, consulte [Control de las aplicaciones detectadas por Microsoft Defender para punto de conexión](/cloud-app-security/mde-govern).

## <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Creación de un indicador para direcciones IP, direcciones URL o dominios desde la página de configuración

1. En el panel de navegación, seleccione **Configuración** \> **Indicadores** de **puntos** \> de conexión (en **Reglas**).

2. Seleccione la pestaña **Direcciones IP, direcciones URL o dominios** .

3. Seleccione **Agregar elemento**.

4. Especifique los detalles siguientes:
   - Indicador: especifique los detalles de la entidad y defina la expiración del indicador.
   - Acción: especifique la acción que se va a realizar y proporcione una descripción.
   - Ámbito: defina el ámbito del grupo de máquinas.

5. Revise los detalles de la pestaña Resumen y haga clic en **Guardar**.

## <a name="related-topics"></a>Temas relacionados

- [Crear indicadores](manage-indicators.md)
- [Crear indicadores para los archivos](indicator-file.md)
- [Creación de indicadores basados en certificados](indicator-certificates.md)
- [Administrar indicadores](indicator-manage.md)
