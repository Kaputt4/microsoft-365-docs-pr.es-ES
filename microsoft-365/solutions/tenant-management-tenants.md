---
title: Paso 1. Su microsoft 365 para inquilinos empresariales
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- highpri
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Implemente y administre uno o varios inquilinos de Microsoft 365, con opciones para ubicaciones multigeográficas y móviles.
ms.openlocfilehash: a1fdf6cf86fd7e889712e020f5aaeb33284c96ae
ms.sourcegitcommit: 0af064e8b6778060f1bd365378d69b16fc9949b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2022
ms.locfileid: "67730581"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Paso 1. Su microsoft 365 para inquilinos empresariales

Una de las primeras decisiones del inquilino es cuántas tener. Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365. Su inquilino de Azure AD correspondiente también es distinto, único e independiente de todos los demás inquilinos de Microsoft 365.

## <a name="single-tenant"></a>Inquilino único
Tener un solo inquilino simplifica muchos aspectos del uso de Microsoft 365 por parte de la organización. Un único inquilino significa un único inquilino de Azure AD con un único conjunto de cuentas, grupos y directivas. Los permisos y el uso compartido de recursos en toda la organización se pueden realizar a través de este proveedor de identidades central.

Un único inquilino proporciona la experiencia de colaboración y productividad más enriquecida y simplificada para los usuarios.

Este es un ejemplo que muestra la ubicación predeterminada y el inquilino de Azure AD de un inquilino de Microsoft 365.

