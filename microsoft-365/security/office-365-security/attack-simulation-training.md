---
title: Simular un ataque de suplantación de identidad con Microsoft defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Los administradores pueden obtener información sobre cómo simular ataques de suplantación de identidad y entrenarles a sus usuarios en la prevención de suplantación de identidad mediante la simulación de ataques en Microsoft defender para Office 365.
ms.openlocfilehash: 3707041067fd76ee9535d0dccf5cdfcb9d74fbd7
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667580"
---
# <a name="simulate-a-phishing-attack"></a>Simular un ataque de suplantación de identidad

El aprendizaje del simulador de ataques en Microsoft defender para Office 365 le permite ejecutar simulaciones benignas de ciberataque en su organización para probar las directivas y prácticas de seguridad, así como entrenar a sus empleados para aumentar su conocimiento y reducir la susceptibilidad a los ataques. En este artículo se explica cómo crear un ataque simulado de suplantación de identidad mediante el aprendizaje de simulación de ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Para iniciar un ataque simulado de suplantación de identidad (phishing), abra el [centro de seguridad de Microsoft 365](https://security.microsoft.com/), vaya a **correo electrónico &** \> el **simulador de ataque** de colaboración y cambie a la pestaña [**simulaciones**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

En **simulaciones**, seleccione **+ iniciar una simulación**.

![Iniciar un botón de simulación en el centro de seguridad 365 de Microsoft](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> En cualquier momento durante la creación de la simulación, puede guardar y cerrar para seguir configurando la simulación en un momento posterior.

## <a name="selecting-a-social-engineering-technique"></a>Selección de una técnica de ingeniería social

Seleccione cuatro técnicas distintas, creados de la [Mitre de ATT&CK® Framework](https://attack.mitre.org/techniques/enterprise/). Hay diferentes cargas disponibles para distintas técnicas:

- La **cosecha de credenciales** intenta recopilar las credenciales poniendo a los usuarios en un sitio web de aspecto conocido con cuadros de entrada para enviar un nombre de usuario y una contraseña.
- Los **datos adjuntos de malware** agregan datos adjuntos malintencionados a un mensaje. Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.
- El **vínculo en datos adjuntos** es un tipo de una implementación híbrida de cosecha de credenciales. Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico. La dirección URL dentro de los datos adjuntos sigue la misma técnica que la cosecha de credenciales.
- El **vínculo a malware** ejecutará código arbitrario de un archivo hospedado en un conocido servicio de uso compartido de archivos. El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado. Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo de destino.

> [!TIP]
> Al hacer clic en **Ver detalles** en la descripción de cada técnica se mostrará más información y los pasos de simulación para la técnica.
>
> ![Pasos de simulación para la recopilación de credenciales en la simulación de ataques en el centro de seguridad de Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

Una vez que haya seleccionado la técnica y haya hecho clic en **siguiente**, dé un nombre a su simulación y, opcionalmente, una descripción.

## <a name="selecting-a-payload"></a>Selección de una carga

A continuación, tendrá que seleccionar una carga del catálogo de carga existente.

Las cargas tienen varios puntos de datos para ayudarle a elegir:

- Los **tipos de tasa de clics** tienen en cuenta cuántos usuarios hacen clic en esta carga.
- La **tasa de compromiso pronosticada** pronostica el porcentaje de personas que se verán comprometidas con esta carga en función de los datos históricos de la carga en Microsoft defender para Office 365 clientes.
- **Simulations lanzadas** cuenta el número de veces que se usó esta carga en otras simulaciones.
- La **complejidad**, disponible a través de **filtros**, se calcula en función del número de indicadores dentro de la carga en los que se encuentra un ataque a los objetivos de una pista. Más indicadores conducen a una complejidad más baja.
- **Origen**, disponible a través de **filtros**, indica si la carga se creó en su inquilino o forma parte del catálogo de carga existente (global) de Microsoft.

![Carga seleccionada en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-select-payload.png)

Seleccione una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.

Si quiere crear su propia carga de carga, lea [crear una carga para la formación de simulación de ataques](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Identificación de audiencia

Ahora es el momento de seleccionar la audiencia de esta simulación. Puede elegir incluir a **todos los usuarios de la organización** o **incluir sólo usuarios y grupos específicos**.

Cuando elige **incluir sólo usuarios y grupos específicos** , puede:

- **Agregue usuarios**, lo que le permite aprovechar la búsqueda para su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a los usuarios que no han sido dirigidos por una simulación en los últimos tres meses.
  ![Filtrado de usuarios en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-user-targeting.png)
- **Importar desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación.

## <a name="assigning-training"></a>Asignar formación

Le recomendamos que asigne un entrenamiento para cada simulación, ya que los empleados que vayan a realizar cursos de formación serán menos susceptibles a ataques similares.

Puede elegir entre tener un entrenamiento asignado para usted o seleccionar los módulos y los cursos de formación usted mismo.

Seleccione la **fecha de vencimiento** de la formación para asegurarse de que los empleados finalicen la formación de manera oportuna.

> [!NOTE]
> Si decide seleccionar los cursos y los módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.
>
> ![Adición de formación recomendada en el centro de seguridad de la simulación de ataques en Microsoft 365 Security Center](../../media/attack-sim-preview-add-training.png)

En los pasos siguientes, tendrá que **Agregar formación** si opta por seleccionarla usted mismo y personalizar su página de inicio de formación. Podrá obtener una vista previa de la página de inicio del aprendizaje, así como cambiar el encabezado y el cuerpo de la misma.

## <a name="launch-details-and-review"></a>Información de lanzamiento y revisión

Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior. También tendrá que elegir cuándo finalizar esta simulación. Dejaremos de capturar la interacción con esta simulación más allá del tiempo seleccionado.

**Habilite la entrega de zona horaria consciente** de la región para entregar mensajes de ataque simulados a los empleados durante el horario laboral en función de su región.

Una vez que haya terminado, haga clic en **siguiente** y revise los detalles de la simulación. Haga clic en **Editar** en cualquiera de las partes para volver y cambiar los detalles que deben cambiar. Una vez hecho, haga clic en **Enviar**.
