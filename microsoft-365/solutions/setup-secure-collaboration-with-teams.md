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
recommendations: false
description: Obtenga información sobre cómo configurar la colaboración de contenido seguro en Teams para proteger los datos en función de su confidencialidad.
ms.openlocfilehash: 7a5b8f58cc5e4a23d2d143419f99ecdd87b949c1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924364"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>Configurar la colaboración segura con Microsoft 365 y Microsoft Teams

Poder compartir fácilmente información con las personas correctas a la vez que se evita el exceso de compartición es clave para el éxito de una organización. Esto incluye poder compartir datos confidenciales de forma segura solo con aquellos que deberían tener acceso a ellos. Según el proyecto, esto puede incluir el uso compartido de datos confidenciales con personas ajenas a la organización.

Esta guía de solución de colaboración incluye dos componentes que le ayudarán:
- Implementar Microsoft Teams con el nivel adecuado de protección para cada proyecto
- Configurar el uso compartido externo con las opciones de seguridad adecuadas para cada proyecto

![Implementar Teams con la protección adecuada y configurar el uso compartido externo con la configuración de seguridad adecuada](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Si las herramientas de colaboración de contenido versátiles y fáciles de usar no están disponibles, los usuarios a menudo colaborarán mediante el envío de documentos por correo electrónico. Se trata de un método de colaboración tedioso y propenso a errores y puede aumentar el riesgo de compartir información de forma inadecuada. Si a las personas les resulta demasiado difícil compartir información, podrían volver a usar productos de consumo que no están regido por TI. Esto puede suponer un riesgo aún mayor.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Con Microsoft 365, puede implementar Teams con una variedad de configuraciones que ayudan a:

- Proteger la propiedad intelectual
- Habilitar la colaboración fácil
- Crear un equilibrio entre la seguridad y la facilidad de uso que aumente la satisfacción del usuario y reduzca el riesgo de que se cree UNA SOMBRA

La mayoría de las organizaciones tienen una variedad de información, con distintos grados de confidencialidad y distintos grados de impacto empresarial si la información se comparte de forma inadecuada. Dependiendo de la confidencialidad de una determinada información, es posible que desee permitir el uso compartido con:

- Cualquiera (sin autenticar)
- Personas dentro de la organización
- Personas específicas dentro de la organización
- Personas específicas dentro y fuera de la organización

La información, como los folletos de marketing, están pensadas para compartirse ampliamente fuera de la organización. La información, como los menús de cafetería, no está pensada para el uso compartido externo, pero no tendría ningún impacto empresarial si se compartiese externamente. Estos tipos de información necesitan poca o ninguna protección.

Esos mismos folletos de marketing, mientras están en desarrollo, solo se pueden compartir dentro de la organización. En este caso, la configuración de uso compartido predeterminada Teams puede ser suficiente.

La información sobre un nuevo producto que está en desarrollo puede considerarse confidencial, incluso dentro de la organización. Un mayor grado de protección podría ser apropiado en este caso. Puede restringir el acceso a esta información a los miembros de un equipo específico, por ejemplo. Según el proyecto, es posible que deba colaborar con personas ajenas a la organización, como un proveedor o una organización asociada.

La información que es fundamental para el éxito de su organización o que tiene requisitos de seguridad o cumplimiento estrictos puede requerir niveles de protección aún mayores.

![Escala de riesgos de bajo (folleto publicado) a alto (datos empresariales confidenciales)](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Para todos los escenarios mencionados anteriormente, puede usar teams en Microsoft Teams almacenar, compartir y colaborar en la información. 

Para configurar la colaboración segura, use estas Microsoft 365 y características.

| Producto o componente | Funcionalidad o característica | Licencias |
|:-------|:-----|:-------|
| Microsoft Defender para Office 365 | Caja fuerte Datos adjuntos para SPO, OneDrive y Teams; Caja fuerte Documentos; Caja fuerte Vínculos para Teams    | Microsoft 365 E1, E3 y E5 |
| SharePoint    | Directivas de uso compartido de sitios y archivos, permisos de uso compartido de sitios, vínculos de uso compartido, solicitudes de Access, configuración de uso compartido de invitados del sitio | Microsoft 365 E1, E3 y E5 |
| Microsoft Teams   | Acceso de invitado, equipos privados, canales privados | Microsoft 365 E1, E3 y E5 |
| Cumplimiento de Microsoft 365  | Etiquetas de confidencialidad    | Microsoft 365 E3 y E5 |

### <a name="collaboration-governance"></a>Gobierno de colaboración

Microsoft 365 ofrece muchas opciones para gobernar la solución de colaboración. Se recomienda usar este contenido de implementación junto con el contenido de gobierno de [colaboración](collaboration-governance-overview.md) para crear la mejor solución de colaboración para su organización.

### <a name="using-teams-for-all-kinds-of-data"></a>Uso Teams para todos los tipos de datos

Para administrar el acceso a la información con diferentes sensibilidades, hemos desarrollado tres niveles de protección diferentes para [Teams](configure-teams-three-tiers-protection.md). Puede personalizar cualquiera de estos niveles para satisfacer mejor las necesidades o su empresa. 

![Gráfico de tres niveles de protección para Teams](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)


Estos niveles *(línea* base, *confidencial* y altamente *confidencial)* aumentan gradualmente las protecciones que ayudan a evitar la sobresharing y la posible pérdida de información, como se muestra en la tabla siguiente.

|-|**Nivel de línea base**|**Nivel confidencial**|**Nivel altamente confidencial**|
|:--|:-----------|:------------|:-------------------|
|Equipo público o privado|Ambos|Private|Private|
|Uso compartido no autenticado|Blocked|Blocked|Blocked|
|Uso compartido de archivos|Permitido|Permitido|Solo los propietarios de equipos pueden compartir.|
|Pertenencia a un equipo|Cualquier persona puede unirse a equipos públicos.<br>La aprobación del propietario del equipo necesaria para unirse a equipos privados.|Se requiere la aprobación del propietario del equipo para unirse.|Se requiere la aprobación del propietario del equipo para unirse.|
|Cifrado de documentos|||Disponible con etiqueta de confidencialidad|
|Uso compartido de invitados|Permitido|Se puede permitir o bloquear|Se puede permitir o bloquear|
|Dispositivos no administrados|Sin restricción|Acceso solo web|Blocked|

La configuración de estos niveles implica:

- Configuración de opciones en Teams acceso de invitado y canales privados
- Configuración de la configuración en el sitio de SharePoint asociado de un equipo para el uso compartido interno y de invitado, las solicitudes de acceso y los vínculos de uso compartido
- Para los  *niveles confidenciales* y altamente confidenciales, configurar etiquetas de confidencialidad para clasificar los equipos y controlar el uso compartido de invitados y el acceso desde dispositivos no administrados
- Para el *nivel altamente* confidencial, configurar una etiqueta de confidencialidad para cifrar los documentos a los que se aplica

Comience con el nivel de línea base  y, a continuación, agregue equipos que usen los niveles confidenciales y altamente *confidenciales* según sea necesario para ayudar a proteger la información de su organización. Vea estos recursos para empezar:

- [Configure equipos con la protección de base de referencia](configure-teams-baseline-protection.md)
- [Configure equipos con protección de datos confidenciales](configure-teams-sensitive-protection.md)
- [Configuración de equipos con protección de datos con un nivel de confidencialidad alto](configure-teams-highly-sensitive-protection.md)

Si tiene un proyecto altamente confidencial que requiere protección adicional para compartir incluso dentro de su organización, puede configurar un equipo que use su propia etiqueta de confidencialidad para cifrar archivos de modo que solo los miembros del equipo puedan leerlos. Consulte [Configurar un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para obtener más información.

### <a name="sharing-with-people-outside-your-organization"></a>Compartir con personas de fuera de la organización

Es posible que deba [compartir información de cualquier confidencialidad con personas ajenas a su organización.](collaborate-with-people-outside-your-organization.md) Esto puede variar desde compartir un solo documento con una sola persona hasta colaborar en un proyecto importante con una organización de partners grande o independientes de todo el mundo. En Microsoft 365, esta gama de uso compartido externo se puede realizar fácilmente y con las medidas de seguridad adecuadas para ayudar a proteger su información confidencial.

Estos recursos le ayudarán a empezar a configurar el entorno para colaborar con personas ajenas a su organización:

- [Colaborar en documentos para](collaborate-on-documents.md) compartir archivos individuales de carpetas.
- [Colabore en un sitio](collaborate-in-site.md) para colaborar con invitados en un SharePoint web.
- [Colaborar como equipo para](collaborate-as-team.md) colaborar con invitados en un equipo.

Dependiendo de la confidencialidad de la información que se comparta, puede agregar medidas de seguridad para ayudar a evitar el exceso de compartición. Estos recursos le ayudarán a configurar las protecciones que necesita para su organización:

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)
- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](share-limit-accidental-exposure.md)
- [Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

Si tiene un proyecto principal con una organización asociada, puede usar Azure Entitlement Management para administrar los invitados de esa organización en un equipo que haya configurado para el proyecto. Consulte [Crear una extranet B2B con invitados administrados para](b2b-extranet.md) obtener más información.



## <a name="training-for-administrators"></a>Formación para administradores

Estos módulos de aprendizaje de Microsoft Learn pueden ayudarle a aprender las características de colaboración, gobierno e identidad en Teams y SharePoint.

#### <a name="teams"></a>Teams

|Aprendizaje:|Administración de la colaboración en grupo con Microsoft Teams|
|:---|:---|
|![Teams de aprendizaje de colaboración](../media/manage-team-collaboration-with-microsoft-teams.svg)|Administración de la colaboración en grupo con Microsoft Teams le presenta las características y funciones de Microsoft Teams, el núcleo central para la colaboración en grupo de Microsoft 365. Aprenderá cómo puede usar Teams para facilitar el trabajo en equipo y la comunicación dentro de la organización, tanto en un entorno local como externo, en dispositivos muy diversos, desde equipos de escritorio a tabletas y teléfonos, a la vez que aprovecha toda la funcionalidad enriquecida de las aplicaciones de Office 365. Comprenderá cómo Teams ofrece un entorno completo y flexible para la colaboración en aplicaciones y dispositivos. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teams Administrator Associate.<br><br>2 h 17 min - Ruta de aprendizaje - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

#### <a name="sharepoint"></a>SharePoint

|Aprendizaje:|Colaborar con SharePoint en Microsoft 365|
|:---|:---|
|![SharePoint de aprendizaje](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Administrar el contenido compartido con Microsoft SharePoint le ofrece una introducción a las características y funciones de SharePoint y cómo funciona con Microsoft 365. Obtendrá información sobre los distintos tipos de sitios de SharePoint, incluidos los sitios concentradores, así como la protección de la información, la creación de informes y la supervisión. También obtendrá información sobre cómo emplear el uso compartido de archivos y carpetas de SharePoint para optimizar la colaboración, cómo compartir archivos externamente y cómo administrar sitios de SharePoint en el centro de administración de SharePoint. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teamwork Administrator Associate.<br><br>1 h 14 min - Ruta de aprendizaje - 4 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

#### <a name="information-protection"></a>Protección de la información

|Aprendizaje:|Proteger la información de la empresa con Microsoft 365|
|:---|:---|
|![Teams de aprendizaje de protección de información](../media/protect-enterprise-information-microsoft-365.svg)|Proteger y asegurar la información de su organización es más difícil que nunca. La ruta de aprendizaje Proteger la información de la empresa con Microsoft 365 analiza cómo proteger su información confidencial de un uso excesivo o indebido accidental, cómo descubrir y clasificar los datos, cómo protegerlos con etiquetas de sensibilidad y cómo supervisar y analizar su información confidencial para protegerla contra su pérdida. Esta ruta de aprendizaje puede ayudarle a prepararse para las certificaciones Microsoft 365 Certified: Security Administrator Associate and Microsoft 365 Certified: Enterprise Administration Expert.<br><br>1 hora - Ruta de aprendizaje: 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-security-info-overview/introduction/)

#### <a name="identity-and-access"></a>Identidad y acceso

|Aprendizaje:|Proteger la identidad y el acceso con Azure Active Directory|
|:---|:---|
|![Icono de aprendizaje de identidad y acceso](../media/protect-identity-and-access-with-microsoft-365.svg)|La Ruta de aprendizaje de identidad y acceso cubre las últimas tecnologías de identidad y acceso, herramientas para reforzar la autenticación y orientación sobre la protección de la identidad dentro de su organización. Las tecnologías de acceso e identidad de Microsoft le permiten asegurar la identidad de su organización, ya sea en sus instalaciones o en la nube, y permiten a sus usuarios trabajar de forma segura desde cualquier lugar. Esta ruta de aprendizaje puede ayudarle a preparar los certificados Microsoft 365 Certified: Security Administrator Associate y Microsoft 365 Certified: Enterprise Administration Expert.<br><br>2 h 52 min - Ruta de aprendizaje - 6 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Entrenamiento para usuarios finales

Estos módulos de aprendizaje pueden ayudar a los usuarios a usar Teams, grupos y SharePoint colaboración en Microsoft 365.

|Teams|SharePoint|
|:---|:---|
|![Configurar y personalizar el icono de aprendizaje de equipo](../media/set-up-customize-team-training.png)<br>**[Configurar y personalizar el equipo](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint compartir y sincronizar el icono de aprendizaje](../media/sharepoint-share-sync-training.png)<br>**[Compartir y sincronizar](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams cargar y encontrar el icono de aprendizaje de archivos](../media/smc-teams-upload-find-files-training.png)<br>**[Upload y buscar archivos](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Icono Colaborar en equipos y canales](../media/teams-collaborate-channels-training.png)<br>**[Colaborar en equipos y canales](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>Ilustraciones

Estas ilustraciones le ayudarán a comprender cómo interactúan grupos y equipos con otros servicios de Microsoft 365 y qué características de gobierno y cumplimiento están disponibles para ayudarle a administrar estos servicios en su organización.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupos en Microsoft 365 para arquitectos de TI
Lo que necesitan saber los arquitectos de TI sobre los grupos en Microsoft 365

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen en miniatura para la infografía de grupos](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> Actualizado en junio de 2019|Estas ilustraciones detallan los diferentes tipos de grupos, cómo se crean y administran, y algunas recomendaciones para el gobierno de estos.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams y servicios de productividad relacionados de Microsoft 365 para arquitectos de TI
La arquitectura lógica de los servicios de productividad en Microsoft 365, una de las más destacadas gracias a Microsoft Teams.

|**Item**|**Descripción**|
|:-----|:-----|
|[![Imagen en miniatura para el póster de la arquitectura lógica de Teams](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Actualizado en abril de 2019   |Microsoft proporciona un conjunto de servicios de productividad que funcionan en conjunto para proporcionar experiencias de colaboración con funcionalidades de gobierno, seguridad y cumplimiento. <br/> <br/>Esta serie de ilustraciones proporciona una vista de la arquitectura lógica de los servicios de productividad para arquitectos empresariales, que es una de las más destacadas gracias a Microsoft Teams.|

## <a name="deploy-the-secure-collaboration-solution"></a>Implementar la solución de colaboración segura

Cuando esté listo para implementar esta solución, siga estos pasos:
1. Configure los [tres niveles de protección diferentes para Teams](configure-teams-three-tiers-protection.md).
2. Configurar las opciones [para compartir información de cualquier confidencialidad con personas fuera de la organización.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>Ver también

[Documentación de Seguridad de Microsoft 365](../security/index.yml)

[Documentación de cumplimiento de Microsoft 365](../compliance/index.yml)

[Le damos la bienvenida a Microsoft Teams](/MicrosoftTeams/Teams-overview)
