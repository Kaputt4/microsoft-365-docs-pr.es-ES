---
title: Sitio de SharePoint Online para activos digitales altamente confidenciales de la empresa Contoso
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Resumen: Cómo Contoso implementa un sitio de SharePoint Online para altamente regulados datos para facilitar la colaboración entre su investigación de los equipos.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871750"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Sitio de SharePoint Online para activos digitales altamente confidenciales de la empresa Contoso

 **Resumen:** Cómo Contoso implementa un sitio de SharePoint Online para datos altamente regulados para facilitar la colaboración entre sus equipos de investigación.
  
Activos más valiosos de Contoso son de su propiedad intelectual en el formulario de secretos comerciales, como las técnicas de fabricación propietario y las especificaciones de productos que se encuentran en el desarrollo de diseño. Estos activos están en formato digital, que originalmente se almacenan como archivos en un sitio de SharePoint Server 2016. Cuando Contoso implementa Microsoft 365 Enterprise, que deseaba realizar la transición de sus activos digitales de local a la nube para facilitar el acceso y la colaboración más susceptible a través de equipos de investigación en Bangalore, Moscú, Nueva York, Beijing y París. 
  
Sin embargo, debido a su naturaleza confidencial, debe tener acceso a estos archivos:

- Restringido al conjunto de personas que tienen permiso para ver o cambiar a ellas, con permisos de curso para el sitio administrados sólo por los administradores de SharePoint. 
- Protegida con la prevención de pérdida de datos (DLP) para evitar que los usuarios de distribución de los mismos fuera del sitio.
- Access cifrada y protegida con control de listas para impedir que los usuarios no autorizados obtengan acceso a su contenido, incluso si se distribuyen fuera del sitio.

Los administradores de seguridad y SharePoint en Contoso del departamento de TI decidió usar un [sitio de SharePoint Online para altamente regulado datos](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso utiliza estos pasos para crear y proteger un sitios de grupo de SharePoint Online para sus equipos de investigación.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Paso 1: Revisar y comprobar a los miembros de grupos de investigación de equipo

Los administradores de TI de Contoso realizan una revisión del conjunto de grupos de seguridad de sus equipos de investigación. Ha quitado cualquier persona que no era un entrevistador o no tuvo acceso a los activos de investigación. 

También y crea estos nuevos grupos de seguridad:

- **Administradores de investigación**  El conjunto de administradores de SharePoint que tienen control total a través del sitio, incluida la posibilidad de modificar los permisos.
- **Research (miembros)**  El conjunto de grupos de seguridad para los equipos de investigación todo el mundo.
- **Visores de investigación**  El conjunto de usuarios de administración, como los ejecutivos en la organización de investigación, que puede ver los activos en el sitio.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Paso 2: Crear un sitio de grupo de SharePoint Online aislado 

Los administradores de Contoso SharePoint crea por primera vez un nuevo sitio de grupo con el nombre **Research**. A continuación, configurar:

- El nivel de permiso Control total para utilizar el grupo de SharePoint de propietarios de investigación, que tiene el grupo de seguridad **Administradores de investigación** como un miembro
- El nivel de permisos Editar para usar el grupo de SharePoint miembros de investigación, que tiene el grupo de seguridad de **Los miembros de investigación** como un miembro
- El nivel de permiso de lectura para usar el grupo de visitantes de SharePoint de investigación, que tiene el grupo de seguridad de **Visores de investigación** como un miembro

A continuación presentamos los niveles de permisos de SharePoint resultantes, los grupos de SharePoint y sus miembros.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

A continuación, configuran restricciones adicionales para el sitio.

Para los detalles de configuración, vea [implementar un sitio de grupo de SharePoint Online aislado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>Paso 3: Configurar el sitio para una etiqueta de Office 365 restrictivo directiva de DLP

En primer lugar, los administradores de Contoso aplican la etiqueta de Office 365 **Altamente confidencial** en el sitio de **investigación** .

A continuación, crea una nueva directiva de DLP de Office 365 con el nombre **Research** que:

- Utiliza la etiqueta de Office 365 **Altamente confidencial** . 
- Se aplica al sitio de **investigación** .
- Impide que los usuarios compartir documentos.

Para los detalles de configuración, vea [archivos de protección de SharePoint Online con las etiquetas de Office 365 y DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Paso 4: Crear una etiqueta de fracciones de protección de la información de Azure para el sitio

Los administradores de Contoso creados una nueva etiqueta de fracciones de protección de la información de Azure denominan **investigación** de la etiqueta **Altamente confidencial** de forma predeterminada en una directiva de ámbito:

- Requiere cifrado.
- Permite acceso total por los miembros del grupo de seguridad de **Los miembros de la investigación** .
- Permite el acceso de lectura por los miembros del grupo de seguridad de **Los visores de investigación** .

A continuación, implementa al cliente de protección de la información de Azure en los dispositivos de miembros del equipo de investigación.

Para los detalles de configuración, vea [archivos de protección de SharePoint Online con protección de la información de Azure](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Aquí es la configuración resultante del sitio de **investigación** de activos altamente confidenciales.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Paso 5: Migrar los datos de investigación de SharePoint local

Los administradores de Contoso se mueven que todos los locales en los archivos en el sitio de SharePoint Server 2016 local a las carpetas en el nuevo sitio de SharePoint Online de **investigación** de la investigación.

## <a name="step-6-trained-their-users"></a>Paso 6: Aprendizaje a sus usuarios 

Personal de seguridad de Contoso formado los equipos de investigación en un curso obligatorio que había escalonada ellos a través de:

- Cómo obtener acceso a sus archivos existentes y el nuevo sitio de SharePoint Online de **investigación** .
- Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.
- Una demostración de cómo la directiva de DLP bloquea los archivos desde que se está compartiendo externamente.
- Cómo utilizar al cliente de protección de la información de Azure para etiquetar los archivos de investigación con la etiqueta de fracciones de **investigación** .
- Una demostración de cómo la etiqueta subcaracterística **Research** protege un archivo incluso cuando lo se agotaron desde el sitio.

El resultado final es un entorno seguro en el que los investigadores puedan colaborar en toda la organización en un entorno seguro. 

Si un documento de investigación con la etiqueta de fracciones de **investigación** se agotaron desde el sitio de **investigación** , es cifradas y sólo pueden tener acceso los miembros de los grupos de seguridad de **Los miembros de la investigación** y **Los visores de investigación** con credenciales válidas.

## <a name="next-step"></a>Siguiente paso

[Implemente](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.

