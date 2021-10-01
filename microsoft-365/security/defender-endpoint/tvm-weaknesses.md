---
title: 'Vulnerabilidades en mi organización: Administración de amenazas y vulnerabilidades'
description: Enumera el identificador de vulnerabilidades y exposiciones (CVE) común de las debilidades encontradas en el software que se ejecuta en la organización. Detectada por la funcionalidad de Microsoft Defender para Administración de amenazas y vulnerabilidades punto de conexión.
keywords: Microsoft Defender para endpoint threat & administración de vulnerabilidades, Administración de amenazas y vulnerabilidades, Microsoft Defender for Endpoint tvm weaknesses page, finding weaknesses through tvm, tvm vulnerability list, vulnerability details in tvm
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 13391bb906f2d056d4c554d52ffcf1ed8b6a6e2b
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042751"
---
# <a name="vulnerabilities-in-my-organization---threat-and-vulnerability-management"></a>Vulnerabilidades en mi organización: Administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Quiere experimentar Microsoft Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-portaloverview-abovefoldlink)

Threat y administración de vulnerabilidades usa las mismas señales en Defender for Endpoint's endpoint protection para examinar y detectar vulnerabilidades.

En la página Puntos débiles se enumeran las vulnerabilidades de software a las que se exponen los dispositivos al enumerar el identificador vulnerabilidades y **exposiciones** comunes (CVE). También puede ver la gravedad, la clasificación del Sistema de puntuación de vulnerabilidad común (CVSS), la prevalencia en su organización, la vulneración correspondiente, las perspectivas de amenazas y mucho más.

> [!NOTE]
> Si no hay ningún identificador CVE oficial asignado a una vulnerabilidad, el nombre de vulnerabilidad se asigna mediante Administración de amenazas y vulnerabilidades.

> [!TIP]
> Para obtener correos electrónicos sobre nuevos eventos de vulnerabilidad, consulte [Configure vulnerability email notifications in Microsoft Defender for Endpoint](configure-vulnerability-email-notifications.md)

## <a name="navigate-to-the-weaknesses-page"></a>Vaya a la página Puntos débiles

Acceder a la página Puntos débiles de varias maneras diferentes:

- Selección de **puntos débiles** en el menú de navegación **Administración** de vulnerabilidades en el [Microsoft 365 Defender portal] (portal-overview.md)
- Búsqueda global

### <a name="navigation-menu"></a>Menú navegación

Vaya al menú **de navegación Administración** de vulnerabilidades y seleccione Puntos **débiles** para abrir la lista de CVEs.

### <a name="vulnerabilities-in-global-search"></a>Vulnerabilidades en la búsqueda global

1. Vaya al menú desplegable búsqueda global.
2. Seleccione **Vulnerabilidad y** clave en el identificador de vulnerabilidades y exposiciones comunes (CVE) que está buscando y, a continuación, seleccione el icono de búsqueda. La **página Puntos débiles** se abre con la información CVE que está buscando.
![Cuadro de búsqueda global con la opción desplegable "vulnerabilidad" seleccionada y un cve de ejemplo.](images/tvm-vuln-globalsearch.png)
3. Selecciona CVE para abrir un panel desplegable con más información, incluida la descripción de vulnerabilidad, los detalles, las perspectivas de amenazas y los dispositivos expuestos.

Para ver el resto de las vulnerabilidades en la página Puntos **débiles,** escriba CVE y, a continuación, seleccione buscar.

## <a name="weaknesses-overview"></a>Información general sobre debilidades

Corrija las vulnerabilidades de los dispositivos expuestos para reducir el riesgo para los activos y la organización. Si la **columna Dispositivos expuestos** muestra 0, significa que no estás en riesgo.

![Página de aterrizaje Debilidades.](images/tvm-weaknesses-overview.png)

### <a name="breach-and-threat-insights"></a>Información sobre infracciones y amenazas

Vea cualquier información relacionada sobre infracciones y amenazas en la columna **Amenaza** cuando los iconos estén de color rojo.

 > [!NOTE]
 > Priorice siempre las recomendaciones asociadas con amenazas continuas. Estas recomendaciones se marcan con el icono de información de amenazas ![ Dibujo simple de un error rojo.](images/tvm_bug_icon.png) e icono de información de vulneración ![ Dibujo simple de una flecha que alcanza un destino. ](images/tvm_alert_icon.png) .

