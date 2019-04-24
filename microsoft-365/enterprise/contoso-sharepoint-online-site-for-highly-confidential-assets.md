---
title: Sitio de SharePoint Online para activos digitales altamente confidenciales de Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/15/2019
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: Cómo contoso implementó un sitio de SharePoint Online para datos altamente regulados para una colaboración más sencilla entre sus equipos de investigación.'
ms.openlocfilehash: c20e3a1c4ad0b862e81b897acc1462e3a1d1f776
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289236"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>Sitio de SharePoint Online para activos digitales altamente confidenciales de Contoso Corporation

 **Resumen:** Cómo contoso implementó un sitio de SharePoint Online para datos altamente regulados para una colaboración más sencilla entre sus equipos de investigación.
  
Los activos más valiosos de Contoso son su propiedad intelectual en forma de secretos comerciales, como técnicas de fabricación patentadas, así como especificaciones de diseño para productos que están en desarrollo. Estos activos están en formato digital, que se almacenaban originalmente como archivos en un sitio de SharePoint Server 2016. Cuando contoso implementó Microsoft 365 Enterprise, quería realizar la transición de sus activos digitales locales a la nube para facilitar el acceso y aumentar la colaboración entre los equipos de investigación de París, Moscú, Nueva York, Beijing y Bangalore. 
  
Sin embargo, debido a su carácter confidencial, el acceso a estos archivos debe ser:

- Se limita al conjunto de personas a las que se les permite ver o cambiar, con permisos en curso para el sitio administrado solo por los administradores de SharePoint. 
- Protegido con prevención de pérdida de datos (DLP) para evitar que los usuarios los distribuyan fuera del sitio.
- Cifrado y protegido con listas de control de acceso para evitar que los usuarios no autorizados obtengan acceso a su contenido, incluso si se distribuyen fuera del sitio.

Los administradores de SharePoint y de seguridad en el Departamento de TI de Contoso decidieron usar un [sitio de SharePoint Online para datos altamente regulados](teams-sharepoint-online-sites-highly-regulated-data.md).
  
Contoso usó estos pasos para crear y proteger sitios de grupo de SharePoint Online para sus equipos de investigación.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Paso 1: revisado y comprobado los miembros de los grupos de equipo de investigación

Los administradores de TI de Contoso realizaron una revisión del conjunto de grupos de seguridad para sus equipos de investigación. Quitaron a todos los usuarios que no eran un investigador o no necesitaban acceso a los activos de investigación. 

También han creado estos nuevos grupos de seguridad:

- **Investigación: administradores**  El conjunto de administradores de SharePoint que tienen control total sobre el sitio, incluida la capacidad de modificar permisos.
- **Investigación: miembros**  El conjunto de grupos de seguridad para los equipos de investigación de todo el mundo.
- **Investigación-visores**  El conjunto de usuarios de administración, como los ejecutivos de la organización de investigación, que solo pueden ver los activos del sitio.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Paso 2: crear un sitio de grupo de SharePoint Online aislado 

En primer lugar, los administradores de SharePoint de Contoso creaban un nuevo sitio de grupo denominado **Research**. A continuación, se configuran:

- El nivel de permiso control total para usar el grupo de SharePoint propietarios de la investigación, que tiene el grupo de seguridad **Research-Admins** como miembro
- El nivel de permisos editar para usar el grupo de SharePoint miembros de Research, que tiene el grupo de seguridad integrantes de **investigación** como miembro
- El nivel de permiso de lectura para usar el grupo de SharePoint visitantes de investigación, que tiene el grupo **de seguridad Research-views** como miembro

Estos son los niveles de permisos resultantes de SharePoint, los grupos de SharePoint y sus miembros.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

A continuación, se configuraron restricciones adicionales para el sitio.

Para obtener información detallada sobre la configuración, vea [implementar un sitio de grupo de SharePoint Online aislado](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-dlp-policy"></a>Paso 3: configurar el sitio para una directiva DLP restrictiva

En primer lugar, los administradores de Contoso aplicaron la etiqueta de retención **altamente confidencial** de Office 365 al sitio de **investigación** .

A continuación, creamos una nueva Directiva de DLP de Office 365 denominada **Research** que:

- Usa la etiqueta de retención **alta confidencial** de Office 365. 
- Se aplica al sitio de **investigación** .
- Impide que los usuarios compartan documentos.

Para obtener información detallada sobre la configuración, vea [proteger archivos de SharePoint Online con Office 365 etiquetas y DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Paso 4: se creó una etiqueta secundaria de Azure Information Protection para el sitio

Los administradores de Contoso crearon una nueva etiqueta secundaria de Azure Information Protection denominada **Research** of the default **extremadamente Confidential** Label en una directiva con ámbito que:

- Requiere cifrado.
- Permite el acceso total por parte de miembros del grupo de seguridad **Research-Members** .
- Permite el acceso de lectura por parte de los miembros del grupo de seguridad **Research-Viewers** .

A continuación, implementó el cliente de Azure Information Protection en los dispositivos de los miembros del equipo de investigación.

Para obtener información detallada sobre la configuración, vea [proteger archivos de SharePoint Online con Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Esta es la configuración resultante del sitio de **investigación** para los activos extremadamente confidenciales.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

Los archivos de las carpetas del sitio de **investigación** están protegidos por:

- La subetiqueta **Research** Azure Information Protection, que aplica cifrado y permssions a cada archivo que viaja con el archivo cuando se mueve o se copia desde el sitio de **investigación** .
- La Directiva DLP de **investigación** , que usa la etiqueta de retención y la configuración **altamente confidenciales** que impiden que el archivo abandone el sitio.
- El conjunto de permisos de sitio, que solo permiten el acceso a los **** miembros de los grupos de seguridad Research-Members y Research **-views** y a la administración por parte de los miembros del grupo de seguridad **Research-Admins** .

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Paso 5: migrar los datos de la investigación de SharePoint local

Los administradores de Contoso movieron todos los archivos de investigación local en el sitio local de SharePoint Server 2016 a las carpetas del nuevo sitio de **referencia** de SharePoint Online.

## <a name="step-6-trained-their-users"></a>Paso 6: formación para los usuarios 

El personal de seguridad de Contoso ha entrenado a los equipos de investigación en un curso obligatorio que les ha ejecutado:

- Cómo obtener acceso al nuevo sitio de SharePoint Online de **referencia** y sus archivos existentes.
- Cómo crear archivos nuevos en el sitio o cargar archivos nuevos almacenados de forma local.
- Una demostración de cómo la Directiva DLP bloquea los archivos para que no se compartan de forma externa.
- Cómo usar el cliente de Azure Information Protection para etiquetar archivos de referencia con la etiqueta secundaria **Research** .
- Una demostración de cómo la subetiqueta **Research** protege un archivo incluso cuando se pierde del sitio.

El resultado final es un entorno seguro en el que los investigadores pueden colaborar en toda la organización en un entorno seguro. 

Si se pierde del sitio de **investigación** un documento de investigación con la subetiqueta **Research** , este se cifra y es accesible sólo para los miembros de los grupos de seguridad **Research-Members** y **Research-Viewers** con credenciales válidas.

## <a name="next-step"></a>Siguiente paso

[Implementar](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise en su organización.

