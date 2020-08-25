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
ms.openlocfilehash: 66ab028282fb8c74087713083e43e22cf6708897
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868860"
---
# <a name="microsoft-productivity-score-preview"></a>Puntuación de productividad de Microsoft (versión preliminar)

La puntuación de productividad ayuda a las organizaciones a transformar cómo se realiza el trabajo con información sobre cómo los usuarios usan Microsoft 365 y las experiencias tecnológicas que los admiten. La puntuación refleja el rendimiento de su organización con respecto a las medidas de experiencia de empleado y tecnología, y compara su puntuación con organizaciones como la suya.

La puntuación incluye:

- **Métricas** que le ayudarán a ver cómo los usuarios usan productos de 365 de Microsoft para colaborar, comunicarse y trabajar en todas las plataformas.
- **Información acerca de** los datos para ayudarle a identificar las oportunidades para mejorar la productividad y la satisfacción de los empleados.
- **Acciones recomendadas** que puede llevar a cabo para ayudar a las personas de su organización a usar los productos de Microsoft 365 de forma eficaz para que todos los usuarios puedan realizar su mejor trabajo.

Proporcionamos datos, información y recomendaciones en dos áreas: 

- **Experiencia de los empleados:** Medimos cómo los usuarios colaboran en el contenido, cómo usan los productos de 365 de Microsoft para comunicarse y si usan Microsoft 365 en todas las plataformas. 

    Proporcionamos esta información porque cuando los usuarios colaboran en línea, ahorran tiempo. Cuando tienen libertad para trabajar en cualquier dispositivo, son más productivos y están satisfechos. Cuando se pueden comunicar de forma flexible, son más eficientes, forman mejores relaciones y la organización es más unificada. Para obtener evidencia, consulte [Forrester Report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

- **Experiencia tecnológica:** La productividad depende de una tecnología fiable y de rendimiento, así como del uso eficaz de Microsoft 365. Proporcionamos [análisis de extremos](https://aka.ms/endpointanalytics), que ayuda a comprender cómo la productividad de los usuarios puede verse afectada por problemas de rendimiento y estado con el hardware y software de extremo, a la vez que proporcionan acciones recomendadas para solucionarlos; Además, proporcionamos información de conectividad de red de Microsoft 365 para su organización.

Consulte [What is Endpoint Analytics](https://docs.microsoft.com/mem/analytics/overview) para obtener información general y requisitos previos. Para obtener más información acerca de la información de conectividad de red 365 de Microsoft, lea [la introducción a la conectividad de red](https://docs.microsoft.com/office365/enterprise/office-365-networking-overview).
  

## <a name="how-the-score-is-calculated"></a>Cómo se calcula la puntuación

La puntuación de productividad se basa en los resultados combinados de las categorías de empleado y experiencia tecnológica. Cada categoría se pondera equitativamente, con un total de 100 puntos por categoría. El total de puntos posibles para la puntuación de productividad es de 500.

### <a name="score-categories"></a>Categorías de puntuación 

- Colaboración de contenido (100 puntos)
- Comunicación (100 puntos)
- Mobility (100 puntos)
- Análisis de extremos (100 puntos)
- Conectividad de red (100 puntos)
- **Total posible = 500 puntos**
 
 En cada categoría, identificamos patrones para actividades clave que son indicadores sobre cómo los usuarios usan los productos de 365 de Microsoft para colaborar, comunicarse y trabajar en todas las plataformas. Proporcionamos vistas de las actividades clave de 28 días y 180 días. También proporcionamos métricas auxiliares que no forman parte del cálculo de la puntuación, pero son importantes para ayudarle a identificar los comportamientos subyacentes y las opciones de configuración en las que puede actuar para impulsar el cambio.

### <a name="products-included-in-productivity-score"></a>Productos incluidos en la puntuación de productividad 

La puntuación de productividad incluye datos de Exchange, SharePoint, OneDrive, Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer y Skype.

La puntuación se actualiza diariamente y refleja las acciones del usuario realizadas en los últimos 28 a 180 días (incluido el día actual).


## <a name="pre-requisites"></a>Requisitos previos 

Necesita una suscripción a Microsoft 365 para empresas o Office 365 para empresas para obtener los datos de experiencia de los empleados y necesita usar servicios en la nube multiinquilino. Para obtener datos de análisis de extremos para el espacio empresarial, debe agregar Microsoft Intune a su suscripción. Intune le ayuda a proteger los datos de su organización mediante la administración de dispositivos y aplicaciones.       Una vez que tenga Intune, puede activar el análisis de extremo en la experiencia de Intune. Obtenga más información sobre Microsoft Intune. 

Para ver la puntuación de productividad de su organización, debe tener uno de los siguientes roles: 

- Administrador global 
- Administradores de Exchange
- Administrador de SharePoint 
- Administrador de Skype Empresarial 
- Administrador de Teams 
- Lector global 
- Lector de informes 

Puede tener acceso a la experiencia desde la Página principal de administración de Microsoft 365 en **Reports**  >  **score score**.

## <a name="interpreting-productivity-score"></a>Interpretación de la puntuación de productividad 

La página de inicio de la puntuación de productividad muestra la puntuación total y el historial de puntuación, así como la información principal de cada categoría.

![Página principal de puntuación de productividad](../../media/pslanding.png)

**La puntuación** se muestra como un valor porcentual, así como en puntos, de modo que puede ver los puntos (Numerator) y los puntos máximos posibles (denominador).

Las pruebas comparativas **del mismo nivel** le permiten comparar su puntuación con organizaciones como la suya. Para las categorías de experiencia de empleado, la medida de Benchmark del mismo nivel se calcula como el promedio de medidas dentro de un conjunto de organizaciones similares. El conjunto está compuesto por organizaciones en su región con un número similar de usuarios con licencia, tipos de licencias, industria y permanencia con Microsoft 365. 

El punto de referencia del punto de conexión del análisis de extremos incluye objetivos para el rendimiento de inicio de dispositivo y la configuración de software recomendada en función de los valores de la mediana agregada en todos los inquilinos.

Para la conectividad de red, el benchmark recomendado es de 80 puntos.

La sección de **desglose de puntuación** proporciona un desglose de la puntuación de productividad con puntos de referencia de las áreas de experiencia de empleados y tecnología.

Historial de puntuación muestra cómo ha cambiado su puntuación en cada categoría en los últimos 6 meses.

Las áreas experiencia de los **empleados** y **experiencia de tecnología** contienen la visión principal de las categorías de esas áreas. Puede hacer clic en cada categoría para ver información más detallada.

## <a name="category-details-pages"></a>Páginas de detalles de categoría

En cada página de detalles de categoría se muestran las métricas principales de conocimiento y apoyo, así como la investigación y las acciones relacionadas que puede realizar para impulsar el cambio en su organización. La investigación apoya la importancia y la lógica que hay tras la información principal de cada categoría. para obtener más información, [Lea el informe de Forrester](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

### <a name="content-collaboration-details"></a>Detalles de colaboración de contenido

La información principal sobre la colaboración de contenido es el número de personas que crean, leen y colaboran (editar y compartir) en línea. Estas medidas son importantes porque la investigación muestra que cuando los usuarios colaboran con archivos en línea, cada persona ahorra un promedio de 100 minutos, o casi 2 horas, por semana.

La colaboración de contenido se define como una persona que crea y comparte un archivo de Office y, a continuación, al menos otra persona editando. 

Lectores: personas que acceden o descargan archivos en línea en OneDrive o SharePoint.

**Creadores:** Personas que crean, modifican, cargan, sincronizan, protegen, copian o mueven archivos de OneDrive o de SharePoint en línea.

Colaboradores: personas que colaboran con archivos en línea con OneDrive o SharePoint. Dos personas son colaboradores si una de ellas lee o edita un documento en línea de Word, Excel, PowerPoint, OneNote o PDF en la nube después de que la otra persona lo cree o modifique, en un período de 28 días.

Los tipos de archivo considerados para la colaboración son archivos de Word, Excel, PowerPoint, OneNote y PDF.

Proporcionamos información sobre las horas de inicio y configuramos para dispositivos de su organización, así como información sobre conectividad de red para la colaboración de contenido porque la colaboración de archivos en línea requiere dispositivos confiables que se inician rápidamente y tienen software actualizado, así como una buena conectividad a Microsoft 365.

### <a name="communication-details"></a>Detalles de comunicación

La información principal sobre comunicación es la frecuencia con la que los usuarios de la organización usan el correo electrónico, el chat y las publicaciones de la comunidad para comunicarse. Esta información es importante porque cuando los usuarios usan una variedad de herramientas de comunicación en tiempo real, pueden elegir el modo de comunicación que les ayude a ser más eficientes y tienen herramientas como chat y comunidades que les ayudan a desarrollar relaciones entre las oficinas.

### <a name="mobility-details"></a>Detalles de movilidad

La información principal sobre movilidad es el número de personas que tienen acceso a los archivos y usan el correo electrónico y el chat en varias plataformas. La capacidad de trabajar desde cualquier ubicación en cualquier dispositivo que elija es importante para los usuarios con roles de ventas, directores Senior, asesores y otros usuarios que necesiten trabajar fuera de la oficina para ser productivos. Las mejoras para estos trabajadores tienen un gran impacto. 

Medimos el porcentaje y el número absoluto de personas que usaban al menos una aplicación de productividad de Microsoft 365 en dos o más plataformas, entre las que se incluye escritorio, móvil y Web. Las aplicaciones de productividad que medimos son Outlook, Teams, Word, Excel, PowerPoint, OneNote, Yammer y Skype. Los usuarios deben tener licencias de Microsoft 365 apps for Enterprise, Exchange, Yammer, Skype o teams que se medirán. 

## <a name="business-continuity-special-report"></a>Informe especial de continuidad del negocio

El informe de continuidad empresarial es un informe de inteligencia de trabajo limitado disponible para todos los clientes de Microsoft 365 para ayudarles a guiar a sus organizaciones durante este difícil tiempo.  

Este informe ayuda a los líderes de negocios a comprender: 

- Cómo la colaboración y la comunicación se ven afectadas por el cambio a la tarea remota. 

- El impacto en el saldo de la vida laboral mientras los usuarios se ajustan a trabajar desde casa. 

- Si las reuniones remotas admiten la toma de decisiones efectiva.

[Obtenga más información sobre el informe de continuidad empresarial](https://aka.ms/bcrps)

[Más información sobre Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>Queremos conocer su opinión

Comparta sus ideas sobre la puntuación de productividad y sus ideas sobre cómo mejorarla. Use las secciones de **comentarios** del producto y/o póngase en contacto con el equipo de puntuación de productividad en ProductivityScorePreview@service.microsoft.com.
