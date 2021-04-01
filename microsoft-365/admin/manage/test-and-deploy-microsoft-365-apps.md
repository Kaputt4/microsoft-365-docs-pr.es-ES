---
title: Probar e implementar aplicaciones de Microsoft 365 por partners en el portal de aplicaciones integradas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Busque, pruebe e implemente aplicaciones asociadas de Microsoft y Microsoft para usuarios y grupos de su organización desde el portal de aplicaciones integradas en el Centro de administración de Microsoft 365.
ms.openlocfilehash: f806d48e0ed582b1b5c1ee262058ce987125bd99
ms.sourcegitcommit: 7ebed5810480d7c49f8ca03207b5ea84993d253f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "51488294"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Probar e implementar aplicaciones de Microsoft 365 por partners en el portal de aplicaciones integradas

El Centro de administración de Microsoft 365 te ofrece la flexibilidad de implementar aplicaciones de una sola tienda, una línea de negocio personalizada de aplicaciones y aplicaciones asociadas de Microsoft 365 desde una sola ubicación. Se puede obtener acceso a la ubicación en el Centro de administración de Microsoft > Configuración > aplicaciones integradas. La capacidad de encontrar, probar e implementar completamente aplicaciones compradas y con licencia por parte de los partners de Microsoft desde el portal de aplicaciones integradas proporciona la comodidad y las ventajas que su organización necesita para mantener los servicios empresariales actualizados periódicamente y ejecutándose de forma eficaz.

