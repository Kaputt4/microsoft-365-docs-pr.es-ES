---
title: Configurar la colaboración moderna con Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
description: Obtenga información sobre cómo configurar la colaboración de contenido segura en Teams para proteger los datos en función de su confidencialidad.
ms.openlocfilehash: c92dc6dbf62d3fa0cb00307447b3d5a793830394
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233861"
---
# <a name="set-up-secure-collaboration-with-microsoft-365"></a>Configurar la colaboración moderna con Microsoft 365

Poder compartir fácilmente información con las personas correctas a la vez que se evita el uso compartido en exceso es clave para el éxito de una organización. Esto incluye poder compartir datos confidenciales de forma segura solo con aquellos que deberían tener acceso a ellos. Según el proyecto, esto puede incluir el uso compartido de datos confidenciales con personas ajenas a la organización.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Esta guía de soluciones de colaboración incluye dos componentes que le ayudarán:
- Implementar Microsoft Teams con el nivel de protección adecuado para cada proyecto
- Configurar el uso compartido externo con las opciones de seguridad adecuadas para cada proyecto

![Implementar Teams con la protección adecuada y configurar el uso compartido externo con la configuración de seguridad adecuada](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Si las herramientas de colaboración de contenido versátiles y fáciles de usar no están disponibles, los usuarios a menudo colaborarán por correo electrónico con documentos. Este es un método de colaboración tedioso y propenso a errores y puede aumentar el riesgo de compartir información de forma inadecuada. Si a los usuarios les resulta demasiado difícil compartir información, podrían volver a usar productos de consumidor que no están regido por TI. Esto puede suponer un riesgo aún mayor.

Con Microsoft 365, puede implementar Teams con una variedad de configuraciones que le ayudarán a:

- Proteger la propiedad intelectual
- Habilitar la colaboración sencilla
- Crear un equilibrio entre la seguridad y la facilidad de uso que aumente la satisfacción del usuario y reduzca el riesgo de sombras de IT

La mayoría de las organizaciones tienen una variedad de información, con distintos grados de confidencialidad y distintos grados de impacto en la empresa si la información se comparte de forma inadecuada. Dependiendo de la confidencialidad de un elemento de información determinado, es posible que desee permitir el uso compartido con:

- Cualquiera (no autenticado)
- Personas dentro de la organización
- Personas específicas dentro de la organización
- Personas específicas dentro y fuera de la organización

La información, como los folletos de marketing, está pensada para compartir ampliamente fuera de la organización. La información, como los menús de cafetería, no está destinada al uso compartido externo, pero no tendría ningún impacto en la empresa si se compartiese externamente. Estos tipos de información necesitan poca o ninguna protección.

Esos mismos folletos de marketing, mientras están en desarrollo, solo se pueden compartir dentro de la organización. En este caso, la configuración de uso compartido predeterminada en Teams puede ser suficiente.

La información sobre un nuevo producto que está en desarrollo puede considerarse confidencial, incluso dentro de la organización. Un mayor grado de protección podría ser apropiado en este caso. Puede restringir el acceso a esta información a los miembros de un equipo específico, por ejemplo. Según el proyecto, es posible que deba colaborar con personas ajenas a la organización, como un proveedor o una organización asociada.

La información que es fundamental para el éxito de su organización o que tiene requisitos de seguridad o cumplimiento estrictos puede requerir niveles de protección aún mayores.

![Escala de riesgos de bajo (folleto publicado) a alto (datos empresariales confidenciales)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Para todos los escenarios mencionados anteriormente, puede usar los equipos de Microsoft Teams para almacenar, compartir y colaborar en la información. 

Para configurar la colaboración segura, use estas funciones y características de Microsoft 365.

| Producto o componente | Funcionalidad o característica | Licencias |
|:-------|:-----|:-------|
| Microsoft Defender para Office 365 | Datos adjuntos seguros para SPO, OneDrive y Teams; Documentos seguros; Vínculos seguros para Teams    | Microsoft 365 E1, E3 y E5 |
| SharePoint    | Directivas de uso compartido de sitios y archivos, permisos de uso compartido de sitios, vínculos para compartir, solicitudes de acceso, configuración de uso compartido de invitados del sitio | Microsoft 365 E1, E3 y E5 |
| Microsoft Teams   | Acceso de invitado, equipos privados, canales privados | Microsoft 365 E1, E3 y E5 |
| Cumplimiento de Microsoft 365  | Etiquetas de confidencialidad    | Microsoft 365 E3 y E5 |

### <a name="using-teams-for-all-kinds-of-data"></a>Uso de Teams para todo tipo de datos

Para administrar el acceso a la información con diferentes sensibilidades, hemos desarrollado tres niveles diferentes de [protección para Teams.](configure-teams-three-tiers-protection.md) Puede personalizar cualquiera de estos niveles para satisfacer mejor las necesidades o su empresa. 

![Imagen en miniatura para el póster de la arquitectura lógica de Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Estos niveles (línea  *base,* confidencial y altamente confidencial) aumentan gradualmente las protecciones que ayudan a evitar el exceso de uso compartido y la posible fuga de información, como se muestra en la tabla siguiente. 

|-|**Nivel de línea base**|**Nivel confidencial**|**Nivel altamente confidencial**|
|:--|:-----------|:------------|:-------------------|
|Equipo público o privado|Ambos|Private|Private|
|Uso compartido no autenticado|Blocked|Blocked|Blocked|
|Uso compartido de archivos|Permitido|Permitido|Solo los propietarios del equipo pueden compartir.|
|Pertenencia al equipo|Cualquier persona puede unirse a equipos públicos.<br>Se requiere la aprobación del propietario del equipo para unirse a equipos privados.|Se requiere la aprobación del propietario del equipo para unirse.|Se requiere la aprobación del propietario del equipo para unirse.|
|Cifrado de documentos|||Disponible con etiqueta de confidencialidad|
|Uso compartido de invitados|Permitido|Se puede permitir o bloquear|Se puede permitir o bloquear|
|Dispositivos no administrados|Sin restricciones|Acceso solo web|Blocked|

La configuración de estos niveles implica lo siguiente:

- Configuración de opciones en Teams para el acceso de invitados y canales privados
- Configuración de opciones en el sitio de SharePoint asociado a un equipo para el uso compartido interno e invitado, las solicitudes de acceso y los vínculos de uso compartido
- Para los *niveles confidenciales* y *altamente* confidenciales, configurar etiquetas de confidencialidad para clasificar los equipos y controlar el uso compartido de invitados y el acceso desde dispositivos no administrados
- Para el *nivel altamente* confidencial, configurar una etiqueta de confidencialidad para cifrar los documentos a los que se aplica

Comience con el nivel de línea base  y, a continuación, agregue equipos que usen los niveles confidenciales y altamente confidenciales según sea necesario para ayudar a proteger la información de su organización.  Vea estos recursos para empezar:

- [Configure equipos con la protección de base de referencia](configure-teams-baseline-protection.md)
- [Configure equipos con protección de datos confidenciales](configure-teams-sensitive-protection.md)
- [Configuración de equipos con protección de datos con un nivel de confidencialidad alto](configure-teams-highly-sensitive-protection.md)

Si tiene un proyecto altamente confidencial que requiere protección adicional contra el uso compartido incluso dentro de su organización, puede configurar un equipo que use su propia etiqueta de confidencialidad para cifrar archivos de modo que solo los miembros del equipo puedan leerlos. Consulte [Configurar un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para obtener más información.

### <a name="sharing-with-people-outside-your-organization"></a>Compartir con personas de fuera de la organización

Es posible que tenga que [compartir información de cualquier confidencialidad con personas ajenas a su organización.](collaborate-with-people-outside-your-organization.md) Esto puede oscilar entre compartir un único documento con una sola persona o colaborar en un proyecto importante con una organización de socios de gran tamaño o escritores de todo el mundo. En Microsoft 365, esta gama de uso compartido externo se puede realizar fácilmente y con las medidas de seguridad adecuadas para ayudar a proteger su información confidencial.

Estos recursos le ayudarán a empezar a configurar el entorno para colaborar con personas ajenas a su organización:

- [Colaborar en documentos para](collaborate-on-documents.md) compartir archivos individuales de carpetas.
- [Colaborar en un sitio para](collaborate-in-site.md) colaborar con invitados en un sitio de SharePoint.
- [Colaborar como equipo para](collaborate-as-team.md) colaborar con invitados en un equipo.

En función de la confidencialidad de la información que se comparta, puede agregar medidas de seguridad para ayudar a evitar el exceso de uso compartido. Estos recursos le ayudarán a configurar las protecciones que necesita para su organización:

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)
- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](share-limit-accidental-exposure.md)
- [Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

Si tiene un proyecto importante con una organización asociada, puede usar Azure Entitlement Management para administrar los invitados de esa organización en un equipo que haya configurado para el proyecto. Consulte [Crear una extranet B2B con invitados administrados para](b2b-extranet.md) obtener más información.

## <a name="deploy-the-secure-collaboration-solution"></a>Implementar la solución de colaboración segura

Cuando esté listo para implementar esta solución, siga estos pasos:
1. Configure los [tres niveles diferentes de protección para Teams.](configure-teams-three-tiers-protection.md)
2. Configure las opciones para [compartir información de cualquier confidencialidad con personas ajenas a su organización.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Vea también

[Documentación de Seguridad de Microsoft 365](https://docs.microsoft.com/microsoft-365/security)

[Documentación de cumplimiento de Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance)

[Le damos la bienvenida a Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
