---
title: Plantillas de aviso de administración de riesgos de Insider
description: Más información sobre las plantillas de avisos de administración de riesgos internos en Microsoft Purview
keywords: Microsoft 365, Microsoft Purview, riesgo interno, administración de riesgos, cumplimiento
ms.localizationpriority: medium
ms.service: O365-seccomp
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- tier1
- purview-compliance
ms.custom: admindeeplinkCOMPLIANCE
ms.openlocfilehash: 04117f0880266f934955c1285250e509667a8482
ms.sourcegitcommit: 50da6f1f6ef2274c17ed9729e7ad84395b0a9be2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/08/2022
ms.locfileid: "68505211"
---
# <a name="insider-risk-management-notice-templates"></a>Plantillas de aviso de administración de riesgos de Insider

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

Las plantillas de aviso de administración de riesgos internos permiten enviar automáticamente mensajes de correo electrónico a los usuarios cuando se crea un caso para las actividades que han generado una coincidencia de directiva y una alerta confirmada. Para la mayoría de las alertas que generan casos, las acciones del usuario son el resultado de errores o actividades involuntarias sin mala intención. Los avisos sirven como recordatorios sencillos a los usuarios para tener más cuidado, para proporcionar vínculos a información para el entrenamiento del actualizador o a los recursos de directiva corporativa. Los avisos pueden ser una parte importante del programa de entrenamiento de cumplimiento interno y pueden ayudar a crear una pista de auditoría documentada para los usuarios con actividades de riesgo periódicas.

Cree plantillas de aviso si desea enviar a los usuarios un aviso de aviso por correo electrónico para las coincidencias de directivas como parte del proceso de resolución de casos. Los avisos solo se pueden enviar a la dirección de correo electrónico del usuario asociada al caso específico que se está revisando. Al seleccionar una plantilla de aviso para aplicar a una coincidencia de directiva, puede optar por aceptar los valores de campo definidos en la plantilla o sobrescribir los campos según sea necesario.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="notice-templates-dashboard"></a>Panel de plantillas de aviso

El **panel de plantillas de avisos** muestra una lista de plantillas de avisos configuradas y le permite crear nuevas plantillas de avisos. Las plantillas de aviso se muestran en orden de fecha inverso con la plantilla de aviso más reciente al principio de la lista.

![Panel de plantilla de aviso de administración de riesgos internos.](../media/insider-risk-notices-dashboard.png)

## <a name="html-for-notices"></a>HTML para avisos

Si desea crear más que un mensaje de correo electrónico simple basado en texto para las notificaciones, puede crear un mensaje más detallado mediante HTML en el campo cuerpo del mensaje de una plantilla de aviso. En el ejemplo siguiente se proporciona el formato de cuerpo del mensaje para una plantilla básica de notificación de correo electrónico basada en HTML:

```HTML
<!DOCTYPE html>
<html>
<body>
<h2>Action Required: Contoso User Code of Conduct Policy Training</h2>
<p>A recent activity you've performed has generated a risk alert prohibited by the Contoso User <a href='https://www.contoso.com'>Code of Conduct Policy</a>.</p>
<p>You are required to attend the Contoso User Code of Conduct <a href='https://www.contoso.com'>training</a> within the next 14 days. Please contact <a href='mailto:hr@contoso.com'>Human Resources</a> with any questions about this training request.</p>
<p>Thank you,</p>
<p><em>Human Resources</em></p>
</body>
</html>
```

> [!NOTE]
> La implementación del atributo html href en las plantillas de aviso de administración de riesgos internos admite actualmente solo comillas simples en lugar de comillas dobles para las referencias URL.

## <a name="create-a-new-notice-template"></a>Creación de una plantilla de aviso

Para crear una nueva plantilla de aviso de administración de riesgos internos, usará la herramienta de creación de avisos en la solución **de administración de riesgos insider** en el portal de cumplimiento Microsoft Purview.

Complete los pasos siguientes para crear una nueva plantilla de aviso de administración de riesgos internos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **Plantillas de aviso**.
2. Seleccione **Crear plantilla de aviso** para abrir la herramienta de creación de avisos.
3. En la página **Crear una plantilla de aviso,** complete los campos siguientes:
    - **Nombre de plantilla**: escriba un nombre descriptivo para el aviso. Este nombre aparece en la lista de avisos en el panel de avisos y en la lista de selección de avisos al enviar avisos desde un caso.
    - **Enviar desde**: escriba la dirección de correo electrónico del remitente para el aviso. Esta dirección aparecerá en el campo **Desde:** en todos los avisos enviados a los usuarios a menos que se cambien al enviar un aviso desde un caso.
    - **Campos Cc y CCO** : usuarios o grupos opcionales a los que se va a notificar la coincidencia de directiva, seleccionados en Active Directory para la suscripción.
    - **Asunto**: la información que aparece en la línea de asunto del mensaje admite caracteres de texto.
    - **Cuerpo del mensaje**: información que aparece en el cuerpo del mensaje, admite valores de texto o HTML.
4. Seleccione **Crear** para crear y guardar la plantilla de aviso o seleccione **Cancelar** para cerrar sin guardar la plantilla de aviso.

## <a name="update-a-notice-template"></a>Actualización de una plantilla de aviso

Para actualizar una plantilla de aviso de administración de riesgos internos existente, complete los pasos siguientes:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **Plantillas de aviso**.
2. En el panel de avisos, seleccione la plantilla de aviso que desea administrar.
3. En la página de detalles del aviso, seleccione **Editar**.
4. En la página **Editar** , puede editar los campos siguientes:
    - **Nombre de plantilla**: escriba un nuevo nombre descriptivo para el aviso. Este nombre aparece en la lista de avisos en el panel de avisos y en la lista de selección de avisos al enviar avisos desde un caso.
    - **Enviar desde**: actualice la dirección de correo electrónico del remitente para el aviso. Esta dirección aparecerá en el campo **Desde:** en todos los avisos enviados a los usuarios a menos que se cambien al enviar un aviso desde un caso.
    - **Campos Cc y CCO** : actualice los usuarios o grupos opcionales para que se notifiquen de la coincidencia de directiva, seleccionados en Active Directory para su suscripción.
    - **Asunto**: la información de actualización que aparece en la línea de asunto del mensaje admite caracteres de texto.
    - **Cuerpo del mensaje**: actualice la información que aparece en el cuerpo del mensaje, admite valores de texto o HTML.
5. Seleccione **Guardar** para actualizar y guardar el aviso o seleccione **Cancelar** para cerrar sin guardar la plantilla de aviso.

## <a name="delete-a-notice-template"></a>Eliminación de una plantilla de aviso

Para eliminar una plantilla de aviso de administración de riesgos internos existente, siga estos pasos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com), vaya a **Administración de riesgos de Insider** y seleccione la pestaña **Plantillas de aviso**.
2. En el panel de avisos, seleccione la plantilla de aviso que desea eliminar.
3. Seleccione el icono **Eliminar** en la barra de herramientas.
4. Para eliminar la plantilla de aviso, seleccione **Sí** en el cuadro de diálogo eliminar. Para cancelar la eliminación, seleccione **Cancelar**.
