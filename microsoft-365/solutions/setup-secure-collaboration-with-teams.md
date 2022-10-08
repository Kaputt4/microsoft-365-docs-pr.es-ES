---
title: Configuración del uso compartido seguro de archivos y documentos y la colaboración con Teams en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
recommendations: false
description: Obtenga información sobre los procedimientos recomendados para configurar la colaboración y el uso compartido de archivos seguros en Teams para proteger los datos en función de su confidencialidad.
ms.openlocfilehash: ab3d57f45aed00ab2b9500a7cdb80b3adda76483
ms.sourcegitcommit: fce27da5140691b013a6f7c0ea9c88b4ea4b7c10
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2022
ms.locfileid: "67985990"
---
# <a name="set-up-secure-file-sharing-and-collaboration-with-microsoft-teams"></a>Configuración del uso compartido de archivos seguro y la colaboración con Microsoft Teams

Poder compartir fácilmente archivos y documentos con las personas adecuadas a la vez que se evita el uso compartido excesivo es clave para el éxito de una organización. Esto incluye poder compartir datos confidenciales u otros datos confidenciales de forma segura solo con aquellos que deben tener acceso a ella. En función del proyecto, esto podría incluir el uso compartido de datos confidenciales con personas ajenas a la organización.

Esta guía de solución de colaboración incluye dos componentes que le ayudarán a:

- Implementación de Teams con el nivel de protección adecuado para cada proyecto
- Configuración del uso compartido externo con la configuración de seguridad adecuada para cada proyecto

![Implemente Teams con la protección adecuada y configure el uso compartido externo con la configuración de seguridad adecuada.](..\media\solutions-architecture-center\secure-collaboration-overview.png)

Si las herramientas de colaboración de archivos versátiles y fáciles de usar no están disponibles, los usuarios suelen colaborar mediante el envío de documentos por correo electrónico. Se trata de un método de colaboración tedioso y propenso a errores, y puede aumentar el riesgo de compartir información de forma inapropiada. Si a las personas les resulta demasiado difícil compartir archivos, podrían volver a usar productos de consumidor que no se rigen por TI. Esto puede suponer un riesgo aún mayor.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

Con Microsoft 365, puede implementar Teams con una variedad de configuraciones que ayudan a:

- Protección de su propiedad intelectual
- Habilitación de una colaboración sencilla con documentos y otros archivos
- Crear un equilibrio entre seguridad y facilidad de uso que aumente la satisfacción del usuario y reduzca el riesgo de shadow IT

La mayoría de las organizaciones tienen una variedad de información, con distintos grados de sensibilidad y distintos grados de impacto empresarial si la información se comparte inapropiadamente. En función de la confidencialidad de una parte determinada de la información, es posible que desee permitir el uso compartido con:

- Cualquier persona (sin autenticar)
- Personas dentro de la organización
- Personas específicas dentro de la organización
- Personas específicas dentro y fuera de la organización

La información, como los folletos de marketing, está pensada para compartirse ampliamente fuera de la organización. La información como los menús de cafetería no está pensada para el uso compartido externo, pero no tendría ningún impacto empresarial si se compartiesen externamente. Estos tipos de información necesitan poca o ninguna protección.

Esos mismos folletos de marketing, mientras están en desarrollo, solo se pueden compartir dentro de la organización. En este caso, la configuración de uso compartido predeterminada en Teams puede ser suficiente.

La información sobre un nuevo producto que se está desarrollando podría considerarse confidencial, incluso dentro de la organización. Un mayor grado de protección podría ser adecuado en este caso. Por ejemplo, podría restringir el acceso a esta información a los miembros de un equipo específico. En función del proyecto, es posible que tenga que colaborar con personas ajenas a su organización, como un proveedor o una organización asociada.

La información que es fundamental para el éxito de su organización o que tiene requisitos estrictos de seguridad o cumplimiento puede requerir incluso mayores niveles de protección.