El icono de información de infracciones se resalta si hay una vulnerabilidad encontrada en su organización.
![Ejemplo de un texto de información de infracciones que podría aparecer al pasar el mouse sobre el icono. Este dice que "la posible alerta activa está asociada con esta recomendación.](images/tvm-breach-insights.png)

El icono de información sobre amenazas se resalta si hay vulnerabilidades asociadas en la vulnerabilidad encontrada en la organización. Si se mantiene el mouse sobre el icono, se muestra si la amenaza forma parte de un kit de vulnerabilidades o está conectada a grupos de actividades o campañas persistentes avanzadas específicos. Cuando está disponible, hay un vínculo a un informe de Análisis de amenazas con noticias de explotación de día cero, divulgaciones o avisos de seguridad relacionados.

![Threat insights text that could show up when hovering over icon. Este tiene varios puntos de viñeta y texto vinculado.](images/tvm-threat-insights.png)

### <a name="gain-vulnerability-insights"></a>Obtener información sobre vulnerabilidades

Si seleccionas una CVE, se abrirá un panel desplegable con más información, como la descripción de vulnerabilidad, los detalles, las perspectivas de amenazas y los dispositivos expuestos.

- La categoría "Característica del sistema operativo" se muestra en escenarios relevantes
- Puedes ir a la recomendación de seguridad relacionada para cada CVE con dispositivo expuesto

 ![Ejemplo de flyout de debilidad.](images/tvm-weakness-flyout400.png)

### <a name="software-that-isnt-supported"></a>Software que no es compatible

Las CVE para software que actualmente no son compatibles con amenazas & administración de vulnerabilidades todavía está presente en la página Debilidades. Dado que el software no es compatible, solo estarán disponibles datos limitados.

La información de dispositivo expuesta no estará disponible para las CVE con software no compatible. Filtre por software no compatible seleccionando la opción "No disponible" en la sección "Dispositivos expuestos".

:::image type="content" alt-text="Filtro de dispositivos expuestos." source="images/tvm-exposed-devices-filter.png":::

## <a name="view-common-vulnerabilities-and-exposures-cve-entries-in-other-places"></a>Ver entradas de vulnerabilidades y exposiciones comunes (CVE) en otros lugares

### <a name="top-vulnerable-software-in-the-dashboard"></a>Software vulnerable superior en el panel

1. Ve al panel [de Administración de amenazas y vulnerabilidades y](tvm-dashboard-insights.md) desplázate hacia abajo hasta el widget de software **vulnerable** superior. Verás el número de vulnerabilidades encontradas en cada software, junto con la información sobre amenazas y una vista de alto nivel de la exposición del dispositivo con el tiempo.

    ![Tarjeta de software vulnerable superior con cuatro columnas: software, debilidades, amenazas, dispositivos expuestos.](images/tvm-top-vulnerable-software500.png)

2. Seleccione el software que desea investigar para ir a una página de investigación.

3. Seleccione la **pestaña Vulnerabilidades detectadas.**

4. Seleccione la vulnerabilidad que desea investigar para obtener más información sobre los detalles de vulnerabilidad

    ![Windows Información general sobre server 2019.](images/windows-server-drilldown.png)

### <a name="discover-vulnerabilities-in-the-device-page"></a>Detectar vulnerabilidades en la página del dispositivo

Ver información de puntos débiles relacionados en la página del dispositivo.

1. Ve a la barra Microsoft 365 Defender menú de navegación y, a continuación, selecciona el icono del dispositivo. Se **abre la página Inventario** de dispositivos.

2. En la **página Inventario de** dispositivos, selecciona el nombre del dispositivo que quieras investigar.

    ![Lista de dispositivos con el dispositivo seleccionado para investigar.](images/tvm_machinetoinvestigate.png)

3. La página del dispositivo se abrirá con detalles y opciones de respuesta para el dispositivo que quieras investigar.

4. Seleccione **Vulnerabilidades detectadas**.

   :::image type="content" alt-text="Página del dispositivo con detalles y opciones de respuesta." source="images/tvm-discovered-vulnerabilities.png" lightbox="images/tvm-discovered-vulnerabilities.png":::

5. Seleccione la vulnerabilidad que desea investigar para abrir un panel desplegable con los detalles de CVE, como: descripción de vulnerabilidad, información sobre amenazas y lógica de detección.

#### <a name="cve-detection-logic"></a>Lógica de detección CVE

De forma similar a la evidencia de software, ahora mostramos la lógica de detección que aplicamos en un dispositivo para decir que es vulnerable. La nueva sección se denomina "Lógica de detección" (en cualquier vulnerabilidad detectada en la página del dispositivo) y muestra la lógica y el origen de detección.

La categoría "Característica del sistema operativo" también se muestra en escenarios relevantes. Una CVE afectaría a los dispositivos que ejecutan un sistema operativo vulnerable solo si se habilita un componente del sistema operativo específico. Supongamos que Windows Server 2019 o Windows Server 2022 tiene vulnerabilidad en su componente DNS. Con esta nueva funcionalidad, solo adjuntaremos esta CVE a los dispositivos de Windows Server 2019 y Windows Server 2022 con la funcionalidad DNS habilitada en su sistema operativo.

:::image type="content" alt-text="Ejemplo de lógica de detección que enumera el software detectado en el dispositivo y los KB." source="images/tvm-cve-detection-logic.png":::

## <a name="report-inaccuracy"></a>Imprecisión de informe

Informe de un falso positivo cuando vea información imprecisa, inexacta o incompleta. También puede informar sobre las recomendaciones de seguridad que ya se han corregido.

1. Abra CVE en la página Puntos débiles.
2. Seleccione **Informar de imprecisión y** se abrirá un panel desplegable.
3. Seleccione la categoría de imprecisión en el menú desplegable y rellene la dirección de correo electrónico y los detalles de imprecisión.
4. Seleccione **Enviar**. Sus comentarios se envían inmediatamente a los Administración de amenazas y vulnerabilidades expertos.

## <a name="related-articles"></a>Artículos relacionados

- [Información general sobre amenazas administración de vulnerabilidades amenazas](next-gen-threat-and-vuln-mgt.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
- [Inventario de software](tvm-software-inventory.md)
- [Panel de Conclusiones](tvm-dashboard-insights.md)
- [Ver y organizar la lista de Microsoft Defender para dispositivos de punto de conexión](machines-view-overview.md)
