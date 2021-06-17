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
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.openlocfilehash: d28ad22721e22dfd0dc5962bd46bab2b45469781
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985665"
---
# <a name="configure-your-event-hub"></a>Configurar el centro de eventos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Obtén información sobre cómo configurar el Centro de eventos para que pueda ingerir eventos desde Microsoft 365 Defender.


## <a name="setup-the-required-resource-provider-in-the-event-hub-subscription"></a>Configurar el proveedor de recursos necesario en la suscripción al Centro de eventos


1. Inicie sesión en el [portal de Azure](https://portal.azure.com).
1. Select **Subscriptions { Select the subscription the event hub will be deployed \> ***to***} \> Resource providers**.
1. Compruebe que el **proveedor de microsoft.Ideas** está registrado. De lo contrario, regístrelo.

![Imagen de proveedores de recursos en Microsoft Azure](../../media/f893db7a7b1f7aa520e8b9257cc72562.png)

## <a name="setup-azure-active-directory-app-registration"></a>Configurar Azure Active Directory de aplicaciones


>! [NOTA] Debe tener un rol de administrador o Azure Active Directory (AAD) debe establecerse para permitir que los usuarios que no son administradores registren aplicaciones. También debe tener un rol Propietario o Administrador de acceso de usuario para asignar un rol a la entidad de servicio.  
>Para obtener más información, vea [Create an Azure AD app & service principal in the portal - Plataforma de identidad de Microsoft Microsoft \| Docs](/azure/active-directory/develop/howto-create-service-principal-portal).

1. Cree un nuevo registro (que cree inherentemente una entidad de servicio) en **Azure Active Directory registros de aplicaciones Nuevo \> \> registro.**

1. Rellene el formulario con solo el nombre (no se requiere URI de redireccionamiento).

    ![Imagen del registro de una aplicación](../../media/336bc84e6be23900c43232b4ef0c253c.png)

    ![Imagen de información general](../../media/06ac04c4ff713c2065cec2ef2f99a294.png)

1. Crear un secreto haciendo clic en **Certificados & secretos \> nuevo secreto de cliente:**

    ![Imagen de certificados y secretos](../../media/d2ef88d3d2310d2c60c294b569cdf02e.png)

>[!WARNING]
>**No podrá volver a tener acceso al secreto de cliente,** así que asegúrese de guardarlo.

## <a name="setup-event-hub-namespace"></a>Espacio de nombres del Centro de eventos de instalación


1. Crear un espacio de nombres de centro de eventos:

    Vaya **a Event Hubs \> Add** and select the pricing tier, throughput units and Auto-Inflate (requires standard pricing and under features) appropriate for the load you are expecting.  
    Para obtener más información, vea [Pricing - Event Hubs \| Microsoft Azure](https://azure.microsoft.com/en-us/pricing/details/event-hubs/)

    >[!NOTE]
    > Puede usar un centro de eventos existente, pero el rendimiento y el escalado se establecen en el nivel de espacio de nombres, por lo que se recomienda colocar un centro de eventos en su espacio de nombres.

   ![Imagen del espacio de nombres del centro de eventos](../../media/ebc4ca37c342ad1da75c4aee4018e51a.png)

1. También necesitará el identificador de recurso de este espacio de nombres de centro de eventos. Vaya a la página de espacio de nombres de Azure Event Hubs \> Propiedades. Copie el texto en Id. de recurso y grabe para usarlo durante la sección Configuración de M365 que se muestra a continuación. 

    ![Imagen de propiedades](../../media/759498162a4e93cbf17c4130d704d164.png)

1. Una vez creado el espacio de nombres del centro de eventos, deberá agregar la entidad de seguridad del servicio de registro de aplicaciones como lector, el receptor de datos de Azure Event Hubs y el usuario que iniciará sesión en Microsoft 365 Defender como colaborador (esto también se puede hacer en el nivel de grupo de recursos o suscripción).

    Esto se hace en **Event Hubs Namespace \> Access Control (IAM) \> Add** and verify under **Role assignments**:

    ![Imagen del control de acceso](../../media/9c9c29137b90d5858920202d87680d16.png)

## <a name="setup-event-hub"></a>Centro de eventos de instalación


**Opción 1:**

Puede crear un centro de  eventos en el espacio de nombres y todos los tipos de eventos (tablas) que seleccione exportar se escribirán en **este único centro de** eventos.

**Opción 2:**

En lugar de exportar todos los tipos de evento (tablas) a un centro de eventos, puede exportar cada tabla a un centro de eventos diferente dentro del espacio de nombres del centro de eventos (un centro de eventos por tipo de evento).  

En esta opción, Microsoft 365 Defender creará centros de eventos.  
>[!NOTE]
> Si usa un espacio de  nombres de centro de eventos que no forma parte de un clúster de concentradores de eventos, solo podrá elegir hasta 10 tipos de eventos (tablas) para exportar en cada Configuración de exportación que defina, debido a una limitación de Azure de 10 centros de eventos por espacio de nombres de centro de eventos.

Por ejemplo:

![Imagen del centro de eventos de ejemplo](../../media/005c1f6c10c34420d387f594987f9ffe.png)

Si elige esta opción, puede ir a la sección [Configurar Microsoft 365 Defender para enviar tablas de correo](#configure-microsoft-365-defender-to-send-email-tables) electrónico.

Para crear un centro de eventos en el espacio de nombres, seleccione **Event Hubs \> + Event Hub**.

El recuento de particiones permite un rendimiento adicional mediante paralelismo, por lo que se recomienda aumentar este número en función de la carga que espera.  
Se recomiendan los valores predeterminados de retención y captura de mensajes de 1 y Off.

![Imagen de create Event Hub](../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png)

Para este Centro de eventos (no espacio de nombres) deberá configurar una directiva de acceso compartido con Enviar, Escuchar notificaciones. Haga clic en las directivas de acceso compartido del centro de eventos **\> \> +** Agregar y, a continuación, déle un nombre de directiva (no se usa en ningún otro lugar) y **compruebe Enviar** y **escuchar**.

![Imagen de directivas de acceso compartido](../../media/1867d13f46dc6a0f4cdae6cf00df24db.png)

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>Configurar Microsoft 365 Defender para enviar tablas de correo electrónico


### <a name="setup-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>Configurar Microsoft 365 Defender enviar tablas de correo electrónico a Splunk a través del Centro de eventos


1. Inicie sesión Microsoft 365 Defender <https://security.microsoft.com> con una cuenta que cumpla todos los requisitos de roles siguientes:

    - Rol colaborador en el nivel de recurso *de espacio de* nombres del centro de eventos o superior para el centro de eventos al que exportará. Sin esto, se producirá un error de exportación al intentar guardar la configuración.

    - Rol de administrador global o de administración de seguridad en el inquilino vinculado a Microsoft 365 Defender y Azure.

    ![Imagen del portal de seguridad](../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png)

1. Haga clic **en Exportación de datos sin procesar \> +Agregar**.

    Ahora usará los datos que registró anteriormente.

    **Nombre:** esto es local y debe ser lo que funcione en el entorno.

    **Reenviar eventos al centro de eventos:** Active esta casilla.

    **Identificador de recurso del centro de** eventos: este es el identificador de recurso de espacio de nombres del centro de eventos que registró anteriormente al configurar el centro de eventos.

    **Nombre del centro de** eventos: si creó un centro de eventos dentro del espacio de nombres del centro de eventos, pegue el nombre del centro de eventos que registró anteriormente.

    Si decide dejar que Microsoft 365 Defender para crear centros de eventos por tipos de evento (tablas), deje este campo vacío.

    **Tipos de eventos:** selecciona las tablas de búsqueda avanzada que quieres reenviar al Centro de eventos y, a continuación, a la aplicación personalizada. Las tablas de alertas son de Microsoft 365 Defender, las tablas de dispositivos son de Microsoft Defender para endpoint (EDR) y las tablas de correo electrónico son de Microsoft Defender para Office 365. Eventos de correo electrónico registra todas las transacciones de correo electrónico. La dirección URL (SafeLinks), los datos adjuntos (datos adjuntos de Caja fuerte) y los eventos posteriores a la entrega (ZAP) también se registran y se pueden unir a los eventos de correo electrónico en el campo NetworkMessageId.

    ![Imagen de la configuración de la API de streaming](../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png)

1. Asegúrese de hacer clic en **Enviar**.

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>Comprobar que los eventos se exportan al Centro de eventos


Puede comprobar que los eventos se envían al Centro de eventos ejecutando una consulta básica de búsqueda avanzada. Seleccione **Buscar consulta de búsqueda \> \> avanzada** y escriba la siguiente consulta:

```
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

Esto le mostrará cuántos correos electrónicos se recibieron en la última hora unidos en todas las demás tablas. También le mostrará si está viendo eventos que podrían exportarse al centro de eventos. Si este recuento muestra 0, no verá ningún dato que vaya al Centro de eventos.

![Imagen de la búsqueda avanzada](../../media/c305e57dc6f72fa9eb035943f244738e.png)

Una vez que haya comprobado que hay datos que exportar, puede ver el Centro de eventos para comprobar que los mensajes están entrantes. Esto puede tardar hasta una hora. 
 
1. En Azure, vaya a **Event Hubs \> Click on the Namespace Event \> Hubs Click on the Event \> Hub**.  
1. En **Información** general, desplácese hacia abajo y en el gráfico Mensajes debería ver Mensajes entrantes. Si no ves ningún resultado, no habrá mensajes para que la aplicación personalizada ingieren.

    ![Imagen de la pestaña información general con mensajes](../../media/e88060e315d76e74269a3fc866df047f.png)
