---
title: Introducción a la visibilidad y la información
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
description: Introducción a la visibilidad y la información.
ms.openlocfilehash: fc7a76154437b57876a52cad5de1f637b8da7bc0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201942"
---
# <a name="get-started-with-visibility-and-insights"></a>Introducción a la visibilidad y la información

>*[Guía de licencias de Microsoft 365 para la seguridad y el cumplimiento](https://aka.ms/ComplianceSD).*

El primer lugar para comenzar es el panel de gobernanza de aplicaciones en [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Tenga en cuenta que su cuenta de inicio de sesión debe tener uno de estos [roles de administrador de gobernanza de aplicaciones](app-governance-get-started.md#administrator-roles) para ver cualquier dato de gobernanza de aplicaciones.

![Página de información general de gobernanza de aplicaciones en el Centro de cumplimiento de Microsoft 365](..\media\manage-app-protection-governance\mapg-cc-overview.png)

También puede acceder al panel de gobernanza de aplicaciones desde **Office 365 > Centro de cumplimiento de Microsoft 365 > Gobernanza de aplicaciones > Información general**.

## <a name="whats-available-on-the-dashboard"></a>Lo que está disponible en el panel

El panel contiene un resumen de los componentes del ecosistema de aplicaciones Microsoft 365 en el usuario:

- **Resumen de usuarios**: rel recuento de categorías de alertas y aplicaciones clave.
- **Principales alertas**: las diez alertas activas más recientes del espacio empresarial
- **Acceso a datos y recursos**: pase el mouse por cada columna de mes en el gráfico para ver el valor correspondiente.
  - **Acceso a datos durante los últimos cuatro meses**: rastrea la totalidad de datos a los que acceden las aplicaciones del espacio empresarial a través de la API de Graph durante los últimos cuatro meses naturales. Actualmente solo incluye el uso de carga y descarga de archivos y el del correo.
  - **Acceso a los datos de los recursos principales durante los últimos cuatro meses**: uso de datos de los últimos cuatro meses naturales desglosados por tipo de recurso. Actualmente solo incluye el uso de carga y descarga de archivos y el del correo.
- **Mejore la protección y la gobernanza de sus aplicaciones**: acciones recomendadas tales como la creación de una directiva de permisos o de uso de aplicaciones.
- **Principales aplicaciones por categorías**: las aplicaciones principales ordenadas por estas categorías:
  
  - **Todas las categorías**: se ordena entre todas las categorías disponibles.
  - **Privilegios elevados**: privilegios elevados es una categoría determinada internamente basada en el aprendizaje automático y las señales de la plataforma.
  - **Privilegios excesivos**: cuando la gobernanza de aplicaciones recibe datos de telemetría que indican que no se ha usado un permiso concedido a una aplicación en los últimos 90 días, esa aplicación tiene privilegios excesivos. La gobernanza de aplicaciones debe funcionar durante al menos 90 días para determinar si alguna aplicación tiene privilegios excesivos.  
  - **Sin verificar**: las aplicaciones que no han recibido [certificación de editorial](/azure/active-directory/develop/publisher-verification-overview) se consideran sin verificar.
  - **Solo aplicaciones**: [los permisos de aplicaciones](/azure/active-directory/develop/v2-permissions-and-consent#permission-types) se utilizan por aplicaciones que pueden ejecutarse sin un usuario que haya iniciado sesión. Las aplicaciones con permisos para acceder a los datos en el usuario son potencialmente de mayor riesgo.
  - **Aplicaciones nuevas**: nuevas aplicaciones de Microsoft 365 que se han registrado en los últimos siete días.  

## <a name="view-app-insights"></a>Ver información de la aplicación

Uno de los principales puntos de valor para el gobierno de las aplicaciones es la posibilidad de ver rápidamente las alertas y la información de las aplicaciones. Para ver la información de sus aplicaciones:

1. En la página del portal de gobernanza de aplicaciones, seleccione **Aplicaciones**.
1. Use la lista desplegable **Categorías** para seleccionar entre las siguientes opciones:
    - Todas las aplicaciones
    - Privilegio alto
    - Demasiados privilegios
    - Editor no verificado
    - Solo aplicación
    - Aplicaciones nuevas
1. Seleccione el nombre de una aplicación para ver los detalles. Al seleccionar un nombre de aplicación, se abre un panel de detalles a la derecha, como se muestra en el siguiente gráfico.

:::image type="content" source="../media/manage-app-protection-governance/app-governance-app-insight.png" alt-text="Imagen que muestra el panel de detalles de una aplicación seleccionada.":::

> [!NOTE]
> Las aplicaciones que se muestran dependerán de las aplicaciones presentes en el inquilino.

Guardar la consulta permite guardar la lista de filtros definida en la vista actual. Esto podría ahorrar tiempo al seleccionar un subconjunto de datos en el futuro.

El panel de detalles también le permite ver el uso de la aplicación durante los últimos 30 días, los usuarios que han dado su consentimiento a la aplicación y los permisos asignados a la aplicación. Un administrador podría revisar la actividad y los permisos de una aplicación que genera alertas y tomar la decisión de deshabilitar la aplicación mediante el botón **Deshabilitar aplicación** del panel Detalles.

## <a name="next-step"></a>Paso siguiente

[Obtenga información detallada sobre una aplicación específica](app-governance-visibility-insights-view-apps.md).
