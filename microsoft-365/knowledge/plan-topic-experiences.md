---
title: Planeación de temas de Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Obtenga información sobre cómo planear los temas de Microsoft Viva
ms.openlocfilehash: a407fd6e6919c3b85235e317e5ed3ff103607700
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229544"
---
# <a name="plan-for-microsoft-viva-topics"></a>Planeación de temas de Microsoft Viva

Tiene el control de cómo se experimentan los temas en su organización. Las decisiones de planeación de temas garantizan que los temas de alta calidad se muestran a los usuarios y que tienen los permisos adecuados para consumir y aportar conocimientos.

En este artículo examinaremos estas decisiones de planeación:

- Qué SharePoint los sitios que desea rastrear para los temas
- Qué temas, si los hay, que desea excluir de las experiencias de temas
- Qué usuarios desea que los temas sean visibles
- Qué usuarios desea conceder permisos para administrar temas en el centro de temas
- Qué usuarios desea conceder permisos para crear o editar temas en el centro de temas
- Qué nombre desea dar al centro de temas

Se respeta la seguridad y privacidad de los datos y las experiencias de temas no conceden a los usuarios acceso adicional a los archivos a los que no tienen derechos. También se recomienda leer Temas de [Microsoft Viva seguridad y privacidad](topic-experiences-security-privacy.md) como parte del proceso de planeación.

Para obtener más información sobre la tecnología de inteligencia artificial detrás de Los temas de Viva, lea El tema de Alejandría en [Temas de Microsoft Viva: de big data a big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).

## <a name="requirements"></a>Requisitos

