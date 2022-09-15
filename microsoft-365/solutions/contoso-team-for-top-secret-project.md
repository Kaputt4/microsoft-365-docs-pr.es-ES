---
title: Equipo aislado para un proyecto secreto de Contoso Corporation
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- highpri
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: cómo Contoso usó un equipo con aislamiento de seguridad para un proyecto de alto secreto para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: 2afc993245e2ad1a67242855dd658a38de5e628a
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730669"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipo aislado para un proyecto secreto de Contoso Corporation

Después de un ejecutivo fuera del sitio, el CEO de Contoso ordenó el desarrollo de un nuevo conjunto de productos y servicios que podrían duplicar las ganancias de Contoso en los próximos cinco años. El proyecto de alto secreto para desarrollar el plan de negocio, ingeniería y mercado se llamó **Project 2X** y se reclutó personal clave en toda la empresa. 

Las escalas de tiempo para la investigación y el desarrollo eran estrictas, lo que significaba que la colaboración debía ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.

Los resultados resultantes para Project 2X eran planes de negocio, especificaciones de productos e ingeniería, y materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint. 

Debido a su naturaleza confidencial, el acceso a estos archivos era:

- Restringido a los miembros del equipo de Project 2X y a la dirección sénior.
- Cifrado y protegido con permisos para permitir el acceso solo a los miembros del equipo de Project 2X y a la dirección sénior, incluso si los archivos se distribuyeron fuera de sus carpetas protegidas.

El personal de TI de Contoso usó un [equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para Project 2X y estos pasos.

## <a name="step-1-created-a-private-team"></a>Paso 1: Creación de un equipo privado

En primer lugar, para proteger el acceso al sitio de SharePoint subyacente para el equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](../security/office-365-security/sharepoint-file-access-policies.md).

A continuación, un administrador de TI de Contoso creó un nuevo equipo privado denominado Project 2X y agregó las cuentas de usuario del personal de Project 2X como miembros. También configuraron el equipo para que solo los propietarios del equipo de Project 2X puedan crear canales privados.

Para obtener los detalles de configuración, consulte [Creación de un equipo privado](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Paso 2: Creación de una etiqueta de confidencialidad para el equipo de Project 2X

Los administradores de Contoso crearon una nueva etiqueta de confidencialidad denominada **Project 2X** que:

- Cifrado habilitado.
- Permisos de Co-Author permitidos para el grupo de Microsoft 365 de Project 2X.
- Permisos de visor permitidos para el grupo de liderazgo sénior.
- Acceso bloqueado a dispositivos no administrados.

Los archivos de la sección **Documentos** del sitio subyacente de SharePoint de Project 2X estaban protegidos por:

- Permisos de sitio, que solo permiten permisos completos a los miembros del grupo de Project 2X Microsoft 365 y permisos de lectura para el grupo de liderazgo sénior.
- La etiqueta de confidencialidad de Project 2X, con cifrado y permisos que viajan con el archivo si se mueve o copia del sitio.

Para obtener los detalles de configuración, consulte [Creación de una etiqueta de confidencialidad](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Paso 3: Configurar el sitio de SharePoint subyacente

En primer lugar, para proteger el acceso al sitio de SharePoint subyacente para el equipo, los administradores de TI de Contoso configuraron las [directivas de acceso de SharePoint recomendadas](../security/office-365-security/sharepoint-file-access-policies.md).

A continuación, configuraron opciones de permisos adicionales para el sitio:

- Para evitar que los miembros del grupo de Project 2X compartan el acceso al sitio. Para obtener los detalles de configuración, vea [Configuración de SharePoint para un equipo con aislamiento de seguridad](secure-teams-security-isolation.md#sharepoint-settings).
- Para Permisos de lectura para el grupo de liderazgo sénior.

A continuación, configuraron opciones de permisos adicionales para el sitio para impedir que los miembros del grupo de Project 2X compartan el acceso al sitio. 

A medida que se crearon canales privados para Project 2X, el propietario del grupo deshabilitó el uso compartido de invitados y estableció el vínculo de uso compartido predeterminado en el valor **Personas específicas** .

Esta es la configuración resultante del equipo de Project 2X con aislamiento de seguridad.

![Configuración resultante del equipo de Project 2X.](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Paso 4: Miembros del equipo entrenado de Project 2X

El personal de seguridad de Contoso entrenó a los miembros del equipo de Project 2X en un curso obligatorio que los avanzó:

- Cómo acceder al nuevo equipo de Project 2X, usar reuniones y chats y cómo colaborar en archivos de equipo.
- Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados localmente.
- Cómo etiquetar archivos con la etiqueta de confidencialidad de Project 2X.
- Una demostración de cómo la etiqueta de Project 2X protege un archivo incluso cuando deja el equipo.

El resultado final fue un entorno seguro en el que los miembros del equipo de Project 2X colaboraron en un entorno seguro para chats, reuniones y archivos.

Este es un ejemplo de un archivo almacenado en el sitio subyacente de Project 2X con la etiqueta de confidencialidad de Project 2X asignada.

![Ejemplo de un archivo almacenado en el sitio subyacente de Project 2X.](../media/contoso-team-for-top-secret-project-example.png)

En un par de instancias, los miembros del equipo de Project 2X descargaron archivos protegidos por la etiqueta de Project 2X en una unidad local para el trabajo sin conexión. 

Sin embargo, después de que se les pidan credenciales al abrirlas, se dieron cuenta de su error y las eliminaron.

Debido al entorno de colaboración de Teams y a las características de seguridad de Microsoft 365, los detalles de Project 2X se mantienen en secreto mientras dure el proyecto. Contoso anunció sus planes y está en proceso de implementar los nuevos productos y servicios para deleite de sus clientes e inversores y el disgusto de sus competidores.

## <a name="next-step"></a>Paso siguiente

[Implemente un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) en su organización.

