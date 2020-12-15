---
title: Planeación de experiencias de temas en Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Obtenga información sobre cómo planear experiencias de temas en Microsoft 365
ms.openlocfilehash: 153937cf6bc4a12f0a27866204b2286c343ddf55
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668230"
---
# <a name="plan-topic-experiences-in-microsoft-365"></a>Planeación de experiencias de temas en Microsoft 365

Tiene el control de cómo se experimentan los temas en su organización. Las decisiones de planeación para las experiencias de los temas garantizan que se muestren temas de alta calidad a los usuarios y tengan los permisos adecuados para consumir y contribuir con el conocimiento.

En este artículo, analizaremos estas decisiones de planeación:

- Los sitios de SharePoint que desea rastrear en busca de temas.
- Qué temas, en caso de haberlos, desea excluir de las experiencias del tema
- Los usuarios a los que desea que los temas sean visibles.
- Los usuarios a los que desea conceder permisos para administrar temas en el centro de temas.
- Los usuarios a los que desea conceder permisos para crear o editar temas en el centro de temas.
- El nombre que desea dar al centro de temas.

La seguridad y privacidad de los datos se respetan y las experiencias del tema no conceden a los usuarios acceso adicional a los archivos a los que no tienen derechos. También le recomendamos que lea el [tema experiencias de seguridad y privacidad](topic-experiences-security-privacy.md) como parte del proceso de planeación.

## <a name="requirements"></a>Requirements

Debe ser administrador global o administrador de SharePoint para tener acceso al centro de administración de Microsoft 365 y configurar las experiencias de los temas.

