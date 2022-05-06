---
title: Configuración del centro de eventos
description: Obtenga información sobre cómo configurar el centro de eventos
keywords: event hub, configure, insights
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
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
MS.technology: mde
ms.openlocfilehash: 40211d37b8b036f93b826a383d9d0aa87f44fc68
ms.sourcegitcommit: 292de1a7e5ecc2e9e6187126aebba6d3b9416dff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2022
ms.locfileid: "65243082"
---
# <a name="configure-your-event-hub"></a>Configuración del centro de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Obtenga información sobre cómo configurar el centro de eventos para que pueda ingerir eventos de Microsoft 365 Defender.

## <a name="set-up-the-required-resource-provider-in-the-event-hub-subscription"></a>Configuración del proveedor de recursos necesario en la suscripción del centro de eventos

1. Inicie sesión en el [portal de Azure](https://portal.azure.com).
1. Seleccione **Suscripciones** > **{ Seleccione la suscripción a la que se implementarán los centros de eventos en }** > **Proveedores de recursos**.
1. Compruebe que **microsoft.Ideas** El proveedor está registrado. De lo contrario, regístrelo.

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="Página de la lista de proveedores de servicios en el portal de Microsoft Azure" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>Configuración Azure Active Directory registro de aplicaciones

> ! [NOTA] Debe tener el rol de administrador o Azure Active Directory (AAD) debe establecerse para permitir que los usuarios que no son administradores registren aplicaciones. También debe tener un rol propietario o administrador de acceso de usuario para asignar un rol a la entidad de servicio. Para obtener más información, consulte [Creación de una aplicación de Azure AD & entidad de servicio en el portal: Plataforma de identidad de Microsoft \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Cree un nuevo registro (que crea inherentemente una entidad de servicio) en **Azure Active Directory** \> **Registros de aplicaciones** \> **Nuevo registro.**

1. Rellene el formulario con solo el nombre (no se requiere ningún URI de redirección).

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="Sección para mostrar del nombre de la aplicación en el portal de Microsoft Azure" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="La sección Información general del portal de Microsoft Azure" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. Cree un secreto haciendo clic en **Certificados & secretos** \> **Nuevo secreto de cliente**:

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="La sección Secreto de cliente del portal de Microsoft Azure" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::
    

> [!WARNING]
> **No podrá acceder al secreto de cliente de nuevo, así que asegúrese de guardarlo**.

## <a name="set-up-event-hub-namespace"></a>Configuración del espacio de nombres del centro de eventos

1. Cree un espacio de nombres del centro de eventos:

    Vaya **a Event Hub \> Agregar** y seleccione el plan de tarifa, las unidades de rendimiento y el inflado automático (requiere precios estándar y en características) adecuados para la carga que espera. Para obtener más información, consulte [Precios: event hub \| Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/)

    > [!NOTE]
    > Puede usar un centro de eventos existente, pero el rendimiento y el escalado se establecen en el nivel de espacio de nombres, por lo que se recomienda colocar un centro de eventos en su propio espacio de nombres.

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="Sección event hubs en el portal de Microsoft Azure" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. También necesitará el identificador de recurso de este espacio de nombres del centro de eventos. Vaya a la página \> Del espacio de nombres del centro de eventos de Azure Propiedades. Copie el texto en Id. de recurso y anote el texto para usarlo durante la sección Configuración de Microsoft 365 siguiente.

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="La sección de propiedades de Event Hubs en el portal de Microsoft Azure" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::


1. Una vez creado el espacio de nombres del centro de eventos, deberá agregar la entidad de servicio de registro de aplicaciones como lector, Azure Event Hubs receptor de datos y el usuario que iniciará sesión en Microsoft 365 Defender como colaborador (también puede hacerlo en el nivel de grupo de recursos o suscripción).

    Realice este paso en Espacio de nombres de **Event Hub** \> **Access Control (IAM)** \> **Agregar** y comprobar en **Asignaciones de roles**:

    :::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="Una sección de entidad de servicio de registro de aplicaciones en el portal de Microsoft Azure" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hub"></a>Configuración del centro de eventos

**Opción 1:**

Puede crear un centro de eventos dentro del espacio de nombres y **todos los** tipos de eventos (tablas) que seleccione exportar se escribirán en este **centro** de eventos.

**Opción 2:**

En lugar de exportar todos los tipos de eventos (tablas) a un centro de eventos, puede exportar cada tabla a otro centro de eventos dentro del espacio de nombres del centro de eventos (un centro de eventos por tipo de evento).

En esta opción, Microsoft 365 Defender creará el centro de eventos automáticamente.

> [!NOTE]
> Si usa un espacio de nombres de Centro de eventos que **no** forma parte de un clúster de Event Hub, solo podrá elegir hasta 10 tipos de eventos (tablas) para exportar en cada Configuración de exportación que defina, debido a una limitación de Azure de 10 centros de eventos por espacio de nombres del centro de eventos.

Por ejemplo:

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="Una sección de Event Hubs en el portal de Microsoft Azure" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

Si elige esta opción, puede ir a la sección [Configurar Microsoft 365 Defender para enviar tablas de correo electrónico](#configure-microsoft-365-defender-to-send-email-tables).

Para crear un centro de eventos en el espacio de nombres, seleccione **Centro de eventos** \> **y centro de eventos**.

El recuento de particiones permite un mayor rendimiento a través del paralelismo, por lo que se recomienda aumentar este número en función de la carga que espera. Se recomiendan los valores predeterminados de Retención de mensajes y Captura de 1 y Desactivado.

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="Una sección de creación de Event Hubs en el portal de Microsoft Azure" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::
 

Para estos centros de eventos (no el espacio de nombres), deberá configurar una directiva de acceso compartido con notificaciones de envío y escucha. Haga clic en las **directivas** \> de acceso compartido del **centro** \> de eventos **+ Agregar** y, a continuación, asígnele un nombre de directiva (no usado en otro lugar) y active **Enviar** y **escuchar**.

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="Página Directivas de acceso compartido en el portal de Microsoft Azure" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Configuración de Microsoft 365 Defender para enviar tablas de correo electrónico

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Configurar Microsoft 365 Defender enviar tablas de correo electrónico a Splunk a través del centro de eventos

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta que cumpla todos los siguientes requisitos de rol:

    - Rol colaborador en el nivel de recurso del *espacio de nombres* del centro de eventos o superior para el centro de eventos al que va a exportar. Sin este permiso, obtendrá un error de exportación al intentar guardar la configuración.

    - Rol de administrador global o administrador de seguridad en el inquilino vinculado a Microsoft 365 Defender y Azure.

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="Página Configuración del portal de Microsoft 365 Defender" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. Haga clic en **Exportación de \> datos sin procesar +Agregar**.

    Ahora usará los datos que registró anteriormente.

    **Nombre**: este valor es local y debe ser lo que funcione en su entorno.

    **Reenviar eventos al centro de eventos**: active esta casilla.

    **Identificador de recurso del centro** de eventos: este valor es el identificador de recurso del espacio de nombres del centro de eventos que registró al configurar el centro de eventos.

    **Nombre del centro de** eventos: si creó un centro de eventos dentro del espacio de nombres del centro de eventos, pegue el nombre del centro de eventos que registró anteriormente.

    Si decide permitir que Microsoft 365 Defender cree el centro de eventos por tipo de evento (tablas), deje este campo vacío.

    **Tipos de eventos**: seleccione las tablas de búsqueda avanzada que desea reenviar al centro de eventos y, después, a la aplicación personalizada. Las tablas de alertas proceden de Microsoft 365 Defender, las tablas Dispositivos proceden de Microsoft Defender para punto de conexión (EDR) y las tablas de correo electrónico son de Microsoft Defender para Office 365. Eventos de correo electrónico registra todas las transacciones de correo electrónico. La dirección URL (vínculos de Caja fuerte), los datos adjuntos (Caja fuerte datos adjuntos) y los eventos posteriores a la entrega (ZAP) también se registran y se pueden unir a los eventos de correo electrónico en el campo NetworkMessageId.

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="Página Configuración de Streaming API en el portal de Microsoft Azure" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. Asegúrese de hacer clic en **Enviar**.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Comprobación de que los eventos se exportan al centro de eventos

Puede comprobar que los eventos se envían al centro de eventos mediante la ejecución de una consulta de búsqueda avanzada básica. Seleccione Hunting Advanced Hunting **Query (Consulta** **de búsqueda** \> avanzada de **búsqueda**\>) y escriba la consulta siguiente:

```console
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Esto le mostrará cuántos correos electrónicos se recibieron en la última hora unidos en todas las demás tablas. También le mostrará si ve eventos que se pueden exportar a los centros de eventos. Si este recuento muestra 0, no verá ningún dato que salga al centro de eventos.

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="Página de búsqueda avanzada en el portal de Microsoft Azure" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

Una vez que haya comprobado que hay datos que exportar, puede ver la página del Centro de eventos para comprobar que los mensajes son entrantes. Esto puede tardar hasta una hora.

1. En Azure, vaya a **Centro de eventos** \> Haga clic en el **centro de eventos** \> espacio de **nombres** \> Haga clic en el **centro de eventos**.
1. En **Información general**, desplácese hacia abajo y, en el gráfico Mensajes, debería ver Mensajes entrantes. Si no ves ningún resultado, no habrá mensajes para que la aplicación personalizada la ingiera.

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="La página Información general de la Microsoft 365 Azure Portal" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
