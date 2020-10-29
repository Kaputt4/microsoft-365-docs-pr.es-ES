---
title: Puntuación de productividad de Microsoft
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ROBOTS: NOINDEX, NOFOLLOW
description: Información general sobre la puntuación de productividad de Microsoft.
ms.openlocfilehash: 3d014cd0eb3a3ceed3b3f3b48f126453e4ced193
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794970"
---
# <a name="microsoft-productivity-score"></a>Puntuación de productividad de Microsoft 

La puntuación de productividad ayuda a las organizaciones a transformar cómo se realiza el trabajo con información sobre cómo los usuarios usan Microsoft 365 y las experiencias tecnológicas que los admiten. La puntuación refleja el rendimiento de su organización con respecto a los usuarios y a las experiencias tecnológicas, y compara su puntuación con organizaciones como la suya.

La puntuación incluye:

- **Métricas** que le ayudarán a ver cómo los usuarios usan productos de 365 de Microsoft para colaborar, comunicarse y trabajar en todas las plataformas.
- **Información acerca de** los datos para ayudarle a identificar las oportunidades para mejorar la productividad y la satisfacción de los empleados.
- **Acciones recomendadas** que puede llevar a cabo para ayudar a las personas de su organización a usar los productos de Microsoft 365 de forma eficaz para que todos los usuarios puedan realizar su mejor trabajo.

Proporcionamos datos, información y recomendaciones en dos áreas: 

