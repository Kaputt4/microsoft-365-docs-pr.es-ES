---
title: Investigar una cuenta de usuario en Microsoft Defender para endpoint
description: Investigue una cuenta de usuario para obtener credenciales potencialmente comprometidas o pivote en la cuenta de usuario asociada durante una investigación.
keywords: investigar, cuenta, usuario, entidad de usuario, alerta, Microsoft Defender para endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e98142e4076c5e695f16eb06c062bc69d3d7dd55
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935070"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Investigar una cuenta de usuario en Microsoft Defender para endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Investigar entidades de cuenta de usuario

Identifique las cuentas de usuario con las alertas más activas (mostradas en el panel como "Usuarios en riesgo") e investigue casos de credenciales potencialmente comprometidas, o pivote en la cuenta de usuario asociada al investigar una alerta o dispositivo para identificar posibles movimientos laterales entre dispositivos con esa cuenta de usuario.

Puede encontrar información de cuenta de usuario en las siguientes vistas:

- Panel
- Cola de alertas
- Página de detalles del dispositivo

En estas vistas hay disponible un vínculo de cuenta de usuario en el que se puede hacer clic, que le llevará a la página de detalles de la cuenta de usuario donde se muestran más detalles sobre la cuenta de usuario.

Cuando investigue una entidad de cuenta de usuario, verá:

- Detalles de la cuenta de usuario, alertas de Microsoft Defender para identidad y dispositivos, rol, tipo de inicio de sesión y otros detalles
- Información general sobre los incidentes y los dispositivos del usuario
- Alertas relacionadas con este usuario
- Observado en la organización (dispositivos que iniciaron sesión en)

![Imagen de la página de detalles de la entidad de la cuenta de usuario](images/atp-user-details-view.png)

### <a name="user-details"></a>Detalles del usuario

El  panel De detalles del usuario a la izquierda proporciona información sobre el usuario, como incidentes abiertos relacionados, alertas activas, nombre SAM, SID, Alertas de Identidad de Microsoft Defender, número de dispositivos en los que el usuario ha iniciado sesión, cuándo se ha visto por primera vez y por última vez, tipos de rol e inicio de sesión. Dependiendo de las características de integración que haya habilitado, verá otros detalles. Por ejemplo, si habilita la Skype para la integración empresarial, podrá ponerse en contacto con el usuario desde el portal. La sección Alertas **de ATP** de Azure contiene un vínculo que te llevará a la página de Microsoft Defender para identidad, si has habilitado la característica Microsoft Defender para identidad y hay alertas relacionadas con el usuario. La página microsoft defender para la identidad proporcionará más información sobre las alertas.

>[!NOTE]
>Tendrás que habilitar la integración en Microsoft Defender para Identidad y Defender para endpoint para usar esta característica. En Defender para endpoint, puedes habilitar esta característica en características avanzadas. Para obtener más información sobre cómo habilitar características avanzadas, vea [Activar características avanzadas.](advanced-features.md)

Overview, Alerts y Observed in organization son pestañas diferentes que muestran varios atributos sobre la cuenta de usuario.

### <a name="overview"></a>Información general

La **pestaña** Información general muestra los detalles de incidentes y una lista de los dispositivos en los que el usuario ha iniciado sesión. Puedes expandir estos para ver detalles de los eventos de inicio de sesión para cada dispositivo.

### <a name="alerts"></a>Alertas

La **pestaña** Alertas proporciona una lista de alertas asociadas con la cuenta de usuario. Esta lista es una [](alerts-queue.md)vista filtrada de la cola de alertas y muestra alertas en las que el contexto del usuario es la cuenta de usuario seleccionada, la fecha en que se detectó la última actividad, una breve descripción de la alerta, el dispositivo asociado a la alerta, la gravedad de la alerta, el estado de la alerta en la cola y quién tiene asignada la alerta.

### <a name="observed-in-organization"></a>Observado en la organización

La pestaña **Observed in organization** te permite especificar un intervalo de fechas para ver una lista de dispositivos en los que se observó que este usuario inició sesión, la cuenta de usuario más frecuente y menos frecuente para cada uno de estos dispositivos y el total de usuarios observados en cada dispositivo.

Al seleccionar un elemento en la tabla Observado en la organización, se expandirá el elemento, lo que revelará más detalles sobre el dispositivo. Si selecciona directamente un vínculo dentro de un elemento, se le enviará a la página correspondiente.

## <a name="search-for-specific-user-accounts"></a>Buscar cuentas de usuario específicas

1. Seleccione **Usuario** en el **menú** desplegable Barra de búsqueda.
2. Escriba la cuenta de usuario en el **campo** Búsqueda.
3. Haga clic en el icono de búsqueda o presione **Entrar**.

Se muestra una lista de usuarios que coinciden con el texto de la consulta. Verás el dominio y el nombre de la cuenta de usuario, cuando se vio por última vez la cuenta de usuario y el número total de dispositivos en los que se observó que inició sesión en los últimos 30 días.

Puede filtrar los resultados por los siguientes períodos de tiempo:

- 1 día
- 3 días
- 7 días
- 30 días
- 6 meses

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de Alertas de punto de conexión de Microsoft Defender](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para puntos de conexión](manage-alerts.md)
- [Investigar alertas de punto de conexión de Microsoft Defender](investigate-alerts.md)
- [Investigar un archivo asociado a una alerta de Defender for Endpoint](investigate-files.md)
- [Investigar dispositivos en la lista Defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigar una dirección IP asociada a una alerta de Defender for Endpoint](investigate-ip.md)
- [Investigar un dominio asociado a una alerta de Defender for Endpoint](investigate-domain.md)
