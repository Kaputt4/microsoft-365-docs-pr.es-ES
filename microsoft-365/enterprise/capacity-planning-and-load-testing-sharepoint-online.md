---
title: Planeamiento de capacidad y pruebas de carga en SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: En este artículo se describe cómo implementar en SharePoint Online sin realizar pruebas de carga tradicionales, ya que no está permitido.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905229"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Planeamiento de capacidad y pruebas de carga en SharePoint Online
En este artículo se describe cómo implementar en SharePoint Online sin pruebas de carga tradicionales, ya que las pruebas de carga no están permitidas en SharePoint Online. SharePoint Online es un servicio en la nube y Microsoft administra las capacidades de carga, el estado y el equilibrio general de carga en el servicio.
  
El mejor enfoque para garantizar el éxito del inicio del sitio es seguir los principios, prácticas y recomendaciones básicos que se destacan en el plan de lanzamiento del [portal.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Información general sobre cómo SharePoint Online realiza la planeación de capacidad 
Una de las principales ventajas de SharePoint Online en una implementación local es la elasticidad de la nube, así como las optimizaciones para los usuarios de las regiones distribuidas. Nuestro entorno a gran escala está configurado para dar servicio a millones de usuarios diariamente, por lo que es importante que controlemos la capacidad de forma eficaz equilibrando y expandiendo granjas de servidores.
  
Aunque el crecimiento suele ser impredecible para cualquier inquilino de una granja de servidores, la suma agregada de solicitudes es predecible con el tiempo. Al identificar las tendencias de crecimiento en SharePoint Online, podemos planear la expansión futura.
  
Con el fin de usar eficazmente la capacidad y hacer frente a un crecimiento inesperado, en cualquier granja de servidores, tenemos automatización que realiza un seguimiento y supervisa varios elementos del servicio. Se usan varias métricas, siendo una de las principales la carga de CPU, que se usa como señal para escalar los servidores front-end verticales. Además, se recomienda un enfoque por fases o de [onda,](planportallaunchroll-out.md)ya que los entornos de SQL se escalarán según la carga y el crecimiento con el tiempo, y seguir las fases y las ondas permite la distribución correcta de esa carga y crecimiento. 

La capacidad es más que simplemente agregar más hardware de forma continua, pero también se refiere a administrar y controlar esa capacidad para garantizar que está dando servicio a solicitudes de carga válidas. Se recomienda que los clientes sigan las instrucciones recomendadas para asegurarse de que tienen la mejor experiencia. También significa que tenemos patrones de limitación y controles para garantizar que no se permita un comportamiento "abusivo" en el servicio. Aunque no todo el comportamiento "malo" es intencionado, tenemos que asegurarnos de limitar el efecto de ese comportamiento. Para obtener más información sobre la limitación y cómo evitarla, revise el artículo sobre cómo evitar que se [limite la](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) limitación.

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Por qué no puede cargar pruebas de SharePoint Online
Con entornos locales, las pruebas de carga se usan para validar la suposición de escala y, en última instancia, encontrar el punto de separación de una granja de servidores; saturando con carga. 

Con SharePoint Online debemos hacer las cosas de forma diferente porque la escala es relativamente fluida y se ajusta, se cargan los aceleradores y los controles, en función de cierta heurística. Al ser un entorno multiinquilino a gran escala, debemos proteger todos los inquilinos de la misma granja de servidores, por lo que limitaremos automáticamente las pruebas de carga. Sin embargo, si intenta cargar la prueba, además de limitarse, recibirá resultados desalentadores y potencialmente engañosos, ya que la granja de servidores que ha probado hoy probablemente habrá tenido cambios de escala durante la ventana de prueba o en las horas adicionales a las pruebas, ya que las acciones de equilibrio de escala y granja de servidores se realizan de forma continua.

En lugar de intentar cargar SharePoint como servicio de prueba, en lugar de centrarse en seguir los procedimientos recomendados y seguir las instrucciones para [crear,](/sharepoint/portal-health) iniciar y mantener un portal en buen estado.