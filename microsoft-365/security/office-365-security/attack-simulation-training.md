---
title: Simular un ataque de suplantación de identidad con Microsoft Defender para Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Los administradores pueden aprender a simular ataques de suplantación de identidad (phishing) y entrenar a sus usuarios sobre la prevención de suplantación de identidad mediante la formación de simulación de ataques en Microsoft Defender para Office 365.
ms.openlocfilehash: dfdd3c93afb1b0fb30cc5b5affc040a369c29447
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870972"
---
# <a name="simulate-a-phishing-attack"></a>Simular un ataque de suplantación de identidad

La formación de simulación de ataques en Microsoft Defender para Office 365 le permite ejecutar simulaciones de ciberataques benignos en su organización para probar las directivas y prácticas de seguridad, así como entrenar a sus empleados para aumentar su concienciación y reducir su susceptibilidad a los ataques. Este artículo le guiará a través de la creación de un ataque de suplantación de identidad simulado mediante el entrenamiento de simulación de ataques.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Para obtener información de introducción sobre el aprendizaje de simulación de ataques, consulta Introducción [al entrenamiento de simulación de ataques.](attack-simulation-training-get-started.md)

Para iniciar un ataque de suplantación de identidad simulado, abra el Centro de seguridad de [Microsoft 365,](https://security.microsoft.com/)vaya a Formación de simulación de ataques de colaboración de correo electrónico & y cambie **a** la pestaña \>  [**Simulaciones.**](https://security.microsoft.com/attacksimulator?viewid=simulations)

En **Simulaciones,** seleccione **+ Iniciar una simulación.**

![Iniciar un botón de simulación en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> En cualquier momento durante la creación de la simulación, puede guardar y cerrar para continuar configurando la simulación más adelante.

## <a name="selecting-a-social-engineering-technique"></a>Selección de una técnica de ingeniería social

Seleccione entre 4 técnicas diferentes, conservadas en el marco de trabajo&[CK ® MITRE ATT.](https://attack.mitre.org/techniques/enterprise/) Hay diferentes cargas disponibles para diferentes técnicas:

- **La recolección de** credenciales intenta recopilar credenciales llevando a los usuarios a un sitio web de aspecto conocido con cuadros de entrada para enviar un nombre de usuario y una contraseña.
- **Los datos adjuntos** de malware agregan datos adjuntos malintencionados a un mensaje. Cuando el usuario abre los datos adjuntos, se ejecuta código arbitrario que ayudará al atacante a poner en peligro el dispositivo del destino.
- **El vínculo en los datos** adjuntos es un tipo de recolección de credenciales híbrida. Un atacante inserta una dirección URL en un archivo adjunto de correo electrónico. La dirección URL dentro de los datos adjuntos sigue la misma técnica que la recolección de credenciales.
- **El vínculo al malware** ejecutará código arbitrario desde un archivo hospedado en un servicio de uso compartido de archivos conocido. El mensaje enviado al usuario contendrá un vínculo a este archivo malintencionado. Abrir el archivo y ayudar al atacante a poner en peligro el dispositivo del destino.

> [!TIP]
> Al hacer **clic en Ver detalles** de la descripción de cada técnica, se mostrará más información y los pasos de simulación de la técnica.
>
> ![Pasos de simulación para la recolección de credenciales dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-sim-steps.png)

Después de seleccionar la técnica y hacer clic **en** Siguiente, asigne a la simulación un nombre y, opcionalmente, una descripción.

## <a name="selecting-a-payload"></a>Selección de una carga

A continuación, tendrás que seleccionar una carga del catálogo de carga ya existente.

Las cargas de trabajo tienen una serie de puntos de datos que le ayudarán a elegir:

- **La tasa de clics** cuenta cuántas personas han hecho clic en esta carga.
- **La tasa de compromiso** previsto predice el porcentaje de personas que se verán comprometidas por esta carga en función de los datos históricos de la carga en Microsoft Defender para los clientes de Office 365.
- **Las simulaciones iniciadas** cuentan el número de veces que esta carga se usó en otras simulaciones.
- **La** complejidad, disponible **a través de** filtros, se calcula en función del número de indicadores dentro de la carga en la que se dirige la pista en que se trata de un ataque. Si hay más indicadores, la complejidad es menor.
- **Source**, available through **filters**, indicates whether the payload was created on your tenant or is a part of Microsoft's pre-existing payload catalog (global).

![Carga seleccionada dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-select-payload.png)

Selecciona una carga de la lista para ver una vista previa de la carga con información adicional sobre ella.

Si quieres crear tu propia carga, lee crear una carga [para el entrenamiento de simulación de ataques.](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>Identificación de audiencia

Ahora es el momento de seleccionar la audiencia de esta simulación. Puede elegir incluir todos **los usuarios de su** organización o incluir solo usuarios y grupos **específicos.**

Si elige incluir **solo usuarios y** grupos específicos, puede:

- **Agregue** usuarios, lo que le permite aprovechar la búsqueda de su espacio empresarial, así como las capacidades avanzadas de búsqueda y filtrado, como dirigirse a usuarios que no han sido objetivo de una simulación en los últimos 3 meses.
  ![Filtrado de usuarios en la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-user-targeting.png)
- **La importación desde CSV** permite importar un conjunto predefinido de usuarios para esta simulación.

## <a name="assigning-training"></a>Asignación de aprendizaje

Te recomendamos que asignes formación para cada simulación, ya que los empleados que pasan por el entrenamiento son menos susceptibles a ataques similares.

Puede elegir que se le asigne formación o seleccionar cursos de aprendizaje y módulos usted mismo.

Seleccione la **fecha de vencimiento del aprendizaje** para asegurarse de que los empleados finalicen su aprendizaje de forma oportuna.

> [!NOTE]
> Si decide seleccionar cursos y módulos usted mismo, podrá ver el contenido recomendado, así como todos los cursos y módulos disponibles.
>
> ![Adición de formación recomendada dentro de la formación de simulación de ataques en el Centro de seguridad de Microsoft 365](../../media/attack-sim-preview-add-training.png)

En los pasos siguientes,  tendrá que agregar cursos de aprendizaje si optó por seleccionarlo usted mismo y personalizar la página de aterrizaje de la formación. Podrás obtener una vista previa de la página de aterrizaje del entrenamiento, así como cambiar el encabezado y el cuerpo de la página.

## <a name="launch-details-and-review"></a>Detalles de inicio y revisión

Ahora que todo está configurado, puede iniciar esta simulación inmediatamente o programarla para una fecha posterior. También tendrá que elegir cuándo finalizar esta simulación. Dejaremos de capturar la interacción con esta simulación más allá de la hora seleccionada.

**Habilitar la entrega de zona horaria consciente de** la región para entregar mensajes de ataque simulado a los empleados durante sus horas de trabajo en función de su región.

Una vez que haya terminado, haga clic en **Siguiente** y revise los detalles de la simulación. Haga clic **en Editar** en cualquiera de los elementos para volver atrás y cambiar los detalles que necesiten cambiar. Una vez hecho esto, haga clic **en Enviar**.
