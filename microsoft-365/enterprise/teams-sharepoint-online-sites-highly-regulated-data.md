---
title: Sitios de SharePoint para datos altamente regulados
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: Cree un sitio de grupo de SharePoint seguro para almacenar los archivos más importantes y confidenciales.
ms.openlocfilehash: 97a01275d1d45cb02e66e88f82c95311bcb6fe70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636716"
---
# <a name="sharepoint-sites-for-highly-regulated-data"></a>Sitios de SharePoint para datos altamente regulados

*Este escenario se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

Microsoft 365 Enterprise incluye una serie completa de servicios basados en la nube para que pueda crear, almacenar, proteger y administrar los datos altamente regulados almacenados en archivos de. Se incluyen datos que:

- Datos sujetos a regulaciones regionales.
- Los datos más importantes para su organización, como pueden ser secretos comerciales, información de recursos humanos o financiera y estrategias de la organización.

>[!Note]
> Un escenario similar usando equipos de Microsoft Teams está [aqui](secure-teams-highly-regulated-data-scenario.md).
>

Un escenario basado en la nube de Microsoft 365 Enterprise que cumpla estas necesidades de negocio requiere que usted:

- Almacenar archivos de (documentos, presentaciones de diapositivas, hojas de cálculo, etc.) en un sitio de grupo de SharePoint.
- Bloquee el sitio para evitar:
  - Acceso a los usuarios que no sean miembros del grupo de Microsoft 365 para el sitio.
  - Que miembros del sitio concedan acceso a terceros.
  - Que aquellos que no sean miembros del sitio soliciten acceso.
- Configure una etiqueta de retención para los sitios de SharePoint de forma predeterminada para impedir que los usuarios envíen archivos fuera de la organización.
- Cifre la mayoría de los archivos confidenciales del sitio con un método de cifrado que se desplaza con el archivo.
- Agregue permisos a los archivos más confidenciales de modo que, incluso si se comparten fuera del sitio, aún se requieran las credenciales válidas de una cuenta de usuario para abrir el archivo.

En la tabla siguiente se asignan los requisitos de este escenario a una característica de Microsoft 365 Enterprise.

|||
|:-------|:-----|
| **Requisito** | **Característica de Microsoft 365 Enterprise** |
| Almacenar archivos | Sitios de grupo de SharePoint |
| Bloquear el sitio | Permisos para grupos de Microsoft 365 y para el sitio de grupo de SharePoint |
| Etiquetar los archivos del sitio | Etiquetas de retención de Microsoft 365 |
| Bloquear a los usuarios cuando envían archivos fuera de la organización | Directivas para la prevención de pérdida de datos (DLP) |
| Cifrar todos los archivos del sitio | Etiquetas o subetiquetas de confidencialidad de Microsoft 365 |
| Añadir permisos a los archivos del sitio | Etiquetas o subetiquetas de confidencialidad de Microsoft 365 |
|||

Aquí tiene un ejemplo de configuración para un sitio de SharePoint seguro.

