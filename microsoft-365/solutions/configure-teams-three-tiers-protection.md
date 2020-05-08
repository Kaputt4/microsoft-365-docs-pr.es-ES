---
title: Configurar Teams con tres niveles de protección
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- M365solutions
ms.custom:
- Ent_Architecture
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
description: Recomendaciones de configuración para proteger archivos en Microsoft Teams.
ms.openlocfilehash: 129baed3286e445b9e0e440d4ec7f7a3402d3305
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159436"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>Configurar Teams con tres niveles de protección

En los artículo de esta serie se ofrecen recomendaciones para configurar equipos en Microsoft Teams y sus sitios de SharePoint asociados, de forma que se equilibre la seguridad con la facilidad de colaboración.

Aquí se definen cuatro configuraciones distintas, empezando por un equipo público con las directivas de uso compartido más abiertas. Cada configuración adicional representa un paso significativo para la protección, mientras que el correspondiente conjunto de miembros del equipo pierde capacidad de acceder a los archivos almacenados en Teams y de colaborar en ellos. 

Las configuraciones que se explican en este artículo concuerdan con las recomendaciones de Microsoft para los tres niveles de protección de datos, identidades y dispositivos:

- Protección de base de referencia

- protección confidencial

- Protección altamente confidencial

Para más información sobre estos niveles y capacidades recomendadas para cada nivel, vea los siguientes recursos.