Todos los usuarios que vayan a usar las experiencias de los temas requieren un tema de licencia de **experiencia** . La asignación de licencias se describe en [set up topic experiencias](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Detección de temas

La configuración de detección de temas especifica los sitios de SharePoint que se usan como orígenes para los temas. Puede elegir incluir todos los sitios de SharePoint, una lista específica de sitios o ningún sitio. Le recomendamos que elija todos los sitios para que las experiencias del tema puedan detectar un gran número de temas buenos para los usuarios.

Al configurar las experiencias de los temas, puede elegir entre las siguientes opciones:

- **Todos los sitios**: todos los sitios de SharePoint de la organización. Esto incluye los sitios actuales y futuros.
- **Todos, excepto los sitios seleccionados**: todos los sitios excepto los que usted especifique. Los sitios creados en el futuro se incluirán como orígenes para la detección de temas. 
- **Solo sitios seleccionados**: solo los sitios que especifique. Los sitios que se creen en el futuro no se incluirán como orígenes para la detección de temas.
- **Sin sitios**: no incluye ningún sitio de SharePoint.

Si elige **todos los sitios, excepto los seleccionados** o **solo los seleccionados**, puede cargar un archivo. csv con una lista de sitios. Estas opciones son útiles si está realizando una prueba piloto y desea incluir un número limitado de sitios para iniciarse.

Puede copiar la plantilla. csv a continuación:

``` csv
Site name,URL
```

No se recomienda no elegir **ningún sitio** porque impide que los temas se creen o actualicen automáticamente. Sin embargo, puede elegir esta opción si desea configurar experiencias de tema y agregar sitios más adelante.

Le recomendamos que cree un proceso para que los usuarios o los administradores del conocimiento soliciten sitios individuales para que se elimine de la detección de temas si es necesario en su organización.

## <a name="user-permissions"></a>Permisos de usuario

Los permisos de usuario que especifique determinan las personas de su organización que interactúan con los temas y lo que pueden hacer.

*Administrar temas*

Los administradores de conocimientos supervisan la calidad de la información, el modo en que se han estructurado y otros procedimientos recomendados en la organización. Pueden confirmar y rechazar temas.

Aunque puede especificar los administradores de temas individuales, le recomendamos que cree un grupo de seguridad (o use uno existente) que contenga las personas que desea que sean responsables de conocimiento. Puede especificar este grupo de seguridad durante el proceso de instalación.

*Creación y edición de temas*

Los colaboradores de temas son los expertos y expertos en la materia de la organización. Pueden crear y editar temas. 

Le recomendamos que permita que todos los usuarios de la organización creen y editen temas porque la experiencia del tema funciona mejor cuando todos los usuarios pueden compartir información.

Si desea limitar la creación y edición de temas a personas o grupos específicos, cree un grupo de seguridad para ellos y, a continuación, especifique durante el proceso de instalación.

Sin embargo, puede optar por no permitir que nadie contribuya con temas, pero no se recomienda. Los administradores de conocimiento seguirán pudiendo editar y crear temas.

*Visores de temas*

Los visores de temas pueden ver información sobre las páginas del tema, en los resultados de la búsqueda y cuando los temas están resaltados en el contenido como las páginas de SharePoint. Los usuarios solo pueden ver los temas detectados cuando tienen acceso a los archivos y las páginas en los que se detectó el tema.

Al configurar los visores de temas, puede elegir entre:

- **Todos los usuarios de mi organización**
- **Solo personas seleccionadas o grupos de seguridad**
- **No hay nadie**

Recomendamos a **todos los usuarios de mi organización**, pero si está realizando una prueba piloto, es posible que quiera elegir solo a las personas o grupos de seguridad seleccionados. También puede elegir **nadie** si desea configurar experiencias de tema, pero no permitir que los usuarios vean todavía los temas. (Los administradores de conocimiento seguirán teniendo acceso para permitirles ver los temas y la ayuda con la decisión de que las experiencias de los temas estén disponibles de forma generalizada).

## <a name="knowledge-rules"></a>Reglas de conocimiento

Como administrador, puede excluir determinados temas de las experiencias de los temas. Esto es útil si desea impedir que los datos confidenciales aparezcan en los temas. Mientras que los administradores de conocimiento pueden excluir temas en el centro de temas, los temas excluidos por el administrador ni son visibles para los administradores de conocimiento. (Los administradores de conocimientos también pueden quitar temas del centro de temas después de la detección).

Si desea excluir temas en el nivel de administrador, debe agregarlos a un archivo. csv y cargar el archivo. Puede hacerlo durante la instalación o posteriormente.

El archivo. csv debe contener los siguientes parámetros:

- **Name**: escriba el nombre del tema que desea excluir. Puede realizar esto de dos maneras:
- **MatchType-Exact/Partial**: escriba si el nombre que ha escrito es un tipo de coincidencia *exacta* o *parcial* .
    - Coincidencia exacta: puede incluir el acrónimo o el nombre exacto (por ejemplo, *contoso* o *ATL*).
    - Coincidencia parcial: puede excluir todos los temas que contengan una palabra específica.  Por ejemplo, *arco* excluirá todos los temas que contengan la palabra *Arc* , como *círculo arco*, *soldadura de arco de plasma* o arco de *formación*. Tenga en cuenta que no se excluirán los temas en los que se incluya el texto como parte de una palabra, como la *arquitectura*.
- **Significa (opcional)**: (también conocido como *expansión*) Si desea excluir un acrónimo, escriba las palabras que representa el acrónimo.

    ![Excluir temas en la plantilla CSV](../media/exclude-topics-csv.png) 

Puede copiar la plantilla CSV a continuación:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administración

Cuando se configuran experiencias de tema, como parte del proceso de configuración, se crea automáticamente un centro de temas. Piense en lo que desea asignar al centro de temas y en lo que desea que sea la dirección URL. Puede establecer el nombre y la dirección URL como parte del proceso de instalación y puede cambiar el nombre (pero no la dirección URL) más adelante en el centro de administración de Microsoft 365. Solo puede tener un centro de temas.

## <a name="setup-checklist"></a>Lista de comprobación de configuración

Al configurar las experiencias de los temas, necesitará los siguientes elementos a medida que avanza en el Asistente de configuración:

> [!div class="checklist"]
> * Lista de sitios que se van a incluir o excluir si no se incluyen todos los sitios para la detección de temas
> * Grupo de seguridad para visores de temas si no permite que todos los usuarios vean temas
> * Grupo de seguridad para colaboradores de temas si no permite a todos los usuarios crear y editar temas
> * Grupo de seguridad para administradores de conocimiento del tema si no permite que todos los usuarios administren temas
> * Lista de temas confidenciales que se deben excluir del descubrimiento de temas
> * Un nombre para el sitio del centro de temas

## <a name="see-also"></a>Vea también

[Configurar experiencias de tema](set-up-topic-experiences.md)

[Administrar la detección de temas en Microsoft 365](topic-experiences-discovery.md)

[Administrar la visibilidad de los temas en Microsoft 365](topic-experiences-knowledge-rules.md)

[Administrar los permisos de temas en Microsoft 365](topic-experiences-user-permissions.md)

[Cambiar el nombre del centro de temas en Microsoft 365](topic-experiences-administration.md)
