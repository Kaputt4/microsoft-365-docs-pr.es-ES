---
title: Introducción a las pruebas forenses de administración de riesgos internos (versión preliminar)
description: Introducción a las pruebas forenses de administración de riesgos internos en Microsoft Purview. La evidencia forense es una herramienta de investigación para ver la actividad de usuario relacionada con la seguridad capturada para ayudar a determinar si las acciones del usuario suponen un riesgo y pueden provocar un incidente de seguridad.
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
ms.collection: m365-security-compliance
ms.openlocfilehash: 38dd4b4ee3908da144b1e55d8efbc0af30a39dc9
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68814393"
---
# <a name="get-started-with-insider-risk-management-forensic-evidence-preview"></a>Introducción a las pruebas forenses de administración de riesgos internos (versión preliminar)

>[!IMPORTANT]
>Administración de riesgos internos de Microsoft Purview correlaciona varias señales para identificar posibles riesgos internos malintencionados o involuntarios, como el robo de IP, la pérdida de datos y las infracciones de seguridad. La administración de riesgos internos permite a los clientes crear directivas para administrar la seguridad y el cumplimiento. Creados con privacidad por diseño, los usuarios se seudonimizan de forma predeterminada y los controles de acceso basados en roles y los registros de auditoría están en su lugar para ayudar a garantizar la privacidad del nivel de usuario.

## <a name="configure-forensic-evidence"></a>Configuración de pruebas forenses

La configuración de pruebas forenses en su organización es similar a la configuración de otras directivas a partir de plantillas de directivas de administración de riesgos internos. En general, seguirá los mismos pasos de configuración básicos para configurar pruebas forenses, pero hay algunas áreas que necesitan acciones de configuración específicas de características antes de empezar con los pasos de configuración básicos.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

### <a name="step-1-confirm-your-subscription-and-configure-data-storage-access"></a>Paso 1: Confirmar la suscripción y configurar el acceso al almacenamiento de datos

Antes de empezar a trabajar con pruebas forenses, debe confirmar su [suscripción de administración de riesgos](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-insider-risk-management) internos y cualquier complemento.

Además, deberá agregar el siguiente dominio a la lista de permitidos del firewall para admitir el almacenamiento de captura de pruebas forenses para su organización:

- *compliancedrive.microsoft.com*

Las capturas y capturas de datos se almacenan en este dominio y solo se asignan a su organización. Ninguna otra organización de Microsoft 365 tiene acceso a capturas de pruebas forenses para su organización.

### <a name="step-2-configure-supported-devices"></a>Paso 2: Configuración de dispositivos compatibles

Los dispositivos de usuario aptos para la captura de pruebas forenses deben incorporarse al [portal de cumplimiento Microsoft Purview](/microsoft-365/compliance/microsoft-365-compliance-center) y deben tener instalado el cliente de Microsoft Purview. 