- [Protección de identidades y dispositivos para Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#identity-and-device-protection-for-office-365)

- [Soluciones de protección de archivos en Office 365](https://docs.microsoft.com/office365/enterprise/microsoft-cloud-it-architecture-resources#file-protection-solutions-in-office-365)

## <a name="three-tiers-at-a-glance"></a>Tres niveles de un vistazo

En la tabla siguiente se resumen las configuraciones para cada nivel. Use estas configuraciones como punto de partida y ajuste las configuraciones para satisfacer las necesidades de la organización. Es posible que no necesite todos los niveles.

||**Línea base (pública)**|**Línea base (privada)**|**Confidencial**|**Altamente confidencial**|
|:-----|:-----|:-----|:-----|:-----|
|Equipo privado o público|Público|Private|Private|Private|
|¿Quién tiene acceso?|Todos los usuarios de la organización, incluidos los usuarios B2B.|Solo los miembros del equipo. Otros usuarios pueden solicitar acceso al sitio asociado.|Solo los miembros del equipo.|Solo los miembros del equipo.|
|Canales privados|Los propietarios y miembros pueden crear canales privados|Los propietarios y miembros pueden crear canales privados|Solo los propietarios pueden crear canales privados|Solo los propietarios pueden crear canales privados|
|Acceso de invitado en el nivel de sitio|**Invitados nuevos y existentes** (predeterminado).|**Invitados nuevos y existentes** (predeterminado).|**Invitados nuevos y existentes** o **Solo las personas de su organización** en función de las necesidades del equipo.|**Invitados nuevos y existentes** o **Solo las personas de su organización** en función de las necesidades del equipo.|
|Configuración de uso compartido del sitio |**Los propietarios y los miembros del sitio, y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios del sitio pueden compartir el sitio.**|**Los propietarios y los miembros del sitio, y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios del sitio pueden compartir el sitio.**|**Los propietarios y los miembros del sitio, y las personas con permisos de edición pueden compartir archivos y carpetas, pero solo los propietarios del sitio pueden compartir el sitio.**|**Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio.**<br>Solicitudes de acceso **desactivadas**.|
|Acceso de un dispositivo no administrado a nivel de sitio|**Acceso total desde aplicaciones de escritorio, aplicaciones móviles y la web** (predeterminado).|**Acceso total desde aplicaciones de escritorio, aplicaciones móviles y la web** (predeterminado).|**Permitir el acceso limitado, solo a través de la web**.|**Bloquear acceso**.|
|Tipo de vínculo de uso compartido predeterminado|**Solo personas de la organización**|**Solo personas de la organización**|**Usuarios específicos**|**Personas que tienen acceso ya existente**|
|Etiquetas de confidencialidad|Ninguno|Ninguno|Etiqueta de confidencialidad usada para clasificar el equipo y controlar el uso compartido de invitado y el acceso de dispositivos no administrados.|Etiqueta de confidencialidad usada para clasificar el equipo y controlar el uso compartido de invitado y el acceso de dispositivos no administrados. La etiqueta también se puede usar en archivos para encriptar archivos.|

Una variación de la opción altamente confidencial, [Equipos con aislamiento de seguridad](secure-teams-security-isolation.md) usa una etiqueta de confidencialidad exclusiva para un equipo, lo que proporciona seguridad adicional. Puede usar esta etiqueta para cifrar archivos y solo podrán leerlos los miembros de ese equipo.

La protección de línea base incluye equipos públicos privados. Los equipos públicos son aquellos visibles y accesibles por cualquier persona de la organización. Los equipos privados solo pueden detectarlos y acceder a ellos los miembros del equipo. Ambas configuraciones restringen el uso compartido del sitio de SharePoint asociado a los propietarios del equipo para ayudar en la administración de permisos.

Los equipos para la protección confidencial y altamente confidencial son equipos privados en los que el uso compartido y la solicitud de acceso para el sitio asociado son limitados y las etiquetas de confidencialidad se usan para establecer directivas en relación con el uso compartido de invitados, el acceso a dispositivos y el cifrado de contenido.

## <a name="sensitivity-labels"></a>Etiquetas de confidencialidad

Los niveles confidenciales y muy confidenciales usan etiquetas de confidencialidad para ayudar a proteger el equipo y sus archivos. Para implementar estos niveles, debe habilitar [etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Office 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Aunque el nivel de línea base no requiere etiquetas de confidencialidad, considere la posibilidad de crear una etiqueta "general" y requerir que todos los equipos tengan la etiqueta. Esto ayudará a garantizar que los usuarios hagan una elección consciente sobre la confidencialidad cuando creen un equipo. Si tiene previsto implementar niveles confidenciales o altamente confidenciales, le recomendamos que cree una etiqueta "general" que pueda usar para los equipos de línea base y para los archivos que no son confidenciales.

Si es nuevo en el uso de etiquetas de confidencialidad, le recomendamos que lea [Empezar a usar las etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-sensitivity-labels) para comenzar. 

Si ya ha implementado etiquetas de confidencialidad en la organización, tenga en cuenta que las etiquetas utilizadas en los niveles confidenciales y muy confidenciales se ajustan a la estrategia general de la etiqueta. 

## <a name="sharing-the-sharepoint-site"></a>Compartir el sitio de SharePoint

Cada equipo tiene un sitio de SharePoint asociado en el que se almacenan los documentos. (Esta es la pestaña **Archivos** en un canal de equipos). El sitio de SharePoint conserva su propia administración de permisos, pero se vincula a los permisos de equipo. Los propietarios del equipo se incluyen como propietarios del sitio y los miembros del equipo se incluyen como miembros del sitio en el sitio asociado.

Los permisos resultantes permiten lo siguiente:

- Que los propietarios de los equipos administren el sitio y tengan control total sobre el contenido del sitio.
- Que los miembros de los equipos puedan crear y editar archivos en el sitio. 

De forma predeterminada, los propietarios y miembros del equipo pueden compartir el sitio con personas ajenas al equipo sin tener que agregarlos al equipo. Se recomienda no hacerlo ya que complica la administración de usuarios y puede dar lugar a que personas que no son miembros del equipo tengan acceso a los archivos del equipo sin que los propietarios del equipo se den cuenta. Para ayudar a evitar esto, comenzando por el nivel de línea base de protección, se recomienda permitir que solo los propietarios puedan compartir el sitio directamente.

Mientras que los equipos no tienen una opción de permisos de solo lectura, el sitio de SharePoint sí. Si tiene miembros de grupos de asociados que necesitan ver archivos del equipo, pero no editarlos, considere la posibilidad de agregarlos directamente al sitio de SharePoint con permisos de lectura.

## <a name="sharing-files-and-folders"></a>Compartir archivos y carpetas

De forma predeterminada, los propietarios y miembros del equipo pueden compartir archivos y carpetas con personas ajenas al equipo. Esto puede incluir personas de fuera de su organización, si ha permitido el uso compartido de invitados. En los tres niveles, actualizamos el tipo de vínculo compartido predeterminado para ayudar a evitar el uso compartido accidental. En el nivel altamente confidencial, restringimos este uso compartido únicamente a los propietarios de equipo.

## <a name="guest-sharing"></a>Uso compartido de invitado

Si necesita colaborar con personas de fuera de su organización, le recomendamos que configure la [integración de SharePoint y OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) para obtener la mejor experiencia de uso compartido y administración.

El uso compartido de invitado de Teams está desactivado de forma predeterminada, aunque el uso compartido para grupos de Office 365 (donde se almacenan los miembros del equipo) y SharePoint está activado. Activamos el uso compartido de Teams en el nivel de línea base, y puede desactivarlo si es necesario en los niveles confidenciales y altamente confidenciales mediante el uso de una etiqueta de confidencialidad.

La etiqueta de confidencialidad solo afecta al uso compartido de invitado para el equipo. La configuración de uso compartido de invitado para el sitio de SharePoint asociado se controla por separado, y hemos alineado las dos configuraciones tanto para los niveles confidenciales como altamente confidenciales.

En la capa altamente confidencial, configuramos la etiqueta de confidencialidad para cifrar los archivos a los que se aplica. Si necesita que los invitados tengan acceso a estos archivos, deberá concederles permisos cuando cree la etiqueta.

Le recomendamos encarecidamente que deje el uso compartido de invitado activado para el nivel de línea base y para los niveles de confidencialidad o altamente confidenciales si necesita colaborar con personas ajenas a su organización. Las características de uso compartido de invitado de Microsoft 365 proporcionan una experiencia de uso compartido mucho más segura y controlada que al enviar archivos como datos adjuntos en mensajes de correo electrónico. También reduce el riesgo de TI en la sombra donde los usuarios usan productos de consumo no controlados para compartir con colaboradores externos legítimos.

Vea las siguientes referencias para crear un entorno de uso compartido de invitado seguro y productivo para su organización:

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)
- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](share-limit-accidental-exposure.md)
- [Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>Acceso desde dispositivos no administrados

Para los niveles confidenciales y altamente confidenciales, restringimos el acceso al contenido de SharePoint con etiquetas de confidencialidad. El acceso condicional de Azure AD ofrece muchas opciones para determinar cómo los usuarios acceden a Microsoft 365, incluyendo limitaciones basadas en la ubicación, el riesgo, el cumplimiento de dispositivos y otros factores. Se recomienda leer [¿Qué es el acceso condicional?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) y considerar otras directivas que podrían ser adecuadas para su organización.

## <a name="next-step"></a>Paso siguiente

Comience por [configurar el nivel de línea base de protección](configure-teams-baseline-protection.md). Si es necesario, puede agregar [protección confidencial](configure-teams-sensitive-protection.md) y [protección altamente confidencial](configure-teams-highly-sensitive-protection.md) además de la línea base.

## <a name="see-also"></a>Consulte también

[Seguridad y cumplimiento en Microsoft Teams](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[Directivas de alerta en el Centro de seguridad y cumplimiento](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)