Debe estar suscrito a [Viva Topics](https://www.microsoft.com/microsoft-viva/topics) y ser administrador global o administrador de SharePoint para tener acceso a la Centro de administración de Microsoft 365 y configurar temas.

Todos los usuarios que van a usar Temas requieren una **licencia de Experiencias de** tema. La asignación de licencias se trata [en Configurar temas de Microsoft Viva](set-up-topic-experiences.md).

## <a name="topic-discovery"></a>Detección de temas

La configuración de la detección de temas especifica qué sitios de SharePoint se utilizan como fuentes de temas. Esto incluye sitios clásicos y modernos, así como sitios asociados con Microsoft Teams y Microsoft 365 grupos. OneDrive no se incluyen los sitios.

Puede elegir entre incluir todos los sitios de SharePoint, una lista específica de sitios o ningún sitio. Le recomendamos que elija todos los sitios para que las experiencias del tema puedan descubrir una gran cantidad de temas buenos para los usuarios.

Cuando se configuran los Temas, se puede elegir entre las siguientes opciones:

- **Todos los sitios**: Todos los sitios de SharePoint de su organización. Esto incluye los sitios actuales y futuros.
- **Todos, excepto los sitios seleccionados**: Todos los sitios excepto los que usted especifique. Los sitios creados en el futuro se incluirán como orígenes para la detección de temas. 
- **Solo sitios seleccionados:** solo los sitios que especifique. Los sitios creados en el futuro no se incluirán como fuentes para el descubrimiento de temas.
- **Ningún sitio**: No incluya ningún sitio de SharePoint.

Si elige **Todos,** excepto los sitios seleccionados o Solo los sitios seleccionados, puede cargar un archivo .csv con una lista de sitios. Estas opciones son útiles si está realizando una prueba piloto y desea incluir un número limitado de sitios para iniciar.

Puede copiar la siguiente .csv siguiente:

``` csv
Site name,URL
```

No se recomienda elegir **Ningún sitio** porque impide que los temas se creen o actualicen automáticamente. Sin embargo, puede elegir esta opción si desea configurar Temas y, a continuación, agregar sitios más adelante.

Se recomienda crear un proceso para que los usuarios o administradores de conocimientos soliciten que los sitios individuales se quiten de la detección de temas si es necesario en la organización.

### <a name="multi-geo"></a>Multi-Geo

Si su organización ha implementado [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), el centro de temas se aprovisiona en la ubicación central y solo SharePoint los sitios de la ubicación central están disponibles para su uso como orígenes para los temas. (Si selecciona Todos **los sitios,** Viva Topics usará todos los sitios de la ubicación central).

Todo el procesamiento y almacenamiento del contenido se realiza en la ubicación central.

## <a name="user-permissions"></a>Permisos de usuario

Los permisos de usuario que especifique determinan qué personas de la organización interactúan con los temas y qué pueden hacer.

> [!Note] 
> En este momento, Viva Topics no admite proporcionar licencias o permisos de usuario para usuarios invitados (externos). 

*Administrar temas*

Los administradores de conocimientos supervisan la calidad de la información, su estructura y otros procedimientos recomendados en su organización. Pueden confirmar y rechazar temas.

Aunque puede especificar administradores de temas individuales, le recomendamos que cree un grupo de seguridad (o use uno existente) que contenga las personas que desea que sean administradores de conocimientos. Puede especificar este grupo de seguridad durante el proceso de instalación.

*Crear y editar temas*

Los colaboradores de temas son los campeones y expertos en la materia de su organización. Pueden crear y editar temas. 

Se recomienda permitir que todos los usuarios de la organización creen y editan temas porque las experiencias de tema funcionan mejor cuando todos los usuarios pueden compartir información.

Si desea limitar la creación y edición de temas para personas o grupos específicos, cree un grupo de seguridad para ellos y especifiquelo durante el proceso de configuración.

Puedes elegir no permitir que nadie contribuya a los temas, pero esto no se recomienda. Los administradores de conocimientos podrán editar y crear temas si elige esta opción.

*Visores de temas*

Los visores de temas pueden ver información sobre las páginas de temas, los resultados de la búsqueda y cuándo se resaltan los temas en el contenido, como SharePoint páginas. Los usuarios solo pueden ver temas detectados cuando tienen acceso a los archivos y páginas en los que se descubrió el tema.

Al configurar visores de temas, puede elegir entre:

- **Todos los miembros de mi organización**
- **Solo personas o grupos de seguridad seleccionados**
- **Nadie**

Recomendamos **todos los miembros de** mi organización, pero si está realizando un piloto, es posible que desee elegir solo personas seleccionadas o grupos de seguridad. También puede elegir **Nadie si** desea configurar Temas, pero no permitir que los usuarios vean temas todavía. (Los administradores de conocimientos seguirán teniendo acceso para permitirles ver los temas y ayudarles con la decisión de hacer que los temas estén ampliamente disponibles).

## <a name="knowledge-rules"></a>Reglas de conocimiento

Como administrador, puede excluir determinados temas de las experiencias del tema. Esto es útil si desea evitar que los datos confidenciales aparezcan en los temas. Aunque los administradores de conocimientos pueden excluir los temas del centro de temas, los temas excluidos por el administrador ni siquiera son visibles para los administradores de conocimientos. (Los administradores de conocimientos también pueden quitar temas en el centro de temas después de la detección).

Si desea excluir temas en el nivel de administrador, debe agregarlos a un archivo .csv y cargar el archivo. Puede hacerlo durante la instalación o posterior.

El .csv debe contener los siguientes parámetros:

- **Nombre**: Escriba el nombre del tema que quiera excluir. Hay dos formas de hacerlo:
- **MatchType-Exact/Partial:** escriba si el nombre que escribió era *un tipo de* coincidencia exacto *o* parcial.
    - Coincidencia exacta: puede incluir el nombre exacto o el acrónimo (por ejemplo, *Contoso* o *ATL*).
    - Coincidencia parcial: puede excluir todos los temas que tengan una palabra específica.  Por ejemplo, *el arco* excluirá  todos los temas con la palabra arco en él, como *Círculo* de arco, *Soldador de arco de* plasma o Arco *de aprendizaje.* Tenga en cuenta que no excluirá los temas en los que el texto se incluye como parte de una palabra, como *Arquitectura*.
- **Significa (opcional)**: (También conocido como expansión *)* Si desea excluir un acrónimo, escriba las palabras que el acrónimo representa.

    ![Excluir temas en plantilla CSV](../media/exclude-topics-csv.png) 

Puede copiar la plantilla csv siguiente:

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a>Administración

Al configurar Temas, como parte del proceso de configuración, se crea automáticamente un centro de temas. Piense en lo que desea nombrar el centro de temas y en qué desea que sea la dirección URL. Puede establecer el nombre y la dirección URL como parte del proceso de instalación y puede cambiar el nombre (pero no la dirección URL) más adelante en el Centro de administración de Microsoft 365. Solo puede tener un centro de temas.

## <a name="setup-checklist"></a>Lista de comprobación de configuración

Cuando configures experiencias de tema, necesitarás los siguientes elementos a medida que pases por el asistente de configuración:

> [!div class="checklist"]
> * Lista de sitios que se incluirán o excluirán si no se incluyen todos los sitios para la detección de temas
> * Grupo de seguridad para lectores de temas si no se permite que todos los usuarios puedan ver los temas
> * Grupo de seguridad para colaboradores de temas si no se permite que los usuarios creen y editen temas
> * Grupo de seguridad para gerentes de información de temas si no se permite que todos los usuarios administren temas
> * Lista de temas confidenciales que se excluirán de la detección de temas
> * Un nombre para el sitio del centro de temas

## <a name="see-also"></a>Vea también

[Configurar las experiencias temáticas](set-up-topic-experiences.md)

[Administrar la detección de temas en Microsoft 365](topic-experiences-discovery.md)

[Administrar la visibilidad del tema en Microsoft 365](topic-experiences-knowledge-rules.md)

[Administrar permisos de temas en Microsoft 365](topic-experiences-user-permissions.md)

[Cambie el nombre del centro de temas en Microsoft 365](topic-experiences-administration.md)
