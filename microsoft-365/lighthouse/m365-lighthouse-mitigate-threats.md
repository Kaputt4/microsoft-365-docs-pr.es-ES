---
title: Mitigar amenazas con Antivirus de Microsoft Defender
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre las amenazas de mitigación con Antivirus de Microsoft Defender.
ms.openlocfilehash: 297c35104ae58efb1b7c58d3d1968158d42c0fce
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63315517"
---
# <a name="mitigate-threats-with-microsoft-defender-antivirus"></a>Mitigar amenazas con Antivirus de Microsoft Defender

Microsoft 365 Lighthouse permite a los partners investigar y mitigar las amenazas en todos los inquilinos. También puede iniciar exámenes antivirus en dispositivos, asegurarse de que los dispositivos están obteniendo las actualizaciones más recientes para Antivirus de Microsoft Defender y revisar las acciones pendientes después de los exámenes antivirus. Lighthouse solo admite dispositivos que Windows 10 o posterior.

## <a name="before-you-begin"></a>Antes de empezar

- Microsoft 365 Lighthouse se implementa solo en el espacio empresarial asociado, no en los inquilinos del cliente, pero asegúrese de que usted y sus inquilinos de clientes cumplen los requisitos que se enumeran [en Microsoft 365 Lighthouse requisitos](m365-lighthouse-requirements.md).

- Los usuarios deben ejecutar Antivirus de Microsoft Defender (incluido con Windows). Lighthouse no admite software antivirus que no sea de Microsoft. Para obtener más información, [vea Activar Antivirus de Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows).

- Debe ser un administrador global en el espacio empresarial asociado al que está iniciando sesión.

## <a name="investigate-active-threats"></a>Investigar amenazas activas

Para investigar una amenaza específica:

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Administración de amenazas**.

2. Seleccione la **pestaña** Amenazas.

3. En la lista de amenazas, seleccione la amenaza que desea investigar.

El panel de detalles de amenazas proporciona la siguiente información:

| Categoría                                      | Definición                                                                                                   |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Dispositivo e inquilino                             | El nombre del dispositivo y el inquilino donde se encontró la amenaza. Seleccione el nombre del dispositivo para ver información adicional. |
| Estado de la amenaza                                 | El estado de la amenaza.                                                                                    |
| Tipo de amenaza                                   | Tipo de amenaza.                                                                                              |
| Gravedad de la amenaza                               | Gravedad de la amenaza (grave, alta, moderada, baja, desconocida)                                                    |
| Instancias                                     | Número de instancias de esta amenaza presentes en el dispositivo.                                                    |
| Detectado por primera vez                                | Cuando la amenaza se detectó por primera vez en este dispositivo.                                                           |
| Documentación                                 | Vínculo a información adicional sobre la amenaza.                                                             |
| Otros dispositivos de este inquilino con esta amenaza | Una lista de otros dispositivos en el mismo inquilino con la misma amenaza activa.                                      |
| Otros inquilinos con esta amenaza                | Una lista de otros inquilinos con la misma amenaza activa.                                                         |

Para investigar amenazas en un dispositivo específico:

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Administración de amenazas**.

2. Seleccione la **pestaña Protección antivirus** .

3. Selecciona un dispositivo de la lista.

4. En el panel de detalles del dispositivo, selecciona la **pestaña Amenazas** actuales.

Lighthouse muestra todas las amenazas encontradas en el dispositivo. Para ver detalles, seleccione la amenaza.

## <a name="scan-for-threats-on-a-device"></a>Buscar amenazas en un dispositivo

Un examen rápido busca ubicaciones comunes en las que podría haber malware, como las claves del Registro y las carpetas de inicio. Un examen completo busca en todo el dispositivo. En la mayoría de los casos, un examen rápido es suficiente y es la opción recomendada para exámenes programados.

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Administración de amenazas**.

2. Seleccione la **pestaña Protección antivirus** .

3. En la lista de dispositivos, selecciona un dispositivo.

4. En el panel de detalles del dispositivo, selecciona **Ejecutar examen completo** o **Ejecutar examen rápido**.

También puedes examinar varios dispositivos seleccionando la casilla situada junto a cada nombre de dispositivo de la lista y, a continuación, selecciona **Ejecutar examen completo** o **Ejecutar examen rápido**.

## <a name="get-updates-for-microsoft-defender-antivirus"></a>Obtener actualizaciones para Antivirus de Microsoft Defender

Para actualizar Antivirus de Microsoft Defender en un solo dispositivo:

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Administración de amenazas**.

2. Seleccione la **pestaña Protección antivirus** .

3. En la lista de dispositivos, selecciona un dispositivo.

4. En el panel de detalles del dispositivo, seleccione **Actualizar antivirus**.

Puedes obtener actualizaciones para varios dispositivos seleccionando la casilla situada junto a cada nombre de dispositivo de la lista y, a continuación, selecciona **Actualizar antivirus**.

Si necesitas crear una nueva directiva, selecciona **Actualizar directiva** en el panel de detalles del dispositivo. Lighthouse le redirigirá a Microsoft Endpoint Manager (MEM). Para obtener más información acerca de la creación de una directiva, vea [Create a compliance policy in Microsoft Intune](/mem/intune/protect/create-compliance-policy).

## <a name="check-pending-antivirus-actions-on-a-device"></a>Comprobar las acciones antivirus pendientes en un dispositivo

Cuando se aplican acciones consecutivas a un dispositivo, recibirás un mensaje pendiente de acción. Para comprobar qué acciones están pendientes en un dispositivo:

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Administración de amenazas**.

2. Seleccione la **pestaña Protección antivirus** .

3. En la lista de dispositivos, selecciona un dispositivo.

4. En el panel de detalles del dispositivo, selecciona la **pestaña Estados de la** acción Dispositivo para ver las acciones pendientes.

## <a name="restart-a-device"></a>Reiniciar un dispositivo

Algunas actualizaciones pueden requerir que un dispositivo se reinicie para instalarse correctamente.

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Administración de amenazas**.

2. Seleccione la **pestaña Protección antivirus** .

3. En la lista de dispositivos, selecciona un dispositivo.

4. En el panel de detalles del dispositivo, selecciona **Reiniciar dispositivo**.

También puedes reiniciar varios dispositivos seleccionando la casilla situada junto a cada nombre de dispositivo de la lista y, a continuación, selecciona **Reiniciar dispositivo**.

## <a name="related-content"></a>Contenido relacionado

[Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md) (artículo)\
[Introducción a la página de administración de amenazas ](m365-lighthouse-threat-management-page-overview.md) (artículo)\
[Crear una directiva de cumplimiento en Microsoft Intune](/mem/intune/protect/create-compliance-policy) (artículo)\
[Activar Antivirus de Microsoft Defender](/mem/intune/user-help/turn-on-defender-windows) (artículo)\
[Inteligencia de seguridad de Microsoft](https://www.microsoft.com/wdsi/threats) (página web)