- **Experiencias de personas:** Mide cómo colaboran los usuarios en el contenido, cómo usan los productos de 365 de Microsoft para comunicarse y si usan Microsoft 365 en varias plataformas. 

    Proporcionamos esta información porque cuando los usuarios colaboran en línea, ahorran tiempo y, con la libertad de trabajar en cualquier dispositivo, su productividad es más productiva y satisfactoria. La capacidad de comunicarse de una manera flexible hace que los usuarios sean más eficientes, capaces de formar mejores relaciones, por lo que su organización es más unificada. Para obtener evidencia, consulte [Forrester Report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

- **Experiencias tecnológicas:** La productividad depende de una tecnología fiable y con buen rendimiento, así como del uso eficaz de Microsoft 365. Proporcionamos [análisis de extremos](https://aka.ms/endpointanalytics), que le ayuda a comprender cómo la productividad de los usuarios puede verse afectada por problemas de rendimiento y estado con el hardware y software de extremo. También proporcionamos acciones recomendadas para corregirlos, así como la información de conectividad de red de Microsoft 365 para su organización.

Consulte [What is Endpoint Analytics](https://docs.microsoft.com/mem/analytics/overview) para obtener información general y requisitos previos. Para obtener más información acerca de la información de conectividad de red 365 de Microsoft, lea [la introducción a la conectividad de red](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview).
  

## <a name="how-the-score-is-calculated"></a>Cómo se calcula la puntuación

La puntuación de productividad se basa en los resultados combinados de las categorías de personas y experiencias tecnológicas. Cada categoría se pondera equitativamente, con un total de 100 puntos. La mayor puntuación de productividad posible es de 500.

### <a name="score-categories"></a>Categorías de puntuación 

- Colaboración de contenido (100 puntos)
- Comunicación (100 puntos)
- Mobility (100 puntos)
- Análisis de extremos (100 puntos)
- Conectividad de red (100 puntos)
- **Total posible = 500 puntos**
 
 En cada categoría, identificamos patrones para actividades clave que son indicadores sobre cómo los usuarios usan los productos de 365 de Microsoft para colaborar, comunicarse y trabajar en todas las plataformas. Proporcionamos vistas de las actividades clave de 28 días y 180 días. También proporcionamos métricas auxiliares que no forman parte del cálculo de la puntuación, pero son importantes para ayudarle a identificar los comportamientos y configuraciones subyacentes en los que puede actuar.

### <a name="products-included-in-productivity-score"></a>Productos incluidos en la puntuación de productividad 

La puntuación de productividad incluye datos de Exchange, SharePoint, OneDrive, Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer y Skype.

La puntuación se actualiza diariamente y refleja las acciones del usuario completadas en el último 28 (incluido el día actual).


## <a name="pre-requisites"></a>Requisitos previos 

Para que los usuarios experimenten datos, necesita una suscripción de Microsoft 365 para empresas o Office 365 para empresas, y necesita usar los servicios en la nube multiinquilino. Para obtener datos de análisis de extremos para el espacio empresarial, debe agregar Microsoft Intune a su suscripción. Intune le ayuda a proteger los datos de su organización mediante la administración de dispositivos y aplicaciones.       Una vez que tenga Intune, puede activar el análisis de extremo en la experiencia de Intune. Obtenga más información sobre Microsoft Intune. 

Para ver la puntuación de productividad de su organización, debe tener uno de los siguientes roles: 

- Administrador global 
- Administradores de Exchange
- Administrador de SharePoint 
- Administrador de Skype Empresarial 
- Administrador de Teams 
- Lector global 
- Lector de informes 

Puede tener acceso a la experiencia desde la Página principal de administración de Microsoft 365 en **Reports**  >  **score score** .

## <a name="interpreting-productivity-score"></a>Interpretación de la puntuación de productividad 

La página de inicio de la puntuación de productividad muestra el historial de puntuación y la puntuación totales y la información principal de cada categoría.

![Página principal de puntuación de productividad](../../media/pslanding.png)

**La puntuación** se muestra como un valor porcentual y en puntos. Puede ver los puntos en el numerador y los puntos máximos posibles en el denominador.

Las pruebas comparativas **del mismo nivel** le permiten comparar su puntuación con organizaciones como la suya. Para las categorías de experiencias de personas, la medida de Benchmark del mismo nivel se calcula como el promedio de medidas dentro de un conjunto de organizaciones similares. El conjunto está compuesto por organizaciones en su región con un número similar de usuarios con licencia, tipos de licencias, industria y permanencia con Microsoft 365. 

El punto de referencia del punto de conexión del análisis de extremos incluye objetivos para el rendimiento de inicio de dispositivo y la configuración de software recomendada en función de los valores de la mediana agregada en todos los inquilinos.

Para la conectividad de red, el benchmark recomendado es de 80 puntos.

La sección de **desglose de puntuación** proporciona un desglose de la puntuación de productividad con los benchmarks de las personas y las áreas de experiencia de tecnología.

Historial de puntuación muestra cómo ha cambiado su puntuación en cada categoría en los últimos 6 meses.

Las áreas experiencias de las **personas** y **experiencias tecnológicas** contienen la visión principal de las categorías de esas áreas. Puede hacer clic en cada categoría para ver información más detallada.

## <a name="category-details-pages"></a>Páginas de detalles de categoría

En cada página de detalles de categoría se muestran las métricas principales de conocimiento y apoyo, así como la investigación y las acciones relacionadas que puede realizar para impulsar el cambio en su organización. La investigación apoya la importancia y la lógica que hay tras la información principal de cada categoría. para obtener más información, [Lea el informe de Forrester](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

Las páginas de detalles son:
- [Colaboración de contenido: experiencias de personas](content-collaboration.md)
- [Comunicación: experiencias de personas](communication.md)
- [Reuniones: experiencias de personas](meetings.md)
- [Movilidad: experiencias de personas](mobility.md)
- [Trabajo en equipo: experiencias de personas](teamwork.md)
- [Experiencias de tecnología de Microsoft 365, estado de las aplicaciones](apps-health.md)

## <a name="business-continuity-special-report"></a>Informe especial de continuidad del negocio

El informe de continuidad empresarial es un informe de inteligencia de trabajo limitado disponible para todos los clientes de Microsoft 365 para ayudarles a guiar a sus organizaciones durante este difícil tiempo.  

Este informe ayuda a los líderes de negocios a comprender: 

- Modo en que la colaboración y la comunicación se ven afectadas por el cambio al trabajo remoto. 

- El impacto en el saldo de la vida laboral mientras los usuarios se ajustan a trabajar desde casa. 

- Si las reuniones remotas admiten la toma de decisiones efectiva.

[Obtenga más información sobre el informe de continuidad empresarial](https://aka.ms/bcrps)

[Más información sobre Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Comparta sus ideas sobre la puntuación de productividad y sus ideas sobre cómo mejorarla. Use las secciones de **comentarios** del producto y/o póngase en contacto con el equipo de puntuación de productividad en ProductivityScorePreview@service.microsoft.com.
