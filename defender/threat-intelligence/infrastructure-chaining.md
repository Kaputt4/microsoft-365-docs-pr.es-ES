---
title: 'Inteligencia contra amenazas de Microsoft Defender (Ti de Defender): Encadenamiento de infraestructura'
description: En este artículo de concepto, obtenga información sobre el encadenamiento de infraestructura y cómo puede aplicar ese proceso para realizar análisis de infraestructura de amenazas mediante Inteligencia contra amenazas de Microsoft Defender (TI de Defender).
author: alexroland24
ms.author: aroland
manager: dolmont
ms.service: threat-intelligence
ms.topic: conceptual
ms.date: 08/02/2022
ms.custom: template-concept
ms.openlocfilehash: 2f2187b2b49e41bf9751be46fab771f66b601995
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67737156"
---
# <a name="infrastructure-chaining"></a>Encadenamiento de infraestructura

El encadenamiento de infraestructura aprovecha las relaciones entre conjuntos de datos altamente conectados para crear una investigación. Este proceso es el núcleo del análisis de la infraestructura de amenazas y permite a las organizaciones exponer nuevas conexiones, agrupar actividades de ataque similares y fundamentar suposiciones durante la respuesta a incidentes.

![Encadenamiento de infraestructura](media/infrastructureChaining.png)

## <a name="prerequisites"></a>Requisitos previos

1. Artículo de [información general sobre conjuntos de datos de Inteligencia contra amenazas de Microsoft Defender (TI de Defender)](data-sets.md)
2. Revisar el artículo de procedimientos de [búsqueda y dinamización de Inteligencia contra amenazas de Microsoft Defender (TI de Defender)](searching-and-pivoting.md)

## <a name="all-you-need-is-a-starting-point"></a>Todo lo que necesita es un punto de partida...

Vemos que las campañas de ataque emplean una amplia gama de técnicas de ofuscación, como el filtrado geográfico simple a tácticas complejas, como la huella digital pasiva del sistema operativo. Esto puede detener potencialmente una investigación a un momento dado en sus pistas. En la captura de pantalla anterior se resalta el concepto de encadenamiento de infraestructura. Con nuestra funcionalidad de enriquecimiento de datos, podríamos empezar con un fragmento de malware que intenta conectarse a una dirección IP (posiblemente un C2). Esa dirección IP puede haber hospedado un certificado SSL que tenga un nombre común, como un nombre de dominio. Ese dominio puede estar conectado a una página que contiene un seguimiento único en el código, como NewRelicID o algún otro identificador analítico que hayamos observado en otro lugar. O bien, tal vez el dominio haya estado históricamente conectado a otra infraestructura que pueda aclarar nuestra investigación. La principal ventaja es que un punto de datos fuera de contexto puede no ser especialmente útil, pero cuando observamos la conexión natural con todos estos otros datos técnicos, podemos empezar a unir una historia.

## <a name="an-adversarys-outside-in-perspective"></a>Perspectiva externa de un adversario

La perspectiva externa de un adversario les permite aprovechar su presencia móvil y web en continua expansión que funciona fuera del firewall.

Aproximarse e interactuar con las propiedades web y móviles como un usuario real permite que la tecnología de rastreo, examen y aprendizaje automático de Microsoft desarme las técnicas de evasión de adversarios mediante la recopilación de datos de sesión de usuario, la detección de phishing, malware, aplicaciones no autorizadas, contenido no deseado e infracción de dominio a escala. Esto ayuda a ofrecer flujos de trabajo y alertas de amenazas accionables basadas en eventos en forma de [inteligencia sobre amenazas](index.md), [etiquetas del sistema](using-tags.md), [información de analistas](analyst-insights.md) y [puntuaciones de reputación asociadas](reputation-scoring.md) a la infraestructura de adversarios.

A medida que hay más datos de amenazas disponibles, se requieren más herramientas, educación y esfuerzo para que los analistas comprendan los conjuntos de datos y sus amenazas correspondientes. Inteligencia contra amenazas de Microsoft Defender (Ti de Defender) unifica estos esfuerzos proporcionando una vista única en varios orígenes de datos.

## <a name="next-steps"></a>Pasos siguientes
Para obtener más información, consulte [Tutorial: Recopilación de inteligencia sobre amenazas y encadenamiento de infraestructura](gathering-threat-intelligence-and-infrastructure-chaining.md).
