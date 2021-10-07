---
title: Simular un ataque de suplantación de identidad con Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a simular ataques de suplantación de identidad (phishing) y entrenar a sus usuarios en la prevención de suplantación de identidad mediante el aprendizaje de simulación de ataques en Microsoft Defender para Office 365.
ms.technology: mdo
ms.openlocfilehash: fec06f65c67f0ec4c470660689a1f3fc1d9bfbcd
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213510"
---
# <a name="simulate-a-phishing-attack"></a>Simular un ataque de suplantación de identidad

**Se aplica a** [Microsoft Defender para Office 365 plan 2](defender-for-office-365.md)

El aprendizaje de simulación de ataques en Microsoft Defender para Office 365 te permite ejecutar simulaciones de ciberataques benignas en tu organización para probar las directivas y prácticas de seguridad, así como entrenar a tus empleados para aumentar su concienciación y disminuir su susceptibilidad a los ataques. Este artículo le guiará a través de la creación de un ataque de suplantación de identidad simulado mediante el entrenamiento de simulación de ataques.

Para obtener información de introducción sobre el aprendizaje de simulación de ataques, consulta [Introducción al aprendizaje de simulación de ataques.](attack-simulation-training-get-started.md)

Para iniciar un ataque de suplantación de identidad simulada, abra el portal de Microsoft 365 Defender ( ), vaya a Correo electrónico & aprendizaje de simulación de ataques de colaboración y cambie a la pestaña <https://security.microsoft.com/>  \>  **[Simulaciones.](https://security.microsoft.com/attacksimulator?viewid=simulations)**

En **Simulaciones,** seleccione **+ Iniciar una simulación**.

