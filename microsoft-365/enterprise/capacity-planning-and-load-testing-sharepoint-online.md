---
title: Planeamiento de capacidad y pruebas de carga en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: En este artículo se describe cómo se puede implementar en SharePoint Online sin realizar pruebas de carga tradicionales, ya que no se permite.
ms.openlocfilehash: 1d1714bbcdefdbc41ff3ac5d038c6b59a7043a26
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65101103"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Planeamiento de capacidad y pruebas de carga en SharePoint Online
En este artículo se describe cómo puede implementar en SharePoint Online sin pruebas de carga tradicionales, ya que las pruebas de carga no se permiten en SharePoint Online. SharePoint Online es un servicio en la nube y Microsoft administra las funcionalidades de carga, el estado y el equilibrio general de carga en el servicio.
  
El mejor enfoque para garantizar el éxito del inicio del sitio es seguir los principios básicos, las prácticas y las recomendaciones que se resaltan en el [plan de lanzamiento del portal](planportallaunchroll-out.md).

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Información general sobre cómo SharePoint Online realiza el planeamiento de la capacidad 
Una de las principales ventajas de SharePoint Online en una implementación local es la elasticidad de la nube y las optimizaciones para los usuarios de regiones distribuidas. Nuestro entorno a gran escala está configurado para atender a millones de usuarios diariamente, por lo que es importante controlar la capacidad de forma eficaz mediante el equilibrio y la expansión de granjas.
  
Aunque el crecimiento suele ser imprevisible para cualquier inquilino de una granja de servidores, la suma agregada de solicitudes es predecible con el tiempo. Al identificar las tendencias de crecimiento en SharePoint Online, podemos planear una expansión futura.
  
Con el fin de usar de forma eficaz la capacidad y hacer frente a un crecimiento inesperado, en cualquier granja de servidores, tenemos automatización que realiza un seguimiento y supervisa varios elementos del servicio. Se usan varias métricas, una de las principales es la carga de CPU, que se usa como señal para escalar verticalmente los servidores front-end. Además, se recomienda un [enfoque por fases o ola](planportallaunchroll-out.md), ya que SQL entornos se escalarán según la carga y el crecimiento a lo largo del tiempo, y seguir las fases y ondas permite la distribución correcta de esa carga y crecimiento. 

La capacidad es más que simplemente agregar más hardware de forma continua, pero también se refiere a la administración y control de esa capacidad para asegurarse de que está dando servicio a solicitudes de carga válidas. Se recomienda que los clientes sigan las instrucciones recomendadas para asegurarse de que tienen la mejor experiencia. También significa que tenemos patrones de limitación y controles implementados para garantizar que no se permite un comportamiento "abusivo" en el servicio. Aunque no todo el comportamiento "malo" es intencionado, tenemos que asegurarnos de limitar el efecto de ese comportamiento. Para obtener más información sobre la limitación y cómo evitarla, consulte el artículo [sobre cómo evitar que se limiten las instrucciones](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) .

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Por qué no puede cargar la prueba SharePoint Online
Con entornos locales, las pruebas de carga se usan para validar la suposición de escalado y, en última instancia, encontrar el punto de interrupción de una granja de servidores; saturando con carga. 

Con SharePoint Online, tenemos que hacer las cosas de manera diferente porque la escala es relativamente fluida y ajusta, limita y controla la carga, en función de cierta heurística. Al ser un entorno multiinquilino a gran escala, debemos proteger todos los inquilinos de la misma granja, por lo que limitaremos automáticamente las pruebas de carga. Sin embargo, si intenta cargar la prueba, además de limitarse, recibirá resultados decepcionantes y potencialmente engañosos porque la granja de servidores que ha probado hoy probablemente habrá tenido cambios de escala durante la ventana de pruebas o en las horas posteriores a la prueba, ya que las acciones de equilibrio de escala y granja de servidores se realizan de forma continua.

En lugar de intentar cargar la prueba SharePoint como servicio, céntrese en seguir los procedimientos recomendados y siga las instrucciones [de Creación, inicio y mantenimiento de un portal en buen estado](/sharepoint/portal-health).