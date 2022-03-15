---
title: Implementar Microsoft 365 Lighthouse base
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Para los proveedores de servicios administrados (MSP) que usan Microsoft 365 Lighthouse, obtenga información sobre cómo implementar Microsoft 365 Lighthouse líneas base.
ms.openlocfilehash: 0e19843ee6cfebaf9b37e10929884d0671608451
ms.sourcegitcommit: 8423f47fce3905a48db9daefe69c21c841da43a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2022
ms.locfileid: "63504501"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>Implementar Microsoft 365 Lighthouse base

Microsoft 365 Lighthouse permite implementar configuraciones estándar de inquilino administrado para proteger usuarios, dispositivos y datos dentro de los inquilinos de clientes. Hay siete [configuraciones de línea base predeterminadas](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) que vienen de serie con Lighthouse. Con la característica plan de implementación de Lighthouse, puede ver, probar e implementar configuraciones de seguridad en todos los inquilinos. Un plan de implementación solo está disponible para los inquilinos activos. Una vez incorporado un inquilino, puede comparar la configuración actual de los clientes con la configuración de línea base predeterminada y realizar las acciones adecuadas.

## <a name="before-you-begin"></a>Antes de empezar

Asegúrese de que usted y sus inquilinos de clientes cumplen los requisitos enumerados en [Requisitos para Microsoft 365 Lighthouse](m365-lighthouse-requirements.md).

## <a name="view-a-deployment-plan"></a>Ver un plan de implementación

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el espacio empresarial que desea ver.

3. Seleccione la **pestaña Plan de** implementación.

    La pestaña Plan de implementación proporciona una lista exportable y de búsqueda de cada paso de implementación que se incluye en el plan de implementación del inquilino que incluye la siguiente información para cada paso de implementación:

    | Columna            | Descripción |
    |-----------------|-------------------------------------------------------------------------------------|
    | Paso de implementación | Descripción del paso de implementación.                                                     |
    | Estado          | El estado del paso de implementación.                                                  |
    | Línea base        | Línea base desde la que se deriva el paso de implementación.                             |
    | Categoría        | Si el paso de implementación está asociado con la administración de dispositivos, identidad o datos. |
    | Actualizado por última vez    | La fecha en la que se actualizó por última vez el paso de implementación.                             |

4. En la lista, seleccione un paso de implementación que desee revisar.

    La página Paso de implementación proporciona la siguiente información:

    | Columna            | Descripción |
    |-------------------|-----------------------------------------------------------------------------------------------|
    | Resumen        | Un resumen del propósito del paso de implementación.                                         |
    | Línea base       | Línea base desde la que se deriva el paso de implementación.                             |
    | Categoría       | Si el paso de implementación está asociado con la administración de dispositivos, identidad o datos. |
    | SKU necesaria   | SKU necesarias para completar el paso de implementación.                                      |
    | Impacto en el usuario    | El impacto de implementar el paso para los usuarios del espacio empresarial.                             |
    | Para los usuarios | Los vínculos a recursos que los usuarios del inquilino pueden resultar útiles.                             |
    | Pasos siguientes     | Vínculos e instrucciones sobre los pasos siguientes aplicables.                                |

    Los pasos de implementación se componen de uno o varios procesos que deben completarse para cumplir los requisitos del paso de implementación. La página Paso de implementación incluye la tabla de proceso que enumera cada proceso incluido en el paso de implementación y proporciona la siguiente información:

    | Columna            | Descripción |
    |-------------------|-------------------------------------------------------------|
    | Nombre del proceso      | Nombre del proceso, que, cuando se selecciona, abrirá la pestaña Proceso correspondiente.          |
    | Estado            | Estado detectado de estas configuraciones de configuración incluidas en el proceso de implementación.           |
    | Portal de administración | Portal a través del cual se administran las opciones de configuración asociadas con el proceso. |

## <a name="deploy-a-deployment-step"></a>Implementar un paso de implementación

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el espacio empresarial que desea ver.

3. Seleccione la **pestaña Plan de** implementación.

4. En la lista Paso de implementación, seleccione el paso de implementación que desea implementar.

5. Seleccione **Revisar e implementar**.

6. En el **panel Confirmar configuraciones** , seleccione **Implementar**.

## <a name="test-a-deployment-step"></a>Probar un paso de implementación

Para los pasos de implementación implementados a través de directivas de acceso condicional, puede comparar las opciones de configuración del paso de implementación con las opciones de las directivas existentes sin implementar la configuración en el espacio empresarial.

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el espacio empresarial que desea ver.

3. Seleccione la **pestaña Plan de** implementación.

4. En la lista Paso de implementación, seleccione el paso de implementación que desea implementar.

5. Seleccione **Revisar e implementar**.

6. En el **panel Confirmar configuraciones** , seleccione **Probar esta configuración sin una implementación**.

7. Seleccione **Probar**.

El panel Confirmar configuraciones se cerrará y mostrará la comparación de directivas. Cada directiva dentro del espacio empresarial existente aparecerá en la tabla Configuración detectada.

La tabla Configuración detectada enumera cada directiva existente y resume el número de configuraciones y, entre paréntesis, el número de usuarios que se encuentran en uno de los siguientes estados:

| Estado         | Descripción
|-------------|------------------------------------------------------------|
| Configuración igual       | Número total de opciones de configuración en el plan de implementación con un valor equivalente en el espacio empresarial.      |
| Falta configuración     | Número total de opciones de configuración en el plan de implementación a las que falta un valor en el espacio empresarial.      |
| Configuración en conflicto | Número total de opciones de configuración del plan de implementación que tienen un valor en conflicto en el espacio empresarial. |

