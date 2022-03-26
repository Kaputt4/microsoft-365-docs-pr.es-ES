---
title: Configurar el centro de eventos
description: Obtenga información sobre cómo configurar el centro de eventos
keywords: centro de eventos, configuración, insights
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
ms.openlocfilehash: a842f9161aa823203354917326653b583e5fddb9
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754297"
---
# <a name="configure-your-event-hub"></a>Configurar el centro de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Obtén información sobre cómo configurar el Centro de eventos para que pueda ingerir eventos desde Microsoft 365 Defender.

## <a name="set-up-the-required-resource-provider-in-the-event-hub-subscription"></a>Configurar el proveedor de recursos necesario en la suscripción al Centro de eventos

1. Inicie sesión en el [Azure Portal](https://portal.azure.com).
1. Seleccione **Suscripciones** > **{ Seleccione la suscripción que los centros de eventos se implementarán en }** > **Proveedores de recursos**.
1. Compruebe que **microsoft.Ideas** El proveedor está registrado. De lo contrario, regístrelo.

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="La página lista de proveedores de servicios en el portal Microsoft Azure servicio" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>Configurar el registro Azure Active Directory aplicación

> ! [NOTA] Debe tener un rol de administrador o Azure Active Directory (AAD) debe establecerse para permitir que los usuarios que no son administradores registren aplicaciones. También debe tener un rol Propietario o Administrador de acceso de usuario para asignar un rol a la entidad de servicio. Para obtener más información, vea [Create an Azure AD app & service principal in the portal - Plataforma de identidad de Microsoft \| Microsoft Docs](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Crear un nuevo registro (que crea inherentemente una entidad de servicio) en **Azure Active Directory** \> **registros de aplicaciones Nuevo** \> **registro.**

1. Rellene el formulario con solo el nombre (no se requiere URI de redireccionamiento).

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="Sección para mostrar el nombre de la aplicación en el portal Microsoft Azure aplicación" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="La sección Información general del portal de Microsoft Azure información general" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. Crear un secreto haciendo clic en **Certificados & secretos nuevo** \> **secreto de cliente**:

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="Sección Secreto de cliente en el portal Microsoft Azure cliente" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::
    

> [!WARNING]
> **No podrá volver a tener acceso al secreto de cliente, así que asegúrese de guardarlo**.

## <a name="set-up-event-hub-namespace"></a>Configurar espacio de nombres de Event Hub

1. Crear un espacio de nombres de centro de eventos:

    Vaya **a Agregar centro \>** de eventos y seleccione el nivel de precios, las unidades de rendimiento y la opción Autoinflate (requiere precios estándar y características) adecuadas para la carga que espera. Para obtener más información, vea [Pricing - Event Hub \| Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/)

    > [!NOTE]
    > Puede usar un centro de eventos existente, pero el rendimiento y el escalado se establecen en el nivel de espacio de nombres, por lo que se recomienda colocar un centro de eventos en su propio espacio de nombres.

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="Sección de concentradores de eventos en el portal de Microsoft Azure eventos" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. También necesitará el identificador de recurso de este espacio de nombres de centro de eventos. Vaya a la página de espacio de nombres del Centro de eventos de Azure Propiedades \> . Copie el texto en Id. de recurso y grabe para usarlo durante la Microsoft 365 configuración siguiente.

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="La sección de propiedades del centro de eventos en el portal Microsoft Azure eventos" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::


1. Una vez creado el espacio de nombres del centro de eventos, deberá agregar la entidad de seguridad del servicio de registro de aplicaciones como Lector, receptor de datos del centro de eventos de Azure y el usuario que inicia sesión en Microsoft 365 Defender como colaborador (también puede hacerlo en el nivel de grupo de recursos o suscripción).

    Realice este paso en **Event Hub Namespace** \> **Access Control (IAM)** \> **Add** and verify under **Role assignments**:

    :::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="Sección de entidad de seguridad de servicio de registro de aplicaciones en el portal Microsoft Azure aplicación" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hub"></a>Configurar el centro de eventos

**Opción 1:**

Puede crear un centro de eventos en el espacio de  nombres y todos los tipos de eventos (tablas) que seleccione exportar se escribirán en **este único centro de** eventos.

**Opción 2:**

En lugar de exportar todos los tipos de evento (tablas) a un centro de eventos, puede exportar cada tabla a un centro de eventos diferente dentro del espacio de nombres del centro de eventos (un centro de eventos por tipo de evento).

En esta opción, Microsoft 365 Defender creará el Centro de eventos.

> [!NOTE]
> Si usa un espacio de nombres de centro de eventos  que no forma parte de un clúster de concentradores de eventos, solo podrá elegir hasta 10 tipos de eventos (tablas) para exportar en cada Configuración de exportación que defina, debido a una limitación de Azure de 10 centros de eventos por espacio de nombres de centro de eventos.

Por ejemplo:

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="Una sección de centros de eventos en el portal Microsoft Azure eventos" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

Si elige esta opción, puede ir a la sección Configurar [Microsoft 365 Defender para enviar tablas de correo](#configure-microsoft-365-defender-to-send-email-tables) electrónico.

Para crear el centro de eventos en el espacio de nombres, seleccione **Centro de eventos** \> **+ Centro de eventos**.

El recuento de particiones permite más rendimiento a través del paralelismo, por lo que se recomienda aumentar este número en función de la carga que se espera. Se recomiendan los valores predeterminados de retención y captura de mensajes de 1 y Off.

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="Sección de creación de centros de eventos en el portal Microsoft Azure eventos" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::
 

Para estos Event Hub (no espacio de nombres), deberá configurar una directiva de acceso compartido con Send, Listen Claims. Haz clic en las **directivas de acceso** \>  \> compartido del Centro de eventos **+** Agregar y, a continuación, dale un nombre de directiva (no se usa en ningún otro lugar) y comprueba **Enviar** y **escuchar**.

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="La página Directivas de acceso compartido en el portal de Microsoft Azure compartido" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Configurar Microsoft 365 Defender para enviar tablas de correo electrónico

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Configurar Microsoft 365 Defender enviar tablas de correo electrónico a Splunk a través del Centro de eventos

1. Inicie sesión en <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a> con una cuenta que cumpla todos los siguientes requisitos de función:

    - Rol colaborador en el nivel de recurso *de espacio de* nombres del centro de eventos o superior para el centro de eventos al que exportará. Sin este permiso, se producirá un error de exportación al intentar guardar la configuración.

    - Rol de administrador global o de administración de seguridad en el inquilino vinculado a Microsoft 365 Defender y Azure.

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="La Configuración del portal de Microsoft 365 Defender web" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. Haga clic **en Exportación de datos sin procesar \> +Agregar**.

    Ahora usará los datos que registró anteriormente.

    **Nombre**: este valor es local y debe ser lo que funciona en el entorno.

    **Reenviar eventos al centro de eventos**: active esta casilla.

    **Identificador de recurso event-hub**: este valor es el identificador de recurso de espacio de nombres del centro de eventos que registró al configurar el centro de eventos.

    **Nombre del centro de** eventos: si creó un centro de eventos dentro del espacio de nombres del centro de eventos, pegue el nombre del centro de eventos que registró anteriormente.

    Si decide dejar que Microsoft 365 Defender centro de eventos por tipos de evento (tablas), deje este campo vacío.

    **Tipos de eventos**: selecciona las tablas de búsqueda avanzada que quieres reenviar al Centro de eventos y, a continuación, a la aplicación personalizada. Las tablas de alertas son de Microsoft 365 Defender, las tablas de dispositivos son de Microsoft Defender para endpoint (EDR) y las tablas de correo electrónico son de Microsoft Defender para Office 365. Eventos de correo electrónico registra todas las transacciones de correo electrónico. La dirección URL (vínculos Caja fuerte), datos adjuntos (datos adjuntos de Caja fuerte) y eventos posteriores a la entrega (ZAP) también se registran y se pueden unir a los eventos de correo electrónico en el campo NetworkMessageId.

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="La página Configuración de la API de streaming en el portal Microsoft Azure web" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. Asegúrese de hacer clic en **Enviar**.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Comprobar que los eventos se exportan al Centro de eventos

Puede comprobar que los eventos se envían al Centro de eventos ejecutando una consulta básica de búsqueda avanzada. Seleccione **Buscar consulta** \> **de búsqueda** \> **avanzada** y escriba la siguiente consulta:

```console
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Esto le mostrará cuántos correos electrónicos se recibieron en la última hora unidos en todas las demás tablas. También le mostrará si está viendo eventos que podrían exportarse a los centros de eventos. Si este recuento muestra 0, no verá ningún dato que vaya al Centro de eventos.

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="La página de búsqueda avanzada en el portal Microsoft Azure búsqueda" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

Una vez que haya comprobado que hay datos que exportar, puede ver la página centro de eventos para comprobar que los mensajes están entrantes. Esto puede tardar hasta una hora.

1. En Azure, vaya a **Centro de eventos Haga** \> clic **en el Centro** \> \> de eventos de espacio de **nombres Haga clic** en el **centro de eventos**.
1. En **Información** general, desplácese hacia abajo y en el gráfico Mensajes debería ver Mensajes entrantes. Si no ves ningún resultado, no habrá mensajes para que la aplicación personalizada ingieren.

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="La página Información general en el Microsoft 365 Azure Portal" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
