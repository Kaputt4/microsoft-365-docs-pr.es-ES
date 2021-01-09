---
title: Probar e implementar Aplicaciones de Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Busque, pruebe e implemente aplicaciones de partners de Microsoft y Microsoft para usuarios y grupos de su organización desde el portal de aplicaciones integradas en el Centro de administración de Microsoft 365.
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790195"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>Probar e implementar Aplicaciones de Microsoft 365 en el Centro de administración de Microsoft 365

El Centro de administración de Microsoft 365 le ofrece flexibilidad para implementar aplicaciones de microsoft y de partners de Microsoft desde una única ubicación. La capacidad de buscar, probar y implementar completamente aplicaciones compradas y con licencia por parte de Microsoft y los partners de Microsoft desde el portal de aplicaciones integradas proporciona la comodidad y las ventajas que necesita su organización para mantener los servicios empresariales actualizados periódicamente y en funcionamiento de forma eficaz.  

Para obtener información adicional sobre cómo comprar y otorgar licencias a aplicaciones de Microsoft 365 para su organización, consulte la entrada de blog denominada Administrar e implementar aplicaciones de Microsoft 365 desde el Centro de administración de [Microsoft 365.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>Administrar aplicaciones en el portal de aplicaciones integradas

Al elegir aplicaciones integradas en el Centro de administración de Microsoft 365, puede administrar las pruebas y la implementación de las aplicaciones de microsoft y de los partners de Microsoft compradas y con licencia. 

1. En el centro de administración, en el panel de navegación izquierdo, elija **Configuración** y, a continuación, elija **Aplicaciones integradas.** 

2. Elija una aplicación con el **estado** de **Más aplicaciones disponibles.**

3. Seleccione **Implementar** en la parte superior de la página junto al mensaje que hace referencia a esperar a ser implementado.

    Algunas aplicaciones requieren que agregues usuarios para poder seleccionar **Implementar.**

    a. Seleccione **Agregar usuarios,** elija **Implementación completa** y, a continuación, elija Toda la **organización** o Usuarios o **grupos específicos.**

    Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo distribuido.

    También puedes elegir Probar **implementación si** prefieres esperar a implementar la aplicación en toda la organización.

    b. Seleccione **Actualizar,** **Listo** y ahora puede seleccionar **Implementar en** la **pestaña** Información general.  

4. Revise la información de la aplicación y, a continuación, **seleccione Implementar**. 

5. Seleccione **Listo en** la página Implementación **completada.** 

    Revise los detalles de la prueba o la implementación completa en la **pestaña** Información general.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Buscar aplicaciones publicadas para pruebas e implementación completa 

Puedes buscar, probar e implementar completamente aplicaciones publicadas que aún no aparecen en la lista de la página Aplicaciones integradas. Al comprar y otorgar licencias a las aplicaciones desde el centro de administración, puedes agregar aplicaciones de microsoft y de partners de Microsoft a tu lista desde una única ubicación.

1. En el centro de administración, en el panel de navegación izquierdo, elija **Configuración** y, a continuación, elija **Aplicaciones integradas.** 

2. Selecciona **Obtener aplicaciones encima** de la lista de aplicaciones.

3. En la página aplicaciones publicadas de Aplicaciones de **Microsoft 365,** seleccione la aplicación que desea implementar eligiendo **Obtener ahora.**

4. Acepte los permisos y, a continuación, **seleccione Continuar**.

5. Seleccione **Implementar** en la parte superior de la página junto al mensaje que hace referencia a esperar a ser implementado.

    Algunas aplicaciones requieren que agregues usuarios para poder seleccionar **Implementar.**

    a. Seleccione **Agregar usuarios,** elija **Implementación completa** y, a continuación, elija Toda la **organización** o Usuarios o **grupos específicos.**

    Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo distribuido.

    También puedes elegir Probar **implementación si** prefieres esperar a implementar la aplicación en toda la organización.

    b. Seleccione **Actualizar,** **Listo** y ahora puede seleccionar **Implementar en** la **pestaña** Información general.  

6. Revise la información de la aplicación y, a continuación, **seleccione Implementar**. 

7. Seleccione **Listo en** la página Implementación **completada.** 

    Revise los detalles de la prueba o la implementación completa en la **pestaña** Información general.

En el Centro de administración de Microsoft  365, cada estado de la aplicación implementada es correcto con un tipo de implementación de **prueba,** implementación completa o **personalizada,** y la fecha en que implementó la aplicación.  

> [!NOTE]
> Si una aplicación se implementó anteriormente desde otro lugar que no sea el portal de aplicaciones integradas, el **tipo de implementación** es **personalizado.**

## <a name="unsupported-scenarios"></a>Escenarios no admitidos

Los siguientes escenarios no se admiten actualmente para la implementación desde el portal de aplicaciones integradas:

- La aplicación o el complemento está vinculado a más de una oferta de software como servicio (SaaS).
- La aplicación SaaS está vinculada a aplicaciones y complementos, pero no tiene un AADid asociado.
- Dos aplicaciones SaaS comparten el mismo AADid y ambas están vinculadas a aplicaciones o complementos.
  