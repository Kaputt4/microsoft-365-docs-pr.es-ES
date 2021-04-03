---
title: 'Informe de dispositivos vulnerables: administración de amenazas y vulnerabilidades'
description: Un informe que muestra tendencias de dispositivos vulnerables y estadísticas actuales. El objetivo es que comprendas la respiración y el alcance de la exposición del dispositivo.
keywords: mdatp-tvm dispositivos vulnerables, mdatp, tvm, reducir la exposición a amenazas & vulnerabilidad, reducir la amenaza y la vulnerabilidad, supervisar la configuración de seguridad
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: f481ddca897594bd73de9b5f4762903f23fb24c6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500458"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>Informe de dispositivos vulnerables: administración de amenazas y vulnerabilidades

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>¿Desea experimentar Microsoft Defender para endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

El informe muestra gráficos y gráficos de barras con tendencias de dispositivo vulnerables y estadísticas actuales. El objetivo es que comprendas la respiración y el alcance de la exposición del dispositivo. 

Para obtener acceso al informe en el Centro de seguridad de Microsoft Defender, vaya **a Informes > dispositivos vulnerables**

Hay dos columnas:

- Tendencias (con el tiempo). Puede mostrar los últimos 30 días, 3 meses, 6 meses o un intervalo de fechas personalizado.
- Hoy (información actual)

**Filtro:** puedes filtrar los datos por niveles de gravedad de vulnerabilidad, disponibilidad de vulnerabilidad, antigüedad de vulnerabilidad, plataforma del sistema operativo, versión de Windows 10 o grupo de dispositivos.

**Explorar en profundidad:** si hay una información que desea explorar más adelante, seleccione el gráfico de barras relevante para ver una lista filtrada de dispositivos en la página Inventario de dispositivos. Desde allí, puede exportar la lista.

## <a name="severity-level-graphs"></a>Gráficos de nivel de gravedad

Cada dispositivo se cuenta solo una vez de acuerdo con la vulnerabilidad más grave encontrada en ese dispositivo.

![Un gráfico de los niveles actuales de gravedad de vulnerabilidad del dispositivo y un gráfico que muestra los niveles con el tiempo.](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Gráficos de disponibilidad de vulnerabilidades

Cada dispositivo se cuenta solo una vez en función del nivel más alto de vulnerabilidad conocida.

![Un gráfico de disponibilidad actual de vulnerabilidades de seguridad del dispositivo y un gráfico que muestra la disponibilidad con el tiempo.](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>Gráficos de antigüedad de vulnerabilidad

Cada dispositivo se cuenta solo una vez en la fecha de publicación de vulnerabilidad más antigua. Las vulnerabilidades más antiguas tienen más posibilidades de ser aprovechadas.

![Un gráfico de la antigüedad de vulnerabilidad del dispositivo actual y un gráfico que muestra la antigüedad con el tiempo.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>Dispositivos vulnerables por gráficos de plataforma de sistema operativo

El número de dispositivos en cada sistema operativo que se exponen debido a vulnerabilidades de software.

![Un gráfico de dispositivos vulnerables actuales por plataforma del sistema operativo y un gráfico que muestra los dispositivos vulnerables de las plataformas del sistema operativo a lo largo del tiempo.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Dispositivos vulnerables por gráficos de versión de Windows 10

El número de dispositivos en cada versión de Windows 10 que se exponen debido a aplicaciones vulnerables u sistema operativo.

![Un gráfico de dispositivos vulnerables actuales de la versión de Windows 10 y un gráfico que muestra los dispositivos vulnerables de la versión de Windows 10 con el tiempo.](images/tvm-report-version.png)

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
