---
title: Obtener soporte técnico de usuario para Microsoft Managed Desktop
description: Cómo los usuarios pueden obtener ayuda con el servicio y los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d10f2e938e201fa25505abc820d05b03af04e543
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374417"
---
# <a name="getting-help-for-users"></a>Obtener ayuda para los usuarios

Si has llegado al punto [](../service-description/user-support.md) del flujo de trabajo en el que necesitas solicitar acceso o escalación de dispositivos elevados a Microsoft, sigue estos pasos:
 
>[!NOTE]
>Estas opciones de soporte técnico no están disponibles para los dispositivos del grupo De prueba.

## <a name="elevation-requests"></a>Solicitudes de elevación

Antes de solicitar acceso elevado a un dispositivo, es mejor revisar qué acciones son más adecuadas.

- **Las acciones típicas** son para lo que está pensado este proceso y se realizarían de forma rutinaria al solucionar problemas con dispositivos de Escritorio administrado de Microsoft. Algunos ejemplos son:
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
    - Instalación de software o características que entren en conflicto con las funciones u operaciones de seguridad o administración de Escritorio administrado de Microsoft
    - Deshabilitar una característica Windows de escritorio administrado de Microsoft, como BitLocker
    - Modificar la configuración administrada por la organización

### <a name="to-request-elevation"></a>Para solicitar elevación

1. Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos.**
2. Busque la sección Escritorio administrado de  **Microsoft** y, a continuación,  seleccione la hoja Dispositivos, que contiene dos pestañas: la pestaña Dispositivos y la pestaña **Solicitudes de elevación.** 
3. Para crear una nueva  solicitud de elevación en la pestaña Dispositivo,  selecciona un solo dispositivo que quieras elevar y, a continuación, selecciona Solicitar elevación en el menú desplegable Acciones del dispositivo. Aparecerá un nuevo panel desplegable de solicitud de elevación con el nombre del dispositivo prepopulado en ese campo.
4. Como alternativa, para crear una nueva solicitud de elevación en la pestaña Solicitudes de **elevación,** seleccione **+Nueva solicitud de elevación.**
5. Proporcione estos detalles:
    - **Id. de vale de** soporte técnico de su propio sistema de vales de soporte técnico.
    - **Nombre del dispositivo**(solo al crear una solicitud desde la pestaña **Solicitudes** de elevación): escriba el número de serie del dispositivo y, a continuación, seleccione el dispositivo en el menú.
    - **Categoría:** seleccione la categoría que mejor se adapte a su problema. Si ninguna opción parece estar cerca, seleccione **Otros**. Es mejor seleccionar una categoría si es posible.
    - **Título:** proporcione una breve descripción del problema en el dispositivo.
    - **Plan de acción:** proporcione los pasos de solución de problemas que tiene previsto realizar una vez que se conceda la elevación. 
6. Seleccione **Enviar**.
7. La lista y los detalles de todas las solicitudes activas y cerradas se pueden ver en la pestaña **Solicitudes de elevación.**



## <a name="escalation-requests"></a>Solicitudes de escalación


Si necesita escalar [un problema](../service-description/user-support.md#escalation-portal) a Microsoft, siga estos pasos:

1. Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al menú **Administración de inquilinos.**
2. Busque la sección Escritorio administrado de Microsoft y, a continuación, **seleccione Solicitudes de servicio**.
3. En la **hoja Solicitudes de servicio,** seleccione **+ Nueva solicitud de soporte técnico**.
4. Proporcione una descripción muy breve en el **cuadro** Título. A continuación, **establezca el tipo de solicitud** en **Incident**. 
5. Seleccione la **categoría** y **subcategoría** que mejor se adapte a su problema y seleccione **Siguiente**.
6. En la **sección** Detalles, proporcione la siguiente información:
    - **Descripción:** agregue cualquier información adicional que pueda ayudar a nuestro equipo a comprender el problema. Si necesita adjuntar archivos, puede hacerlo volviendo a la solicitud después de enviarlo.
    - **Información de contacto principal:** proporcione información sobre cómo ponerse en contacto con la persona principal responsable de trabajar con nuestro equipo.
7. Seleccione el **nivel de gravedad.** Para obtener más información, vea Support request severity definitions.
8. Proporcione tanta información sobre la solicitud como sea posible para ayudar al equipo a responder rápidamente. Según el tipo de solicitud, es posible que deba proporcionar diferentes detalles.
9. Revise toda la información que proporcionó para obtener precisión.
10. Cuando haya terminado, seleccione **Crear**.
