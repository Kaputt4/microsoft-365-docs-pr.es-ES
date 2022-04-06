---
title: Configuración y estado del sensor de Identidad de Microsoft Defender en Microsoft 365 Defender
description: Obtenga información sobre cómo configurar sensores de Microsoft Defender para identidades y supervisar su estado en Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
ms.custom: admindeeplinkDEFENDER
manager: raynew
ms.collection: M365-security-compliance
ms.openlocfilehash: 246fd5ca880ca2d7e187283d06f19d071f5d7e0e
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2022
ms.locfileid: "64468531"
---
# <a name="microsoft-defender-for-identity-sensor-health-and-settings-in-microsoft-365-defender"></a>Configuración y estado del sensor de Identidad de Microsoft Defender en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar y supervisar [sensores de identidad de Microsoft Defender](/defender-for-identity) [en Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="view-defender-for-identity-sensor-settings-and-status"></a>Ver configuración y estado del sensor de Defender para identidad

1. En <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>, vaya a Configuración y, a **continuación**, **Identities**.

   :::image type="content" source="../../media/defender-identity/settings-identities.png" alt-text="La opción de Identidades en la Configuración página" lightbox="../../media/defender-identity/settings-identities.png":::

1. Selecciona la **página Sensores** , que muestra todos los sensores de Defender for Identity. Para cada sensor, verá su nombre, su pertenencia a un dominio, el número de versión, si las actualizaciones deben retrasarse, el estado del servicio, el estado de actualización, el estado de mantenimiento, el número de problemas de mantenimiento y cuándo se creó el sensor.

    [![Página del sensor.](../../media/defender-identity/sensor-page.png)](../../media/defender-identity/sensor-page.png#lightbox)

    >[!NOTE]
    >En el portal de Defender for Identity, la configuración del sensor y la información de estado estaban en ubicaciones independientes. Ten en cuenta Microsoft 365 Defender que ahora están en la misma página.

1. Si **selecciona Filtros,** puede elegir qué filtros estarán disponibles. A continuación, con cada filtro, puede elegir qué sensores mostrar.

    [![Filtros de sensor.](../../media/defender-identity/sensor-filters.png)](../../media/defender-identity/sensor-filters.png#lightbox)

    :::image type="content" source="../../media/defender-identity/filtered-sensor.png" alt-text="Sensor filtrado" lightbox="../../media/defender-identity/filtered-sensor.png":::

1. Si selecciona uno de los sensores, se mostrará un panel con información sobre el sensor y su estado de mantenimiento.

    [![Detalles del sensor.](../../media/defender-identity/sensor-details.png)](../../media/defender-identity/sensor-details.png#lightbox)

1. Si selecciona alguno de los problemas de mantenimiento, se obtiene un panel con más detalles sobre ellos. Si elige un problema cerrado, puede volver a abrirlo desde aquí.

   :::image type="content" source="../../media/defender-identity/issue-details.png" alt-text="Detalles del problema" lightbox="../../media/defender-identity/issue-details.png":::
    

1. Si selecciona Administrar **sensor**, se abrirá un panel donde podrá configurar los detalles del sensor.

   :::image type="content" source="../../media/defender-identity/manage-sensor.png" alt-text="La opción Administrar sensor" lightbox="../../media/defender-identity/manage-sensor.png":::

   :::image type="content" source="../../media/defender-identity/configure-sensor-details.png" alt-text="La página en la que se configuran las opciones para el sensor" lightbox="../../media/defender-identity/configure-sensor-details.png":::

1. En la **página** Sensores, puede exportar la lista de sensores a un archivo .csv **seleccionaNdo Exportar**.

   :::image type="content" source="../../media/defender-identity/export-sensors.png" alt-text="La lista Exportar de sensores" lightbox="../../media/defender-identity/export-sensors.png":::

## <a name="add-a-sensor"></a>Agregar un sensor

En la **página** Sensores, puede agregar un nuevo sensor.

1. Seleccione **Agregar sensor**.

   :::image type="content" source="../../media/defender-identity/add-sensor.png" alt-text="La opción Agregar sensor" lightbox="../../media/defender-identity/add-sensor.png":::

1. Se abrirá un panel que le proporciona un botón para descargar el instalador del sensor y una clave de acceso generada.

   :::image type="content" source="../../media/defender-identity/installer-access-key.png" alt-text="Las opciones para descargar el instalador y regenerar la clave" lightbox="../../media/defender-identity/installer-access-key.png":::

1. Seleccione **Descargar instalador** para guardar el paquete localmente. El archivo zip incluye los siguientes archivos:

    - El instalador del sensor Defender for Identity

    - El archivo de configuración con la información necesaria para conectarse al servicio en la nube de Defender for Identity

1. Copie la **clave de Access**. La clave de acceso es necesaria para que el sensor Defender for Identity se conecte a la instancia de Defender for Identity. La clave de acceso es una contraseña única para la implementación de sensores, después de la cual todas las comunicaciones se realizan con certificados para autenticación y cifrado TLS. Use el **botón Regenerar clave** si alguna vez necesita regenerar la nueva clave de acceso. No afectará a los sensores implementados anteriormente, ya que solo se usa para el registro inicial del sensor.

1. Copie el paquete en el servidor o controlador de dominio dedicado en el que va a instalar el sensor Defender for Identity.

## <a name="see-also"></a>Vea también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
