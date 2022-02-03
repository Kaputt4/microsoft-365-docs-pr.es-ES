---
title: Obtener soporte técnico de usuario para Microsoft Managed Desktop
description: Cómo los usuarios pueden obtener ayuda con el servicio y los dispositivos
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 48be29f8db689ddd0911d7512b267ba50c85a469
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2022
ms.locfileid: "62322412"
---
# <a name="getting-help-for-users"></a>Obtener ayuda para los usuarios

Si has llegado al punto del flujo de trabajo [](../service-description/user-support.md) en el que necesitas solicitar acceso o escalación de dispositivos elevados a Microsoft, sigue estos pasos:

>[!NOTE]
>Estas opciones de soporte técnico no están disponibles para los dispositivos del grupo De prueba.

## <a name="elevation-requests"></a>Solicitudes de elevación

Antes de solicitar acceso elevado a un dispositivo, es mejor revisar qué acciones son más adecuadas.

| Acciones | Ejemplos |
| ------ | ------ |
| **Las acciones típicas** están diseñadas para el proceso de solicitud de elevación. Se realiza de forma rutinaria al solucionar problemas con dispositivos de Escritorio administrado de Microsoft. | <ul><li>Elevación de los solucionadores de problemas del sistema integrados, el símbolo del sistema o Windows PowerShell solución de problemas de aplicaciones de línea de negocio.</li><li>Usar una solución alternativa para corregir algo que debe funcionar por diseño (como la activación de BitLocker o el tiempo del sistema no se actualiza).</li><li>Elevar el Administrador de dispositivos para hacer cosas como actualizar controladores, desinstalar un dispositivo o buscar nuevos cambios.</li></ul>
| **Acciones que no se recomiendan** | <ul><li>Instalación de software o exploradores.</li><li>Instalar controladores fuera de Windows configuración, incluidos los controladores para periféricos.</li><li>Instalar .msi o .exe archivos.</li><li>Instalación Windows características.</li></ul>
| **Acciones que no son compatibles** | <ul><li>Instalación de software o características que entren en conflicto con las funciones u operaciones de seguridad o administración de Escritorio administrado de Microsoft.</li><li>Deshabilitar una característica Windows de escritorio administrado de Microsoft, como BitLocker.</li><li>Modificar la configuración administrada por la organización.</li><ul>

**Para solicitar elevación:**

1. Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al **menú Dispositivos**.
1. En la **sección Escritorio administrado de Microsoft**, seleccione **Dispositivos**, que contiene dos pestañas: la pestaña Dispositivos y la pestaña **Solicitudes de elevación**.
1. Para crear una nueva solicitud de elevación en la **pestaña Dispositivo** , selecciona un solo dispositivo que quieras elevar.
1. En el menú desplegable Acciones del dispositivo, selecciona **Solicitar elevación**. Aparecerá una nueva solicitud de elevación con el nombre del dispositivo rellenado previamente en ese campo.
1. En su lugar, para crear una nueva solicitud de elevación en la pestaña **Solicitudes de elevación** , seleccione **+Nueva solicitud de elevación.**
1. Proporcione estos detalles:
    - **Id. de vale de** soporte técnico: se trata de su propio sistema de vales de soporte técnico.
    - **Nombre del dispositivo**: esto solo se hace al crear una solicitud desde la pestaña **Solicitudes de elevación** . Escribe el número de serie del dispositivo y, a continuación, selecciona el dispositivo en el menú.
    - **Categoría**: seleccione la categoría que mejor se adapte a su problema. Si no hay ninguna opción cerca, seleccione **Otro**. Es mejor seleccionar una categoría si es posible.
    - **Título**: proporcione una breve descripción del problema en el dispositivo.
    - **Plan de acción**: proporcione los pasos de solución de problemas que tiene previsto realizar una vez que se conceda la elevación.
1. Seleccione **Enviar**.
1. La lista y los detalles de todas las solicitudes activas y cerradas se pueden ver en la pestaña **Solicitudes de elevación** .

## <a name="escalation-requests"></a>Solicitudes de escalación

**Para [escalar un](../service-description/user-support.md#escalation-portal) problema a Microsoft:**

1. Inicie sesión en [Microsoft Endpoint Manager](https://endpoint.microsoft.com/) y vaya al menú **Administración de inquilinos**.
2. En la sección Escritorio administrado de Microsoft, seleccione **Solicitudes de servicio**.
3. En la **sección Solicitudes de servicio** , seleccione **+ Nueva solicitud de soporte técnico**.
4. Proporcione una breve descripción en el **campo** Título. A continuación, establezca el **tipo request** en **Incident**.
5. Seleccione las **categorías Categoría** **y Subcategoría** que mejor se adapten a su problema. Después, seleccione **Siguiente**.
6. En la **sección** Detalles, proporcione la siguiente información:
    - **Descripción**: agregue cualquier información adicional que pueda ayudar a nuestro equipo a comprender el problema. Si necesita adjuntar archivos, puede hacerlo volviendo a la solicitud después de enviarlo.
    - **Información de contacto principal**: proporcione información sobre cómo ponerse en contacto con la persona principal responsable de trabajar con nuestro equipo.
7. Seleccione el **nivel de gravedad** . Para obtener más información, vea [Support request severity definitions](../working-with-managed-desktop/admin-support.md#support-request-severity-definitions).
8. Proporcione tanta información sobre la solicitud como sea posible para ayudar al equipo a responder rápidamente. Según el tipo de solicitud, es posible que deba proporcionar diferentes detalles.
9. Revise toda la información que proporcionó para obtener precisión.
10. Cuando haya terminado, seleccione **Crear**.
