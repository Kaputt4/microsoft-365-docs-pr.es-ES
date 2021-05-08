---
title: Cambios en el servicio y comunicación
description: Cómo se producen los cambios en el servicio y se comunican
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 20af244d14f8f29e0175fb5e8efdabff94ff9a2b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244109"
---
# <a name="service-changes-and-communication"></a>Cambios en el servicio y comunicación

A veces, Microsoft puede necesitar cambiar los detalles sobre la forma en que Escritorio administrado de Microsoft funciona. Del mismo modo, es posible que también tenga que realizar cambios que afecten al servicio. Estos cambios se controlan de forma diferente en función de su importancia. En este tema se definen los cambios que consideramos principales y se explica cómo los manejamos frente a otros cambios.



## <a name="changes-made-by-microsoft"></a>Cambios realizados por Microsoft

Le aviso con al menos 30 días de antelación para cualquier cambio importante que requiera acción. Le haremos saber mediante el sistema de mensajería Escritorio administrado de Microsoft portal de administración.

**Los cambios** principales son los que pueden afectar a cualquiera de estas áreas:
- Cambios que afectan a la productividad diaria
- Cambios en las características y aplicaciones personalizadas
- Aumentar o disminuir la capacidad visible
- Cambios en la personalización de marca del producto que pueden causar confusión o cambios en los procesos del departamento de soporte técnico y el material de referencia o las direcciones URL
- Cambios que requieren permisos más allá de los requeridos por el servicio para las operaciones diarias, excluyendo las acciones que impiden o corrigen problemas
- Cambios en el lugar donde se almacenan los datos
- Agregar un nuevo servicio o aplicación de componentes al ámbito del servicio
- Eliminación de un servicio o aplicación de componentes del ámbito del servicio
- Agregar nueva característica al servicio

> [!NOTE]
> Es posible que debamos realizar cambios para mitigar incidentes o problemas de seguridad que se excluirían de la directiva de notificación de 30 días.

Rutinariamente, realizaremos otros cambios en el servicio para mejorar la experiencia del usuario, la seguridad, la confiabilidad y los informes. Algunos ejemplos de estos cambios son:

- Instalación de Windows y Office actualizaciones
- Actualizaciones de la línea base de seguridad aplicada a dispositivos
- Dispositivos compatibles. Para ver los dispositivos recomendados, filtre Escritorio administrado de Microsoft en el sitio [De Windows 10 Pro de dispositivos](https://www.microsoft.com/windowsforbusiness/view-all-devices) empresariales.

Comunicaremos estos cambios mediante canales establecidos. Si tiene alguna pregunta sobre los cambios, póngase en contacto con el equipo Escritorio administrado de Microsoft [operaciones](../working-with-managed-desktop/admin-support.md). Los cambios en el servicio también se documentan según sea necesario en el [historial de cambios](../change-history-managed-desktop.md).

Escritorio administrado de Microsoft cambios y comunicaciones se rigen por dos directivas de Microsoft:
- [Directiva de ciclo de vida moderno](https://support.microsoft.com/help/30881/modern-lifecycle-policy)
- [Microsoft 365 Cambiar directiva de comunicación](/office365/admin/manage/message-center)

## <a name="changes-you-make"></a>Cambios que realice

Algunos cambios que puede realizar en el entorno podrían afectar a Escritorio administrado de Microsoft. Para estos cambios importantes, le pedimos que nos dé un aviso de al menos 30 días enviando una solicitud de servicio en el portal de administración Escritorio administrado de Microsoft administración. Consulta [Compatibilidad con administradores Escritorio administrado de Microsoft](../working-with-managed-desktop/admin-support.md) para obtener instrucciones. Esto nos permite un tiempo adecuado para planear y preparar el cambio para evitar interrupciones.

Los cambios principales son los que pueden afectar a cualquiera de estas áreas:

- Sistemas y grupos de identidades
- Controles de red y redes, como firewalls, proxy o almacenamiento en caché, y sistemas VPN
- Controles para obtener acceso a configuraciones de servicios en la nube
- Certificados de usuario o dispositivo usados para la identidad o la protección de servicios de red
- Sistemas de administración que interactúan con el servicio
- Sistemas de seguridad o agentes que interactúan con el servicio
- Configuración de cualquiera de los servicios Microsoft 365 en la nube asociados con o usados por el servicio

Es probable que estos cambios no sean perjudiciales, por lo que no es necesario que nos haga saber acerca de ellos con antelación:

- Limpieza de objetos huérfanos
- Agregar o quitar usuarios del servicio
- Configuración del sistema que no tiene un impacto material en la entrega del Escritorio administrado de Microsoft
- Actualizaciones de la versión de la aplicación, a excepción de las aplicaciones VPN o proxy