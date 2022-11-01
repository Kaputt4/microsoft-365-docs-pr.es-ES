---
title: Data Residency para Microsoft Teams
description: Más información sobre la residencia de datos para Microsoft Teams
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.service: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.date: ''
ms.reviewer: dmwmsft
ms.custom:
- it-pro
ms.collection:
- M365-subscription-management
ms.openlocfilehash: 6f7853537a4a263e888fc27b496cd61f83f13024
ms.sourcegitcommit: 0c72639cc3dc74667a6b14343d303f318e70d457
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2022
ms.locfileid: "68806183"
---
# <a name="data-residency-for-microsoft-teams"></a>Data Residency para Microsoft Teams

## <a name="data-residency-commitments-available"></a>Data Residency compromisos disponibles

### <a name="product-terms"></a>Términos del producto

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_, la Unión Europea o la Estados Unidos.

**Compromiso:**

_Para conocer el idioma actual, consulte los [Términos del producto de privacidad y seguridad](https://www.microsoft.com/licensing/terms/product/PrivacyandSecurityTerms/all) y vea la sección titulada "Ubicación de los datos del cliente en reposo para Core Online Services"._

### <a name="advanced-data-residency-add-on"></a>Complemento de Data Residency avanzado

Condiciones necesarias:

1. _El inquilino_ tiene un país de registro incluido en _Geografía de la región local_ o _Geografía de región local expandida_.
1. _El inquilino_ tiene una suscripción de Data Residency avanzada válida para todos los usuarios del _inquilino_.
1. Los datos del cliente de la suscripción de Microsoft Teams se aprovisionan en _Geografía de la región local_ o _Geografía expandida de la región local_.

**Compromiso:**

Consulte la [página Compromiso de ADR](m365-dr-commitments.md#microsoft-teams) para conocer los compromisos específicos proporcionados a través de los Términos del producto.  Algunos ejemplos de los datos confirmados son:

- Mensajes de chat/ canal y estructura de equipo: cada equipo de Microsoft Teams está respaldado por un grupo moderno de Microsoft 365 y su sitio de SharePoint y su buzón de Exchange. Los chats privados (incluidos los chats de grupo), los mensajes enviados como parte de una conversación en un canal y la estructura de los equipos y canales se almacenan en un servicio de chat con tecnología de Azure. Los datos también se almacenan en una carpeta oculta en los buzones de usuario y grupo para habilitar las características de protección de la información.  
- Imágenes y medios: los medios utilizados en los chats (excepto los GIF giphy que no se almacenan pero son un vínculo de referencia a la dirección URL original de Giphy) se almacenan en un servicio multimedia basado en Azure implementado en las mismas ubicaciones que el servicio de chat.
- Grabaciones de reuniones: para los usuarios de Microsoft Stream (en SharePoint) las grabaciones de reuniones se almacenan en el almacenamiento OneDrive para la Empresa del usuario que inicia la grabación.

### <a name="multi-geo-add-on"></a>Complemento multigeográfica

Condiciones necesarias:

1. _Los inquilinos_ tienen una suscripción multigeográfica válida que cubre a todos los usuarios asignados a una _geografía satélite_.
1. El cliente debe tener una Enterprise Agreement activa.
1. El total de unidades multigeográficas adquiridas debe ser superior al 5 % del total de puestos elegibles en el _inquilino_.

**Compromiso:** Los clientes pueden asignar usuarios de Microsoft Teams a cualquier _geografía satélite_ compatible con multigeográfica. Los siguientes datos de cliente se almacenarán en la _geografía satélite_ pertinente: datos de chat de Teams que constan de mensajes de chat, incluidos mensajes privados, mensajes de canal e imágenes que se usan en los chats.

## <a name="multi-geo-capabilities-in-microsoft-teams"></a>Funcionalidades multigeográficas en Microsoft Teams

Las funcionalidades multigeográficas de Teams permiten que los datos de chat de Teams se almacenen en reposo en una ubicación _de geografía de región de macro_ especificada o _de geografía de región local_ . Los datos de chat constan de mensajes de chat, incluidos mensajes privados, mensajes de canal e imágenes que se usan en los chats.

Teams usa la ubicación de datos preferida (PDL) para que los usuarios y grupos determinen dónde almacenar los datos. Si la PDL no está establecida o no es válida, los datos se almacenan en la ubicación _geografía aprovisionada principal_ del inquilino.

>[!NOTE]
>Las funcionalidades multigeográficas de Teams se implantaron en julio de 2021. Los mensajes de chat y canal se migrarán automáticamente a la ubicación geográfica de _la región de macro_ o geografía de _la región local_ correcta en los próximos trimestres. Los nuevos cambios de PDL se procesarán después de que el _inquilino_ haya completado la sincronización inicial y los nuevos cambios de PDL posteriores se pondrán en cola y se procesarán en el orden en que se reciban.

### <a name="user-chat"></a>Chat de usuario

El chat de usuario incluye mensajes de reunión uno a uno, uno a varios y privados.

Cuando se crea un nuevo usuario, Teams lee la PDL del usuario y almacena todos sus datos de chat en la ubicación _Geografía de la región de macro_ o _Geografía de la región local_ .
En el caso de los usuarios existentes, si un administrador agrega o modifica la PDL de un usuario, los datos de chat de ese usuario se agregan a una cola de migración para moverse a la ubicación _geografía de la región de macro_ o a la ubicación _geográfica de la región local_ especificada.

La ubicación de almacenamiento de un chat uno a uno o uno a varios se basa en la PDL de la persona que creó el chat. Si se cambia la PDL de ese usuario, el chat se migrará a la nueva ubicación _Geografía de la región de macro_ o _Geografía de la región local_ . La ubicación de almacenamiento de un chat de reunión se basa en la PDL del organizador de la reunión.

Para buscar la ubicación actual de los datos de Teams de un usuario, conéctese a PowerShell de Teams y ejecute el siguiente comando:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

### <a name="channel-messages"></a>Mensajes del canal

Cada grupo de Microsoft 365 tiene una ubicación de datos preferida (PDL) que indica la ubicación _geográfica_ donde se van a almacenar los datos relacionados. Teams usa la PDL del grupo asociado a cada equipo para determinar dónde almacenar los datos de mensajería de canal para ese equipo. Esto incluye canales privados y chat que se producen dentro de una reunión de canal.

Cuando un usuario crea un nuevo equipo, la PDL de ese usuario determina qué PDL se asigna al grupo de Microsoft 365. La PDL del grupo determina dónde se almacenan los datos de ese equipo. Si la PDL de ese usuario cambia más adelante, no se cambia la PDL del grupo.

En el caso de los equipos existentes, si un administrador agrega o modifica la PDL para el grupo de Microsoft 365 que respalda a un equipo, los datos de mensajería de canal de ese equipo se agregan a una cola de migración para moverse a la ubicación _geografía de la región de macros_ o a la ubicación _geográfica de la región local_ especificada.

Al cambiar la PDL del grupo de Microsoft 365, se ponen en cola los datos de Teams para migrarlos a la ubicación _geográfica de la región de macros_ o a la ubicación _geográfica de la región local_ elegida. Sin embargo, esto no migra automáticamente el sitio de SharePoint ni los archivos asociados al grupo. Debe mover el sitio por separado siguiendo los procedimientos descritos en Mover un sitio de SharePoint a otra ubicación _geográfica_ . Asegúrese de realizar ambos pasos para evitar los datos de Teams y los datos de SharePoint para un grupo en ubicaciones diferentes.

Para buscar la ubicación actual de los datos de un equipo, conéctese a PowerShell de Teams y ejecute el siguiente comando:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

### <a name="user-experience"></a>Experiencia del usuario

Teams Multi-Geo es perfecto para el usuario final. Una vez que cambie la PDL de un usuario o un grupo, los datos respectivos se pondrán en cola para la migración y la migración se producirá automáticamente sin ningún impacto para el usuario o su cliente de Teams, incluso si están activos mientras se produce la migración.

### <a name="migration"></a>Migración

**Pestaña Archivos** Una vez completada la migración, la pestaña Archivos puede tardar más tiempo (hasta 7 segundos) en cargarse completamente cuando el usuario intenta usarla por primera vez.

**Período de solo lectura** Los servicios de chat de Teams mueven cada subproceso individualmente. El subproceso está bloqueado en un estado de solo lectura durante el movimiento, que dura unos segundos por subproceso. Los subprocesos siguen siendo accesibles durante la migración.

**En el ámbito de la migración** Además de Exchange Online, SharePoint Online y OneDrive para la Empresa; Microsoft migrará los datos de Teams al centro de datos local.

- Mensajes de chat de Teams, incluidos mensajes privados y mensajes de canal.
- Imágenes de Teams usadas en los chats.

Los archivos de Teams se almacenan en SharePoint Online y los archivos de chat de Teams se almacenan en OneDrive para la Empresa. El correo de voz, el calendario y los contactos se almacenan en Exchange Online. En muchos casos, el cliente ya usa Exchange Online, SharePoint Online y OneDrive para la Empresa en el centro de datos local _Geography_ y también forman parte del programa de migración de Microsoft 365 para los países de clientes aptos.

### <a name="how-can-i-determine-customer-data-location"></a>¿Cómo puedo determinar la ubicación de los datos del cliente?
Puede encontrar la ubicación de datos real en el Centro de Administración de _inquilinos_. Como administrador de _inquilinos_, puede encontrar la ubicación de datos real para los datos confirmados; para ello, vaya a Administración| Configuración| Configuración de la organización| Perfil de la organización| Ubicación de datos.