![Un único inquilino de Microsoft 365 con su inquilino de Azure AD.](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Varios inquilinos

Hay muchas razones por las que su organización podría tener varios inquilinos:

- Aislamiento administrativo
- TI descentralizada
- Decisiones históricas
- Fusiones, adquisiciones o desinversiones
- Separación clara de la personalización de marca para organizaciones conglomerados
- Inquilinos de preproducción, prueba o espacio aislado

Este es un ejemplo de una organización que tiene dos inquilinos (inquilino A y inquilino B) en la misma ubicación geográfica del centro de datos predeterminado. Cada inquilino como inquilino de Azure AD independiente.

![Varios inquilinos de Microsoft 365 con sus propios inquilinos de Azure AD.](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Cuando tiene varios inquilinos, hay restricciones y consideraciones adicionales al administrarlos y proporcionar servicios a los usuarios.

### <a name="inter-tenant-collaboration"></a>Colaboración entre inquilinos

Si desea que los usuarios colaboren de forma más eficaz en distintos inquilinos de Microsoft 365 de forma segura, las opciones de colaboración entre inquilinos incluyen el uso de una ubicación central para archivos y conversaciones, el uso compartido de calendarios, el uso de mensajería instantánea, llamadas de audio y vídeo para la comunicación y la protección del acceso a recursos y aplicaciones.

Para obtener más información, consulte [Colaboración entre inquilinos de Microsoft 365](../enterprise/microsoft-365-inter-tenant-collaboration.md).

### <a name="cross-tenant-mailbox-migration-preview"></a>Migración de buzones entre inquilinos (versión preliminar)

Antes de la migración de buzones entre inquilinos (en versión preliminar), al mover Exchange Online buzones entre inquilinos, debe desconectar completamente un buzón de usuario de su inquilino actual (el inquilino de origen) al entorno local y, a continuación, incorporarlos a un nuevo inquilino (el inquilino de destino). Con la nueva característica de migración de buzones entre inquilinos, los administradores de inquilinos de los inquilinos de origen y de destino pueden mover buzones entre los inquilinos con dependencias de infraestructura mínimas en sus sistemas locales. Esto elimina la necesidad de incorporar buzones de correo fuera del panel e incorporarlos.

Estos son dos inquilinos de ejemplo y sus buzones antes de la migración de buzones entre inquilinos.

![Varios inquilinos de Microsoft 365 y sus buzones.](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

En esta ilustración, dos inquilinos independientes tienen sus propios dominios y un conjunto de buzones de Exchange.

Este es el inquilino de destino (inquilino A) después de la migración del buzón entre inquilinos.

![Inquilino de destino después de la migración del buzón entre inquilinos.](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

En esta ilustración, un único inquilino tiene dominios y ambos conjuntos de buzones de Exchange.

Para obtener más información, vea [Migración de buzones entre inquilinos](../enterprise/cross-tenant-mailbox-migration.md).

### <a name="tenant-to-tenant-migrations"></a>Migraciones de espacio empresarial a espacio empresarial

Hay varios enfoques arquitectónicos para fusiones, adquisiciones, desinversiones y otros escenarios que pueden llevar a migrar un inquilino existente de Microsoft 365 a un nuevo inquilino. 

Para obtener instrucciones [detalladas, consulte Migraciones de inquilino a inquilino de Microsoft 365](../enterprise/microsoft-365-tenant-to-tenant-migrations.md).

## <a name="multi-geo-for-a-tenant"></a>Multigeográfico para un inquilino

Con Microsoft 365 Multi-Geo, puede aprovisionar y almacenar datos en reposo en las otras ubicaciones geográficas del centro de datos que ha elegido para cumplir los requisitos de residencia de datos y, al mismo tiempo, desbloquear la implementación global de experiencias de productividad modernas para los trabajadores.

En un entorno multigeográfico, el inquilino de Microsoft 365 consta de una ubicación predeterminada o central donde se creó originalmente la suscripción de Microsoft 365 y una o varias ubicaciones satélite. En un inquilino multigeográfico, la información sobre las ubicaciones geográficas, los grupos y la información de usuario se domina en un inquilino global de Azure AD. Dado que la información del inquilino se domina de forma centralizada y se sincroniza en cada ubicación geográfica, las experiencias de colaboración que implican a cualquier usuario de la empresa se comparten entre las ubicaciones.

Este es un ejemplo de una organización que tiene su ubicación predeterminada en Europa y una ubicación por satélite en Norteamérica. Ambas ubicaciones comparten el mismo inquilino global de Azure AD para el único inquilino de Microsoft 365.

![Ejemplo de un inquilino de Microsoft 365 multigeográfico.](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Para más información, vea [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Traslado de datos principales a una nueva ubicación geográfica del centro de datos

Microsoft continúa abriendo nuevas zonas geográficas de centros de datos para los servicios de Microsoft 365. Estas nuevas zonas geográficas del centro de datos agregan recursos de capacidad y proceso para dar soporte a nuestro crecimiento continuo de la demanda y el uso de los clientes. Además, las nuevas zonas geográficas del centro de datos ofrecen residencia de datos en la ubicación geográfica para los datos principales de los clientes.

Aunque la apertura de una nueva ubicación geográfica del centro de datos no afecta a usted y a los datos principales almacenados en una ubicación geográfica del centro de datos ya existente, Microsoft le permite solicitar una migración temprana de los datos principales del cliente de su organización en reposo a una nueva ubicación geográfica del centro de datos.

Este es un ejemplo en el que se ha movido un inquilino de Microsoft 365 de la geolocalía del centro de datos de la Unión Europea (UE) al que se encuentra en el Reino Unido (Reino Unido).

![Ejemplo de traslado de un inquilino de Microsoft 365 entre las zonas geográficas del centro de datos.](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Para obtener más información, consulte [Traslado de datos principales a nuevas geoáreas del centro de datos de Microsoft 365](../enterprise/moving-data-to-new-datacenter-geos.md).

## <a name="products-and-licenses-for-a-tenant"></a>Productos y licencias para un inquilino

El inquilino de Microsoft 365 se crea al comprar el primer producto, como Microsoft 365 E3. Junto con el producto son licencias, a las que se les cobra una cuota mensual o anual. A continuación, un administrador asigna una licencia disponible de uno de los productos a una cuenta de usuario, ya sea directamente o a través de la pertenencia a grupos. En función de las necesidades empresariales de su organización, es posible que tenga un conjunto de productos, cada uno con su propio grupo de licencias. 

Para determinar el conjunto de productos y el número de licencias para cada uno, es necesario planear lo siguiente:

- Asegúrese de que tiene suficientes licencias para las cuentas de usuario que necesitan características avanzadas.
- Evite quedarse sin licencias o tener demasiadas licencias sin asignar, en función de los cambios en el personal de la organización.


## <a name="results-of-step-1"></a>Resultado del paso 1

Para los inquilinos de Microsoft 365 para empresas, ha determinado lo siguiente:

- Cuántos inquilinos tiene o necesita.
- Para cada inquilino, qué productos y licencias se deben comprar.
- Si un inquilino debe ser multigeográfico para cumplir con los requisitos de residencia de datos.
- Si necesita configurar la colaboración entre inquilinos.
- Si necesita migrar un inquilino a otro.
- Si necesita mover datos principales de una ubicación geográfica del centro de datos a uno nuevo.

Este es un ejemplo de un nuevo inquilino.

![Ejemplo de un nuevo inquilino.](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

En esta ilustración, el inquilino tiene:

- Ubicación predeterminada correspondiente a una ubicación geográfica del centro de datos de Microsoft 365.
- Un conjunto de productos y licencias.
- Conjunto de aplicaciones de productividad en la nube, algunas de las cuales son específicas de los productos.
- Un inquilino de Azure AD que contiene cuentas de administrador globales y un nombre de dominio DNS inicial.

A medida que pasemos por los pasos adicionales de esta solución, crearemos esta figura.

## <a name="ongoing-maintenance-for-tenants"></a>Mantenimiento continuo de inquilinos

De forma continua, es posible que tenga que:

- Agregue un nuevo inquilino.
- Agregue nuevos productos a un inquilino con un número inicial de licencias.
- Cambie el conjunto de licencias de un producto de un inquilino para ajustarlo a los requisitos de personal cambiantes.
- Mueva los datos principales de un inquilino a una nueva ubicación geográfica del centro de datos.
- Agregue Multi-Geo para los requisitos de residencia de datos.
- Configurar la colaboración entre inquilinos.

## <a name="next-step"></a>Paso siguiente

[![Paso 2. Optimice el inquilino para obtener acceso a la red.](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Continúe con [las redes](tenant-management-networking.md) para proporcionar redes óptimas desde los trabajadores a los servicios en la nube de Microsoft 365.
