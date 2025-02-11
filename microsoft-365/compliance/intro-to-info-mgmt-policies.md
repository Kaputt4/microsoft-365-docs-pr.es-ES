---
title: Introduction to information management policies (Introducción a las directivas de administración de la información)
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Obtenga información sobre cómo usar directivas de administración de información para controlar y realizar un seguimiento de cosas como cuánto tiempo se conserva el contenido o qué acciones pueden realizar los usuarios con ese contenido.
ms.openlocfilehash: 98eae2a08aa246a1f0ebe7d037103a82c132d060
ms.sourcegitcommit: 437461fa1d38ff9bb95dd8a1c5f0b94e8111ada2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2022
ms.locfileid: "67680491"
---
# <a name="introduction-to-information-management-policies"></a>Introduction to information management policies (Introducción a las directivas de administración de la información)

Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Las directivas de administración de información permiten a las organizaciones controlar y hacer un seguimiento de cosas como cuánto tiempo se mantiene el contenido o qué acciones pueden realizar los usuarios con ese contenido. Las directivas de administración de información pueden ayudar a las organizaciones a cumplir normas legales o gubernamentales, o simplemente pueden forzar la aplicación de procesos empresariales internos. 
  
Por ejemplo, una organización que debe seguir las regulaciones gubernamentales que requieren que demuestren "controles adecuados" de sus estados financieros podría crear una o más directivas de administración de información que auditen acciones específicas en el proceso de creación y aprobación de todos los documentos relacionados con las presentaciones financieras.
  
