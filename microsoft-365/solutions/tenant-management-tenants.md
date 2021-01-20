---
title: Paso 1. Sus inquilinos de Microsoft 365 para empresas
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
ms.custom:
- Ent_Solutions
description: Implemente y administre uno o varios inquilinos de Microsoft 365, con opciones para ubicaciones multige geográficas y móviles.
ms.openlocfilehash: 567a2cb46e715ec560bf973a33ab83cfa63d403b
ms.sourcegitcommit: 99a7354e6a6b4d9d5202674ef57852d52a43fef6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49908720"
---
# <a name="step-1-your-microsoft-365-for-enterprise-tenants"></a>Paso 1. Sus inquilinos de Microsoft 365 para empresas

Una de las primeras decisiones del espacio empresarial es cuántos deben tener. Cada inquilino de Microsoft 365 es distinto, único e independiente de todos los demás inquilinos de Microsoft 365. Su inquilino de Azure AD correspondiente también es distinto, único e independiente de todos los demás inquilinos de Microsoft 365.

## <a name="single-tenant"></a>Inquilino único
Tener un único inquilino simplifica muchos aspectos del uso de Microsoft 365 por parte de su organización. Un único inquilino significa un único inquilino de Azure AD con un único conjunto de cuentas, grupos y directivas. Los permisos y el uso compartido de recursos en toda la organización se pueden realizar a través de este proveedor de identidades central.

Un único espacio empresarial proporciona la experiencia de productividad y colaboración más completa y simplificada de características para los usuarios.

Este es un ejemplo que muestra la ubicación predeterminada y el inquilino de Azure AD de un inquilino de Microsoft 365.

![Un único inquilino de Microsoft 365 con su inquilino de Azure AD](../media/tenant-management-overview/tenant-management-example-tenant.png)

## <a name="multiple-tenants"></a>Varios inquilinos

Hay muchas razones por las que su organización podría tener varios inquilinos:

- Aislamiento administrativo
- IT descentralizada
- Decisiones históricas
- Fusiones, adquisiciones o desinsticiones
- Separación clara de la personalción de marca para organizaciones conglomerados
- Inquilinos de espacio aislado, pruebas o preproducción

Este es un ejemplo de una organización que tiene dos inquilinos (Inquilino A y Inquilino B) en la misma ubicación geográfica predeterminada del centro de datos. Cada inquilino como un inquilino de Azure AD independiente.

![Varios inquilinos de Microsoft 365 con sus propios inquilinos de Azure AD](../media/tenant-management-overview/tenant-management-example-multi-tenant.png)

Cuando tiene varios inquilinos, existen restricciones y consideraciones adicionales al administrarlos y proporcionar servicios a los usuarios.

### <a name="inter-tenant-collaboration"></a>Colaboración entre inquilinos

Si desea que los usuarios colaboren de forma más eficaz entre diferentes inquilinos de Microsoft 365 de forma segura, las opciones de colaboración entre inquilinos incluyen el uso de una ubicación central para archivos y conversaciones, el uso compartido de calendarios, el uso de mensajería instantánea, llamadas de audio y vídeo para la comunicación y la protección del acceso a recursos y aplicaciones.

Para obtener más información, consulte [Colaboración entre inquilinos de Microsoft 365.](../enterprise/microsoft-365-inter-tenant-collaboration.md)

### <a name="cross-tenant-mailbox-migration-preview"></a>Migración de buzones entre inquilinos (versión preliminar)

Antes de la migración de buzones entre inquilinos (en versión preliminar), al mover buzones de Exchange Online entre inquilinos, debe quitar completamente un buzón de usuario de su inquilino actual (el inquilino de origen) a local y, a continuación, incorporarlos a un nuevo inquilino (el inquilino de destino). Con la nueva característica de migración de buzones entre inquilinos, los administradores de inquilinos de los inquilinos de origen y de destino pueden mover buzones entre los inquilinos con dependencias de infraestructura mínimas en sus sistemas locales. De esta forma, se elimina la necesidad de incorporar buzones de correo.

Estos son dos inquilinos de ejemplo y sus buzones antes de la migración de buzones entre inquilinos.

![Varios inquilinos de Microsoft 365 y sus buzones](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-before.png)

En esta ilustración, dos inquilinos independientes tienen sus propios dominios y un conjunto de buzones de Exchange.

Este es el inquilino de destino (inquilino A) después de la migración de buzones entre inquilinos.

![El inquilino de destino después de la migración de buzones entre inquilinos](../media/tenant-management-overview/tenant-management-cross-tenant-mailbox-after.png)

En esta ilustración, un único inquilino tiene dominios y ambos conjuntos de buzones de Exchange.

Para obtener más información, consulte [Migración de buzones entre inquilinos.](../enterprise/cross-tenant-mailbox-migration.md)

### <a name="tenant-to-tenant-migrations"></a>Migraciones de espacio empresarial a espacio empresarial

Existen varios enfoques arquitectónicos para fusiones, adquisiciones, desintecciones y otros escenarios que pueden llevar a migrar un inquilino de Microsoft 365 existente a un nuevo inquilino. 

Para obtener instrucciones detalladas, consulte Migraciones de inquilino a inquilino [de Microsoft 365.](../enterprise/microsoft-365-tenant-to-tenant-migrations.md)

## <a name="multi-geo-for-a-tenant"></a>Multi-Geo para un inquilino

Con Microsoft 365 Multi-Geo, puede aprovisionar y almacenar datos en reposo en las otras ubicaciones geográficas del centro de datos que haya elegido para cumplir los requisitos de residencia de datos y, al mismo tiempo, desbloquear la implementación global de experiencias de productividad modernas para sus trabajadores.

