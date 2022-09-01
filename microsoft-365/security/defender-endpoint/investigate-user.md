---
title: Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión
description: Investigue una cuenta de usuario para detectar posibles credenciales en peligro o dinamizar en la cuenta de usuario asociada durante una investigación.
keywords: investigar, cuenta, usuario, entidad de usuario, alerta, Microsoft Defender para punto de conexión
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.subservice: mde
ms.openlocfilehash: 61cdee1f64e81b7874c1ad564e7d9eb01d04557d
ms.sourcegitcommit: 228fa13973bf7c2d91504703fab757f552ae40dd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2022
ms.locfileid: "67520959"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a>Investigación de una cuenta de usuario en Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> ¿Quiere experimentar Defender para punto de conexión? [Regístrese para obtener una prueba gratuita.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a>Investigación de entidades de cuenta de usuario

Identifique las cuentas de usuario con las alertas más activas (que se muestran en el panel como "Usuarios en riesgo") e investigue casos de posibles credenciales en peligro, o dinamice la cuenta de usuario asociada al investigar una alerta o dispositivo para identificar el posible movimiento lateral entre los dispositivos con esa cuenta de usuario.

Puede encontrar información de la cuenta de usuario en las vistas siguientes:

- Panel
- Cola de alertas
- Página de detalles del dispositivo

Hay disponible un vínculo de cuenta de usuario que permite hacer clic en estas vistas, que le llevará a la página de detalles de la cuenta de usuario donde se muestran más detalles sobre la cuenta de usuario.

Al investigar una entidad de cuenta de usuario, verá lo siguiente:

- Detalles de la cuenta de usuario, Microsoft Defender for Identity alertas y dispositivos con sesión iniciada, rol, tipo de inicio de sesión y otros detalles
- Información general sobre los incidentes y los dispositivos del usuario
- Alertas relacionadas con este usuario
- Observado en la organización (dispositivos en los que se ha iniciado sesión)

:::image type="content" source="images/atp-user-details-view.png" alt-text="Página de detalles de la entidad de la cuenta de usuario" lightbox="images/atp-user-details-view.png":::

### <a name="user-details"></a>Detalles del usuario

El panel **Detalles** del usuario de la izquierda proporciona información sobre el usuario, como incidentes abiertos relacionados, alertas activas, nombre SAM, SID, Microsoft Defender for Identity alertas, número de dispositivos en los que el usuario ha iniciado sesión, cuándo se ha visto por primera vez al usuario, roles y tipos de inicio de sesión. En función de las características de integración que haya habilitado, verá otros detalles. Por ejemplo, si habilita la integración de Skype Empresarial, podrá ponerse en contacto con el usuario desde el portal. La sección **alertas de Azure ATP** contiene un vínculo que le llevará a la página de Microsoft Defender for Identity, si ha habilitado la característica de Microsoft Defender for Identity y hay alertas relacionadas con el usuario. La página Microsoft Defender for Identity proporcionará más información sobre las alertas.

> [!NOTE]
> Tendrá que habilitar la integración en Microsoft Defender for Identity y Defender para punto de conexión para usar esta característica. En Defender para punto de conexión, puede habilitar esta característica en características avanzadas. Para obtener más información sobre cómo habilitar características avanzadas, consulte [Activar características avanzadas](advanced-features.md).

Información general, Alertas y Observadas en la organización son pestañas diferentes que muestran varios atributos sobre la cuenta de usuario.


>[!NOTE]
>En el caso de los dispositivos Linux, no se muestra información sobre los usuarios que han iniciado sesión.


### <a name="overview"></a>Información general

En la pestaña **Información general** se muestran los detalles de los incidentes y una lista de los dispositivos en los que el usuario ha iniciado sesión. Puede expandirlos para ver los detalles de los eventos de inicio de sesión de cada dispositivo.

### <a name="alerts"></a>Alertas

La pestaña **Alertas** proporciona una lista de alertas asociadas a la cuenta de usuario. Esta lista es una vista filtrada de la [cola de alertas](alerts-queue.md) y muestra alertas donde el contexto de usuario es la cuenta de usuario seleccionada, la fecha en que se detectó la última actividad, una breve descripción de la alerta, el dispositivo asociado a la alerta, la gravedad de la alerta, el estado de la alerta en la cola y a quién se asigna la alerta.

### <a name="observed-in-organization"></a>Observado en la organización

La pestaña **Observada en la organización** permite especificar un intervalo de fechas para ver una lista de dispositivos en los que se observó que este usuario inició sesión, la cuenta de usuario que ha iniciado sesión más frecuente y menos frecuente para cada uno de estos dispositivos y el total de usuarios observados en cada dispositivo.

Al seleccionar un elemento en la tabla Observada en la organización, se expandirá el elemento y se mostrarán más detalles sobre el dispositivo. Al seleccionar directamente un vínculo dentro de un elemento, se le enviará a la página correspondiente.

## <a name="search-for-specific-user-accounts"></a>Búsqueda de cuentas de usuario específicas

1. Seleccione **Usuario** en el menú desplegable **De la barra de búsqueda** .
2. Escriba la cuenta de usuario en el campo **Buscar** .
3. Haga clic en el icono de búsqueda o presione **Entrar**.

Se muestra una lista de usuarios que coinciden con el texto de la consulta. Verá el dominio y el nombre de la cuenta de usuario, cuando se vio por última vez la cuenta de usuario, y el número total de dispositivos en los que se observó que inició sesión en los últimos 30 días.

Puede filtrar los resultados por los siguientes períodos de tiempo:

- 1 día
- 3 días
- 7 días
- 30 días
- 6 meses

## <a name="related-topics"></a>Temas relacionados

- [Ver y organizar la cola de alertas de Microsoft Defender para punto de conexión](alerts-queue.md)
- [Administrar alertas de Microsoft Defender para punto de conexión](manage-alerts.md)
- [Investigar alertas de Microsoft Defender para punto de conexión](investigate-alerts.md)
- [Investigación de un archivo asociado a una alerta de Defender para punto de conexión](investigate-files.md)
- [Investigación de dispositivos en la lista defender para dispositivos de punto de conexión](investigate-machines.md)
- [Investigación de una dirección IP asociada a una alerta de Defender para punto de conexión](investigate-ip.md)
- [Investigación de un dominio asociado a una alerta de Defender para punto de conexión](investigate-domain.md)
