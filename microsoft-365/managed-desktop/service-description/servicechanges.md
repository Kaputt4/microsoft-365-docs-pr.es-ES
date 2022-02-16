---
title: Cambios en el servicio y comunicación
description: Cómo se producen los cambios en el servicio y se comunican
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 59c5c2c10a344c8edec047b5f9290fa5d3d08d75
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825438"
---
# <a name="service-changes-and-communication"></a>Cambios en el servicio y comunicación

En ocasiones, Es posible que Microsoft necesite cambiar los detalles sobre el funcionamiento del Escritorio administrado de Microsoft. Del mismo modo, es posible que también tenga que realizar cambios que afecten al servicio. Estos cambios se controlan de forma diferente en función de su importancia. En este artículo se definen los cambios que consideramos como cambios principales y se explica cómo los manejamos frente a otros cambios.

## <a name="changes-made-by-microsoft"></a>Cambios realizados por Microsoft

Le aviso con al menos 30 días de antelación para cualquier cambio importante que requiera acción. Le haremos saber mediante el sistema de mensajería del portal de administración de escritorio administrado de Microsoft.

**Los cambios** principales son aquellos que pueden afectar a cualquiera de estas áreas:

- Cambios que afectan a la productividad diaria.
- Cambios en las aplicaciones y características personalizadas.
- Aumentar o disminuir la capacidad visible.
- Cambios en la personalización de marca del producto que pueden causar confusión o cambios en los procesos del departamento de soporte técnico y el material de referencia o las direcciones URL.
- Cambios que requieren permisos más allá de los requeridos por el servicio para las operaciones diarias, excluyendo las acciones que impiden o corrigen problemas.
- Cambios en el lugar donde se almacenan los datos.
- Agregar un nuevo servicio de componentes o aplicación al ámbito del servicio.
- Eliminación de un servicio o aplicación de componentes del ámbito del servicio.
- Agregar nueva característica al servicio.

> [!NOTE]
> Es posible que debamos realizar cambios para mitigar incidentes o problemas de seguridad que se excluirían de la directiva de notificación de 30 días.

Rutinariamente, realizaremos otros cambios en el servicio para mejorar la experiencia del usuario, la seguridad, la confiabilidad y los informes. Algunos ejemplos de estos cambios son:

- Instalación de Windows y Office actualizaciones.
- Actualizaciones de la línea base de seguridad aplicada a los dispositivos.
- Dispositivos compatibles. Para ver los dispositivos recomendados, filtre para Escritorio administrado de Microsoft en el sitio [Windows Pro dispositivos empresariales](https://www.microsoft.com/windows/business/devices).

Comunicaremos estos cambios mediante canales establecidos. Si tiene alguna pregunta sobre los cambios, póngase en contacto con el equipo de Operaciones de escritorio [administrado de](../working-with-managed-desktop/admin-support.md) Microsoft. Los cambios en el servicio también se documentan según sea necesario en el [historial de cambios](../change-history-managed-desktop.md).

Los cambios y las comunicaciones de Escritorio administrado de Microsoft se rigen por dos directivas de Microsoft:

- [Directiva de ciclo de vida moderno](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365 cambiar la directiva de comunicación](/office365/admin/manage/message-center)

## <a name="changes-you-make"></a>Cambios que realice

Algunos cambios que puede realizar en su entorno podrían afectar al Escritorio administrado de Microsoft.

Para estos cambios importantes, le pedimos que nos dé un aviso de al menos 30 días enviando una solicitud de soporte técnico en el portal de administración de escritorio administrado de Microsoft. Para obtener instrucciones, consulte [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md). Esto nos permite un tiempo adecuado para planear y preparar el cambio para evitar interrupciones.

**Los cambios** principales son aquellos que pueden afectar a cualquiera de estas áreas:

- Sistemas y grupos de identidades.
- Controles de red y redes, como firewalls, proxy o almacenamiento en caché, y sistemas VPN.
- Controles para obtener acceso a configuraciones de servicios en la nube.
- Certificados de usuario o dispositivo usados para la identidad o la protección de servicios de red.
- Sistemas de administración que interactúan con el servicio.
- Sistemas de seguridad o agentes que interactúan con el servicio.
- Configuración de cualquiera de los Microsoft 365 en la nube asociados con o usados por el servicio.

Es probable que estos cambios no sean perjudiciales, por lo que no es necesario que nos haga saber acerca de ellos con antelación:

- Limpieza de objetos huérfanos.
- Agregar o quitar usuarios del servicio.
- Configuración del sistema que no tiene un impacto material en la entrega del Escritorio administrado de Microsoft.
- Actualizaciones de versión de aplicación, excepto para aplicaciones VPN o proxy.
