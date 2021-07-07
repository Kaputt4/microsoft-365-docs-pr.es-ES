---
title: Ejecutar una versión de prueba de Temas de Microsoft Viva
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Obtenga información sobre cómo planear y ejecutar un programa piloto de prueba para temas de Microsoft Viva en su organización.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327146"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>Ejecutar una versión de prueba de Temas de Microsoft Viva

En este artículo se describe cómo configurar y ejecutar un programa piloto de prueba para implementar Viva Topics en su organización. En este artículo también se recomiendan los procedimientos recomendados para la prueba.

## <a name="sign-up-for-a-trial"></a>Registrarse para una versión de prueba

Las pruebas están disponibles públicamente en uno de los siguientes orígenes. Estas pruebas ofrecen a 25 usuarios acceso a Temas de Viva durante 30 días.

- Página [del producto Temas de Viva](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- El [Centro de administración de Microsoft 365](https://admin.microsoft.com)
    1.  Inicie sesión en el [Centro de administración de Microsoft 365](https://admin.microsoft.com).
    2.  Vaya a **Servicios de compra** de  >  **facturación**.
    3.  Desplácese hacia abajo hasta la sección **Complementos**.
    4.  En el **icono Experiencias del** tema, seleccione **Detalles**.
    5.  Seleccione **Obtener prueba gratuita**.
    6.  Siga los pasos del asistente restantes para confirmar la prueba.

Debe ser un administrador Microsoft 365 global o administrador de facturación para activar una versión de prueba.

> [!NOTE]
> Las pruebas públicas solo se pueden agregar una vez para cada Microsoft 365 inquilino.

### <a name="who-should-be-involved-in-a-trial"></a>Quién debe participar en una prueba

|Rol  |Actividad  |
|---------|---------|
|Microsoft 365 administrador global o de facturación  |   Activar la versión de prueba y asignar licencias      |
|Microsoft 365 administrador global o administrador SharePoint administrador    |       Configurar Temas de Viva y crear centros de temas  |
|Usuario empresarial     |   Realizar roles de administrador de conocimientos, colaborador de temas y consumidor de temas      |

### <a name="before-you-activate-a-trial"></a>Antes de activar una versión de prueba

La planeación es esencial para una prueba eficaz de Viva Topics. El período de prueba es limitado y debe incluir la detección de temas y la exploración de experiencias de calidad, administración y usuario final.

#### <a name="discovery"></a>Descubrimiento

Hay dos opciones de estrategia de alto nivel para la configuración de la detección de temas durante una prueba:

- Indexe todo o la mayor parte de SharePoint contenido en línea.
   - Los inquilinos grandes pueden tardar hasta dos semanas en indizar por completo. Aunque los temas se generarán de forma incremental durante este período, la indización completa podría consumir hasta la mitad del período de prueba.
   - Para los inquilinos con un volumen de datos significativo, esta opción puede producir un gran número de temas, quizás decenas de miles.

- Identifique un subconjunto de los SharePoint web para la indización.

La elección de estas estrategias es un equilibrio de los dos factores siguientes:

- Tener suficientes datos para generar temas significativos. La inteligencia artificial de Viva Topics está ajustada para funcionar en conjuntos de datos grandes, idealmente los que tienen más de 10 000 documentos.
- No generar tantos temas durante el período de prueba que evaluarlos durante el período de tiempo disponible es abrumador.

Para la mayoría de las organizaciones, la segunda estrategia produce el mejor resultado.

> [!NOTE]
> Debido al número de documentos requeridos por la IA, se recomienda ejecutar pruebas de Viva Topics en un inquilino de producción. No hay ningún impacto en el rendimiento del inquilino durante este período. Solo los usuarios que tienen una licencia de prueba pueden acceder a las experiencias de usuario de Viva Topics.

#### <a name="roles"></a>Funciones

Durante la prueba, hay tres roles que deben estar activos, que se describen en la tabla siguiente.

|Rol  |Actividad  |
|---------|---------|
|Gerente de información     |   Controlar las fases del ciclo de vida de los temas; confirmar y quitar temas; actuar como administrador de la comunidad para colaboradores de temas      |
|Colaborador de tema    |      Expertos en la materia del contenido, que pueden:<br> Revisar temas para evaluar la calidad del contenido definido por AI<br>Curación de temas detectados con contenido adicional<br>Crear temas adicionales que no fueron detectados por AI   |
|Consumidor de temas    |     Consumir temas a través de los resaltados de página y la búsqueda<br>Proporcionar comentarios sobre el valor de los temas presentados    |

#### <a name="expected-topics"></a>Temas esperados

Puede ser útil documentar los temas que espera que genere la IA, incluso si esto se basa solo en suposiciones. Esta tarea se completa más fácilmente al indizar un subconjunto definido de los sitios SharePoint para los que las pymes se pueden identificar fácilmente.

Tener una lista documentada le ayudará a:

- Revise la lista de temas generados por IA, que puede ser mayor de lo esperado.
- Conozca los temas que puede que necesite crear manualmente o que son prioridades para la curación.

Siempre habrá una necesidad de una mezcla de temas definidos por la IA y creados por humanos en una implementación o prueba correcta de Viva Topics.

## <a name="activate-a-trial"></a>Activar una versión de prueba

Al iniciar una prueba, debe:

- Asignar licencias a los usuarios relevantes.
- Realice [una configuración adicional](set-up-topic-experiences.md) de Temas de Viva.

Cuando se activa la prueba, comienza el proceso de detección de temas.

## <a name="during-a-trial"></a>Durante una prueba

El período de prueba debe usarse para evaluar los siguientes componentes de Viva Topics:

- Los temas y el contenido del tema sugeridos por AI
- Las experiencias del usuario final, la presentación de tarjetas de temas en páginas SharePoint y en Búsqueda de Microsoft

Ten en cuenta los siguientes factores:

- Para que Viva Topics proporcione el valor máximo, el contenido de los temas debe ser una combinación de contenido definido por la IA y contenido de curación humana.
- Todas las experiencias de usuario están "recortadas por permisos" (incluida la vista del administrador de conocimientos en la **página Administrar temas).** Los usuarios solo verán un tema si tienen permisos para ver algunos de los recursos que se usaron para generar el tema. Esto significa que los diferentes usuarios pueden ver contenido diferente en la misma página de tema.
- Los usuarios pueden ver varios temas con el mismo nombre en la **página Administrar temas.** Estos temas no son necesariamente duplicados, pero pueden deberse a un solo término que se usa en varios contextos de los datos, como un nombre de código de proyecto que usan dos proyectos distintos.

## <a name="after-a-trial"></a>Después de una prueba

En función del resultado de la prueba, puede decidir si continúa con el uso en producción de Temas de Viva.

### <a name="proceed-to-production-use"></a>Continuar con el uso de producción

Para garantizar la continuidad del servicio, debe comprar el número necesario de licencias y asignar esas licencias a los usuarios. Los usuarios de prueba que no tienen una licencia completa al final del período de prueba no podrán acceder a ninguna experiencia de Viva Topics.

### <a name="dont-proceed-to-production-use"></a>No continuar con el uso de producción

Si no compra licencias después de la versión de prueba:

- La detección de temas se detendrá.
- Los usuarios ya no verán las tarjetas o los aspectos destacados del tema.
- El centro de temas no se eliminará, pero los temas sugeridos y las experiencias de administración de temas no estarán disponibles.
- Se perderán los temas definidos por IA.
- Los temas que haya editado un colaborador de temas permanecerán en la biblioteca de páginas del centro de temas. Solo el contenido proporcionado manualmente permanecerá en estas páginas, no cualquier contenido sugerido por AI.

## <a name="see-also"></a>Vea también

[Introducción a la adopción de temas de Microsoft Viva](topics-adoption-getstarted.md)

