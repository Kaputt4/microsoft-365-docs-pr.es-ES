---
title: Aislamiento de inquilinos de Microsoft 365 en Microsoft Graph y Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: En este artículo, busque una explicación de cómo funciona el aislamiento de inquilinos de Microsoft 365 en Office Graph y en Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332393"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Aislamiento de inquilinos de Microsoft 365 en Microsoft Graph y Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Aislamiento de inquilinos en Microsoft Graph

Microsoft [Graph](https://developer.microsoft.com/graph) modela la actividad en los servicios de Microsoft 365, incluidos Exchange Online, SharePoint Online, Yammer, Skype Empresarial, Azure Active Directory, etc., y en servicios externos, como otros servicios microsoft o servicios de terceros. Los componentes de Microsoft Graph se usan en Microsoft 365. Microsoft Graph representa una colección de contenido y actividad, y las relaciones entre ellos que se suceden en todo el conjunto de aplicaciones de Office. Usa técnicas sofisticadas de aprendizaje automático para conectar a las personas con el contenido relevante, las conversaciones y las personas a su alrededor. Por ejemplo, el índice de inquilino de SharePoint Online tiene un índice de Microsoft Graph que se usa para atender consultas de Delve, el motor de procesamiento de análisis en SharePoint Online se usa para almacenar señales y calcular información, y Exchange Online calcula la memoria caché de destinatarios de cada usuario como entrada en el análisis de inquilinos.

Microsoft Graph contiene información sobre objetos de empresa, como personas y documentos, así como las relaciones e interacciones entre estos objetos. Las relaciones y las interacciones se representan como *bordes*. Microsoft Graph se segmenta por inquilino de modo que los bordes solo pueden existir entre *nodos* en el mismo inquilino. Un *nodo* es una entidad con un identificador uniforme de recursos (URI), un tipo de nodo, una lista de control de acceso y un conjunto de facetas que contienen *metadatos* y bordes. Cada nodo tiene metadatos y bordes *asociados, organizados* en facetas como en el modelo de conocimiento común. *Los* metadatos son propiedades con nombre almacenadas en un nodo que se pueden usar para buscar, filtrar o analizar en Microsoft Graph. Una *faceta* es una colección lógica de metadatos y bordes en un nodo. Cada faceta describe un aspecto de un nodo. 

Microsoft Graph no incluye todos los datos en un único repositorio; en su lugar, almacena metadatos y relaciones sobre datos que viven en otro lugar. Microsoft Graph consta de varios almacenes de datos y componentes de procesamiento:

- El Almacén de gráficos de inquilinos proporciona almacenamiento en masa optimizado para un análisis eficaz.
- La caché de contenido activa proporciona acceso aleatorio rápido al nodo activo y a los bordes para impulsar las experiencias del usuario.
- El enrutador de entrada notifica a los componentes internos y externos de los cambios en el gráfico del espacio empresarial.

Los análisis de cada carga de trabajo deducen información relevante para los cálculos de todo el espacio empresarial y las insertan en el gráfico del espacio empresarial. Motivos de análisis de inquilinos sobre toda la actividad en un arrendamiento para producir información sobre patrones de comportamiento. Por ejemplo, Exchange Online calcula la memoria caché de destinatarios para cada usuario con análisis que razón eficiente sobre el buzón de cada usuario. Estos análisis por usuario producen un conjunto de *bordes recipientCache* en cada persona, que a su vez se insertan en el gráfico de inquilinos. Esto mantiene la mayor parte del procesamiento de análisis lo más cerca posible de los datos de origen.

## <a name="tenant-isolation-in-delve"></a>Aislamiento de inquilinos en Delve

Como se mencionó anteriormente, Microsoft Graph ofrece experiencias que ayudan a los usuarios a descubrir y colaborar en las actividades actuales de su empresa, y proporciona una plataforma centrada en la entidad para que el análisis se descarte sobre el contenido y la actividad en cargas de trabajo y más allá de Microsoft 365. Delve es la primera experiencia de este tipo con tecnología de Microsoft Graph.
Delve es una experiencia web de Microsoft 365 que muestra contenido de Microsoft 365 y Yammer Enterprise a los usuarios de Microsoft 365 a través de Microsoft Graph. La experiencia web muestra datos como paneles diferentes, cada uno con un tema determinado, como Tendencias a mi alrededor *o* Modificado *por mí.* Cada panel consta de varias tarjetas de documento que muestran texto de resumen y una imagen del documento. La tarjeta permite a los usuarios hacer cosas como abrir el documento o una página de Yammer para el documento. Hay una página para cada persona en un inquilino de Microsoft 365 que muestra los documentos más relevantes para esta persona y los iconos que pueden invocar Exchange Online o Skype Empresarial para interactuar con esa persona. Dado que Delve se basa en la API de Microsoft Graph, está enlazada por el aislamiento basado en inquilinos de esa API.