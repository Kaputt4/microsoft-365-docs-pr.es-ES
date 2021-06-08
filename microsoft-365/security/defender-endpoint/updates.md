---
title: Administrar el proceso de implementación gradual para actualizaciones de Microsoft Defender
description: Obtenga información sobre el proceso de actualización gradual y los controles
keywords: actualización, proceso de actualización, controles, versión
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: f5db08e4eb98dd3fe6f7e8a84fb0c49e889fb73f
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809340"
---
#  <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Administrar el proceso de implementación gradual para actualizaciones de Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Microsoft Defender para punto de conexión](/microsoft-365/security/defender-endpoint/)


Es importante asegurarse de que los componentes del cliente estén actualizados para ofrecer capacidades de protección críticas y evitar ataques.

Las funcionalidades se proporcionan a través de varios componentes: 

- [Respuesta de detección & extremo](overview-endpoint-detection-response.md) 
- [Protección de última generación](microsoft-defender-antivirus-in-windows-10.md#microsoft-defender-antivirus-your-next-generation-protection) con [protección entregada en la nube](cloud-protection-microsoft-defender-antivirus.md) 
- [Reducción de superficie de ataque](overview-attack-surface-reduction.md)

Las actualizaciones se lanzan mensualmente mediante un proceso de lanzamiento gradual. Este proceso ayuda a habilitar la detección temprana de errores para detectar el impacto a medida que se produce y solucionarlo rápidamente antes de una implementación más grande. 

> [!NOTE]
> Para obtener más información sobre cómo controlar las actualizaciones de definiciones diarias, vea Programar Antivirus de Microsoft Defender de definición: Windows [seguridad | Microsoft Docs](manage-protection-update-schedule-microsoft-defender-antivirus.md). Las actualizaciones de definiciones garantizan que la protección de última generación pueda defenderse de las nuevas amenazas, incluso si la protección entregada en la nube no está disponible para el punto de conexión.

## <a name="microsoft-gradual-rollout-model"></a>Modelo de lanzamiento gradual de Microsoft

Se sigue el siguiente modelo de implementación gradual:

1. La primera versión se publica a los suscriptores del canal beta.
2. Después de la validación, los comentarios y las correcciones, iniciamos el proceso de implementación gradual de una manera limitada y a Los suscriptores del canal de vista previa primero.
3. A continuación, procedemos a liberar la actualización para el resto de la población global, escalando de 10 a 100 %.

Nuestros ingenieros supervisan continuamente el impacto y escalan los problemas para crear una solución según sea necesario.

## <a name="how-to-customize-your-internal-deployment-process"></a>Cómo personalizar el proceso de implementación interna

Si las máquinas reciben actualizaciones de Defender de Windows Update, el proceso de implementación gradual puede provocar que algunas de las máquinas reciban actualizaciones de Defender antes que otras. En la siguiente sección se explica cómo definir una estrategia que permita que las actualizaciones automáticas fluyan de forma diferente a grupos específicos de dispositivos aprovechando la configuración del canal de actualización.

> [!NOTE]
> Al planear tu propia versión gradual, asegúrate de tener siempre una selección de dispositivos suscritos a los canales de vista previa y por fases. Esto proporcionará a su organización y a Microsoft la oportunidad de evitar o encontrar y solucionar problemas específicos de su entorno.

Para las máquinas que reciben actualizaciones a través de, por ejemplo, Windows Server Update Services (WSUS) o Microsoft Endpoint Configuration Manager (MECM), hay más opciones disponibles para todas las actualizaciones de Windows, incluidas las opciones de Microsoft Defender para Endpoint.

- Obtenga más información sobre cómo usar una solución como WSUS, MECM para administrar la distribución y aplicación de actualizaciones en [Manage Antivirus de Microsoft Defender updates and apply baselines - Windows security | Microsoft Docs](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates).

## <a name="update-channels-for-monthly-updates"></a>Actualizar canales para actualizaciones mensuales

Puede asignar una máquina a un canal de actualización para definir la cadencia en la que una máquina recibe actualizaciones mensuales del motor y la plataforma.

Para obtener más información sobre cómo configurar actualizaciones, vea [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).

Los siguientes canales de actualización están disponibles:

| Nombre del canal  | Description  | Aplicación  |
|-|-|-|
| Canal beta: versión preliminar  | Probar actualizaciones antes que otras  | Los dispositivos establecidos en este canal serán los primeros en recibir nuevas actualizaciones mensuales. Seleccione Canal beta para participar en la identificación y la presentación de informes de problemas a Microsoft. Los dispositivos del Windows Insider Program se suscriben a este canal de forma predeterminada. Solo para su uso en entornos de prueba.  |
| Canal actual (vista previa)  | Obtener actualizaciones del canal actual **antes** durante la versión gradual  | Los dispositivos establecidos en este canal recibirán actualizaciones lo antes posible durante el ciclo de lanzamiento gradual. Sugerido para entornos de preproducción/validación.  |
| Canal actual (por fases)  | Obtener actualizaciones del canal actual más adelante durante la versión gradual  | Los dispositivos se ofrecerán actualizaciones más adelante durante el ciclo de lanzamiento gradual. Se sugiere aplicar a una parte pequeña y representativa de la población de dispositivos (~10%).  |
| Canal actual (ancho) | Obtener actualizaciones al final de la versión gradual  | Solo se ofrecerán actualizaciones a los dispositivos una vez completado el ciclo de lanzamiento gradual. Se recomienda aplicar a un amplio conjunto de dispositivos de la población de producción (~10-100%).  |
| (valor predeterminado)  |   | Si deshabilitas o no configuras esta directiva, el dispositivo permanecerá en Canal actual (predeterminado): mantenerse actualizado automáticamente durante el ciclo de lanzamiento gradual. Adecuado para la mayoría de los dispositivos.  |

### <a name="update-channels-for-daily-definition-updates"></a>Actualizar canales para actualizaciones de definiciones diarias

Puede asignar una máquina a un canal de actualización para definir la cadencia en la que una máquina recibe actualizaciones de definiciones diarias.
  
| Nombre del canal  | Description  | Aplicación  |
|-|-|-|
| Canal actual (por fases)  | Obtener actualizaciones del canal actual más adelante durante la versión gradual  | Los dispositivos se ofrecerán actualizaciones más adelante durante el ciclo de lanzamiento gradual. Se sugiere aplicar a una parte pequeña y representativa de la población de dispositivos (~10%).  |
| Canal actual (ancho) | Obtener actualizaciones al final de la versión gradual  | Los dispositivos se ofrecerán actualizaciones después del ciclo de lanzamiento gradual. Ideal para máquinas de centros de datos que solo reciben actualizaciones limitadas. Nota: esta configuración se aplica a todas las actualizaciones de Defender.  |
| (valor predeterminado)  |   | Si deshabilitas o no configuras esta directiva, el dispositivo permanecerá en Canal actual (predeterminado): mantenerse actualizado automáticamente durante el ciclo de lanzamiento gradual. Adecuado para la mayoría de los dispositivos  |

> [!NOTE]
> En caso de que desee forzar una actualización a la firma más reciente en lugar de aprovechar el retraso de tiempo, primero tendrá que quitar esta directiva.

## <a name="update-guidance"></a>Instrucciones de actualización

En la mayoría de los casos, la configuración recomendada al usar Windows Update es permitir que los puntos de conexión reciban y apliquen actualizaciones mensuales de Defender a medida que llegan. Esto proporciona el mejor equilibrio entre la protección y el posible impacto asociado con los cambios que pueden introducir.

Para entornos en los que es necesario un lanzamiento gradual más controlado de actualizaciones automáticas de Defender, considere un enfoque con grupos de implementación:

1. Participa en el Windows Insider o asigna un grupo de dispositivos al canal beta.
2. Designe un grupo piloto que opte por el Canal de vista previa, normalmente entornos de validación, para recibir actualizaciones nuevas antes de tiempo.
3. Designe un grupo de máquinas que reciban actualizaciones más adelante durante el lanzamiento gradual desde el canal por fases. Normalmente, esto sería un representante ~10% de la población.
4. Designe un grupo de máquinas que reciban actualizaciones una vez completado el ciclo de lanzamiento gradual. Por lo general, se trata de sistemas de producción importantes.

Para el resto de dispositivos, la configuración predeterminada es recibir nuevas actualizaciones a medida que llegan durante el proceso de implementación gradual de Microsoft y no se requiere ninguna configuración adicional. 

Adoptar este modelo:
- Permite probar las versiones anticipadas antes de que lleguen a un entorno de producción 
- Asegúrese de que el entorno de producción sigue recibindo actualizaciones periódicas y de garantizar la protección contra amenazas críticas.

## <a name="management-tools"></a>Herramientas de administración
Para crear su propio proceso de implementación gradual personalizado para actualizaciones mensuales, puede usar las siguientes herramientas:

- Directiva de grupo
- Microsoft Endpoint Manager
- PowerShell

Para obtener información detallada sobre cómo usar estas herramientas, consulte [Create a custom gradual rollout process for Microsoft Defender updates](configure-updates.md).
