---
title: Administrar el proceso de implementación gradual para las actualizaciones de Microsoft Defender
description: Más información sobre el proceso de actualización gradual y los controles
keywords: actualización, proceso de actualización, controles, versión
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d8a500babf581cd70b92a39b32a3be0bb5d4acd3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789390"
---
# <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Administrar el proceso de implementación gradual para las actualizaciones de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Antivirus de Microsoft Defender

**Plataformas**
- Windows

Es importante asegurarse de que los componentes de cliente estén actualizados para ofrecer funcionalidades críticas de protección y evitar ataques.

Las funcionalidades se proporcionan a través de varios componentes:

- [Respuesta & de detección de puntos de conexión](overview-endpoint-detection-response.md)
- [Protección de última generación](microsoft-defender-antivirus-windows.md) con [protección entregada en la nube](cloud-protection-microsoft-defender-antivirus.md)
- [Reducción de la superficie expuesta a ataques](overview-attack-surface-reduction.md)

Las actualizaciones se publican mensualmente mediante un proceso de versión gradual. Este proceso ayuda a habilitar la detección temprana de errores para detectar el impacto a medida que se produce y abordarlo rápidamente antes de un lanzamiento mayor.

> [!NOTE]
> Para obtener más información sobre cómo controlar las actualizaciones diarias de inteligencia de seguridad, consulte [Programación Antivirus de Microsoft Defender actualizaciones de protección](manage-protection-update-schedule-microsoft-defender-antivirus.md). Las actualizaciones garantizan que la protección de próxima generación pueda defenderse frente a nuevas amenazas, incluso si la protección proporcionada en la nube no está disponible para el punto de conexión.

## <a name="microsoft-gradual-rollout-model"></a>Modelo de lanzamiento gradual de Microsoft

Se sigue el siguiente modelo de implementación gradual para las actualizaciones mensuales de Defender:

1. La primera versión sale a los suscriptores del canal Beta.
2. Después de la validación, los comentarios y las correcciones, iniciamos el proceso de implementación gradual de una manera limitada y en primer lugar a los suscriptores del canal de vista previa.
3. A continuación, vamos a liberar la actualización al resto de la población global, escalando horizontalmente del 10 al 100 %.

Nuestros ingenieros supervisan continuamente el impacto y escalan los problemas para crear una corrección según sea necesario.

## <a name="how-to-customize-your-internal-deployment-process"></a>Personalización del proceso de implementación interno

Si las máquinas reciben actualizaciones de Defender de Windows Update, el proceso de implementación gradual puede dar lugar a que algunas de las máquinas reciban actualizaciones de Defender antes que otras. En la sección siguiente se explica cómo definir una estrategia que permita que las actualizaciones automáticas fluyan de forma diferente a grupos específicos de dispositivos aprovechando la configuración del canal de actualización.

> [!NOTE]
> Al planear su propia versión gradual, asegúrese de tener siempre una selección de dispositivos suscritos a los canales en versión preliminar y preconfigurados. Esto proporcionará a su organización, así como a Microsoft, la oportunidad de evitar o buscar y corregir problemas específicos de su entorno.

Para las máquinas que reciben actualizaciones a través de, por ejemplo, Windows Server Update Services (WSUS) o Microsoft Endpoint Configuration Manager (MECM), hay más opciones disponibles para todas las actualizaciones de Windows, incluidas las opciones para Microsoft Defender para punto de conexión.