La configuración detectada también se puede ver en una tabla modular que proporciona detalles de configuración para cada directiva en el nivel de configuración y usuario y se puede ordenar por cada uno de los siguientes estados de configuración:

| Estado         | Descripción
|-------------|------------------------------------------------------------|
| Configuración total       | Número total de opciones de configuración que se incluyen en el proceso de implementación.                        |
| Configuración igual       | Número total de opciones de configuración en el plan de implementación con un valor equivalente en el espacio empresarial.      |
| Falta configuración     | Número total de opciones de configuración en el plan de implementación a las que falta un valor en el espacio empresarial.      |
| Configuración en conflicto | Número total de opciones de configuración del plan de implementación que tienen un valor en conflicto en el espacio empresarial. |
| Configuración adicional       | Número total de opciones de configuración con un valor en el espacio empresarial, pero ningún valor en el plan de implementación.     |

Cuando se realiza esta comparación, Lighthouse actualizará automáticamente el estado Detectado, el estado de implementación y el estado paso de implementación.

Si no hay directivas existentes que comparar, seleccione Revisar e implementar para volver a abrir el panel Confirmar configuraciones y seleccione Implementar.

Si hay directivas existentes con las que comparar, puede:

- Edite las opciones de configuración del plan de implementación y vuelva a probarlas con las directivas  existentes, seleccione Revisar e implementar para volver a abrir el panel Confirmar configuraciones, ajustar las opciones de configuración deseadas, volver a seleccionar la casilla y seleccionar Probar en la parte inferior del panel.

- Edite las directivas existentes en el portal de administración aplicable para conciliar las diferencias:
  - Aplicar la configuración que falta
  - Edición de configuraciones en conflicto
  - Eliminación de directivas existentes

Para cada proceso de implementación que se puede automatizar a través de Lighthouse, hay un estado de implementación y un estado detectado.

- El estado detectado indica en qué medida se implementa actualmente la configuración de este proceso.
- El estado de implementación es el estado de la última implementación en el espacio empresarial.

Los pasos de implementación se pueden implementar independientemente de las directivas existentes, pero no se considerarán completados hasta que no haya ninguna configuración en conflicto. Si no se resuelve esta configuración en conflicto, puede afectar a la experiencia del usuario. 

La implementación del paso de implementación en instancias en las que hay configuraciones iguales presentes en el espacio empresarial desde una directiva existente dará como resultado la duplicación de la configuración existente dentro del espacio empresarial, pero no afectará a la experiencia del usuario. 

Se proporciona una configuración adicional para el conocimiento, pero no es necesario que tomes medidas.

Para obtener más información sobre la administración de conflictos de directivas, [Azure AD documentación sobre acceso condicional](/azure/active-directory/conditional-access/).

## <a name="update-deployment-step-status"></a>Actualizar el estado del paso de implementación

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el espacio empresarial que desea ver.

3. Seleccione la **pestaña Plan de** implementación.

4. En la lista de pasos de implementación, seleccione el paso de implementación que desea actualizar.

5. En la **lista desplegable** Dirección para, seleccione un estado de acción.

    | Estado de la acción                        | Descripción      |
    |---------------------------------------|----------------------------------------|
    | Para dirección                        | El estado predeterminado de todos los pasos de implementación que NO incluyen varios procesos de pasos de implementación.      |
    | Planeado                           | El paso de implementación se ha planeado pero aún no se ha completado.                                      |
    | Riesgo aceptado                     | El usuario ha aceptado el riesgo que de lo contrario se habría evitado aplicando el paso de implementación. |
    | Riesgo resuelto a través de terceros | El riesgo se ha resuelto mediante la implementación de una aplicación o software de terceros.             |
    | Resuelto a través de medios alternativos  | El riesgo se ha resuelto a través de medios alternativos, como la implementación de una herramienta interna.    |
    | Configuración manual aplicada      | La configuración prescrita en el plan de implementación se ha aplicado manualmente.                         |

## <a name="share-deployment-step"></a>Paso de implementación de share

1. En la página de navegación izquierda, seleccione **Inquilinos**.

2. En la lista de inquilinos, seleccione el espacio empresarial que desea ver.

3. Seleccione la **pestaña Plan de** implementación.

4. En la lista Paso de implementación, seleccione el paso de implementación que desea compartir.

5. En la **lista** desplegable Compartir, seleccione una de las siguientes opciones.

    | Opción  | Descripción |
    |-----------|-------------------------------------------------------------------------|
    | Copiar  | Copia un vínculo al paso de implementación en el Portapapeles.                                     |
    | Correo electrónico | Abre el nuevo mensaje de correo electrónico en el equipo local e inserta un vínculo al paso de implementación. |

    El vínculo permitirá a cualquier persona con permisos de la organización ver el plan de implementación del inquilino.


## <a name="related-content"></a>Contenido relacionado

[Introducción al uso de líneas base para implementar configuraciones de inquilino estándar](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (artículo)\
[Microsoft 365 de la página faro Inquilinos](m365-lighthouse-tenants-page-overview.md) (artículo)\
[Microsoft 365 Lighthouse preguntas más frecuentes](m365-lighthouse-faq.yml) (artículo)\
[Configurar Microsoft 365 Lighthouse seguridad del portal](m365-lighthouse-configure-portal-security.md) (artículo) 