![Inicie un botón de simulación en Microsoft 365 Defender portal.](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> En cualquier momento durante la creación de la simulación, puede guardar y cerrar para continuar configurando la simulación más adelante.

## <a name="selecting-a-social-engineering-technique"></a>Selección de una técnica de ingeniería social

Seleccione entre 4 técnicas diferentes, seleccionadas en el marco de trabajo&[MITRE ATT ® CK](https://attack.mitre.org/techniques/enterprise/). Hay diferentes cargas disponibles para diferentes técnicas:

- **Credential harvest** attempts to collect credentials by taking users to a well-known looking website with input boxes to submit a username and password.
- **Los datos adjuntos** de malware agregan datos adjuntos malintencionados a un mensaje. Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.
- **Vínculo en datos adjuntos** es un tipo de híbrido de recolección de credenciales. Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico. La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recolección de credenciales.
- **El vínculo al malware** ejecutará código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido. El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado. Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo del destino.
- **La dirección URL de** unidad por es donde la dirección URL malintencionada del mensaje lleva al usuario a un sitio web de aspecto familiar que ejecuta o instala código de forma silenciosa en el dispositivo del usuario.

> [!TIP]
> Al hacer clic **en Ver detalles** dentro de la descripción de cada técnica, se mostrará más información y los pasos de simulación de la técnica.
>
> ![Pasos de simulación para la recolección de credenciales en el aprendizaje de simulación de ataques en el portal Microsoft 365 Defender búsqueda.](../../media/attack-sim-preview-sim-steps.png)

Después de seleccionar la técnica y hacer clic en **Siguiente,** asigne a la simulación un nombre y, opcionalmente, una descripción.

## <a name="selecting-a-payload"></a>Selección de una carga

A continuación, deberá seleccionar una carga del catálogo de carga existente.

Las cargas tienen varios puntos de datos que le ayudarán a elegir:

- **El** idioma muestra el idioma del contenido de carga. El catálogo de carga útil (global) de Microsoft proporciona cargas en más de 10 idiomas que también se pueden filtrar.
- **La tasa de clics** cuenta cuántas personas han hecho clic en esta carga.
- **La tasa de compromiso** predicho predice el porcentaje de personas que se verán comprometidas por esta carga en función de los datos históricos de la carga en Microsoft Defender para Office 365 clientes.
- **Las simulaciones iniciadas** cuentan el número de veces que se usó esta carga en otras simulaciones.
- **La** complejidad , **disponible** a través de filtros, se calcula en función del número de indicadores dentro de la carga que apunta a que se trata de un ataque. Más indicadores llevan a una complejidad menor.
- **Source**, disponible **a** través de filtros , indica si la carga se creó en el espacio empresarial o forma parte del catálogo de carga preexistnte (global) de Microsoft.

![Carga útil seleccionada dentro del entrenamiento de simulación de ataque en el portal Microsoft 365 Defender ataque.](../../media/attack-sim-preview-select-payload.png)

Seleccione una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.

Si quieres crear tu propia carga, lee crear una [carga para el entrenamiento de simulación de ataque.](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>Segmentación de público

Ahora es el momento de seleccionar la audiencia de esta simulación. Puede elegir incluir todos **los usuarios de la organización** o incluir solo usuarios y grupos **específicos.**

Cuando elige incluir **solo usuarios y** grupos específicos, puede:

- **Agregue usuarios**, lo que le permite aprovechar la búsqueda de su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a usuarios que no han sido dirigidos por una simulación en los últimos 3 meses.

  ![Filtrado de usuarios en el aprendizaje de simulación de ataques en el portal Microsoft 365 Defender web.](../../media/attack-sim-preview-user-targeting.png)

- **Importar desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación. El archivo CSV debe contener una dirección de correo electrónico por línea.

## <a name="assigning-training"></a>Asignar formación

Se recomienda asignar formación para cada simulación, ya que los empleados que pasan por el aprendizaje son menos propensos a ataques similares.

Puede elegir que se le asigne formación o seleccionar cursos de formación y módulos usted mismo.

Seleccione la **fecha de vencimiento del entrenamiento** para asegurarse de que los empleados finalicen su formación de forma oportuna.

> [!NOTE]
> Si elige seleccionar cursos y módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.
>
> ![Agregar entrenamiento recomendado dentro del entrenamiento de simulación de ataque en el portal Microsoft 365 Defender ataque.](../../media/attack-sim-preview-add-training.png)

En los pasos siguientes,  tendrás que agregar cursos si optas por seleccionarlo tú mismo y personalizar la página de aterrizaje del entrenamiento. Podrás obtener una vista previa de la página de aterrizaje del entrenamiento, así como cambiar el encabezado y el cuerpo de la página.

## <a name="launch-details-and-review"></a>Detalles de inicio y revisión

Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior. También tendrá que elegir cuándo finalizar esta simulación. Dejaremos de capturar la interacción con esta simulación más allá de la hora seleccionada.

**Habilite la entrega de zona horaria consciente de** la región para entregar mensajes de ataque simulados a sus empleados durante sus horas de trabajo en función de su región.

Una vez que haya terminado, haga clic en **Siguiente** y revise los detalles de la simulación. Haga clic **en Editar** en cualquiera de las partes para volver atrás y cambiar los detalles que necesiten cambiar. Una vez hecho esto, haga clic **en Enviar**.

> [!NOTE]
> Ciertas marcas comerciales, logotipos, símbolos, insignias y otros identificadores de origen reciben una protección más alta en virtud de leyes y leyes locales, estatales y federales. El uso no autorizado de estos indicadores puede someter a los usuarios a sanciones, incluidas las multas penales. Aunque no es una lista extensa, esto incluye los precintos presidencial, vicepresidenta y congresional, la CIA, el FBI, la Seguridad Social, Medicare y Medicaid, el Servicio de Ingresos Internos de estados Unidos y los Juegos Olímpicos. Más allá de estas categorías de marcas comerciales, el uso y modificación de cualquier marca comercial de terceros conlleva una cantidad inherente de riesgo. Usar sus propias marcas comerciales y logotipos en una carga sería menos arriesgado, especialmente cuando su organización permite el uso. Si tiene más preguntas sobre lo que es o no es apropiado usar al crear o configurar una carga, consulte con sus asesores legales.