- Obtenga más información sobre cómo usar una solución como WSUS, MECM para administrar la distribución y aplicación de actualizaciones en [Administración de actualizaciones Antivirus de Microsoft Defender y aplicación de líneas base Windows seguridad](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Actualizar canales para actualizaciones mensuales

Puede asignar una máquina a un canal de actualización para definir la cadencia en la que una máquina recibe actualizaciones mensuales del motor y de la plataforma.

Para obtener más información sobre cómo configurar actualizaciones, consulte [Creación de un proceso de implementación gradual personalizado para las actualizaciones de Microsoft Defender](configure-updates.md).

Están disponibles los siguientes canales de actualización:

<br>

****

|Nombre de canal|Descripción|Aplicación|
|---|---|---|
|Canal beta: versión preliminar|Prueba de actualizaciones antes que otros usuarios|Los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones mensuales. Seleccione Canal beta para participar en la identificación y la notificación de problemas a Microsoft. Los dispositivos del programa Windows Insider están suscritos a este canal de forma predeterminada. Solo para su uso en entornos de prueba.|
|Canal actual (vista previa)|Obtener actualizaciones del canal actual **anteriormente** durante la versión gradual|A los dispositivos establecidos en este canal se les ofrecerán las actualizaciones más pronto durante el ciclo de versión gradual. Se recomienda para entornos de preproducción y validación.|
|Canal actual (preconfigurado)|Obtener actualizaciones del canal actual más adelante durante la versión gradual|Se ofrecerán actualizaciones a los dispositivos más adelante durante el ciclo de versión gradual. Se recomienda aplicar a una parte pequeña y representativa de la población del dispositivo (~10 %).|
|Canal actual (amplio)|Obtener actualizaciones al final de la versión gradual|Solo se ofrecerán actualizaciones a los dispositivos una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (aproximadamente entre el 10 y el 100 %).|
|Crítico: retraso de tiempo|Retraso de las actualizaciones de Defender|Se ofrecerán actualizaciones a los dispositivos con un retraso de 48 horas. Mejor para máquinas de centro de datos que solo reciben actualizaciones limitadas. Solo se sugiere para entornos críticos.|
|(valor predeterminado)||Si deshabilita o no configura esta directiva, el dispositivo permanecerá en Canal actual (valor predeterminado): manténgase actualizado automáticamente durante el ciclo de versión gradual. Adecuado para la mayoría de los dispositivos.|
|

### <a name="update-channels-for-daily-updates"></a>Actualizar canales para actualizaciones diarias

También puede asignar una máquina a un canal para definir la cadencia en la que recibe actualizaciones diarias. Tenga en cuenta que, a diferencia del proceso mensual, no hay ningún canal Beta y este ciclo de lanzamiento gradual se produce varias veces al día.

<br>

****

|Nombre de canal|Descripción|Aplicación|
|---|---|---|
|Canal actual (preconfigurado)|Obtener actualizaciones del canal actual más adelante durante la versión gradual|Se ofrecerán actualizaciones a los dispositivos más adelante durante el ciclo de versión gradual. Se recomienda aplicar a una parte pequeña y representativa de la población del dispositivo (~10 %).|
|Canal actual (amplio)|Obtener actualizaciones al final de la versión gradual|Se ofrecerán actualizaciones a los dispositivos después del ciclo de versión gradual. Mejor para máquinas de centro de datos que solo reciben actualizaciones limitadas. Nota: Esta configuración se aplica a todas las actualizaciones de Defender.|
|(valor predeterminado)||Si deshabilita o no configura esta directiva, el dispositivo permanecerá en Canal actual (valor predeterminado): manténgase actualizado automáticamente durante el ciclo de versión gradual. Adecuado para la mayoría de los dispositivos|
|

> [!NOTE]
> En caso de que desee forzar una actualización a la firma más reciente en lugar de aprovechar el retraso de tiempo, primero tendrá que quitar esta directiva.

## <a name="update-guidance"></a>Guía de actualización

En la mayoría de los casos, la configuración recomendada al usar Windows Update es permitir que los puntos de conexión reciban y apliquen actualizaciones mensuales de Defender a medida que llegan. Esto proporciona el mejor equilibrio entre la protección y el posible impacto asociado a los cambios que pueden introducir.

En entornos en los que se necesita una implementación gradual más controlada de las actualizaciones automáticas de Defender, considere la posibilidad de un enfoque con grupos de implementación:

1. Participe en el programa Windows Insider o asigne un grupo de dispositivos al canal beta.
2. Designe un grupo piloto que opte por el canal de versión preliminar, normalmente entornos de validación, para recibir nuevas actualizaciones al principio.
3. Designe un grupo de máquinas que reciban actualizaciones más adelante durante el lanzamiento gradual del canal preconfigurado. Normalmente, esto sería un representante del ~10 % de la población.
4. Designe un grupo de máquinas que reciban actualizaciones una vez completado el ciclo de lanzamiento gradual. Suelen ser sistemas de producción importantes.

Para el resto de dispositivos, la configuración predeterminada es recibir nuevas actualizaciones a medida que llegan durante el proceso de implementación gradual de Microsoft y no se requiere ninguna configuración adicional.

Adopción de este modelo:

- Permite probar versiones tempranas antes de que lleguen a un entorno de producción
- Asegúrese de que el entorno de producción sigue recibiendo actualizaciones periódicas y de garantizar la protección contra amenazas críticas.

## <a name="management-tools"></a>Herramientas de administración

Para crear su propio proceso de implementación gradual personalizado para las actualizaciones mensuales, puede usar las siguientes herramientas:

- Directiva de grupo
- Administrador de puntos de conexión de Microsoft
- PowerShell

Para obtener más información sobre cómo usar estas herramientas, consulte [Creación de un proceso de implementación gradual personalizado para las actualizaciones de Microsoft Defender](configure-updates.md).

> [!TIP]
> Si busca información relacionada con antivirus para otras plataformas, consulte:
> - [Establecer preferencias para Microsoft Defender para punto de conexión en macOS](mac-preferences.md)
> - [Microsoft Defender para punto de conexión en Mac](microsoft-defender-endpoint-mac.md)
> - [Configuración de directivas de antivirus de macOS para Antivirus de Microsoft Defender para Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Establecer preferencias para Microsoft Defender para punto de conexión en Linux](linux-preferences.md)
> - [Microsoft Defender para punto de conexión en Linux](microsoft-defender-endpoint-linux.md)
> - [Configuración de características de Defender para punto de conexión en Android](android-configure.md)
> - [Configuración de Microsoft Defender para punto de conexión en las características de iOS](ios-configure-features.md)