![Escala de riesgo de baja (folleto publicado) a alta (datos empresariales confidenciales).](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

Para todos los escenarios indicados anteriormente, puede usar los equipos de Microsoft Teams para almacenar, compartir y colaborar en la información.

Para configurar la colaboración segura, use estas funcionalidades y características de Microsoft 365.

|Producto o componente|Funcionalidad o característica|Licencias|
|---|---|---|
|Microsoft Defender para Office 365|Datos adjuntos seguros para SPO, OneDrive y Teams; Documentos seguros; Vínculos seguros para Teams|Microsoft 365 E1, E3 y E5|
|SharePoint|Directivas de uso compartido de sitios y archivos, permisos de uso compartido de sitios, vínculos de uso compartido, solicitudes de acceso, configuración de uso compartido de invitados del sitio|Microsoft 365 E1, E3 y E5|
|Microsoft Teams|Acceso de invitado, equipos privados, canales privados, canales compartidos|Microsoft 365 E1, E3 y E5|
|Microsoft Purview|Etiquetas de confidencialidad|Microsoft 365 E3 y E5|

## <a name="collaboration-governance-framework-for-teams-and-microsoft-365"></a>Marco de gobernanza de colaboración para Teams y Microsoft 365

Microsoft 365 proporciona muchas opciones para gobernar la solución de colaboración. Se recomienda usar este contenido de implementación junto con el [contenido de gobernanza de colaboración](collaboration-governance-overview.md) para crear la mejor solución de colaboración para su organización.

### <a name="securing-teams-for-sensitive-and-highly-sensitive-data"></a>Protección de Teams para datos confidenciales y altamente confidenciales

Para administrar el acceso a la información con diferentes confidencialidades, hemos desarrollado [tres niveles diferentes de protección para Teams](configure-teams-three-tiers-protection.md). Puede personalizar cualquiera de estos niveles para satisfacer mejor las necesidades o su negocio.

![Gráfico de tres niveles de protección para Teams.](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)

Estos niveles ( *línea base*, *confidencial* y *altamente confidencial* ) aumentan gradualmente las protecciones que ayudan a evitar el uso compartido excesivo y posibles pérdidas de información, como se muestra en la tabla siguiente.

|-|Nivel de línea base|Nivel confidencial|Nivel altamente confidencial|
|---|---|---|---|
|Equipo público o privado|Ambos|Private|Private|
|Uso compartido no autenticado|Blocked|Blocked|Blocked|
|Uso compartido de archivos|Permitido|Permitido|Solo los propietarios del equipo pueden compartir.|
|Membresía de equipo|Cualquier persona puede unirse a equipos públicos.<br>Se requiere la aprobación del propietario del equipo para unirse a equipos privados.|Se requiere la aprobación del propietario del equipo para unirse.|Se requiere la aprobación del propietario del equipo para unirse.|
|Cifrado de documentos|||Disponible con etiqueta de confidencialidad|
|Uso compartido de invitados|Permitido|Se puede permitir o bloquear|Se puede permitir o bloquear|
|Dispositivos no administrados|Sin restricción|Acceso solo web|Blocked|

La configuración de estos niveles implica:

- Configuración de opciones en Teams para el acceso de invitado y los canales privados
- Configuración de opciones en el sitio de SharePoint asociado de un equipo para el uso compartido interno e invitado, solicitudes de acceso y vínculos de uso compartido
- Para los niveles *confidenciales* y *altamente confidenciales* , configurar etiquetas de confidencialidad para clasificar los equipos y controlar el uso compartido de invitados y el acceso desde dispositivos no administrados
- Para el nivel *altamente confidencial* , configurar una etiqueta de confidencialidad para cifrar los documentos a los que se aplica

Comience con el nivel de línea base y, a continuación, agregue equipos que usen los niveles *confidenciales* y *altamente confidenciales* según sea necesario para ayudar a proteger la información de su organización. Consulte estos recursos para empezar:

- [Configure equipos con la protección de base de referencia](configure-teams-baseline-protection.md)
- [Configure equipos con protección de datos confidenciales](configure-teams-sensitive-protection.md)
- [Configuración de equipos con protección de datos con un nivel de confidencialidad alto](configure-teams-highly-sensitive-protection.md)

Si tiene un proyecto altamente confidencial que requiere protección adicional contra el uso compartido incluso dentro de su organización, puede configurar un equipo que use su propia etiqueta de confidencialidad para cifrar los archivos de modo que solo los miembros del equipo puedan leerlos. Consulte [Configuración de un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para obtener más información.

### <a name="sharing-with-people-outside-your-organization"></a>Compartir con usuarios ajenos a la organización

Es posible que tenga que [compartir información de cualquier confidencialidad con personas ajenas a su organización](collaborate-with-people-outside-your-organization.md). Esto puede ir desde compartir un solo documento con una sola persona hasta colaborar en un proyecto importante con una organización asociada grande o con trabajadores independientes de todo el mundo. En Microsoft 365, esta gama de uso compartido externo se puede realizar fácilmente y con las medidas de seguridad adecuadas para ayudar a proteger su información confidencial.

Estos recursos le ayudarán a empezar a configurar su entorno para colaborar con personas ajenas a su organización:

- [Colabore en documentos](collaborate-on-documents.md) para compartir archivos individuales de carpetas.
- [Colabore en un sitio](collaborate-in-site.md) para colaborar con invitados en un sitio de SharePoint.
- [Colabore como equipo](collaborate-as-team.md) para colaborar con los invitados de un equipo.
- [Colabore con participantes externos en un canal](/microsoft-365/solutions/collaborate-teams-direct-connect) para colaborar con personas ajenas a la organización en un canal compartido.

En función de la confidencialidad de la información que se comparta, puede agregar medidas de seguridad para ayudar a evitar el uso compartido excesivo. Estos recursos le ayudarán a configurar las protecciones que necesita para su organización:

- [Prácticas recomendadas para compartir archivos y carpetas con usuarios no autenticados](best-practices-anonymous-sharing.md)
- [Limitar la exposición accidental de archivos al compartirlos con usuarios externos a la organización](share-limit-accidental-exposure.md)
- [Crear un entorno seguro de uso compartido para invitados](create-secure-guest-sharing-environment.md)

Si tiene un proyecto importante con una organización asociada, puede usar [canales compartidos](/microsoft-365/solutions/collaborate-teams-direct-connect) o [Azure Entitlement Management](b2b-extranet.md) para administrar a las personas ajenas a la organización con las que necesita colaborar.

## <a name="training-for-administrators"></a>Entrenamiento para administradores

Estos módulos de entrenamiento de Microsoft Learn pueden ayudarle a aprender las características de colaboración, gobernanza e identidad en Teams y SharePoint.

### <a name="teams"></a>Teams

|Aprendizaje:|Administración de la colaboración en grupo con Microsoft Teams|
|---|---|
|![Icono de entrenamiento de colaboración de Teams.](../media/manage-team-collaboration-with-microsoft-teams.svg)|Administración de la colaboración en grupo con Microsoft Teams le presenta las características y funciones de Microsoft Teams, el núcleo central para la colaboración en grupo de Microsoft 365. Aprenderá cómo puede usar Teams para facilitar el trabajo en equipo y la comunicación dentro de la organización, tanto en un entorno local como externo, en dispositivos muy diversos, desde equipos de escritorio a tabletas y teléfonos, a la vez que aprovecha toda la funcionalidad enriquecida de las aplicaciones de Office 365. Comprenderá cómo Teams ofrece un entorno completo y flexible para la colaboración en aplicaciones y dispositivos. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teams Administrator Associate.<p>2 h 17 minutos - Ruta de aprendizaje - 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/training/modules/m365-teams-collab-prepare-deployment/introduction/)

### <a name="sharepoint"></a>SharePoint

|Aprendizaje:|Colaborar con SharePoint en Microsoft 365|
|---|---|
|![Icono de entrenamiento de SharePoint.](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Administrar el contenido compartido con Microsoft SharePoint le ofrece una introducción a las características y funciones de SharePoint y cómo funciona con Microsoft 365. Obtendrá información sobre los distintos tipos de sitios de SharePoint, incluidos los sitios concentradores, así como la protección de la información, la creación de informes y la supervisión. También obtendrá información sobre cómo emplear el uso compartido de archivos y carpetas de SharePoint para optimizar la colaboración, cómo compartir archivos externamente y cómo administrar sitios de SharePoint en el centro de administración de SharePoint. Esta ruta de aprendizaje puede ayudarle a preparar el certificado Microsoft 365 Certified: Teamwork Administrator Associate.<p>1 h 14 min - Ruta de aprendizaje - 4 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/training/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

### <a name="information-protection"></a>Protección de la información

|Aprendizaje:|Proteger la información de la empresa con Microsoft 365|
|---|---|
|![Icono de entrenamiento de protección de información de Teams.](../media/protect-enterprise-information-microsoft-365.svg)|Protecting and securing your organization's information is more challenging than ever. The Protect enterprise information with Microsoft 365 learning path discusses how to protect your sensitive information from accidental oversharing or misuse, how to discover and classify data, how to protect it with sensitivity labels, and how to both monitor and analyze your sensitive information to protect against its loss. This learning path can help you prepare for the Microsoft 365 Certified: Security Administrator Associate and Microsoft 365 Certified: Enterprise Administration Expert certifications.<p>1 h - Ruta de aprendizaje: 5 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/training/modules/m365-security-info-overview/introduction/)

### <a name="identity-and-access"></a>Identidad y acceso

|Aprendizaje:|Proteger la identidad y el acceso con Azure Active Directory|
|---|---|
|![Icono de entrenamiento de identidad y acceso.](../media/protect-identity-and-access-with-microsoft-365.svg)|La Ruta de aprendizaje de identidad y acceso cubre las últimas tecnologías de identidad y acceso, herramientas para reforzar la autenticación y orientación sobre la protección de la identidad dentro de su organización. Las tecnologías de acceso e identidad de Microsoft le permiten asegurar la identidad de su organización, ya sea en sus instalaciones o en la nube, y permiten a sus usuarios trabajar de forma segura desde cualquier lugar. Esta ruta de aprendizaje puede ayudarle a preparar los certificados Microsoft 365 Certified: Security Administrator Associate y Microsoft 365 Certified: Enterprise Administration Expert.<p>2 h 52 min - Ruta de aprendizaje - 6 módulos|

> [!div class="nextstepaction"]
> [Iniciar >](/training/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>Entrenamiento para usuarios finales

Estos módulos de entrenamiento pueden ayudar a los usuarios a usar Teams, grupos y SharePoint para la colaboración en Microsoft 365.

|Teams|SharePoint|
|---|---|
|![Configure y personalice el icono de entrenamiento del equipo.](../media/set-up-customize-team-training.png)<br>**[Configuración y personalización del equipo](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![Icono de aprendizaje de share and sync de SharePoint](../media/sharepoint-share-sync-training.png)<br>**[Compartir y sincronizar](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Icono de entrenamiento cargar y buscar archivos de Teams.](../media/smc-teams-upload-find-files-training.png)<br>**[Carga y búsqueda de archivos](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![Icono colaborar en equipos y canales.](../media/teams-collaborate-channels-training.png)<br>**[Colaborar en equipos y canales](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>Ilustraciones

Estas ilustraciones le ayudarán a comprender cómo los grupos y equipos interactúan con otros servicios de Microsoft 365 y qué características de gobernanza y cumplimiento están disponibles para ayudarle a administrar estos servicios en su organización.

### <a name="groups-in-microsoft-365-for-it-architects"></a>Grupos en Microsoft 365 para arquitectos de TI

Lo que necesitan saber los arquitectos de TI sobre los grupos en Microsoft 365

|**Item**|**Descripción**|
|---|---|
|[![Imagen del pulgar para la infografía de grupos.](../downloads/msft-m365-groups-architecture-thumb.png)](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) <br/> [PDF](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.pdf) \| [Visio](https://download.microsoft.com/download/6/3/0/6309218f-a169-4f2d-af4c-2fe49e30ba17/msft-m365-groups.vsdx) <br> Actualizado en mayo de 2022|Estas ilustraciones detallan los diferentes tipos de grupos, cómo se crean y administran, y algunas recomendaciones para el gobierno de estos.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>Microsoft Teams y servicios de productividad relacionados de Microsoft 365 para arquitectos de TI

La arquitectura lógica de los servicios de productividad en Microsoft 365, una de las más destacadas gracias a Microsoft Teams.

|**Item**|**Descripción**|
|---|---|
|[![Imagen digital del póster de la arquitectura lógica de Teams.](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>Actualizado en abril de 2019|Microsoft proporciona un conjunto de servicios de productividad que funcionan en conjunto para proporcionar experiencias de colaboración con funcionalidades de gobierno, seguridad y cumplimiento. <p>Esta serie de ilustraciones proporciona una vista de la arquitectura lógica de los servicios de productividad para arquitectos empresariales, que es una de las más destacadas gracias a Microsoft Teams.|

## <a name="deploy-the-secure-collaboration-solution"></a>Implementación de la solución de colaboración segura

Cuando esté listo para implementar esta solución, continúe con estos pasos:

1. Configure los [tres niveles diferentes de protección para Teams](configure-teams-three-tiers-protection.md).
2. Configure las opciones para [compartir información de cualquier confidencialidad con personas ajenas a su organización](collaborate-with-people-outside-your-organization.md).

## <a name="see-also"></a>Vea también

[Documentación de Seguridad de Microsoft 365](../security/index.yml)

[Documentación de Microsoft Purview](../compliance/index.yml)

[Le damos la bienvenida a Microsoft Teams](/MicrosoftTeams/Teams-overview)