En un entorno Multi-Geo, su espacio empresarial de Microsoft 365 consta de una ubicación central o predeterminada donde se creó originalmente su suscripción a Microsoft 365 y una o más ubicaciones satélite. En un inquilino multige geográfico, la información sobre las ubicaciones geográficas, los grupos y la información de usuario se masterizó en un inquilino global de Azure AD. Dado que la información del espacio empresarial se masterizó de forma centralizada y se sincroniza en cada ubicación geográfica, las experiencias de colaboración en las que participan todos los usuarios de su empresa se comparten entre las ubicaciones.

Este es un ejemplo de una organización que tiene su ubicación predeterminada en Europa y una ubicación satélite en Norteamérica. Ambas ubicaciones comparten el mismo inquilino global de Azure AD para el único inquilino de Microsoft 365.

![Ejemplo de un inquilino multigemico de Microsoft 365](../media/tenant-management-overview/tenant-management-example-multi-geo.png)

Para más información, vea [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).

## <a name="moving-core-data-to-a-new-datacenter-geo"></a>Mover datos principales a una nueva ubicación geográfica del centro de datos

Microsoft continúa abierto nuevas ubicaciones geográficas de centro de datos para los servicios de Microsoft 365. Estas nuevas ubicaciones geográficas de centro de datos agregan capacidad y recursos de cálculo para admitir nuestra demanda continuada de clientes y el crecimiento del uso. Además, las nuevas ubicaciones geográficas del centro de datos ofrecen residencia de datos en la ubicación geográfica para los datos principales de los clientes.

Aunque la apertura de una nueva ubicación geográfica de centro de datos no afecta a usted y a los datos principales almacenados en una ubicación geográfica de centro de datos ya existente, Microsoft le permite solicitar una migración anticipada de los datos principales del cliente de su organización en reposo a una nueva ubicación geográfica del centro de datos.

Este es un ejemplo en el que un inquilino de Microsoft 365 se movió de la ubicación geográfica del centro de datos de la Unión Europea (UE) al ubicado en el Reino Unido.

![Ejemplo de mover un espacio empresarial de Microsoft 365 entre las ubicaciones geográficas del centro de datos](../media/tenant-management-overview/tenant-management-example-tenant-move.png)

Para obtener más información, vea Mover los datos principales a las nuevas ubicaciones geográficas del centro de datos [de Microsoft 365.](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="products-and-licenses-for-a-tenant"></a>Productos y licencias para un inquilino

El espacio empresarial de Microsoft 365 se crea al comprar el primer producto, como Microsoft 365 E3. Junto con el producto se encuentran las licencias, a las que se les cobra una tarifa mensual o anual. A continuación, un administrador asigna una licencia disponible de uno de los productos a una cuenta de usuario, ya sea directamente o a través de la pertenencia a grupos. Según las necesidades empresariales de su organización, es posible que tenga un conjunto de productos, cada uno con su propio grupo de licencias. 

La determinación del conjunto de productos y el número de licencias de cada uno de ellos requiere cierta planeación para:

- Asegúrese de que tiene suficientes licencias para las cuentas de usuario que necesitan características avanzadas.
- Impedir que se quedas sin licencias o que tenga demasiadas licencias sinsignar, en función de los cambios en el personal de la organización.


## <a name="results-of-step-1"></a>Resultado del paso 1

Para los inquilinos de Microsoft 365 para empresas, ha determinado:

- Cuántos inquilinos tiene o necesita.
- Para cada inquilino, qué productos y licencias se deben comprar.
- Indica si un inquilino debe ser Multi-Geo para cumplir con los requisitos de residencia de datos.
- Si necesita configurar la colaboración entre inquilinos.
- Si necesita migrar un inquilino a otro.
- Si necesita mover los datos principales de una ubicación geográfica de centro de datos a uno nuevo.

Este es un ejemplo de un nuevo inquilino.

![Ejemplo de un nuevo inquilino](../media/tenant-management-overview/tenant-management-tenant-build-step1.png)

En esta ilustración, el inquilino tiene:

- Ubicación predeterminada correspondiente a una ubicación geográfica de centro de datos de Microsoft 365.
- Un conjunto de productos y licencias.
- El conjunto de aplicaciones de productividad en la nube, algunas de las cuales son específicas de los productos.
- Un inquilino de Azure AD que contiene cuentas de administrador global y un nombre de dominio DNS inicial.

A medida que avancemos en los pasos adicionales de esta solución, crearemos esta figura.

## <a name="ongoing-maintenance-for-tenants"></a>Mantenimiento continuo para inquilinos

De forma continua, es posible que deba:

- Agregue un nuevo inquilino.
- Agregue nuevos productos a un inquilino con un número inicial de licencias.
- Cambiar el conjunto de licencias de un producto en un espacio empresarial para ajustarse a los requisitos de personal cambiantes.
- Mueva los datos principales de un espacio empresarial a una nueva ubicación geográfica del centro de datos.
- Agregar Multi-Geo para requisitos de residencia de datos.
- Configurar la colaboración entre inquilinos.

## <a name="next-step"></a>Paso siguiente

[![Paso 2. Optimizar el espacio empresarial para la red para el acceso](../media/tenant-management-overview/tenant-management-step-grid-networking.png)](tenant-management-networking.md)

Continúe con [las redes](tenant-management-networking.md) para proporcionar redes óptimas de sus trabajadores a los servicios en la nube de Microsoft 365.
