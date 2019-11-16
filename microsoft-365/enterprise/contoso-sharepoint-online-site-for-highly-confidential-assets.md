---
title: Sitio de SharePoint para activos digitales altamente confidenciales de Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/04/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso implementó un sitio de SharePoint para datos altamente regulados para una colaboración más sencilla entre sus equipos de investigación.'
ms.openlocfilehash: ce813407c0f4c6f7b68aa997bf5e54b86a24ff2d
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672716"
---
# <a name="sharepoint-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Sitio de SharePoint para activos digitales altamente confidenciales de Contoso Corporation

Los activos más valiosos de Contoso son su propiedad intelectual en forma de secretos comerciales, como técnicas de fabricación patentadas, así como especificaciones de diseño para productos que están en desarrollo. Estos activos estaban en formato digital, que se almacenaban originalmente como archivos en un sitio de SharePoint Server 2016. Cuando contoso implementó Microsoft 365 Enterprise, quería realizar la transición de sus activos digitales locales a la nube para facilitar el acceso y aumentar la colaboración entre los equipos de investigación de París, Moscú, Nueva York, Beijing y Bangalore. 
  
Sin embargo, debido a su carácter confidencial, el acceso a estos archivos debe ser:

- Restringido al conjunto de personas a las que se les permite acceder a ellos. 
- Protegido con una directiva de prevención de pérdida de datos (DLP) para evitar que los usuarios los distribuyan fuera del sitio.
- Cifrado y protegido con permisos para evitar que los usuarios no autorizados obtengan acceso a su contenido, incluso si se distribuyen fuera del sitio.

Los administradores de SharePoint y de seguridad en el Departamento de TI de Contoso decidieron usar un [sitio de SharePoint para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso usó estos pasos para crear y proteger sitios de grupo de SharePoint para sus equipos de investigación.

## <a name="step-1-created-a-private-sharepoint-team-site"></a>Paso 1: crear un sitio de grupo privado de SharePoint

Para proteger el acceso al sitio de SharePoint, contoso ha configurado las [directivas de acceso de SharePoint recomendadas](sharepoint-file-access-policies.md).

Después, los administradores de Contoso IT recopilaron una lista de las cuentas de usuario de los investigadores de sus oficinas de París, Moscú, Nueva York, Beijing y Bangalore. 

A continuación, un administrador de TI de Contoso ha creado un nuevo sitio de grupo privado denominado **Research** y ha agregado todas las cuentas de usuario para sus investigadores.

A continuación, se configuraron opciones de permisos adicionales para el sitio con el fin de evitar que los investigadores compartan el acceso al sitio y evitar que los investigadores soliciten acceso al sitio.

## <a name="step-2-configured-the-site-for-a-restrictive-dlp-policy"></a>Paso 2: configurar el sitio para una directiva DLP restrictiva

En primer lugar, los administradores de Contoso aplicaron la etiqueta de retención **alta confidencial** de Office 365 existente a la carpeta documentos del sitio de **investigación** .

A continuación, creamos una nueva Directiva de DLP de Office 365 denominada **Research** que:

- Usa la etiqueta de retención **alta confidencial** de Office 365. 
- Bloquea a los usuarios cuando intentan compartir un activo digital en el sitio de **investigación** fuera de contoso.

Para obtener información detallada sobre la configuración, vea [proteger archivos de SharePoint con etiquetas de retención y DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-office-365-sensitivity-sublabel-for-the-site"></a>Paso 4: crear una subetiqueta de confidencialidad de Office 365 para el sitio

Contoso Admins creó una nueva subetiqueta de confidencialidad de Office 365 denominada **Teams de investigación** de la etiqueta **extremadamente confidencial** que:

- Requiere cifrado.
- Permite permisos de co-autoría para el grupo de Office 365 **Research**
- Se aplica al grupo de Office 365 **Research**

Esta es la configuración resultante del sitio de grupo de **investigación** para los activos extremadamente confidenciales.

![La configuración resultante del sitio de grupo de investigación para los activos extremadamente confidenciales](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Los archivos de las carpetas del sitio de **investigación** están protegidos por:

- Los permisos del sitio, que solo permiten el acceso a los miembros del grupo de **investigación** 365 de Office.
- La Directiva DLP de **investigación** , que usa la etiqueta de retención y la configuración de retención **extremadamente confidenciales** , que impiden que el archivo se comparta con usuarios externos.
- Subetiqueta de confidencialidad de los **equipos de investigación** , con cifrado y permisos que viajan con el archivo si se mueven o se copian desde el sitio de **investigación** .

A continuación, se muestra un ejemplo de un archivo almacenado en el sitio de **investigación** con la subetiqueta de confidencialidad de **Teams de investigación** asignada.

![La configuración resultante del sitio de grupo de investigación para los activos extremadamente confidenciales](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config-example-file.png)


## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Paso 5: migrar los datos de la investigación de SharePoint local

Los administradores de Contoso movieron todos los archivos de investigación local en el sitio local de SharePoint Server 2016 a las carpetas del nuevo sitio de SharePoint de **referencia** .

## <a name="step-6-trained-their-researchers"></a>Paso 6: formación de sus investigadores

El personal de seguridad de Contoso ha entrenado a los miembros del grupo **Research** Office 365 en un curso obligatorio en el que se han ejecutado:

- Cómo obtener acceso al nuevo sitio de **investigación** y sus archivos existentes.
- Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.
- Una demostración de cómo la Directiva DLP de **investigación** bloquea los archivos para que no se compartan de forma externa.
- Cómo etiquetar archivos con la subetiqueta de confidencialidad de los **equipos de investigación** .
- Una demostración de cómo la subcarpeta **equipos de investigación** protege un archivo incluso cuando se pierde del sitio.

El resultado final es un entorno seguro en el que los investigadores pueden colaborar a través de Contoso en un entorno seguro en archivos que contienen información de referencia. 

Si un documento de investigación de la subetiqueta **equipos de investigación** abandona el sitio de **investigación** , sólo se cifra y es accesible para los miembros del grupo de Office 365 **Research** con credenciales de cuenta de usuario válidas.

## <a name="next-step"></a>Siguiente paso

[Implementar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.

## <a name="see-also"></a>Vea también

[Biblioteca de productividad de Microsoft 365](https://aka.ms/productivitylibrary)(https://aka.ms/productivitylibrary)
