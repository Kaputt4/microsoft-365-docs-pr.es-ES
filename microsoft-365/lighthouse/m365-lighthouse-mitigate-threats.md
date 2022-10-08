---
title: Mitigación de amenazas en Microsoft 365 Lighthouse con Microsoft Defender Antivirus
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
ms-reviewer: algreer
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre la mitigación de amenazas con Microsoft Defender Antivirus.
ms.openlocfilehash: d8a772b3c49525149f88c5990479faee92f04be8
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68188821"
---
# <a name="mitigate-threats-in-microsoft-365-lighthouse-with-microsoft-defender-antivirus"></a>Mitigación de amenazas en Microsoft 365 Lighthouse con Microsoft Defender Antivirus

Microsoft 365 Lighthouse permite a los partners investigar y mitigar las amenazas en todos los inquilinos. También puede iniciar exámenes antivirus en dispositivos, asegurarse de que los dispositivos obtienen las actualizaciones más recientes de Microsoft Defender Antivirus y revisar las acciones pendientes después de los exámenes antivirus. Lighthouse solo admite dispositivos que ejecutan Windows 10 o posterior.

## <a name="before-you-begin"></a>Antes de empezar

- Microsoft 365 Lighthouse solo se implementa en el inquilino del asociado, no en los inquilinos del cliente, sino que se asegura de que usted y los inquilinos del cliente cumplen los requisitos enumerados en [los requisitos de Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

- Los usuarios deben ejecutar Microsoft Defender Antivirus (incluido con Windows). Lighthouse no admite software antivirus que no sea de Microsoft. Para obtener más información, vea [Activar Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows).

- Debe ser administrador global en el inquilino de asociado en el que está iniciando sesión.

## <a name="investigate-active-threats"></a>Investigación de amenazas activas

Para investigar una amenaza específica:

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de amenazas de** **dispositivos** > .

2. Seleccione la pestaña **Amenazas** .

3. En la lista de amenazas, seleccione la amenaza que desea investigar.

El panel de detalles de amenazas proporciona la siguiente información:

| Categoría                                      | Definición                                                                                                   |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Dispositivo e inquilino                             | El nombre del dispositivo y el inquilino donde se encontró la amenaza. Seleccione el nombre del dispositivo para ver información adicional. |
| Estado de la amenaza                                 | Estado de la amenaza.                                                                                    |
| Tipo de amenaza                                   | Tipo de amenaza.                                                                                              |
| Gravedad de la amenaza                               | Gravedad de la amenaza (grave, alta, moderada, baja, desconocida)                                                    |
| Instancias                                     | Número de instancias de esta amenaza presentes en el dispositivo.                                                    |
| Primera vez detectada                                | La primera vez que se detectó la amenaza en este dispositivo.                                                           |
| Documentación                                 | Vínculo a información adicional sobre la amenaza.                                                             |
| Otros dispositivos de este inquilino con esta amenaza | Una lista de otros dispositivos del mismo inquilino con la misma amenaza activa.                                      |
| Otros inquilinos con esta amenaza                | Una lista de otros inquilinos con la misma amenaza activa.                                                         |

Para investigar las amenazas en un dispositivo específico:

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de amenazas de** **dispositivos** > .

2. Seleccione la pestaña **Protección antivirus** .

3. Seleccione un dispositivo de la lista.

4. En el panel de detalles del dispositivo, seleccione la pestaña **Amenazas actuales** .

Lighthouse muestra todas las amenazas que se encuentran en el dispositivo. Para ver los detalles, seleccione la amenaza.

## <a name="scan-for-threats-on-a-device"></a>Buscar amenazas en un dispositivo

Un examen rápido busca ubicaciones comunes en las que podría haber malware, como claves del Registro y carpetas de inicio conocidos. Un examen completo busca en todo el dispositivo. En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para los exámenes programados.

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de amenazas de** **dispositivos** > .

2. Seleccione la pestaña **Protección antivirus** .

3. En la lista de dispositivos, seleccione un dispositivo.

4. En el panel de detalles del dispositivo, seleccione **Ejecutar examen completo** o **Ejecutar examen rápido**.

También puede examinar varios dispositivos seleccionando la casilla situada junto a cada nombre de dispositivo de la lista y, a continuación, seleccione **Ejecutar examen completo** o **Ejecutar examen rápido**.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obtención de actualizaciones para Microsoft Defender Antivirus

Para actualizar Microsoft Defender Antivirus en un único dispositivo:

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de amenazas de** **dispositivos** > .

2. Seleccione la pestaña **Protección antivirus** .

3. En la lista de dispositivos, seleccione un dispositivo.

4. En el panel de detalles del dispositivo, seleccione **Actualizar antivirus**.

Para obtener actualizaciones para varios dispositivos, active la casilla situada junto a cada nombre de dispositivo de la lista y, a continuación, seleccione **Actualizar antivirus**.

Si necesita crear una nueva directiva, seleccione **Actualizar directiva** en el panel de detalles del dispositivo. Lighthouse le redirigirá a Microsoft Endpoint Manager (MEM). Para obtener más información sobre cómo crear una directiva, vea [Crear una directiva de cumplimiento en Microsoft Intune](/mem/intune/protect/create-compliance-policy).

## <a name="check-pending-antivirus-actions-on-a-device"></a>Comprobación de las acciones antivirus pendientes en un dispositivo

Cuando se aplican acciones consecutivas a un dispositivo, recibirá un mensaje de acción pendiente. Para comprobar qué acciones están pendientes en un dispositivo:

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de amenazas de** **dispositivos** > .

2. Seleccione la pestaña **Protección antivirus** .

3. En la lista de dispositivos, seleccione un dispositivo.

4. En el panel de detalles del dispositivo, seleccione la pestaña **Estado de la acción del dispositivo** para ver las acciones pendientes.

## <a name="restart-a-device"></a>Reiniciar un dispositivo

Algunas actualizaciones pueden requerir que un dispositivo se reinicie para instalarse correctamente.

1. En el panel de navegación izquierdo de Lighthouse, seleccione Administración **de amenazas de** **dispositivos** > .

2. Seleccione la pestaña **Protección antivirus** .

3. En la lista de dispositivos, seleccione un dispositivo.

4. En el panel de detalles del dispositivo, seleccione **Reiniciar dispositivo**.

También puede reiniciar varios dispositivos si selecciona la casilla situada junto a cada nombre de dispositivo de la lista y, a continuación, seleccione **Reiniciar dispositivo**.

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[Información general de la página Administración de amenazas en Microsoft 365 Lighthouse](m365-lighthouse-threat-management-page-overview.md) (artículo)\
[Crear una directiva de cumplimiento en Microsoft Intune](/mem/intune/protect/create-compliance-policy) (artículo)\
[Activar Microsoft Defender Antivirus](/mem/intune/user-help/turn-on-defender-windows) (artículo)\
[Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/threats) (página web)
