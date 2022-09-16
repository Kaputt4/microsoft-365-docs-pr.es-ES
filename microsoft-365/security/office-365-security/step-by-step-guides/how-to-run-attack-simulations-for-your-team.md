---
title: Cómo ejecutar simulaciones de ataques para su equipo
description: Los pasos para enviar una carga de simulación de ataque a los usuarios de destino para su equipo u organización para el entrenamiento. Los ataques simulados pueden ayudarle a identificar y encontrar usuarios, directivas y prácticas vulnerables antes de que un ataque real afecte a su organización.
search.product: ''
ms.service: microsoft-365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.subservice: mdo
search.appverid: met150
ms.openlocfilehash: 1b483c75137d3731afbc507e67960201da2ce328
ms.sourcegitcommit: c29af68260ba8676083674b3c70209bff2c2e362
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2022
ms.locfileid: "67737992"
---
# <a name="how-to-run-attack-simulations-for-your-team"></a>Cómo ejecutar simulaciones de ataques para su equipo

Entrenamiento de simulación de ataque permite ejecutar escenarios de ciberataques realistas pero benignos en su organización. Los ataques simulados pueden ayudarle a identificar y encontrar usuarios, directivas y prácticas vulnerables antes de que un ataque real afecte a su organización, aprovechando el entrenamiento integrado o personalizado para reducir el riesgo y educar mejor a los usuarios finales sobre las amenazas.

## <a name="what-youll-need"></a>Lo que necesitará

- Microsoft Defender para Office 365 Plan 2 (incluido como parte de E5)
- Permisos suficientes (rol administrador de seguridad)
- 5-10 minutos para realizar los pasos siguientes.

## <a name="send-a-payload-to-target-users"></a>Envío de una carga útil a los usuarios de destino

1. Vaya a [Entrenamiento de simulación de ataques](https://security.microsoft.com/attacksimulator ) en la suscripción.
1. Elija **Simulaciones** en la barra de navegación superior.
1. Seleccione **Iniciar una simulación**.
1. Elija la técnica que desea usar en el control flotante y presione **Siguiente**.
1. Asigne un nombre a la simulación con algo relevante o memorable y presione **Siguiente**.
1. Elija una carga relevante del asistente, revise los detalles y personalícela si procede, cuando esté satisfecho con la elección, presione **Siguiente**.
1. Elija a quién dirigirse con la carga. Si elige toda la organización, resalte el botón de radio y presione **Siguiente**.
1. De lo contrario, seleccione **Agregar usuarios** y, a continuación, busque o filtre los usuarios con el asistente. Seleccione Agregar usuarios y, a continuación, **Siguiente**.
1. En **Seleccionar preferencia de contenido de entrenamiento**, deje la experiencia de entrenamiento predeterminada de *Microsoft (recomendada)* o seleccione *Redirigir a una dirección URL personalizada* si desea usar la dirección URL personalizada. Si no desea asignar ningún entrenamiento, seleccione *Sin entrenamiento*.
    - Puede permitir que Microsoft asigne cursos de formación seleccionando *Asignar formación para mí* o puede elegir módulos específicos con *Seleccionar cursos y módulos de entrenamiento yo mismo*.
    - Seleccione una fecha de vencimiento (30, 15 o 7 días) en el menú desplegable.
    - Haga clic en **Siguiente** para continuar.
1. Personalice la página de aterrizaje que se muestra cuando un usuario se phished si procede o, de lo contrario, deje el valor predeterminado de Microsoft.
    1. En **Indicadores de carga**, active la casilla para agregar indicadores de carga al correo electrónico. Agregar cargas útiles ayudará a los usuarios a aprender a identificar el correo electrónico de phishing. Seleccione *Abrir panel de vista previa* para ver el mensaje.
    1. Haga clic en **Siguiente** para continuar.
1. Elija si desea recibir notificaciones del usuario final y, si es así, seleccione las preferencias de entrega y personalícelas cuando sea necesario.
    1. Tenga en cuenta que también puede seleccionar *el idioma predeterminado* para la notificación en el menú desplegable **Seleccionar idioma predeterminado** .
1. Seleccione cuándo iniciar la simulación y durante cuánto tiempo debe ser válida. También puede habilitar la *entrega de zona horaria compatible con la región*. Esta opción proporcionará mensajes de ataque simulados a los empleados durante *su horario laboral* en función de su región. Seleccione **Siguiente**.
1. Envíe una prueba si está listo. Revise el resumen de las opciones. Haga clic en **Enviar**.

### <a name="further-reading"></a>Lectura adicional

Para obtener información sobre cómo funciona la simulación de ataques, consulte [Simulación de un ataque de suplantación de identidad con Entrenamiento de simulación de ataque: Office 365 | Microsoft Docs](../../office-365-security/attack-simulation-training.md)
