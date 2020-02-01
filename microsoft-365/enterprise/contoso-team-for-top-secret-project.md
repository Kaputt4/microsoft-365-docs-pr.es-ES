---
title: Equipo para un proyecto confidencial de la empresa Contoso
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso usó un equipo para datos altamente regulados para un proyecto de secreto principal para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: 794fb5cfb6f3011724d37a6a3c42c39dacacc270
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597077"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipo para un proyecto confidencial de la empresa Contoso

Después de una ejecutiva fuera del sitio, el CEO de Contoso solicitó el desarrollo de un nuevo conjunto de productos y servicios que podían duplicar las ganancias de Contoso en los próximos cinco años. El proyecto principal para desarrollar el plan empresarial, de ingeniería y de mercado se llamaba **proyecto 2x** y el personal clave en toda la compañía ha sido reclutado. 

Las escalas de tiempo para la investigación y el desarrollo han sido estrictas, lo que significaba que la colaboración tenía que ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.

Las entregas resultantes del proyecto 2 fueron los planes de negocio, las especificaciones de ingeniería y productos, y los materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint. 

Debido a su naturaleza confidencial, el acceso a estos archivos ha sido:

- Restringido al proyecto el doble de miembros del equipo.
- Está protegido con una directiva de prevención de pérdida de datos (DLP) para evitar que los miembros del equipo con un uso compartido al doble del equipo lo compartan fuera del equipo.
- Cifrado y protegido con permisos para permitir el acceso solo al doble integrante del equipo, incluso si los archivos se distribuyeron fuera de contoso.

El personal de TI de Contoso usó un [equipo para datos altamente regulados](secure-teams-highly-regulated-data-scenario.md) para el proyecto 2x y estos pasos.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Paso 1: creación de un equipo privado y bloqueo del sitio de SharePoint subyacente

Para proteger el acceso al sitio de SharePoint subyacente del equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](sharepoint-file-access-policies.md).

A continuación, un administrador de Contoso ha creado un nuevo equipo privado denominado proyecto 2X y ha agregado las cuentas de usuario del proyecto el doble de personal como miembros.

A continuación, se configuraron opciones de permisos adicionales para el sitio con el fin de evitar que Project 2X comparta el acceso al sitio y evitar que se solicite el acceso al sitio.

Para obtener información detallada sobre la configuración, vea [configuración de SharePoint para un equipo altamente regulado](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Paso 2: configurar una directiva DLP y el sitio subyacente para una etiqueta de retención 

En primer lugar, los administradores de Contoso aplicaron la etiqueta de retención **alta confidencial** de Office 365 existente a la sección de **documentos** del sitio de SharePoint subyacente del equipo del proyecto de dos equipos.

A continuación, creamos una nueva Directiva de DLP de Office 365 denominada **proyecto 2x** que:

- Usa la etiqueta de retención alta confidencial de Office 365.
- Bloquea a los usuarios cuando intentan compartir un archivo en el equipo del proyecto el doble de equipo fuera de contoso.

Para obtener información detallada sobre la configuración, consulte [proteger archivos en Microsoft Teams con etiquetas de retención y DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a>Paso 3: se creó una etiqueta de confidencialidad de Office 365 para el equipo del proyecto de dos equipos

Los administradores de Contoso crearon una nueva etiqueta de confidencialidad de Office 365 denominada **proyecto 2x** que:

- Requiere cifrado.
- Permite permisos de co-autoría para el grupo de Office 365 de dos proyectos.

Esta es la configuración resultante del equipo del proyecto de 2X.

![La configuración resultante del equipo del proyecto de 2X](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Los archivos de la sección documentos del proyecto subyacente 2X del sitio de SharePoint estaban protegidos por:

- Los permisos del sitio, que solo permiten el acceso a los miembros del grupo de Office 365 en el mismo grupo.
- La etiqueta de retención extremadamente confidencial, que se asigna automáticamente a nuevos archivos.
- Una directiva DLP que usa la etiqueta de retención extremadamente confidencial y la configuración que impide que el archivo se comparta con usuarios externos.
- La etiqueta de sensibilidad proyecto 2X, con cifrado y permisos que viajan con el archivo si se mueven o se copian del sitio.

A continuación, se muestra un ejemplo de un archivo almacenado en el sitio del espacio de nombre 2X subyacente con la etiqueta de retención altamente regulada y la etiqueta de sensibilidad espacio en proyecto 2X asignada.

![Un ejemplo de un archivo almacenado en el sitio del proyecto 2X subyacente](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Paso 4: miembros del equipo con experiencia en el 2X del proyecto

El personal de seguridad de Contoso ha entrenado en el proyecto el doble de miembros del equipo en un curso obligatorio que les ha ejecutado:

- Cómo obtener acceso al nuevo proyecto el equipo al doble, usar reuniones y chats y cómo colaborar en archivos de equipo.
- Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados de forma local.
- Una demostración de cómo la Directiva DLP bloquea los archivos para que no se compartan de forma externa.
- Cómo etiquetar archivos con la etiqueta de confidencialidad del proyecto de dos.
- Una demostración de cómo la etiqueta del proyecto 2X protege un archivo incluso cuando éste sale del equipo.

El resultado final fue un entorno seguro en el que el proyecto 2X de miembros del equipo colaboraron en un entorno seguro para chats, reuniones y archivos.

En un par de instancias, Project 2X los miembros del equipo descargaron archivos protegidos por la etiqueta del proyecto 2X en una unidad local para trabajar sin conexión. Sin embargo, después de que se soliciten las credenciales al abrirlas, se han dado cuenta de su error y se han eliminado.

Debido al entorno de colaboración de Microsoft Teams y las características de seguridad de Microsoft 365, los detalles del proyecto 2X se mantuvieron en secreto mientras dure el proyecto. Contoso anunció sus planes y se encuentra en el proceso de implementar los nuevos productos y servicios a la alegría de sus clientes e inversionistas y la Chagrin de sus competidores.

## <a name="next-step"></a>Paso siguiente

[Implementar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.

## <a name="see-also"></a>Vea también

[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)