![Sitios de SharePoint para un escenario de datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Este escenario requiere que ya haya implementado:

- La fase de [identidad](identity-infrastructure.md) y los pasos 1 y 2 de la fase de [protección de la información](infoprotect-infrastructure.md) de la infraestructura de base. 
- [SharePoint](sharepoint-online-onedrive-workload.md).

Las siguientes fases le guiarán a través del diseño, la configuración y el impulso de la adopción de los sitios altamente regulados de SharePoint.

<a name="poster"></a> Para obtener un resumen de una página de este escenario, vea el [póster Sitios de SharePoint para datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf).

[![Póster Sitios de SharePoint para datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/sharepoint-sites-highly-regulated-data-poster.png)](../media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf)

También puede descargar este póster en formato [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePointSitesHighlyRegulatedData.pdf) o [PowerPoint](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/teams-sharepoint-online-sites-highly-regulated-data/SharePoint-Sites-Highly-Regulated-Data.pptx) e imprimirlo en tamaño carta, legal o tabloide (11 x 17).


## <a name="identity-and-device-access-prerequisites"></a>Requisitos previos de acceso a dispositivos e identidades

Para proteger el acceso a los sitios de SharePoint, asegúrese de que configuró las [directivas de acceso a dispositivos e identidades](identity-access-policies.md) y las [directivas de acceso recomendadas de SharePoint](sharepoint-file-access-policies.md).

## <a name="phase-1-design"></a>Fase 1: Diseño

Para crear un sitio de SharePoint para datos altamente regulados, en primer lugar debe identificar su propósito. Por ejemplo, el departamento de investigación y desarrollo de una compañía de fabricación necesita un sitio de SharePoint para almacenar las especificaciones de diseño actuales para los productos existentes y un lugar para colaborar en nuevos productos. Solo podrán acceder al sitio los miembros del Departamento de Investigación y Desarrollo y los ejecutivos seleccionados.

Ese propósito impulsará la determinación de los elementos de configuración esenciales, como:

- La etiqueta de retención para asignar a la parte de Documentos del sitio y las directivas DLP para la etiqueta
- La configuración de una subetiqueta de confidencialidad que los usuarios aplican a los archivos altamente confidenciales almacenados en el sitio

Una vez determinados, use estos ajustes para configurar el sitio en la fase 2. 

### <a name="step-1-microsoft-365-retention-labels-and-dlp-policies"></a>Paso 1 Etiquetas de retención y directivas DLP de Microsoft 365

Cuando se aplican a la parte de Documentos de un sitio de grupo de SharePoint, las etiquetas de retención proporcionan un método predeterminado de clasificación para todos los archivos almacenados en el sitio.
 
En los sitios de SharePoint para datos altamente regulados, debe determinar qué etiqueta de retención usará.

Para conocer las consideraciones de diseño de las etiquetas, consulte [Etiquetas y clasificación de Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels).

Use directivas DLP para proteger la información confidencial y evitar su divulgación accidental o intencionada. Para obtener más información, consulte esta [introducción](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies).

En los sitios de SharePoint, debe configurar una directiva DLP para la etiqueta de retención asignada al sitio para bloquear a los usuarios cuando intenten compartir archivos con usuarios externos. 

### <a name="step-2-your-microsoft-365-sensitivity-sublabel"></a>Paso 2: Su subetiqueta de confidencialidad de Microsoft 365

Para proporcionar cifrado y un conjunto de permisos a los archivos más confidenciales, los usuarios deben aplicar una etiqueta o subetiqueta de confidencialidad. Crear una sub-etiqueta bajo una etiqueta existente. 

Use una etiqueta de confidencialidad cuando necesite, un número reducido de etiquetas tanto para los equipos de uso global como para los individuales privados. Utilice una subetiqueta de confidencialidad cuando tenga un gran número de etiquetas o cuando desee organizar las etiquetas para sitios seguros bajo su etiqueta altamente regulada. 

La configuración de la etiqueta o subetiqueta aplicada se desplaza con el archivo. Incluso si se filtra fuera del sitio, solo las cuentas de usuario autenticadas que tengan permisos podrán abrir el archivo.

### <a name="design-results"></a>Resultados de diseño

Ha decidido lo siguiente:

- La etiqueta de retención adecuada y la directiva DLP que tiene asociada
- La configuración de la subetiqueta de confidencialidad que incluye el cifrado y los permisos

## <a name="phase-2-configure"></a>Fase 2: Configurar

En esta fase, debe tomar la configuración determinada en la Fase 1 e implementarla para crear un sitio de SharePoint para datos altamente regulados.

### <a name="step-1-create-a-private-sharepoint-team-site-with-owners-and-members-of-the-corresponding-microsoft-365-group"></a>Paso 1: Crear un sitio de grupo de SharePoint privado con propietarios y miembros del grupo de Microsoft 365 correspondiente

Siga [estas instrucciones]( https://support.office.com/article/create-a-site-in-sharepoint-online-4d1e11bf-8ddc-499d-b889-2b48d10b1ce8) para crear un sitio de grupo de SharePoint privado.

### <a name="step-2-configure-additional-permissions-settings-for-the-sharepoint-team-site"></a>Paso 2: Configurar ajustes de permisos adicionales para el sitio de grupo de SharePoint

Desde el sitio de SharePoint, configure estos ajustes de permisos.

1. En la barra de herramientas, haga clic en el icono de configuración y, luego, en **Permisos del sitio**.
2. En el panel **Permisos del sitio**, en **Configuración de uso compartido**, haga clic en **Cambiar configuración de uso compartido**.
3. En **Permisos de uso compartido**, seleccione **Solo los propietarios del sitio pueden compartir archivos, carpetas y el sitio**.
4. Desactive **Permitir solicitudes de acceso** y, después, haga clic en **Guardar**.

Con estas ajustes de configuración, se deshabilita la posibilidad de que los miembros del grupo de sitio compartan el sitio con otros miembros o que los usuarios que no son miembros soliciten el acceso al sitio.

### <a name="step-3-configure-the-site-for-a-retention-label"></a>Paso 3: Configurar el sitio para una etiqueta de retención

Siga las instrucciones de [Proteger archivos de SharePoint con DLP y etiquetas](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp) para:

1. Crear y publicar una etiqueta de retención para datos altamente regulados (si es necesario).
2. Configurar el sitio para la etiqueta de retención que creó en el paso 1.
3. Crear una directiva DLP para datos altamente regulados que usen la etiqueta de retención creada en el paso 2 y bloquee el envío de archivos fuera de la organización por parte de los usuarios.

#### <a name="step-4-create-a-sensitivity-sublabel-for-the-site"></a>Paso 4: Crear una subetiqueta de confidencialidad para el sitio

A diferencia de una etiqueta de confidencialidad para datos altamente regulados que cualquier persona puede aplicar a cualquier archivo, un sitio seguro necesita su propia sub-etiqueta para que los archivos con la sub-etiqueta asignada:

- Se cifren y el cifrado se desplace con el archivo.
- Contengan permisos personalizados para que solo los miembros del grupo de sitio puedan abrirlo.

Para lograr este nivel de seguridad adicional para los archivos almacenados en el sitio, debe configurar una nueva etiqueta de confidencialidad o una subetiqueta de la etiqueta general para archivos altamente regulados. Solo los miembros del grupo del sitio la verán en la lista de sub-etiquetas para la etiqueta altamente regulada.

Siga las instrucciones de [aquí](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) para configurar una etiqueta o sub-etiqueta de la etiqueta que está usando para archivos altamente regulados con los siguientes ajustes:

- El nombre de la etiqueta o sub-etiqueta contiene el nombre del sitio para facilitar la asociación al asignar la etiqueta o subetiqueta a un archivo.
- El cifrado está habilitado.
- El grupo del sitio tiene permisos de Coautor.

### <a name="configuration-results"></a>Resultados de la configuración

Ha configurado lo siguiente:

- Configuraciones de permisos más restrictivas en el sitio de SharePoint
- Una etiqueta de retención asignada a la parte de Documentos del sitio de SharePoint
- Una directiva DLP para la etiqueta de retención
- Una etiqueta o subetiqueta de confidencialidad que los usuarios pueden aplicar a los archivos más confidenciales almacenados en el sitio, el cual cifra el archivo y solo permite el acceso de coautoría a los miembros del grupo de sitio del equipo 

Aquí está la configuración resultante que utiliza una sub-etiqueta de la etiqueta altamente regulada.

![Los sitios de SharePoint para un escenario de datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration.png)

Este es un ejemplo de un usuario que ha aplicado la sub-etiqueta a un archivo almacenado en el sitio.

![Sitios de SharePoint para un escenario de datos altamente regulados](../media/teams-sharepoint-online-sites-highly-regulated-data/end-to-end-configuration-example-file.png)


## <a name="phase-3-drive-user-adoption"></a>Fase 3: Adopción por parte de los usuarios

Un sitio de SharePoint para datos altamente regulados solo puede proteger los datos si se usan de forma consistente para almacenar y acceder a archivos confidenciales. Esta es la fase más difícil, ya que depende de que los usuarios cambien sus hábitos y preferencias. 

Por ejemplo, los empleados acostumbrados a guardar archivos confidenciales en unidades USB o en soluciones de almacenamiento personal basadas en la nube, ahora tendrán que almacenarlos de forma exclusiva en el sitio de SharePoint para datos altamente regulados.

### <a name="step-1-train-your-users"></a>Paso 1: formar a los usuarios

Tras completar su configuración, tome un conjunto de usuarios que sean miembros del sitio:

- La importancia de usar el nuevo sitio para proteger archivos valiosos y las consecuencias de la filtración de datos altamente regulados, como las repercusiones legales, las multas, el ramsonware o la pérdida de ventaja frente a la competencia.
- Cómo obtener acceso al sitio y a sus recursos.
- Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.
- Cómo la directiva DLP les impide compartir archivos de forma externa.
- Cómo etiquetar los archivos más confidenciales con la etiqueta o sub-etiqueta del sitio.
- Cómo la etiqueta o sub-etiqueta protege un archivo incluso cuando se filtra el sitio.

Esta formación debe incluir ejercicios prácticos para que los usuarios puedan experimentar con estas operaciones y sus resultados.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>Paso 2: Realizar revisiones periódicas de uso y archivos

En las semanas posteriores a la formación, el administrador del servicio de SharePoint para el sitio de SharePoint puede:

- Analizar el uso del sitio y compararlo con las expectativas de uso.
- Comprobar que los archivos más confidenciales se han etiquetado de forma correcta con la etiqueta o sub-etiqueta de confidencialidad.

  Puede ver qué archivos tienen una etiqueta asignada viendo una carpeta en SharePoint y añadiendo la columna **Confidencialidad** a través de la opción **Mostrar/ocultar columnas** que está en **Añadir columna**.


Volver a dar formación a los usuarios que lo necesiten.

### <a name="user-adoption-results"></a>Resultados de la adopción de usuarios

Los archivos altamente regulados se almacenan exclusivamente en sitios de SharePoint para datos altamente regulados y los archivos más confidenciales tienen la etiqueta o sub-etiqueta de confidencialidad para el sitio aplicado.

## <a name="how-the-contoso-corporation-used-a-sharepoint-site-for-highly-regulated-data"></a>Cómo la empresa Contoso usó un sitio de SharePoint para datos altamente regulados

Contoso Corporation es un conglomerado industrial a nivel mundial que es ficticio y representativo a la vez. Vea cómo Contoso diseñó, configuró e impulsó la adopción de un [sitio de SharePoint Online seguro](contoso-sharepoint-online-site-for-highly-confidential-assets.md) para sus equipos de investigación en París, Moscú, Nueva York, Beijing y Bengaluru (Bangalore). 

## <a name="see-also"></a>Vea también

[Teams para datos altamente regulados](secure-teams-highly-regulated-data-scenario.md)

[Cargas de trabajo y escenarios de Microsoft 365 Enterprise](deploy-workloads.md)

[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)

[Guía de implementación](deploy-microsoft-365-enterprise.md)
