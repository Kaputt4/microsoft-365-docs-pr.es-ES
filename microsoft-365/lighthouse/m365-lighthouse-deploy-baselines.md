---
title: Implementación de líneas base de Microsoft 365 Lighthouse
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
ms.reviewer: shcallaw, kywirpel
audience: Admin
ms.topic: article
ms.service: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: En el caso de los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo implementar líneas base Microsoft 365 Lighthouse.
ms.openlocfilehash: cf23c84f4be87f6e6f9618097822c9ea138a64ae
ms.sourcegitcommit: 87283bb02ca750286f7c069f811b788730ed5832
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2022
ms.locfileid: "68659047"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Implementación de líneas base de Microsoft 365 Lighthouse

Microsoft 365 Lighthouse permite implementar configuraciones estándar de inquilinos administrados para proteger usuarios, dispositivos y datos dentro de los inquilinos del cliente. Hay siete [configuraciones de línea base predeterminadas](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) que vienen estándar con Lighthouse. Con la característica de plan de implementación de Lighthouse, puede ver, probar e implementar configuraciones de seguridad en todos los inquilinos. Un plan de implementación solo está disponible para los inquilinos activos. Una vez que se incorpora un inquilino, puede comparar la configuración actual de los clientes con la configuración de línea base predeterminada y realizar las acciones adecuadas.

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que usted y los inquilinos de sus clientes cumplen los requisitos enumerados en [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="view-a-deployment-plan"></a>Visualización de un plan de implementación

1. En el panel de navegación izquierdo de Lighthouse, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el inquilino que desea ver.

3. Seleccione la pestaña **Plan de implementación** .

    La pestaña Plan de implementación proporciona una lista de cada paso de implementación que se puede buscar y exportar que se incluye en el plan de implementación del inquilino que incluye la siguiente información para cada paso de implementación:

    | Columna            | Descripción |
    |-----------------|-------------------------------------------------------------------------------------|
    | Paso de implementación | Descripción del paso de implementación.                                                     |
    | Estado          | Estado del paso de implementación.                                                  |
    | Línea base        | Línea base desde la que se deriva el paso de implementación.                             |
    | Categoría        | Si el paso de implementación está asociado a la administración de dispositivos, identidades o datos. |
    | Actualizado por última vez    | Fecha en la que se actualizó por última vez el paso de implementación.                             |

4. En la lista de pasos de implementación, seleccione el paso de implementación que desea revisar.

    La página de detalles del paso de implementación proporciona la siguiente información:

    | Columna            | Descripción |
    |-------------------|-----------------------------------------------------------------------------------------------|
    | Resumen        | Un resumen del propósito del paso de implementación.                                         |
    | Línea base       | Línea base desde la que se deriva el paso de implementación.                             |
    | Categoría       | Si el paso de implementación está asociado a la administración de dispositivos, identidades o datos. |
    | SKU necesaria   | SKU necesarias para completar el paso de implementación.                                      |
    | Impacto en el usuario    | Impacto de la implementación del paso en los usuarios del inquilino.                             |
    | Para los usuarios | Vínculos a recursos que los usuarios del inquilino pueden resultar útiles.                             |
    | Pasos siguientes     | Vínculos e instrucciones sobre los pasos siguientes aplicables.                                |

    Los pasos de implementación incluyen uno o varios procesos que deben completarse. La página de detalles del paso de implementación incluye una tabla que enumera cada proceso incluido en el paso de implementación y proporciona la siguiente información:

    | Columna            | Descripción |
    |-------------------|-------------------------------------------------------------|
    | Nombre del proceso      | Nombre del proceso, que, cuando se selecciona, abrirá la pestaña del proceso aplicable.          |
    | Estado            | Estado detectado de las configuraciones de configuración incluidas en el proceso de implementación.           |
    | Portal de administración | Portal a través del cual se administran las configuraciones asociadas al proceso. |

## <a name="deploy-a-deployment-step"></a>Implementación de un paso de implementación

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el inquilino que desea ver.

3. Seleccione la pestaña **Plan de implementación** .

4. En la lista de pasos de implementación, seleccione el paso de implementación que desea implementar.

5. Seleccione **Revisar e implementar**.

6. En el panel **Confirmar configuración** , seleccione **Implementar**.

## <a name="test-a-deployment-step"></a>Prueba de un paso de implementación

Para los pasos de implementación implementados a través de directivas de acceso condicional, puede comparar la configuración del paso de implementación con la configuración de las directivas existentes sin implementar la configuración en el inquilino.

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el inquilino que desea ver.

3. Seleccione la pestaña **Plan de implementación** .

4. En la lista de pasos de implementación, seleccione el paso de implementación que desea implementar.

5. Seleccione **Revisar e implementar**.

6. En el panel **Confirmar configuración** , seleccione **Probar esta configuración sin una implementación**.

7. Seleccione **Probar**.

El panel **Confirmar configuración** se cierra y muestra la comparación de directivas. Cada directiva del inquilino existente aparece en la tabla Configuración detectada.

La tabla Configuración detectada enumera cada directiva existente y resume el número de configuraciones y, entre paréntesis, el número de usuarios que tienen uno de los siguientes estados:

| Estado         | Descripción
|-------------|------------------------------------------------------------|
| Configuración igual       | Número total de opciones de configuración en el plan de implementación con un valor equivalente en el inquilino.      |
| Configuración que falta     | Número total de opciones de configuración en el plan de implementación que faltan un valor en el inquilino.      |
| Configuración en conflicto | Número total de opciones de configuración del plan de implementación que tienen un valor en conflicto en el inquilino. |

También puede ver la configuración detectada en una tabla modular que proporciona detalles de configuración para cada directiva en el nivel de configuración y de usuario y puede ordenar la tabla por los siguientes estados de configuración:

| Estado         | Descripción
|-------------|------------------------------------------------------------|
| Configuración total       | Número total de opciones de configuración que se incluyen en el proceso de implementación.                        |
| Configuración igual       | Número total de opciones de configuración en el plan de implementación con un valor equivalente en el inquilino.      |
| Configuración que falta     | Número total de opciones de configuración en el plan de implementación que faltan un valor en el inquilino.      |
| Configuración en conflicto | Número total de opciones de configuración del plan de implementación que tienen un valor en conflicto en el inquilino. |
| Configuración adicional       | Número total de opciones de configuración con un valor en el inquilino, pero sin valor en el plan de implementación.     |

Cuando se realiza esta comparación, Lighthouse actualiza automáticamente el estado Detectado, Estado de implementación y Paso de implementación.

Si no hay directivas existentes que comparar, seleccione **Revisar e implementar** para volver a abrir el panel **Confirmar configuración** y, a continuación, seleccione **Implementar**.

Si hay directivas existentes con las que comparar, puede hacer lo siguiente:

- Edite la configuración del plan de implementación y vuelva a probarlas con las directivas existentes, seleccione **Revisar e implementar** para volver a abrir el panel **Confirmar configuración** , ajustar los valores de configuración deseados, volver a seleccionar la casilla y, a continuación, seleccione **Probar** en la parte inferior del panel.

- Edite las directivas existentes en el portal de administración aplicable para conciliar las diferencias:
  - Aplicación de la configuración que falta
  - Edición de la configuración en conflicto
  - Eliminación de directivas existentes

Para cada proceso de implementación que se puede automatizar a través de Lighthouse, hay un estado de implementación y un estado detectado.

- El estado detectado indica hasta qué punto la configuración de este proceso está implementada actualmente.
- El estado de la implementación es el estado de la última implementación en el inquilino.

Puede implementar los pasos de implementación independientemente de las directivas existentes, pero no se considerarán completas hasta que no haya ninguna configuración en conflicto. El error al resolver esta configuración en conflicto puede afectar a la experiencia del usuario. 

La implementación del paso de implementación en instancias en las que hay valores de configuración iguales presentes en el inquilino a partir de una directiva existente da como resultado la duplicación de la configuración existente dentro del inquilino, pero no afectará a la experiencia del usuario. 

Se proporcionan configuraciones adicionales para su reconocimiento, pero no es necesario que tome medidas.

Para obtener más información sobre la administración de conflictos de directivas, consulte la [documentación de acceso condicional de Azure AD](/azure/active-directory/conditional-access/).

## <a name="update-deployment-step-status"></a>Actualización del estado del paso de implementación

1. En la página de navegación izquierda de Lighthouse, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el inquilino que desea ver.

3. Seleccione la pestaña **Plan de implementación** .

4. En la lista de pasos de implementación, seleccione el paso de implementación que desea actualizar.

5. En la lista desplegable **To address (Para dirección** ), seleccione un estado de acción.

    | Estado de la acción | Descripción |
    |--|--|
    | Para solucionarlo | Estado predeterminado de todos los pasos de implementación que NO incluyen varios procesos de paso de implementación. |
    | Planificado | El paso de implementación se ha planeado, pero aún no se ha completado. |
    | Riesgo aceptado | El usuario ha aceptado el riesgo que, de lo contrario, se habría evitado aplicando el paso de implementación. |
    | Riesgo resuelto a través de terceros | El riesgo se ha resuelto mediante la implementación de una aplicación o software de terceros. |
    | Resuelto a través de medios alternativos | El riesgo se ha resuelto a través de medios alternativos, como la implementación de una herramienta interna. |
    | Configuración manual aplicada | La configuración prescrita en el plan de implementación se ha aplicado manualmente. |

## <a name="share-deployment-step"></a>Paso de implementación para compartir

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el inquilino que desea ver.

3. Seleccione la pestaña **Plan de implementación** .

4. En la lista de pasos de implementación, seleccione el paso de implementación que desea compartir.

5. En la lista desplegable **Compartir** , seleccione una de las siguientes opciones.

    | Opción  | Descripción |
    |-----------|-------------------------------------------------------------------------|
    | Copiar  | Copia un vínculo al paso de implementación en el Portapapeles.                                     |
    | Correo electrónico | Abre el nuevo mensaje de correo electrónico en el equipo local e inserta un vínculo al paso de implementación. |

    El vínculo permite a cualquier usuario con permisos de su organización ver el plan de implementación del inquilino.


## <a name="related-content"></a>Contenido relacionado

[Información general sobre el uso de líneas base de Microsoft 365 Lighthouse para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)\
[Información general de la página Windows 365 (PC en la nube) de Microsoft 365 Lighthouse](m365-lighthouse-tenants-page-overview.md) (artículo)\
[preguntas más frecuentes sobre Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (artículo)\
[Configuración de la seguridad del portal de Microsoft 365 Lighthouse](m365-lighthouse-configure-portal-security.md) (artículo) 