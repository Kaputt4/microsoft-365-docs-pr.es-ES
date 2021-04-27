---
title: Equipo aislado para un proyecto secreto de Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Resumen: cómo Contoso usó un equipo con aislamiento de seguridad para un proyecto secreto para desarrollar un nuevo conjunto de productos y servicios.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029021"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Equipo aislado para un proyecto secreto de Contoso Corporation

Después de un ejecutivo fuera del sitio, el director ejecutivo de Contoso ordenó el desarrollo de un nuevo conjunto de productos y servicios que podría duplicar las ganancias de Contoso en los próximos cinco años. El proyecto secreto para desarrollar el plan de negocio, ingeniería y mercado se llamó **Project 2X** y se reclutó personal clave en toda la compañía. 

Las escalas de tiempo para la investigación y el desarrollo eran estrechas, lo que significaba que la colaboración debía ser eficaz y proporcionar reuniones seguras, conversaciones en curso y almacenamiento de archivos.

Los resultados de Project 2X fueron planes de negocio, especificaciones de producto e ingeniería, y materiales y programaciones de marketing en forma de archivos de Word, Excel y PowerPoint. 

Debido a su naturaleza confidencial, el acceso a estos archivos era:

- Restringido a los miembros del equipo de Project 2X y a los altos directivos.
- Cifrado y protegido con permisos para permitir el acceso solo a los miembros del equipo de Project 2X y a los jefes de equipo, incluso si los archivos se distribuyeron fuera de sus carpetas protegidas.

El personal de TI de Contoso usó un [equipo con aislamiento de seguridad](secure-teams-security-isolation.md) para Project 2X y estos pasos.

## <a name="step-1-created-a-private-team"></a>Paso 1: Crear un equipo privado

En primer lugar, para proteger el acceso al sitio subyacente de SharePoint para el equipo, los administradores de TI de Contoso configuraron las directivas de acceso [de SharePoint recomendadas.](../security/office-365-security/sharepoint-file-access-policies.md)

A continuación, un administrador de TI de Contoso creó un nuevo equipo privado denominado Project 2X y agregó las cuentas de usuario del personal de Project 2X como miembros. También configuraron el equipo para que solo los propietarios de equipos de Project 2X puedan crear canales privados.

Para obtener los detalles de configuración, vea [Create a private team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Paso 2: Crear una etiqueta de confidencialidad para el equipo de Project 2X

Los administradores de Contoso crearon una nueva etiqueta de confidencialidad denominada **Project 2X** que:

- Cifrado habilitado.
- Se Co-Author permisos para el grupo de Project 2X Microsoft 365.
- Permisos de visor permitidos para el grupo de liderazgo sénior.
- Acceso bloqueado a dispositivos no administrados.

Los archivos de la **sección Documentos** del sitio subyacente de SharePoint de Project 2X estaban protegidos por:

- Permisos de sitio, que solo permiten permisos completos a los miembros del grupo de Project 2X Microsoft 365 y permisos de lectura para el grupo de liderazgo sénior.
- Etiqueta de confidencialidad de Project 2X, con cifrado y permisos que viajan con el archivo si se mueve o copia del sitio.

Para obtener los detalles de configuración, vea [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Paso 3: Configurar el sitio subyacente de SharePoint

En primer lugar, para proteger el acceso al sitio subyacente de SharePoint para el equipo, los administradores de TI de Contoso configuraron las directivas de acceso [de SharePoint recomendadas.](../security/office-365-security/sharepoint-file-access-policies.md)

A continuación, configuraron opciones de permisos adicionales para el sitio:

- Para evitar que los miembros del grupo de Project 2X compartan el acceso al sitio. Para obtener más información sobre la configuración, [vea Configuración de SharePoint para un equipo con aislamiento de seguridad.](secure-teams-security-isolation.md#sharepoint-settings)
- Para permisos de lectura para el grupo de liderazgo sénior.

A continuación, configuraron opciones de permisos adicionales para el sitio para impedir que los miembros del grupo de Project 2X compartan el acceso al sitio. 

Cuando se crearon canales privados para Project 2X, el propietario del grupo deshabilitó el uso compartido de invitados y estableció el vínculo de uso compartido predeterminado en **el valor Personas** específicas.

Esta es la configuración resultante del equipo de Project 2X con aislamiento de seguridad.

![La configuración resultante del equipo de Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Paso 4: Miembros del equipo de Project 2X formados

El personal de seguridad de Contoso entrenó a los miembros del equipo de Project 2X en un curso obligatorio que les intensó:

- Cómo acceder al nuevo equipo de Project 2X, usar reuniones y chats y cómo colaborar en archivos de equipo.
- Cómo crear nuevos archivos en el equipo y cargar nuevos archivos creados localmente.
- Cómo etiquetar archivos con la etiqueta de confidencialidad de Project 2X.
- Una demostración de cómo la etiqueta de Project 2X protege un archivo incluso cuando deja el equipo.

El resultado final fue un entorno seguro en el que los miembros del equipo de Project 2X colaboraban en un entorno seguro para chats, reuniones y archivos.

Este es un ejemplo de un archivo almacenado en el sitio subyacente de Project 2X con la etiqueta de confidencialidad de Project 2X asignada.

![Un ejemplo de un archivo almacenado en el sitio subyacente de Project 2X](../media/contoso-team-for-top-secret-project-example.png)

En un par de instancias, los miembros del equipo de Project 2X descargaron archivos protegidos por la etiqueta de Project 2X en una unidad local para el trabajo sin conexión. 

Sin embargo, después de que se les pidan credenciales al abrirlos, se dieron cuenta de su error y los eliminaron.

Debido al entorno de colaboración de Teams y las características de seguridad de Microsoft 365, los detalles de Project 2X se mantuvieron en secreto durante la duración del proyecto. Contoso anunció sus planes y está en el proceso de implementar los nuevos productos y servicios para el deleite de sus clientes e inversores y el enojo de sus competidores.

## <a name="next-step"></a>Paso siguiente

[Implementar un equipo con aislamiento de seguridad](secure-teams-security-isolation.md) en la organización.