Para obtener información detallada, consulte [Creación y aplicación de directivas de administración de información](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Características de las directivas de administración de información
<a name="__top"> </a>

Hay cuatro categorías básicas de características de directiva predefinidas que las organizaciones pueden usar individualmente o en combinación para administrar el contenido y los procesos. 
  
![Tipos de directivas de contenido.](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
La característica Directiva de auditoría ayuda a las organizaciones a analizar cómo usan sus sistemas de administración de contenido el registro de eventos y operaciones que se realizan en documentos y elementos de lista. Puede configurar la característica Directiva de auditoría para registrar eventos como cuando un documento o elemento se edita, se ve, se registra, se desprotegió, se eliminó o se cambiaron sus permisos. Toda la información de auditoría se almacena en un único registro de auditoría en el servidor y los administradores del sitio pueden ejecutar informes en él. 
  
La característica Directiva de expiración ayuda a las organizaciones a eliminar o quitar contenido obsoleto de sus sitios de una manera coherente y de seguimiento. Esto le ayuda a administrar el costo y el riesgo asociados a la retención de contenido obsoleto. Puede configurar una directiva de expiración para especificar que determinados tipos de contenido expiren en una fecha determinada o dentro de un período de tiempo después de que el documento se haya creado o modificado por última vez.
  
Las organizaciones también pueden crear e implementar características de directivas personalizadas para satisfacer necesidades específicas. Por ejemplo, una organización de fabricación podría querer definir una directiva de administración de la información para todos los borradores de documentos de especificación de diseño de productos que prohíbe a los usuarios imprimir copias de estos documentos en impresoras no seguras. Para definir este tipo de directiva de administración de información, puede crear e implementar una característica de directiva de restricción de impresión que se puede agregar a la directiva de administración de información pertinente para el tipo de contenido de especificación de diseño de producto.
  
## <a name="locations-to-use-an-information-management-policy"></a>Ubicaciones para usar una directiva de administración de información
<a name="__toc340213528"> </a>

Para implementar una directiva de administración de información, debe agregarla a una lista, biblioteca o tipo de contenido en un sitio. La ubicación en la que se crea o agrega una directiva de administración de información afecta a la amplitud de la aplicación de la directiva o a la amplitud con la que se puede usar. Puede:
  
 **Cree una directiva de colección de sitios y agregue esta directiva a un tipo de contenido, lista o biblioteca** . Puede crear una directiva de colección de sitios en la lista Directivas del sitio de nivel superior de una colección de sitios. Después de crear una directiva de colección de sitios, puede exportarla para que los administradores de otras colecciones de sitios puedan importarla en su lista de directivas. La creación de una directiva de recopilación de sitios exportable le permite estandarizar las directivas de administración de información en los sitios de su organización. 
  
Al agregar una directiva de colección de sitios a un tipo de contenido de sitio y se agrega una instancia de ese tipo de contenido de sitio a una lista o biblioteca, el propietario de esa lista o biblioteca no puede modificar la directiva de colección de sitios para la lista o biblioteca. Agregar una directiva de colección de sitios a un tipo de contenido de sitio es una buena manera de asegurarse de que las directivas de colección de sitios se aplican en cada nivel de la jerarquía de sitios.
  
![Vínculo a la plantilla de directiva de tipo de contenido en la página Configuración del sitio.](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Cree una directiva de administración de información para un tipo de contenido de sitio en la Galería de tipos de contenido de sitio del sitio de nivel superior y, a continuación, agregue ese tipo de contenido a una o varias listas o bibliotecas.** También puede crear una directiva de administración de información directamente para un tipo de contenido de sitio y, a continuación, asociar una instancia de ese tipo de contenido de sitio a varias listas o bibliotecas. Si crea una directiva de administración de información de esta manera, todos los elementos de la colección de sitios de ese tipo de contenido o un tipo de contenido que hereda de ese tipo de contenido tienen la directiva. Sin embargo, si crea una directiva de administración de información directamente para un tipo de contenido de sitio, es más difícil reutilizar esta directiva de administración de información en otras colecciones de sitios, ya que las directivas creadas de esta manera no se pueden exportar. 
  
![Vínculo tipos de contenido de sitio en la página Configuración del sitio.](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Vínculo de directiva de administración de información en la página de configuración de un tipo de contenido de sitio.](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Nota Para controlar qué directivas se usan en una colección de sitios, los administradores de colecciones de sitios pueden deshabilitar la capacidad de establecer características de directiva directamente en un tipo de contenido. Cuando esta restricción está en vigor, los usuarios que crean tipos de contenido se limitan a seleccionar directivas en la lista Directivas de colección de sitios.
  
 **Creación de una directiva de administración de información para una lista o biblioteca** Si su organización necesita aplicar una directiva de administración de información específica a un conjunto muy limitado de contenido, puede crear una directiva de administración de información que se aplique solo a una lista o biblioteca individuales. Este método de creación de una directiva de administración de información es el menos flexible, ya que la directiva solo se aplica a una ubicación y no se puede exportar ni reutilizar para otras ubicaciones. Sin embargo, a veces es posible que necesite crear directivas de administración de información únicas con una aplicabilidad limitada para abordar situaciones específicas. 
  
![Vínculo directivas de administración de información en la página de configuración de la biblioteca de documentos.](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Notas 
  
Puede crear una directiva de administración de información para una lista o biblioteca solo si esa lista o biblioteca no admite varios tipos de contenido. Si una lista o biblioteca admite varios tipos de contenido, debe definir una directiva de administración de información para cada tipo de contenido de lista individual asociado a esa lista o biblioteca. (Las instancias de un tipo de contenido de sitio que están asociadas a una lista o biblioteca específica se conocen como tipos de contenido de lista).
  
Para controlar qué directivas se usan en una colección de sitios, los administradores de colecciones de sitios pueden deshabilitar la capacidad de establecer características de directiva directamente en una lista o biblioteca. Cuando esta restricción está en vigor, los usuarios que administran listas o bibliotecas se limitan a seleccionar directivas de la lista Directivas de colección de sitios.
  
[Una directiva de administración de información es un conjunto de reglas para un tipo de contenido. Las directivas de administración de la información permiten a las organizaciones controlar y realizar un seguimiento de cosas como cuánto tiempo se conserva el contenido o qué acciones pueden realizar los usuarios con ese contenido. Las directivas de administración de la información pueden ayudar a las organizaciones a cumplir con las regulaciones legales o gubernamentales, o simplemente pueden aplicar procesos empresariales internos. Por ejemplo, una organización que debe seguir las regulaciones gubernamentales que requieren que demuestren "controles adecuados" de sus estados financieros podría crear una o más directivas de administración de información que auditen acciones específicas en el proceso de creación y aprobación de todos los documentos relacionados con las presentaciones financieras. Para obtener información detallada, consulte Creación y aplicación de directivas de administración de información.](intro-to-info-mgmt-policies.md#__top)
  