Para obtener información adicional sobre cómo comprar y otorgar licencias de aplicaciones de Microsoft 365 a socios de su organización, vea Administrar e implementar aplicaciones de Microsoft 365 desde el Centro de administración de [Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Para obtener más información sobre cómo los partners crean estas aplicaciones, consulta [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)

El portal de aplicaciones integradas solo es accesible para los administradores globales y solo está disponible para los clientes de WorldWide. Esta característica no está disponible en las nubes soberanas y gubernamentales.

El portal de aplicaciones integradas muestra una lista de aplicaciones, que incluye aplicaciones únicas y aplicaciones de Microsoft 365 de socios que se implementan en la organización. Solo se enumeran las aplicaciones web, las aplicaciones de SPFx, los complementos de Office y las aplicaciones de Teams. Para las aplicaciones web, podemos ver 2 tipos de aplicaciones.

- Aplicaciones SaaS que están disponibles en appsource.microsoft.com y pueden implementarse por administradores que dan su consentimiento en nombre de la organización.
- Aplicaciones de galería SAML vinculadas con complementos de Office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Administrar aplicaciones en el portal de aplicaciones integradas

Puedes administrar pruebas e implementación de aplicaciones de Microsoft 365 compradas y con licencia de partners.

1. En el Centro de administración, en la navegación izquierda, elija **Configuración** y, a continuación, elija **Aplicaciones integradas.**

2. Elige una aplicación con **Estado de** Más **aplicaciones disponibles** para abrir el **panel** Administrar. El estado de **más aplicaciones disponibles** te permite saber que hay más integraciones de los ISV que aún no están implementadas.

3. En la **pestaña Información** general, **seleccione Implementar**. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar Implementar.

4. Seleccione **Usuarios**, **elija Esta es una implementación de** prueba y, a continuación, elija Toda la organización , **Usuarios/grupos** específicos o Solo **yo**. También puedes elegir **Probar implementación** si prefieres esperar para implementar la aplicación en toda la organización. Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo de distribución.

5. Seleccione **Actualizar** y, a continuación, **Listo**. Ahora puede seleccionar Implementar en la pestaña Información general.

6. Revise la información de la aplicación y, a continuación, **seleccione Implementar**.

7. Seleccione **Listo** en la página Implementación completada y revise los detalles de la prueba o la implementación completa en la **pestaña** Información general.

8. Si la aplicación tiene un estado de Actualización **pendiente,** puedes hacer clic en la aplicación para abrir el panel Administrar y actualizar la aplicación.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Buscar aplicaciones publicadas para pruebas e implementación completa

Puedes encontrar, probar e implementar completamente aplicaciones publicadas que aún no aparecen en la lista en la página Aplicaciones integradas. Al comprar y otorgar licencias a las aplicaciones desde el Centro de administración, puedes agregar aplicaciones de partners de Microsoft y Microsoft a tu lista desde una única ubicación.

1. En el Centro de administración, en la navegación izquierda, elija **Configuración** y, a continuación, elija **Aplicaciones integradas.**

2. Selecciona **Obtener aplicaciones** para obtener una vista de las aplicaciones.

3. En la página Aplicaciones publicadas de **Microsoft 365** Apps, selecciona la aplicación que quieres implementar eligiendo **Obtener ahora**. Las aplicaciones que se muestran principalmente son Word, PowerPoint, Excel, complementos de Outlook, aplicaciones de Teams y aplicaciones de SharePoint (integradas en la tecnología de SharePoint Framework). Acepte los permisos y seleccione **Continuar**.

5. Seleccione **Implementar** en la parte superior de la página junto al mensaje que hace referencia a la espera de implementarse.

    Si la aplicación seleccionada está vinculada a una oferta SaaS por un ISV, todas las demás aplicaciones que forman parte de esta oferta vinculada aparecerán en la página Configuración. Si elige implementar todas las aplicaciones, seleccione **Siguiente**. De lo contrario, **selecciona Editar** y elige qué aplicaciones quieres implementar. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar **Implementar**.

6. Seleccione **Agregar usuarios**, elija Es esta  una implementación de prueba y, **a** continuación, elija Toda la organización, **Usuarios/grupos** específicos o Solo **yo**.

    Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo distribuido. También puedes elegir **Probar implementación** si prefieres esperar para implementar la aplicación en toda la organización.

7. Seleccione **Siguiente** para ir a la **página Aceptar solicitud de** permiso. Se enumeran las capacidades y permisos de la aplicación de cada una de las aplicaciones. Si la aplicación necesita consentimiento, selecciona **Aceptar permisos**. Solo un administrador global puede dar su consentimiento.

8. Seleccione **Siguiente** para revisar la implementación y elija **Finalizar implementación**. Para ver la implementación desde la pestaña **Información** general, elija **Ver esta implementación.** En el Centro de administración de Microsoft 365, puedes ver el estado de cada aplicación implementada y la fecha en que implementó la aplicación.

> [!NOTE]
> Si una aplicación se implementó anteriormente desde otro lugar que no sea el portal de aplicaciones integradas, el tipo **de implementación** es **Personalizado.**

## <a name="unsupported-scenarios"></a>Escenarios no admitidos

No podrás implementar una aplicación de tienda única o aplicaciones de Microsoft 365 por partner desde el portal de aplicaciones integradas para los siguientes escenarios.

- El mismo complemento está vinculado a más de una oferta saas.
- La oferta SaaS está vinculada a complementos, pero no se integra con Microsoft Graph y no se proporciona ningún identificador de aplicación de AAD.
- La oferta SaaS está vinculada a complementos, pero el id. de aplicación de AAD proporcionado para la integración de Microsoft Graph se comparte entre varias ofertas saas.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Cargar una línea personalizada de aplicaciones empresariales para pruebas e implementación completa

1. En el Centro de administración, en el panel de navegación izquierdo, elija **Configuración** y, a continuación, **Aplicaciones integradas.**

2. Selecciona **Cargar aplicaciones personalizadas**. Solo se admite una línea personalizada de aplicaciones para Word, PowerPoint, Excel y Outlook.

3. Cargue el archivo de manifiesto desde el dispositivo o agregue un vínculo de dirección URL. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar Implementar.

4. Seleccione **Agregar usuarios,** **elija Es esta una implementación de prueba** y **elija** Toda la organización, **Usuarios/grupos** específicos o **Solo yo**.

    Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo distribuido. También puedes elegir **Probar implementación** si quieres esperar para implementar la aplicación en toda la organización.

5. Seleccione **Siguiente** para ir a la **página Aceptar solicitud de** permiso. Se enumeran las capacidades y permisos de la aplicación de las aplicaciones. Si la aplicación necesita consentimiento, selecciona **Aceptar permisos**. Solo un administrador global puede dar su consentimiento.

6. Seleccione **Siguiente** para revisar la implementación y elija **Finalizar implementación**. Para ver la implementación desde la pestaña **Información** general, elija **Ver esta implementación.**

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>¿Qué rol de administrador necesito para tener acceso a aplicaciones integradas?

Solo los administradores globales pueden acceder a aplicaciones integradas. Las aplicaciones integradas no se mostrarán en la navegación izquierda para otros administradores.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>¿Por qué veo El complemento en la navegación izquierda en Configuración pero no aplicaciones integradas?

Puede haber algunas razones:

- El administrador que ha iniciado sesión es un administrador de Exchange.
- El cliente está en la nube soberana y la experiencia de aplicaciones integradas aún está disponible para los clientes de nube soberana.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>¿Qué aplicaciones puedo implementar desde aplicaciones integradas?

Las aplicaciones integradas permiten la implementación de aplicaciones web, aplicaciones de Teams, Excel, PowerPoint, Word, complementos de Outlook y aplicaciones de SPFx. En el caso de los complementos, las aplicaciones integradas admiten la implementación en buzones de Exchange Online y no en buzones de Exchange locales.

### <a name="can-administrators-delete-or-remove-apps"></a>¿Pueden los administradores eliminar o quitar aplicaciones?

Sí. Los administradores globales pueden eliminar o quitar aplicaciones.

- Selecciona una aplicación en la vista de lista. En la **pestaña Configuración,** seleccione qué aplicaciones quitar.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>¿Las aplicaciones integradas están disponibles en la nube soberana?

No. Las aplicaciones integradas no están disponibles para los clientes de nube soberana.

### <a name="is-integrated-apps-available-in-government-clouds"></a>¿Las aplicaciones integradas están disponibles en las nubes gubernamentales?

No. Las aplicaciones integradas no están disponibles para los clientes de la nube gubernamental.