>[!IMPORTANT]
>El cliente de Microsoft Purview recopila automáticamente datos de diagnóstico generales relacionados con la configuración del dispositivo y las métricas de rendimiento. Esto incluye datos sobre errores críticos, consumo de RAM, errores de proceso y otros datos. Estos datos nos ayudan a evaluar el estado del cliente e identificar cualquier problema. Para obtener más información sobre cómo se pueden usar los datos de diagnóstico, consulte Uso de software con servicios en línea en los [Términos del producto de Microsoft](https://www.microsoft.com/licensing/product-licensing/products).

Para obtener una lista de los requisitos de dispositivo y configuración, consulte [Información sobre las pruebas forenses (versión preliminar).](insider-risk-management-forensic-evidence.md#device-and-configuration-requirements) Para incorporar dispositivos compatibles, complete los pasos descritos en el artículo [Introducción a los dispositivos de Windows 10 y Windows 11 a Microsoft 365](/microsoft-365/compliance/device-onboarding-overview). 

Para instalar el cliente de Microsoft Purview, siga estos pasos:

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Insider Risk Management** > **Prueba forense (versión preliminar)** > **Instalación del cliente**.
2. Seleccione **Descargar paquete del instalador (versión x64)** para descargar el paquete de instalación para Windows.
3. Después de descargar el paquete de instalación, use el método que prefiera para instalar el cliente en los dispositivos de los usuarios. Estas opciones pueden incluir la instalación manual del cliente en dispositivos o herramientas para ayudar a automatizar la instalación del cliente:

    - **Microsoft Endpoint Manager**: [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) es una solución integrada para administrar todos los dispositivos. Microsoft reúne [Configuration Manager](/mem/configmgr/core/understand/introduction) y [Intune](/mem/intune/fundamentals/what-is-intune), sin una migración compleja y con licencias simplificadas.
    - **Soluciones de administración de dispositivos de terceros**: si su organización usa soluciones de administración de dispositivos de terceros, consulte la documentación de estas herramientas para instalar el cliente.


### <a name="step-3-configure-settings"></a>Paso 3: Configurar opciones

Las pruebas forenses tienen varias opciones de configuración que proporcionan flexibilidad para los tipos de actividad de usuario relacionada con la seguridad capturada, captura de parámetros, límites de ancho de banda y opciones de captura sin conexión. La captura de pruebas forenses le permite crear directivas basadas en sus requisitos en unos pocos pasos y agregar usuarios a una directiva requiere una autorización doble.

Para configurar la configuración de pruebas forenses, complete los pasos siguientes:

1. En la [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Administración de riesgos** >  internos **Pruebas forenses (versión preliminar)** > **Configuración de evidencia forense**.
2. Seleccione **Captura de evidencia forense** para habilitar la compatibilidad con la captura en las directivas de pruebas forenses. Si se desactiva más adelante, se quitarán todos los usuarios agregados anteriormente para las directivas de pruebas forenses.

    >[!IMPORTANT]
    >El cliente de Microsoft Purview que se usa para capturar la actividad en los dispositivos de los usuarios tiene licencia bajo el Uso de software con los Servicios en línea en los [Términos del producto de Microsoft](https://www.microsoft.com/licensing/product-licensing/products). Tenga en cuenta que los clientes son los únicos responsables de usar la solución de administración de riesgos internos, incluido el cliente de Microsoft Purview, en cumplimiento de todas las leyes aplicables.
 
1. En la sección **Captura de ventana** , defina cuándo iniciar y detener la captura de actividad. Los valores disponibles son *10 segundos*, *30 segundos*, *1 minuto*, *3 minutos* o *5 minutos*.
1. En la sección **Cargar límite de ancho de banda** , defina la cantidad de datos de captura que se cargarán en la cuenta de almacenamiento de datos por usuario y día. Los valores disponibles son *100 MB*, *250 MB*, *500 MB*, *1 GB* o *2 GB*.
1. En la sección **Captura sin conexión** , habilite la captura sin conexión si es necesario. Cuando se habilita, la actividad sin conexión de los usuarios se captura y carga en la cuenta de almacenamiento de datos la próxima vez que estén en línea.
1. En la sección **Límite de caché de captura sin conexión** , defina el tamaño máximo de caché que se almacenará en los dispositivos de los usuarios cuando esté habilitada la captura sin conexión. Los valores disponibles son *100 MB*, *250 MB*, *500 MB*, *1 GB* o *2 GB*.
1. Seleccione **Guardar**.

### <a name="step-4-create-a-policy"></a>Paso 4: Crear una directiva

Las directivas de pruebas forenses definen el ámbito de la actividad de usuario relacionada con la seguridad que se va a capturar en los dispositivos configurados. Puede tener una directiva que capture todas las actividades que los usuarios aprobados realizan en sus dispositivos (todas las pulsaciones de tecla, movimientos del mouse, etc.) y directivas adicionales que capturan solo actividades específicas (como imprimir o filtrar archivos). Una vez creadas, incluirá estas directivas en solicitudes de pruebas forenses para controlar qué actividad capturar para los usuarios cuyas solicitudes se aprueban.

1. En el [portal de cumplimiento Microsoft Purview](https://compliance.microsoft.com/), vaya a **Insider Risk Management** > **Forense evidence (preview)Forensic evidence policies (Directivas de pruebas** **forenses**). > 
2. Seleccione **Crear directiva de evidencia forense**.
3. En la página **Ámbito** , elegirá el ámbito de la actividad de usuario relacionada con la seguridad que se va a capturar. Seleccione una de las siguientes opciones:

    - **Actividades específicas**: esta opción solo captura las actividades detectadas por las directivas en las que se incluyen los usuarios. Estas actividades se definen mediante los indicadores seleccionados en las directivas de pruebas forenses. Las capturas de esta opción estarán disponibles para su revisión en la pestaña **Pruebas forenses (versión preliminar)** del panel **Alertas** o **casos** .
    - **Todas las actividades**: esta opción captura cualquier actividad realizada por los usuarios. Esto incluye el movimiento del mouse, las pulsaciones de teclas y todas las actividades definidas por indicadores de riesgo internos. Las capturas de esta opción estarán disponibles para su revisión en la pestaña **Pruebas forenses (versión preliminar)** del panel **Informes de actividad de usuario (versión preliminar).**
4. Seleccione **Siguiente**.
5. En la página **Nombre y descripción**, siga los siguientes campos:
    - **Nombre (obligatorio):** escriba un nombre descriptivo para la directiva de pruebas forenses. Este nombre no se puede cambiar después de crear la directiva.
    - **Descripción (opcional):** escriba una descripción para la directiva de pruebas forenses.
6. Seleccione **Siguiente**.
7. Si ha seleccionado la opción **Todas las actividades** en el paso 3, la página **Actividades del dispositivo** le dirigirá el último paso del Asistente para directivas. No hay ninguna actividad de dispositivo que configurar cuando se selecciona la opción **Todas las actividades** .

    Si ha seleccionado la opción **Actividades específicas** en el paso 3, seleccionará las actividades de dispositivo que se van a capturar en la página **Actividades del dispositivo** . La directiva capturará solo las actividades seleccionadas. Si los indicadores no se pueden seleccionar, deberá activar estos indicadores para su organización para poder seleccionar estos indicadores en la directiva de pruebas forenses. 

    Después de seleccionar los indicadores, seleccione **Siguiente**.
8. En la página **Finalizar** , revise la configuración que ha elegido para la directiva y las sugerencias o advertencias de las selecciones. Seleccione **Editar** para cambiar cualquiera de los valores de la directiva o seleccione **Enviar** para crear y activar la directiva.

Después de completar los pasos de configuración de la directiva, continúe con el paso 5.

### <a name="step-5-define-and-approve-users-for-capturing"></a>Paso 5: Definir y aprobar usuarios para la captura

Para poder capturar actividades de usuario relacionadas con la seguridad, los administradores deben seguir el proceso de autorización dual en pruebas forenses. Este proceso exige que los usuarios aplicables de la organización definan y aprueben la habilitación de la captura visual para usuarios específicos.

>[!IMPORTANT]
>Para la versión preliminar, un máximo de 5 usuarios simultáneos son aptos para la captura de pruebas forenses. La captura de grupos no se admite en la versión preliminar.

Debe solicitar que la captura de pruebas forenses esté habilitada para usuarios específicos. Cuando se envía una solicitud, los aprobadores de su organización reciben una notificación por correo electrónico y pueden aprobar o rechazar la solicitud. Si se aprueba, el usuario aparecerá en la pestaña **Usuarios aprobados** y será apto para la captura.

- Para solicitar la aprobación de la captura de pruebas forenses para los usuarios, complete [estos pasos de configuración](/microsoft-365/compliance/insider-risk-management-forensic-evidence-manage#request-capturing-approvals).
- Para aprobar (o rechazar) solicitudes de captura de pruebas forenses para los usuarios, complete [estos pasos de configuración](/microsoft-365/compliance/insider-risk-management-forensic-evidence-manage#approve-capturing-requests).

## <a name="next-steps"></a>Pasos siguientes

Después de configurar la directiva de pruebas forenses, las primeras capturas de clip aptas pueden tardar hasta 48 horas en estar disponibles para su revisión en alertas para otras directivas o como actividad en **informes de actividad de usuario**. Para obtener más información sobre cómo administrar pruebas forenses y revisar capturas de clips, consulte el artículo [Administración de pruebas forenses de administración de riesgos de información](/microsoft-365/compliance/insider-risk-management-forensic-evidence-manage) .
