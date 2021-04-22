---
title: Puntuación de seguridad de Microsoft para dispositivos
description: La puntuación de los dispositivos muestra el estado de configuración de seguridad colectiva de los dispositivos en todos los controles de aplicación, sistema operativo, red, cuentas y seguridad.
keywords: Puntuación segura de Microsoft para dispositivos, Puntuación segura de Microsoft Defender para dispositivos, puntuación segura, puntuación de configuración, administración de amenazas y vulnerabilidades, controles de seguridad, oportunidades de mejora, puntuación de configuración de seguridad con el tiempo, posición de seguridad, línea base
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f2c799d477c400482c16b09b4d8a5cdc01106dfa
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934086"
---
# <a name="microsoft-secure-score-for-devices"></a>Puntuación de seguridad de Microsoft para dispositivos

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**

- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> ¿Desea experimentar Defender for Endpoint? [Regístrate para obtener una versión de prueba gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


>[!NOTE]
> La puntuación de configuración ahora forma parte de la administración de amenazas y vulnerabilidades como Puntuación segura de Microsoft para dispositivos.

La puntuación de los dispositivos está visible en el panel de [administración](tvm-dashboard-insights.md) de amenazas y vulnerabilidades del Centro de seguridad de Microsoft Defender. Una puntuación segura de Microsoft más alta para dispositivos significa que los puntos de conexión son más resistentes frente a los ataques de amenazas de ciberseguridad. Refleja el estado de configuración de seguridad colectiva de los dispositivos en las siguientes categorías:

- Aplicación
- Sistema operativo
- Red
- Cuentas
- Controles de seguridad

Seleccione una categoría para ir a la [**página Recomendaciones de seguridad**](tvm-security-recommendation.md) y ver las recomendaciones pertinentes.

## <a name="turn-on-the-microsoft-secure-score-connector"></a>Activar el conector de puntuación segura de Microsoft

Reenvía Microsoft Defender para las señales de punto de conexión, lo que ofrece a Microsoft Secure Score visibilidad en la posición de seguridad del dispositivo. Los datos reenviados se almacenan y procesan en la misma ubicación que los datos de puntuación segura de Microsoft.

Los cambios pueden tardar hasta unas horas en reflejarse en el panel.

1. En el panel de navegación, vaya a **Configuración**  >  **Características avanzadas** 

2. Desplácese hacia abajo **hasta Puntuación segura de Microsoft** y cambie la configuración a **On**.

3. Seleccione **Guardar preferencias**.

## <a name="how-it-works"></a>Cómo funciona

>[!NOTE]
> La puntuación segura de Microsoft para dispositivos actualmente admite configuraciones establecidas a través de la directiva de grupo. Debido a la compatibilidad parcial actual de Intune, las configuraciones que podrían haber sido configuradas a través de Intune podrían aparecer como mal configuradas. Póngase en contacto con el administrador de TI para comprobar el estado de configuración real en caso de que su organización use Intune para la administración de configuración segura.

Los datos de la tarjeta Puntuación segura de Microsoft para dispositivos son el producto del proceso de detección de vulnerabilidades meticuloso y continuo. Se agrega con evaluaciones de detección de configuración que continuamente:

- Comparar configuraciones recopiladas con los puntos de referencia recopilados para detectar activos mal configurados
- Asignar configuraciones a vulnerabilidades que se pueden corregir o corregir parcialmente (reducción de riesgos)
- Recopilar y mantener indicadores de configuración de procedimientos recomendados (proveedores, fuentes de seguridad, equipos de investigación internos)
- Recopilar y supervisar los cambios del estado de configuración del control de seguridad de todos los activos

## <a name="improve-your-security-configuration"></a>Mejorar la configuración de seguridad

Mejore la configuración de seguridad mediante la corrección de problemas de la lista de recomendaciones de seguridad. Al hacerlo, la puntuación segura de Microsoft para dispositivos mejora y la organización se vuelve más resistente frente a las amenazas y vulnerabilidades de ciberseguridad.

1. En la tarjeta Puntuación segura de Microsoft para dispositivos en el panel de administración de amenazas y vulnerabilidades, seleccione una de las categorías. Verá la lista de recomendaciones relacionadas con esa categoría. Le llevará a la página Recomendaciones [**de**](tvm-security-recommendation.md) seguridad. Si desea ver todas las recomendaciones de seguridad, una vez que llegue a la página Recomendaciones de seguridad, desactive el campo de búsqueda.

2. Seleccione un elemento en la lista. El panel desplegable se abrirá con detalles relacionados con la recomendación. Seleccione **Opciones de corrección**.

   ![Recomendaciones de seguridad relacionadas con controles de seguridad](images/tvm_security_controls.png)

3. Lea la descripción para comprender el contexto del problema y qué hacer a continuación. Seleccione una fecha de vencimiento, agregue notas y **seleccione Exportar** todos los datos de actividad de corrección a CSV para poder adjuntarlos a un correo electrónico para su seguimiento.

4. **Enviar solicitud**. Verá un mensaje de confirmación de que se ha creado la tarea de corrección.
   ![Confirmación de creación de tareas de corrección](images/tvm_remediation_task_created.png)

5. Guarde el archivo CSV.
   ![Guardar archivo csv](images/tvm_save_csv_file.png)

6. Envíe un correo electrónico de seguimiento a su administrador de TI y permita el tiempo que haya asignado para que la corrección se propague en el sistema.

7. Revisa la **tarjeta Puntuación segura de Microsoft para** dispositivos de nuevo en el panel. El número de recomendaciones de controles de seguridad disminuirá. Cuando selecciona **Controles de seguridad**  para volver a la página Recomendaciones de seguridad, el elemento que ha abordado ya no aparecerá en la lista. La puntuación segura de Microsoft para dispositivos debe aumentar.

>[!IMPORTANT]
>Para aumentar las tasas de detección de evaluación de vulnerabilidades, descargue las siguientes actualizaciones de seguridad obligatorias e impleméntelas en la red:
>- Clientes de 19H1 | [KB 4512941](https://support.microsoft.com/help/4512941/windows-10-update-kb4512941)
>- Clientes de RS5 | [KB 4516077](https://support.microsoft.com/help/4516077/windows-10-update-kb4516077)
>- Clientes de RS4 | [KB 4516045](https://support.microsoft.com/help/4516045/windows-10-update-kb4516045)
>- Clientes de RS3 | [KB 4516071](https://support.microsoft.com/help/4516071/windows-10-update-kb4516071)
>
>Para descargar las actualizaciones de seguridad:
>1. Vaya a [Catálogo de Microsoft Update](https://www.catalog.update.microsoft.com/home.aspx).
>2. Clave en el número KB de actualización de seguridad que necesita descargar y, a continuación, haga clic en **Buscar**.  

## <a name="related-topics"></a>Temas relacionados

- [Introducción a la administración de amenazas y vulnerabilidades](next-gen-threat-and-vuln-mgt.md)
- [Panel](tvm-dashboard-insights.md)
- [Puntuación de exposición](tvm-exposure-score.md)
- [Recomendaciones de seguridad](tvm-security-recommendation.md)
