---
title: Prueba e implementación de Aplicaciones Microsoft 365 asociados en el portal de aplicaciones integradas
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
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007062"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Prueba e implementación de Aplicaciones Microsoft 365 asociados en el portal de aplicaciones integradas

El Centro de administración de Microsoft 365 te ofrece la flexibilidad para implementar aplicaciones de una sola tienda, una línea de negocio personalizada de aplicaciones y Microsoft 365 aplicaciones asociadas desde una sola ubicación. Se puede tener acceso a la ubicación en la configuración del Centro de administración de Microsoft, en Aplicaciones integradas. La capacidad de encontrar, probar e implementar completamente aplicaciones compradas y con licencia por parte de los partners de Microsoft desde el portal de aplicaciones integradas proporciona la comodidad y las ventajas que su organización necesita para mantener los servicios empresariales actualizados periódicamente y ejecutándose de forma eficaz.

Para obtener información adicional acerca de la compra y las licencias Microsoft 365 aplicaciones de partners para su organización, vea Administrar e implementar Aplicaciones Microsoft 365 desde [el Centro de administración de Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Para obtener más información sobre cómo los partners crean estas aplicaciones, consulta [How to plan a SaaS offer for the commercial marketplace](https://go.microsoft.com/fwlink/?linkid=2158277)

El portal de aplicaciones integradas solo es accesible para los administradores globales y solo está disponible para clientes de todo el mundo. Esta característica no está disponible en las nubes soberanas y gubernamentales.

El portal de aplicaciones integradas muestra una lista de aplicaciones, que incluye aplicaciones únicas y aplicaciones Microsoft 365 de socios que se implementan en la organización. Solo aparecen aplicaciones web, SPFx, Office complementos y Teams aplicaciones. Para las aplicaciones web, puedes ver dos tipos de aplicaciones.

- Las aplicaciones SaaS que están disponibles en appsource.microsoft.com y pueden implementarse por administradores que dan su consentimiento en nombre de la organización.
- Aplicaciones de galería SAML vinculadas con complementos de Office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Administrar aplicaciones en el portal de aplicaciones integradas

Puede administrar las pruebas y la implementación de las licencias adquiridas Aplicaciones Microsoft 365 socios.

1. En el Centro de administración, **seleccione Configuración** y, a continuación, seleccione **Aplicaciones integradas.**

2. Elige una aplicación con **Estado de** Más **aplicaciones disponibles** para abrir el **panel** Administrar. El estado de **más aplicaciones disponibles** te permite saber que hay más integraciones de los ISV que aún no están implementadas.

3. En la **pestaña Información** general, seleccione **Implementar**. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar Implementar.

4. Seleccione **Usuarios**, **elija Esta es una implementación de** prueba y, a continuación, elija Toda la organización , **Usuarios/grupos** específicos o Solo **yo**. También puedes elegir **Probar implementación** si prefieres esperar para implementar la aplicación en toda la organización. Los usuarios o grupos específicos pueden ser un Microsoft 365, un grupo de seguridad o un grupo de distribución.

5. Seleccione **Actualizar** y, a continuación, **Listo**. Ahora puede seleccionar Implementar en la pestaña Información general.

6. Revise la información de la aplicación y, a continuación, **seleccione Implementar**.

7. Seleccione **Listo** en la página Implementación completada y revise los detalles de la prueba o la implementación completa en la **pestaña** Información general.

8. Si la aplicación tiene un estado de Actualización **pendiente,** puedes hacer clic en la aplicación para abrir el panel Administrar y actualizar la aplicación.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Buscar aplicaciones publicadas para pruebas e implementación completa

Puedes encontrar, probar e implementar completamente aplicaciones publicadas que aún no aparecen en la lista en la página Aplicaciones integradas. Al comprar y otorgar licencias a las aplicaciones desde el Centro de administración, puedes agregar aplicaciones de partners de Microsoft y Microsoft a tu lista desde una única ubicación.

1. En el Centro de administración, en el panel de navegación izquierdo, **elija Configuración** y, a continuación, elija **Aplicaciones integradas.**

2. Selecciona **Obtener aplicaciones** para obtener una vista de las aplicaciones.

3. En la **Aplicaciones Microsoft 365** de aplicaciones publicadas, seleccione la aplicación que desea implementar eligiendo **Obtener ahora**. Las aplicaciones que se muestran principalmente son Word, PowerPoint, Excel, complementos de Outlook, aplicaciones Teams y aplicaciones SharePoint (integradas en SharePoint Framework tecnología). Acepte los permisos y seleccione **Continuar**.

5. Seleccione **Implementar** en la parte superior de la página junto al mensaje que hace referencia a la espera de implementarse.

    Si la aplicación seleccionada está vinculada a una oferta SaaS por un ISV, todas las demás aplicaciones que forman parte de esta oferta vinculada aparecerán en la página Configuración. Si elige implementar todas las aplicaciones, seleccione **Siguiente**. De lo contrario, **selecciona Editar** y elige qué aplicaciones quieres implementar. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar **Implementar**.

6. Seleccione **Agregar usuarios**, elija Es esta  una implementación de prueba y, **a** continuación, elija Toda la organización, **Usuarios/grupos** específicos o Solo **yo**.

    Los usuarios o grupos específicos pueden ser un Microsoft 365, un grupo de seguridad o un grupo distribuido. También puedes elegir **Probar implementación** si prefieres esperar para implementar la aplicación en toda la organización.

7. Seleccione **Siguiente** para ir a la **página Aceptar solicitud de** permiso. Se enumeran las capacidades y permisos de la aplicación de cada una de las aplicaciones. Si la aplicación necesita consentimiento, selecciona **Aceptar permisos**. Solo un administrador global puede dar su consentimiento.

8. Seleccione **Siguiente** para revisar la implementación y elija **Finalizar implementación**. Para ver la implementación desde la pestaña **Información** general, elija **Ver esta implementación.** En la Centro de administración de Microsoft 365, puedes ver el estado de cada aplicación implementada y la fecha en que implementaste la aplicación.

> [!NOTE]
> Si una aplicación se implementó anteriormente desde otro lugar que no sea el portal de aplicaciones integradas, el tipo **de implementación** es **Personalizado.**

## <a name="unsupported-scenarios"></a>Escenarios no admitidos

No podrás implementar una sola aplicación de la tienda ni un solo Aplicaciones Microsoft 365 asociado desde el portal de aplicaciones integradas para los siguientes escenarios.

- El mismo complemento está vinculado a más de una oferta saas.
- La oferta SaaS está vinculada a complementos, pero no se integra con Microsoft Graph y no se proporciona ningún identificador de aplicación de AAD.
- La oferta SaaS está vinculada a complementos, pero el id. de aplicación de AAD proporcionado para la integración de Microsoft Graph se comparte entre varias ofertas saas.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Upload aplicaciones personalizadas de línea de negocio para pruebas e implementación completa

1. En el Centro de administración, en el panel de navegación izquierdo, **elija Configuración** y, a continuación, **Aplicaciones integradas.**

2. Selecciona **Upload aplicaciones personalizadas**. Solo se admite una línea personalizada de aplicaciones para Word, PowerPoint, Excel y Outlook.

3. Upload el archivo de manifiesto desde el dispositivo o agregue un vínculo de dirección URL. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar Implementar.

4. Seleccione **Agregar usuarios,** **elija Es esta una implementación de prueba** y **elija** Toda la organización, **Usuarios/grupos** específicos o **Solo yo**.

    Los usuarios o grupos específicos pueden ser un Microsoft 365, un grupo de seguridad o un grupo distribuido. También puedes elegir **Probar implementación** si quieres esperar para implementar la aplicación en toda la organización.

5. Seleccione **Siguiente** para ir a la **página Aceptar solicitud de** permiso. Se enumeran las capacidades y permisos de la aplicación de las aplicaciones. Si la aplicación necesita consentimiento, selecciona **Aceptar permisos**. Solo un administrador global puede dar su consentimiento.

6. Seleccione **Siguiente** para revisar la implementación y elija **Finalizar implementación**. Para ver la implementación desde la pestaña **Información** general, elija **Ver esta implementación.**

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Preparar la implementación de complementos en aplicaciones integradas

Office complementos le ayudarán a personalizar los documentos y simplificar la forma en que accede a la información en la web (vea Start using your Office Add-in). 

Los complementos proporcionan las siguientes ventajas: 

- Cuando se inicia Office aplicación, el complemento se descarga automáticamente. Si el complemento admite comandos de complemento, el complemento aparecerá automáticamente en la cinta de opciones dentro de la Office aplicación. 

- Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento. 

Los complementos se admiten en tres plataformas de escritorio Windows, Mac y Aplicaciones Office línea. También se admite en iOS y Android (solo Outlook complementos móviles). 

Un complemento puede tardar hasta 24 horas en aparecer para todos los usuarios. 

Hoy en Exchange administradores y administradores globales pueden implementar complementos desde aplicaciones integradas.   

### <a name="before-you-begin"></a>Antes de empezar

La implementación de complementos requiere que los usuarios usen licencias de Microsoft 365 Enterprise (E3/E5/F3) o licencias de Microsoft 365 Empresa (Business Basic, Business Standard, Business Premium). Los usuarios también deben haber iniciado sesión en Office con su identificador de organización) y tener Exchange Online buzones de correo Exchange Online activos. El directorio de suscripción debe estar en o federado para Azure Active Directory. 

La implementación no admite lo siguiente: 

- Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013 
- Un servicio de directorio local 
- Implementación de complementos en un buzón Exchange local 
- Implementación de complementos de modelo de objetos componentes (COM) o Visual Studio Tools para Office (VSTO). 
- Implementaciones de Microsoft 365 que no incluyen Exchange Online como Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para Enterprise.  

### <a name="office-requirements"></a>Office Requisitos 

Para word, Excel y PowerPoint complementos, los usuarios deben usar una de las siguientes opciones: 
- En un dispositivo Windows, versión 1704 o posterior de licencias de Microsoft 365 Enterprise (E3/E5/F3) o licencias de Microsoft 365 Empresa (Business Basic, Business Standard, Business Premium). 
- En mac, versión 15.34 o posterior. 

Por Outlook, los usuarios deben usar una de las siguientes opciones: 
- Versión 1701 o posterior de licencias Microsoft 365 Enterprise (E3/E5/F3) o licencias de Microsoft 365 Empresa (Business Basic, Business Standard, Business Premium). 
- Versión 1808 o posterior de Office Professional Plus 2019 u Office Standard 2019. 
- Versión 16.0.4494.1000 o posterior de Office Professional Plus 2016 (MSI) o Office Standard 2016 (MSI).
    > [!NOTE]
    > Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de opciones de Outlook adecuada, no en la sección "Mis complementos".  
- Versión 15.0.4937.1000 o posterior de Office Professional Plus 2013 (MSI) u Office Standard 2013 (MSI).
- Versión 16.0.9318.1000 o posterior de Office 2016 para Mac. 
- Versión 2.75.0 o posterior de Outlook mobile para iOS. 
- Versión 2.2.145 o posterior de Outlook mobile para Android. 



### <a name="exchange-online-requirements"></a>Requisitos de Exchange Online 
Microsoft Exchange almacena los manifiestos del complemento en el inquilino de la organización. El administrador que implementa complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth. 

Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario se puede comprobar mediante el cmdlet [de PowerShell Test-OAuthConnectivity.](/powershell/module/exchange/test-oauthconnectivity)   

### <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo
Actualmente, la implementación del complemento se admite en la mayoría de los grupos admitidos por Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución y los grupos de seguridad. La implementación admite usuarios de grupos de nivel superior o grupos sin grupos primarios, pero no usuarios de grupos anidados o grupos que tienen grupos primarios. 

> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos. 

En el ejemplo siguiente, Sandra, Sheila y el grupo Departamento de ventas se asignan a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento. 

![Diagrama del departamento de ventas](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre del grupo en el campo **Para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o   grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook para el grupo de prueba no muestra usuarios y   solo dos sub grupos. 

![Ficha Miembros de la tarjeta de contacto de Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede <b></b>ver en la pestaña Pertenencia de la tarjeta de contacto de Outlook que sub grupo   1 es miembro del grupo de prueba. 

![Ficha Pertenencia a la tarjeta de contacto de Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Tenga en cuenta que puede usar la API de Graph de Azure Active Directory para ejecutar consultas para buscar la lista de grupos dentro de un grupo. Para obtener más información, vea [Operations on groups | Referencia de la API de Graph](/previous-versions/azure/ad/graph/api/groups-operations). 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar los Complementos de Office 
Para la implementación de complementos mediante un enfoque por fases, se recomienda lo siguiente: 
1. Implemente el complemento en un pequeño conjunto de participantes y miembros del departamento de TI. Puede activar la marca **Es esta una implementación de prueba.** Si la implementación se realiza correctamente, pase al paso 2. 

2. Roll out the add-in to more individuals within the business. De nuevo, evalúe los resultados y, si se realiza correctamente, continúe con la implementación completa. 

3. Realice una implementación completa para todos los usuarios. Desactivar la marca de **¿Es esto una implementación de prueba?** 

Según el tamaño de la audiencia de destino, puede agregar o quitar pasos de implementación.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementar un Complemento de Office con el Centro de administración 

1. En el Centro de administración, selecciona **Configuración** y, a continuación, **selecciona Aplicaciones integradas.** 

2. Selecciona **Obtener aplicaciones** en la parte superior de la página. AppSource se cargará en un formato incrustado. Busque un complemento o báquelo haciendo clic en Producto en la navegación izquierda.  Si el ISV ha vinculado el complemento a una aplicación SaaS u otras aplicaciones y complementos y si la aplicación SaaS es una aplicación de pago, se mostrará un cuadro de diálogo para comprar la licencia o Implementar. Independientemente de si ha comprado la licencia o no, puede continuar con la implementación. Seleccione **Implementar**.  

3. Verás la página **Configuración** en la que se enumeran todas las aplicaciones. Si no tienes permisos o el acceso correcto para implementar la aplicación, se resaltará la información correspondiente. Puedes seleccionar las aplicaciones que quieres implementar. Al seleccionar **Siguiente,** verá la **página Usuarios.** Si el ISV no ha vinculado el complemento, se le enrutará a la página Usuarios. 

4. Seleccione **Todos**, **Usuarios o grupos específicos** o **Solo yo** para especificar a quién se implementa   el complemento. Use el cuadro Buscar para buscar usuarios o grupos específicos. Si va a probar el complemento, seleccione **Is this a test deployment**. 

5. Seleccione **Siguiente**. Todas las funcionalidades y permisos de la aplicación se muestran en un único panel junto con la información de certificación si la aplicación tiene la certificación de Microsoft 365. La selección del logotipo de certificación permite al usuario ver más detalles sobre la certificación.  

6. Revise y, a continuación, **seleccione Finalizar implementación**.  

7. Cuando se implementa el complemento, aparece un icono verde de "tick". Siga las instrucciones de la página para probar el complemento. 

> [!NOTE]
> Es posible que los usuarios necesiten volver a iniciar Office para ver el icono del complemento en la cinta de opciones de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de opciones de la aplicación. 

Es una buena práctica informar a los usuarios y grupos de que el complemento implementado está disponible. Considere el envío de un correo electrónico que describa cuándo y cómo usar el complemento. Incluya o vincule para ayudar al contenido o preguntas frecuentes que pueden ayudar a los usuarios si tienen problemas con el complemento. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Consideraciones al asignar un complemento a usuarios y grupos 

Los administradores globales y los administradores de Exchange pueden asignar un complemento a todos o a usuarios y grupos específicos. Cada opción tiene implicaciones: 

- **Todos**   Esta opción asigna el complemento a todos los usuarios de la organización. Use esta opción con moderación y solo para los complementos que realmente sean de uso universal en su organización. 

- **Usuarios**   Si asigna un complemento a un usuario individual y, a continuación, implementa el complemento en un nuevo usuario, primero debe agregar el nuevo usuario. 

- **Grupos**   Si asigna un complemento a un grupo, los usuarios que se agregan al grupo se asignan automáticamente al complemento. Cuando se quita un usuario de un grupo, el usuario pierde acceso al complemento. En cualquier caso, no se requiere ninguna acción adicional del administrador. 

- **Solo yo**   Si asigna un complemento solo a usted mismo, el complemento solo se asigna a su cuenta, lo que es ideal para probar el complemento. 

La opción correcta para su organización depende de la configuración. Sin embargo, se recomienda realizar asignaciones mediante grupos. Como administrador, es posible que le resulte más fácil administrar complementos mediante grupos y controlando la pertenencia a esos grupos en lugar de asignar usuarios individuales cada vez. En algunas situaciones, es posible que desee restringir el acceso a un pequeño conjunto de usuarios mediante la asignación manual de asignaciones a usuarios específicos. 

### <a name="more-about-office-add-ins-security"></a>Más información sobre la seguridad de complementos de Office 
Los complementos de Office combinan un archivo de manifiesto XML que contiene algunos metadatos sobre el complemento, pero lo más importante es que apunta a una aplicación web que contiene todo el código y la lógica. Las funcionalidades de los complementos pueden variar. Estos son algunos ejemplos de las acciones que pueden realizar los complementos:
- Mostrar datos. 
- Leer el documento de un usuario para proporcionar servicios contextuales. 
- Leer datos del documento de un usuario y escribir datos en él para proporcionar valor a ese usuario.  

Para obtener más información sobre los tipos y capacidades de los complementos de Office, vea Información general sobre la plataforma de complementos de [Office,](/office/dev/add-ins/overview/office-add-ins)especialmente la sección "Anatomía de un complemento de Office". 

Para interactuar con el documento del usuario, el complemento debe declarar el permiso que necesita en el manifiesto. Un modelo de permisos de acceso de la API de JavaScript de cinco niveles proporciona la base de privacidad y seguridad para los usuarios de complementos de panel de tareas. La mayoría de los complementos de la Tienda Office son ReadWriteDocument de nivel con casi todos los complementos compatibles con al menos el nivel ReadDocument. Para obtener más información acerca de los niveles de permisos, vea [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins). 

Cuando se actualiza un manifiesto, los cambios típicos se aplican al icono de un complemento y al texto. En ocasiones, los comandos del complementos cambian. Sin embargo, los permisos del complemento no cambian. La aplicación web en la que se ejecutan todo el código y la lógica del complemento puede cambiar en cualquier momento, lo que forma parte de la naturaleza de las aplicaciones web. 

Las actualizaciones de los complementos se producen de la siguiente manera: 
- **Complemento de** línea de negocio: en este caso, donde un administrador cargó explícitamente un manifiesto, el complemento requiere que el administrador cargue un nuevo archivo de manifiesto para admitir los cambios de metadatos. La próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento. 

- Complemento de la Tienda **Office:** cuando un administrador seleccionó un complemento de la Tienda Office, si un complemento se actualiza en la Tienda Office, la próxima vez que se inicien las aplicaciones de Office relevantes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento. 

> [!NOTE]
> Para Word, Excel y PowerPoint usan un Catálogo de aplicaciones de [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)para implementar complementos para usuarios en un entorno local sin conexión a Microsoft 365 ni compatibilidad con complementos de   SharePoint necesarios. Para Outlook, use el panel de control de Exchange para implementarlo en un entorno local sin conexión a Microsoft 365.  

## <a name="add-in-states"></a>Estados del complemento
Un complemento puede estar en el **estado On**   o **Off.**   

| Estado | Cómo se produce el estado | Impacto |
|:-----|:-----|:-----|
|**Activo**  <br/> |El administrador carizó el complemento y lo asignó a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
 
Considere la posibilidad de eliminar un complemento si ya nadie lo está usando. Por ejemplo, desactivar un complemento puede tener sentido si un complemento se usa solo durante determinadas horas del año. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Administrar un complemento Office con el Centro de administración

Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos. 

1. En el Centro de administración, **seleccione Configuración** y, a continuación, seleccione **Aplicaciones integradas.** 
2. En la página Aplicaciones integradas, mostrará una lista de aplicaciones que serán complementos individuales o complementos que se hayan vinculado con otras aplicaciones. 
3. Selecciona una aplicación con **Estado de** Más   aplicaciones **disponible** para abrir   el **panel**   Administrar. El estado de **más aplicaciones disponibles** te permite saber que hay más integraciones de los ISV que aún no están   implementadas. 
4. En la **pestaña Información**   general, seleccione **Implementar**. Algunas aplicaciones requieren que agregues usuarios antes de seleccionar Implementar. 
5. Seleccione **Usuarios**, **seleccione Esta es una implementación de** prueba y, a continuación, seleccione Toda la organización **,** **Usuarios/grupos** específicos   o Solo **yo**. También puedes seleccionar **Probar implementación** si prefieres esperar para implementar la aplicación en toda   la organización. Los usuarios o grupos específicos pueden ser un Microsoft 365, un grupo de seguridad o un grupo de distribución. 
6. Seleccione  **Actualizar**   y, a continuación, **seleccione Listo**. Ahora puede seleccionar **Implementar en** la **pestaña Información** general. 
7. Revise la información de la aplicación y, a continuación, **seleccione Implementar**.
8. Seleccione **Listo** en la página Implementación completada y revise los detalles de la prueba o la   implementación completa en la **pestaña** Información    general. 
9. Si la aplicación tiene un estado de Actualización  **pendiente,** puedes hacer clic en la aplicación para abrir el **panel** Administrar y actualizar la aplicación. 
10. Para actualizar los usuarios, seleccione la **pestaña Usuarios** y realice el cambio correspondiente. Selecciona **Actualizar** después de realizar los cambios.  

## <a name="delete-an-add-in"></a>Eliminar un complemento

También puede eliminar un complemento que se implementó.

1. En el Centro de administración, **seleccione Configuración** y, a continuación, seleccione **Aplicaciones integradas.**
2. Seleccione cualquier fila para mostrar el panel de administración. 
3. Seleccione la **pestaña** Configuración. 
4. Seleccione el complemento que desea eliminar y, a continuación, **seleccione Quitar**.  

> [!NOTE]
>  Si otro administrador ha implementado el complemento, se deshabilitará el botón Quitar. Solo el administrador que ha implementado la aplicación o un administrador global puede eliminar el complemento.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Escenarios donde Exchange administrador no puede implementar un complemento 

Hay dos casos en los que un Exchange no podrá implementar un complemento:
- Si un complemento necesita permiso para MS Graph API y necesita el consentimiento de un administrador global.
- Si un complemento está vinculado a dos o más complementos y webapps, y al menos uno de estos complementos lo implementa otro administrador (exchange/global) y la asignación de usuario no es uniforme. Solo se permite la implementación de complementos cuando la asignación de usuario es la misma para todas las aplicaciones ya implementadas.  


## <a name="frequently-asked-questions"></a>Preguntas frecuentes.

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>¿Qué rol de administrador necesito para tener acceso a aplicaciones integradas?

Solo los administradores globales pueden acceder a aplicaciones integradas. Las aplicaciones integradas no se mostrarán en la navegación izquierda para otros administradores.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>¿Por qué veo El complemento en la navegación izquierda en Configuración pero no aplicaciones integradas?

Puede haber algunas razones:

- El administrador que ha iniciado sesión es Exchange administrador.
- El cliente está en la nube soberana y la experiencia de aplicaciones integradas aún está disponible para los clientes de nube soberana.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>¿Qué aplicaciones puedo implementar desde aplicaciones integradas?

Las aplicaciones integradas permiten la implementación de aplicaciones web, Teams, Excel, PowerPoint, Word, Outlook complementos y SPFx aplicaciones. En el caso de los complementos, las aplicaciones integradas admiten la implementación en Exchange buzones en línea y no en buzones Exchange locales.

### <a name="can-administrators-delete-or-remove-apps"></a>¿Pueden los administradores eliminar o quitar aplicaciones?

Sí. Los administradores globales pueden eliminar o quitar aplicaciones.

- Selecciona una aplicación en la vista de lista. En la **pestaña Configuración,** seleccione qué aplicaciones quitar.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>¿Las aplicaciones integradas están disponibles en la nube soberana?

No. Las aplicaciones integradas no están disponibles para los clientes de nube soberana.

### <a name="is-integrated-apps-available-in-government-clouds"></a>¿Las aplicaciones integradas están disponibles en las nubes gubernamentales?

No. Las aplicaciones integradas no están disponibles para los clientes de la nube gubernamental.
