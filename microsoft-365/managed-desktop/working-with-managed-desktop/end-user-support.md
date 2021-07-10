---
title: Obtener soporte técnico de usuario para Escritorio administrado de Microsoft
description: Cómo los usuarios pueden obtener ayuda con el servicio y los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eea02b0a891f65ccd7e4e993ca719b0f3aa1b8b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362611"
---
# <a name="getting-help-for-users"></a>Obtener ayuda para los usuarios

Si has llegado al punto [](../service-description/user-support.md) del flujo de trabajo en el que necesitas solicitar acceso o escalación de dispositivos elevados a Microsoft, sigue estos pasos:
 
>[!NOTE]
>Estas opciones de soporte técnico no están disponibles para los dispositivos del grupo De prueba.

## <a name="elevation-requests"></a>Solicitudes de elevación

Antes de solicitar acceso elevado a un dispositivo, es mejor revisar qué acciones son más adecuadas.

- **Las acciones típicas** son para lo que está diseñado este proceso y se realizarían de forma rutinaria al solucionar problemas con Escritorio administrado de Microsoft dispositivos. Algunos ejemplos son:
    - Elevar los solucionadores de problemas del sistema integrados, el símbolo del sistema o Windows PowerShell
    - Solución de problemas de aplicaciones de línea de negocio
    - Usar una solución alternativa para corregir algo que debe funcionar por diseño (como la activación de BitLocker o la hora del sistema no se actualiza)
    - Elevar el Administrador de dispositivos para hacer cosas como actualizar controladores, desinstalar un dispositivo o buscar nuevos cambios

- **Entre las acciones que no se recomiendan** se incluyen las siguientes:
    - Instalación de software o exploradores
    - Instalación de controladores fuera de Windows, incluidos los de periféricos
    - Instalación .msi o .exe archivos
    - Instalación Windows características

- **Entre las acciones que no se admiten** se incluyen las siguientes:
    - Instalación de software o características que entren en conflicto con Escritorio administrado de Microsoft de seguridad o administración o operaciones
    - Deshabilitar una característica Windows necesaria para Escritorio administrado de Microsoft, como BitLocker
    - Modificar la configuración administrada por la organización

### <a name="to-request-elevation"></a>Para solicitar elevación

1. Vaya al portal en [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e inicie sesión con sus Azure Active Directory credenciales.
2. Seleccione **Nueva solicitud de elevación**.
3. Proporcione estos detalles:
    - **Id. de vale de** soporte técnico de su propio sistema de vales de soporte técnico.
    - **Nombre del dispositivo:** escriba el número de serie del dispositivo y, a continuación, seleccione el dispositivo en el menú.
    - **Categoría:** seleccione la categoría que mejor se adapte a su problema. Si ninguna opción parece estar cerca, selecciona **Otros** y proporciona más información en los campos **Título** y **Plan de** acción. Es mejor seleccionar una categoría si es posible.
    - **Subcategoría:** seleccione la que mejor se adapte al problema. Si ninguna opción parece estar cerca, seleccione **Otro** y proporcione una breve descripción en **Título**. En **Plan of action**, proporcione los pasos de solución de problemas que tiene previsto realizar una vez que se conceda la elevación.
4. Seleccione **Enviar**.


## <a name="escalation-requests"></a>Solicitudes de escalación


Si necesita escalar [un problema](../service-description/user-support.md#escalation-portal) a Microsoft, siga estos pasos:

1. Vaya al portal en [https://aka.ms/mmdelevationrequest](https://aka.ms/mmdelevationrequest) e inicie sesión con sus Azure Active Directory credenciales.
2. Seleccione **Solicitudes de escalación** y, a continuación, **nueva solicitud de escalación**.
3. Proporcione estos detalles:
    - **Categoría:** seleccione la categoría que mejor se adapte a su problema.
    - **Título:** proporcione una descripción muy breve.
    - **Descripción:** agregue cualquier información adicional que pueda ayudar a nuestro equipo a comprender el problema. Si necesita adjuntar archivos, puede hacerlo volviendo a la solicitud después de enviarlo.
    - **Información de contacto principal:** proporcione información sobre cómo ponerse en contacto con la persona principal responsable de trabajar con nuestro equipo.
4. Seleccione **Enviar**.
5. Vuelva a visitar el vale en el mismo portal para interactuar con nuestro equipo.

> [!NOTE]
> Solo los problemas de gravedad C se pueden escalar a través de esta ruta de acceso. Para otros problemas, póngase en contacto con el administrador de TI para presentar la solicitud a través del portal de administración.