---
title: Estado y configuración del sensor de Identidad de Microsoft Defender en Microsoft 365 Defender
description: Obtenga información sobre cómo configurar sensores de Microsoft Defender para identidades y supervisar su estado en Microsoft 365 Defender
ms.date: 06/07/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 9d57272626c6f6c5d0e44052522cb73b9b675fd8
ms.sourcegitcommit: c2d752718aedf958db6b403cc12b972ed1215c00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58569326"
---
# <a name="microsoft-defender-for-identity-sensor-health-and-settings-in-microsoft-365-defender"></a>Estado y configuración del sensor de Identidad de Microsoft Defender en Microsoft 365 Defender

**Se aplica a:**

- Microsoft 365 Defender
- Defender for Identity

En este artículo se explica cómo configurar y supervisar [sensores](/defender-for-identity) de Identidad de Microsoft Defender en [Microsoft 365 Defender](/microsoft-365/security/defender/overview-security-center).

>[!IMPORTANT]
>Como parte de la convergencia con Microsoft 365 Defender, algunas opciones y detalles han cambiado desde su ubicación en el portal de Defender for Identity. Lea los detalles siguientes para descubrir dónde encontrar las características conocidas y las nuevas.

## <a name="view-defender-for-identity-sensor-settings-and-status"></a>Ver configuración y estado del sensor de Defender para identidad

1. En [Microsoft 365 Defender](https://security.microsoft.com/), vaya **a Configuración** y, a continuación, **Identities**.

    ![Vaya a Configuración y, a continuación, Identities.](../../media/defender-identity/settings-identities.png)

1. Selecciona la **página Sensores,** que muestra todos los sensores de Defender for Identity. Para cada sensor, verá su nombre, su pertenencia a un dominio, el número de versión, si las actualizaciones deben retrasarse, el estado del servicio, el estado de actualización, el estado de mantenimiento, el número de problemas de mantenimiento y cuándo se creó el sensor.

    [![Página del sensor.](../../media/defender-identity/sensor-page.png)](../../media/defender-identity/sensor-page.png#lightbox)

    >[!NOTE]
    >En el portal de Defender for Identity, la configuración del sensor y la información de estado estaban en ubicaciones independientes. Ten en cuenta Microsoft 365 Defender que ahora están en la misma página.

1. Si selecciona **Filtros,** puede elegir qué filtros estarán disponibles. A continuación, con cada filtro, puede elegir qué sensores mostrar.

    [![Filtros de sensor.](../../media/defender-identity/sensor-filters.png)](../../media/defender-identity/sensor-filters.png#lightbox)

    ![Sensor filtrado.](../../media/defender-identity/filtered-sensor.png)

1. Si selecciona uno de los sensores, se mostrará un panel con información sobre el sensor y su estado de mantenimiento.

    [![Detalles del sensor.](../../media/defender-identity/sensor-details.png)](../../media/defender-identity/sensor-details.png#lightbox)

1. Si selecciona alguno de los problemas de mantenimiento, se obtiene un panel con más detalles sobre ellos. Si elige un problema cerrado, puede volver a abrirlo desde aquí.

    ![Detalles del problema.](../../media/defender-identity/issue-details.png)

1. Si selecciona Administrar **sensor,** se abrirá un panel donde puede configurar los detalles del sensor.

    ![Administrar sensor.](../../media/defender-identity/manage-sensor.png)

    ![Configure los detalles del sensor.](../../media/defender-identity/configure-sensor-details.png)

1. En la **página** Sensores, puede exportar la lista de sensores a un archivo .csv **seleccionando Exportar**.

    ![Exportar lista de sensores.](../../media/defender-identity/export-sensors.png)

## <a name="add-a-sensor"></a>Agregar un sensor

En la **página** Sensores, puede agregar un nuevo sensor.

1. Seleccione **Agregar sensor**.

    ![Agregar sensor.](../../media/defender-identity/add-sensor.png)

1. Se abrirá un panel que le proporciona un botón para descargar el instalador del sensor y una clave de acceso generada.

    ![Descargue el instalador y la clave de acceso.](../../media/defender-identity/installer-access-key.png)

1. Seleccione **Descargar instalador** para guardar el paquete localmente. El archivo zip incluye los siguientes archivos:

    - El instalador del sensor Defender for Identity

    - El archivo de configuración con la información necesaria para conectarse al servicio en la nube de Defender for Identity

1. Copie la **clave de Access**. La clave de acceso es necesaria para que el sensor Defender for Identity se conecte a la instancia de Defender for Identity. La clave de acceso es una contraseña única para la implementación de sensores, después de la cual todas las comunicaciones se realizan con certificados para autenticación y cifrado TLS. Use el **botón Regenerar clave** si alguna vez necesita regenerar la nueva clave de acceso. No afectará a los sensores implementados anteriormente, ya que solo se usa para el registro inicial del sensor.

1. Copie el paquete en el servidor o controlador de dominio dedicado en el que va a instalar el sensor Defender for Identity.

## <a name="see-also"></a>Vea también

- [Administrar alertas de seguridad de Defender for Identity](manage-security-alerts.md)
