---
title: Prueba e implementación de Aplicaciones Microsoft 365 por parte de los asociados en el portal de aplicaciones integradas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Busque, pruebe e implemente aplicaciones de asociados de Microsoft y Microsoft para usuarios y grupos de su organización desde el portal aplicaciones integradas de la Centro de administración de Microsoft 365.
ms.openlocfilehash: 3592cea8c7da906376bfd0cd8e08a71d1d298278
ms.sourcegitcommit: 13a1199fbfeb329da77ce87b2781d5cc77e4a201
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2022
ms.locfileid: "67037598"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Prueba e implementación de Aplicaciones Microsoft 365 por parte de los asociados en el portal de aplicaciones integradas

El Centro de administración de Microsoft 365 le ofrece la flexibilidad de implementar aplicaciones de una sola tienda, una línea de negocio personalizada de aplicaciones y aplicaciones de asociados de Microsoft 365 desde una sola ubicación. Se puede acceder a la ubicación en la configuración del Centro de microsoft Administración, en Aplicaciones integradas. La capacidad de encontrar, probar e implementar completamente aplicaciones compradas y con licencia por parte de los asociados de Microsoft desde el portal de aplicaciones integradas proporciona la comodidad y las ventajas que su organización requiere para mantener actualizados los servicios empresariales periódicamente y ejecutarse de forma eficaz.

Para obtener información adicional sobre cómo comprar y licenciar aplicaciones de Microsoft 365 de asociados de su organización, consulte [Administración e implementación de Aplicaciones Microsoft 365 desde el Centro de administración de Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Para obtener más información sobre cómo los asociados crean estas aplicaciones, consulte [How to plan a SaaS offer for the commercial marketplace (Planeamiento de una oferta de SaaS para marketplace comercial).](https://go.microsoft.com/fwlink/?linkid=2158277)

El portal de aplicaciones integradas solo está disponible para clientes de todo el mundo y los administradores globales, los lectores globales y los administradores de Exchange pueden acceder a ellos. Esta característica no está disponible en nubes soberanas y gubernamentales.

El portal aplicaciones integradas muestra una lista de aplicaciones, que incluye aplicaciones únicas y aplicaciones de Microsoft 365 de asociados que se implementan en su organización. Solo se muestran aplicaciones web, aplicaciones SPFx, complementos de Office y aplicaciones de Teams. En el caso de las aplicaciones web, puede ver dos tipos de aplicaciones.

- Aplicaciones SaaS que están disponibles en appsource.microsoft.com y que los administradores pueden implementar dando su consentimiento en nombre de la organización.
- Aplicaciones de la galería saml que están vinculadas a complementos de Office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Administración de aplicaciones en el portal de aplicaciones integradas

Puede administrar las pruebas y la implementación de Aplicaciones Microsoft 365 compradas y con licencia de asociados.

1. En el Centro de administración, seleccione **Configuración** y, después, **Aplicaciones integradas**.

2. Elija una aplicación con **Estado** de **Más aplicaciones disponibles** para abrir el panel **Administrar** . El estado de **más aplicaciones disponibles** le permite saber que hay más integraciones de los ISV que aún no se han implementado.

3. En la pestaña **Información general** , seleccione **Implementar**. Algunas aplicaciones requieren que agregue usuarios para poder seleccionar Implementar.

4. Seleccione  **Usuarios**, elija **Es una implementación de prueba** y, a continuación, elija **Toda la organización**, **Usuarios o grupos específicos** o **Solo yo**. También puede elegir **Probar implementación** si prefiere esperar a implementar la aplicación en toda la organización. Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo de distribución.

5. Seleccione **Actualizar** y, a continuación, **Listo**. Ahora puede seleccionar Implementar en la pestaña Información general.

6. Revise la información de la aplicación y, a continuación, seleccione **Implementar**.

7. Seleccione **Listo** en la página Implementación completada y revise los detalles de la prueba o la implementación completa en la pestaña **Información general** .

8. Si la aplicación tiene un estado de **Actualización pendiente**, puede hacer clic en la aplicación para abrir el panel Administrar y actualizar la aplicación.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Búsqueda de aplicaciones publicadas para pruebas e implementación completa

Puede encontrar, probar e implementar completamente las aplicaciones publicadas que aún no aparecen en la lista de la página Aplicaciones integradas. Al comprar y conceder licencias a las aplicaciones desde el Centro de administración, puede agregar aplicaciones de microsoft y de asociados de Microsoft a la lista desde una sola ubicación.

1. En el centro de administración, en el panel de navegación izquierdo, elija **Configuración** y, a continuación, seleccione <a href="https://admin.microsoft.com/adminportal/home?#/Settings/IntegratedApps" target="_blank">**Aplicaciones integradas**</a>.

2. Seleccione **Obtener aplicaciones** para obtener una vista de las aplicaciones.

3. En la página **Aplicaciones Microsoft 365** aplicaciones publicadas, seleccione la aplicación que desea implementar; para ello, elija **Obtenerla ahora**. Las aplicaciones que se muestran principalmente son Word, PowerPoint, Excel, complementos de Outlook, aplicaciones de Teams y aplicaciones de SharePoint (basadas en SharePoint Framework tecnología). Acepte los permisos y seleccione **Continuar**.

5. Seleccione **Implementar** en la parte superior de la página situada junto al mensaje que hace referencia a la espera de implementarse.

    Si un ISV vincula la aplicación seleccionada a una oferta SaaS, todas las demás aplicaciones que forman parte de esta oferta vinculada aparecerán en la página Configuración. Si decide implementar todas las aplicaciones, seleccione **Siguiente**. De lo contrario, seleccione **Editar** y elija qué aplicaciones desea implementar. Algunas aplicaciones requieren que agregue usuarios para poder seleccionar **Implementar**.

6. Seleccione **Agregar usuarios**, elija **Es una implementación de prueba** y, a continuación, elija **Toda la organización** , **Usuarios o grupos específicos** o **Solo yo**.

    Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo distribuido. También puede elegir **Probar implementación** si prefiere esperar a implementar la aplicación en toda la organización.

7. Seleccione **Siguiente** para ir a la página **Aceptar solicitud de permiso** . Se muestran las funcionalidades y permisos de la aplicación de cada una de las aplicaciones. Si la aplicación necesita consentimiento, seleccione **Aceptar permisos**. Solo un administrador global puede dar su consentimiento.

8. Seleccione **Siguiente** para revisar la implementación y elija **Finalizar implementación**. Para ver la implementación desde la pestaña **Información general** , elija **Ver esta implementación**. En el Centro de administración de Microsoft 365, puede ver el estado de cada aplicación implementada y la fecha en que implementó la aplicación.

> [!NOTE]
> Si una aplicación se implementó anteriormente desde un lugar distinto del portal aplicaciones integradas, el **tipo de implementación** es **Personalizado.**

## <a name="unsupported-scenarios"></a>Escenarios no admitidos

No podrá implementar una sola aplicación de tienda ni Aplicaciones Microsoft 365 por asociado desde el portal aplicaciones integradas para los siguientes escenarios.

- El mismo complemento está vinculado a más de una oferta de SaaS.
- La oferta de SaaS está vinculada a complementos, pero no se integra con Microsoft Graph y no se proporciona ningún identificador de aplicación de AAD.
- La oferta de SaaS está vinculada a complementos, pero el identificador de aplicación de AAD proporcionado para la integración de Microsoft Graph se comparte entre varias ofertas de SaaS.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Carga de aplicaciones de línea de negocio personalizadas para pruebas e implementación completa

1. En el centro de administración, en el panel de navegación izquierdo, elija **Configuración** y, a continuación, **Aplicaciones integradas**.

2. Seleccione **Cargar aplicaciones personalizadas**. Solo se admite una línea personalizada de aplicaciones para Word, PowerPoint, Excel y Outlook.

3. Cargue el archivo de manifiesto desde el dispositivo o agregue un vínculo de dirección URL. Algunas aplicaciones requieren que agregue usuarios para poder seleccionar Implementar.

4. Seleccione **Agregar usuarios**, elija **Es una implementación de prueba** y elija **Toda la organización** , **Usuarios o grupos específicos** o **Solo yo**.

    Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo distribuido. También puede elegir **Probar implementación** si desea esperar a implementar la aplicación en toda la organización.

5. Seleccione **Siguiente** para ir a la página **Aceptar solicitud de permiso** . Se enumeran las funcionalidades y permisos de la aplicación de las aplicaciones. Si la aplicación necesita consentimiento, seleccione **Aceptar permisos**. Solo un administrador global puede dar su consentimiento.

6. Seleccione **Siguiente** para revisar la implementación y elija **Finalizar implementación**. Para ver la implementación desde la pestaña **Información general** , elija **Ver esta implementación**.

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Preparación para implementar complementos en aplicaciones integradas

Los complementos de Office le ayudan a personalizar sus documentos y a simplificar la forma en que accede a la información en la web (consulte Inicio del uso de su complemento de Office). 

Los complementos proporcionan las siguientes ventajas: 

- Cuando se inicia la aplicación de Office correspondiente, el complemento se descarga automáticamente. Si el complemento admite comandos de complemento, el complemento aparece automáticamente en la cinta de opciones dentro de la aplicación de Office. 

- Los complementos ya no aparecen para los usuarios si el administrador desactiva o elimina el complemento, o si el usuario se quita de Azure Active Directory o de un grupo al que está asignado el complemento. 

Los complementos se admiten en tres plataformas de escritorio windows, mac y aplicaciones de Office en línea. También se admite en iOS y Android (solo complementos de Outlook Mobile). 

Un complemento puede tardar hasta 24 horas en aparecer para el cliente para todos los usuarios. 

En la actualidad, tanto los administradores de Exchange como los administradores globales pueden implementar complementos desde aplicaciones integradas.   

### <a name="before-you-begin"></a>Antes de empezar

La implementación de complementos requiere que los usuarios usen licencias de Microsoft 365 Business (Business Basic, Business Standard, Business Premium), licencias de Office 365 Enterprise (E1/E3/E5/F3) o licencias de Microsoft 365 Enterprise (E3/E5/F3). Los usuarios también deben iniciar sesión en Office con su identificador de organización) y tener Exchange Online y buzones de Exchange Online activos. El directorio de suscripción debe estar en o estar federado en Azure Active Directory. 

La implementación no admite lo siguiente: 

- Complementos que tengan como objetivo Word, Excel o PowerPoint en Office 2013 
- Un servicio de directorio local 
- Implementación de complementos en un buzón local de Exchange 
- Implementación de complementos de modelo de objetos componentes (COM) o Visual Studio Tools para Office (VSTO). 
- Implementaciones de Microsoft 365 que no incluyen Exchange Online como Aplicaciones Microsoft 365 para empresas y Aplicaciones Microsoft 365 para empresas.  

### <a name="office-requirements"></a>Requisitos de Office 

Para los complementos de Word, Excel y PowerPoint, los usuarios deben usar uno de los siguientes elementos: 
- En un dispositivo Windows, versión 1704 o posterior de licencias de Microsoft 365 Business (Business Basic, Business Standard, Business Premium), licencias de Office 365 Enterprise (E1/E3/E5/F3) o licencias de Microsoft 365 Enterprise (E3/E5/F3). 
- En un Equipo Mac, versión 15.34 o posterior. 

Para Outlook, los usuarios deben usar uno de los siguientes elementos: 
- Versión 1701 o posterior de licencias empresariales de Microsoft 365 (Business Basic, Business Standard, Business Premium), licencias de Office 365 Enterprise (E1/E3/E5/F3) o licencias de Microsoft 365 Enterprise (E3/E5/F3). 
- Versión 1808 o posterior de Office Profesional Plus 2019 o Office Standard 2019. 
- Versión 16.0.4494.1000 o posterior de Office Profesional Plus 2016 (MSI) o Office Standard 2016 (MSI).
    > [!NOTE]
    > Las versiones MSI de Outlook muestran complementos instalados por el administrador en la cinta de opciones de Outlook adecuada, no en la sección "Mis complementos".  
- Versión 15.0.4937.1000 o posterior de Office Profesional Plus 2013 (MSI) o Office Standard 2013 (MSI).
- Versión 16.0.9318.1000 o posterior de Office 2016 para Mac. 
- Versión 2.75.0 o posterior de Outlook mobile para iOS. 
- Versión 2.2.145 o posterior de Outlook mobile para Android. 



### <a name="exchange-online-requirements"></a>requisitos de Exchange Online 
Microsoft Exchange almacena los manifiestos de complemento dentro del inquilino de la organización. Los administradores que implementan complementos y los usuarios que reciben esos complementos deben estar en una versión de Exchange Online que admita la autenticación de OAuth. 

Póngase en contacto con el administrador de Exchange de su organización para averiguar qué configuración está en uso. La conectividad de OAuth por usuario puede comprobarse usando el cmdlet de PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity). 

### <a name="user-and-group-assignments"></a>Asignaciones de usuario y de grupo
La implementación del complemento se admite actualmente en la mayoría de los grupos admitidos por Azure Active Directory, incluidos los grupos de Microsoft 365, las listas de distribución y los grupos de seguridad. La implementación admite usuarios de grupos o grupos de nivel superior sin grupos primarios, pero no usuarios de grupos anidados o grupos que tienen grupos primarios. 

> [!NOTE]
> Los grupos de seguridad no habilitados para correo no son compatibles en estos momentos. 

En el ejemplo siguiente, Sandra, Sheila y el grupo Departamento de ventas se asignan a un complemento. Como el departamento de ventas de la Costa Occidental es un grupo anidado, Bert y Fred no están asignados a un complemento. 

![Diagrama del departamento de ventas.](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Averiguar si un grupo contiene grupos anidados

La forma más sencilla de detectar si un grupo contiene grupos anidados es ver la tarjeta de contacto del grupo en Outlook. Si escribe el nombre del grupo en el campo **Para** de un correo electrónico y, a continuación, selecciona el nombre del grupo cuando se resuelve, se mostrará si contiene usuarios o grupos anidados. En el ejemplo siguiente, la pestaña **Miembros** de la tarjeta de contacto de Outlook del grupo de pruebas no muestra usuarios, solo dos subgrupos. 

![Pestaña Miembros de la tarjeta de contacto de Outlook.](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

Puede realizar la consulta opuesta para comprobar si un grupo es miembro de cualquier otro. En el ejemplo siguiente, puede ver en la pestaña <b>Miembros</b> de la tarjeta de contacto de Outlook que el Subgrupo 1 es miembro del grupo de pruebas. 

![Pestaña Pertenencia de la tarjeta de contacto de Outlook.](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Tenga en cuenta que puede usar el Graph API de Azure Active Directory para ejecutar consultas para buscar la lista de grupos dentro de un grupo. Para obtener más información, vea [Operaciones en grupos | Referencia de API de Graph](/previous-versions/azure/ad/graph/api/groups-operations). 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar complementos de Office 
Para implementar complementos mediante un enfoque por fases, se recomienda lo siguiente: 
1. Implemente el complemento en un pequeño conjunto de participantes y miembros del departamento de TI. Puede activar la marca **¿Se trata de una implementación de prueba**? Si la implementación se realiza correctamente, vaya al paso 2. 

2. Implemente el complemento para más personas dentro de la empresa. De nuevo, evalúe los resultados y, si se ejecuta correctamente, continúe con la implementación completa. 

3. Realice una implementación completa para todos los usuarios. Desactive la marca de **¿Se trata de una implementación de prueba**? 

En función del tamaño de la audiencia de destino, puede agregar o quitar pasos de implementación.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementación de un complemento de Office mediante el Centro de administración 

1. En el Centro de administración, seleccione **Configuración** y, después, **Aplicaciones integradas**. 

2. Seleccione **Obtener aplicaciones** en la parte superior de la página. AppSource se cargará en un formato incrustado. Busque un complemento o búscolo haciendo clic en Producto en el panel de navegación izquierdo.  Si el ISV ha vinculado el complemento a una aplicación SaaS u otras aplicaciones y complementos y si la aplicación SaaS es una aplicación de pago, se mostrará un cuadro de diálogo para comprar la licencia o Implementar. Independientemente de si ha comprado la licencia o no, puede continuar con la implementación. Seleccione **Implementar**.  

3. Verá la página **Configuración** donde se muestran todas las aplicaciones. Si no tiene permisos ni el acceso adecuado para implementar la aplicación, se resaltará la información correspondiente. Puede seleccionar las aplicaciones que desea implementar. Al seleccionar **Siguiente**, verá la página **Usuarios** . Si el ISV no ha vinculado el complemento, se le enrutará a la página Usuarios. 

4. Seleccione **Todos**, **Usuarios o grupos específicos** o **Solo yo** para especificar en quién se implementa el complemento. Use el cuadro Buscar para buscar usuarios o grupos específicos. Si va a probar el complemento, seleccione **Is this a test deployment (Es esta una implementación de prueba**). 

5. Seleccione **Siguiente**. Todas las funcionalidades y permisos de la aplicación se muestran en un solo panel junto con la información de certificación si la aplicación tiene la certificación de Microsoft 365. Al seleccionar el logotipo de certificación, el usuario puede ver más detalles sobre la certificación.  

6. Revise y, a continuación, seleccione **Finalizar implementación**.  

7. Cuando se implementa el complemento, aparece un icono verde de "tic". Siga las instrucciones de la página para probar el complemento. 

> [!NOTE]
> Es posible que los usuarios necesiten volver a iniciar Office para ver el icono del complemento en la cinta de opciones de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de las aplicaciones. 

Se recomienda informar a los usuarios y grupos de que el complemento implementado está disponible. Considere la posibilidad de enviar un correo electrónico que describa cuándo y cómo usar el complemento. Incluya o vincule para ayudar al contenido o a las preguntas más frecuentes que podrían ayudar a los usuarios si tienen problemas con el complemento. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Consideraciones al asignar un complemento a usuarios y grupos 

Los administradores globales y los administradores de Exchange pueden asignar un complemento a todos o a usuarios y grupos específicos. Cada opción tiene implicaciones: 

- **Todos** Esta opción asigna el complemento a todos los usuarios de la organización. Use esta opción con moderación y solo para los complementos que realmente sean de uso universal en su organización. 

- **Usuarios** Si asigna un complemento a un usuario individual y, a continuación, implementa el complemento en un nuevo usuario, primero debe agregar el nuevo usuario. 

- **Grupos** Si asigna un complemento a un grupo, a los usuarios que se agregan al grupo se les asigna automáticamente el complemento. Cuando se quita un usuario de un grupo, el usuario pierde el acceso al complemento. En cualquier caso, el administrador no requiere ninguna acción adicional. 

- **Sólo yo** Si asigna un complemento solo a usted mismo, el complemento se asigna solo a su cuenta, lo que es ideal para probar el complemento. 

La opción adecuada para su organización depende de la configuración. Sin embargo, se recomienda realizar asignaciones mediante grupos. Como administrador, es posible que le resulte más fácil administrar complementos mediante el uso de grupos y el control de la pertenencia de esos grupos en lugar de asignar usuarios individuales cada vez. En algunas situaciones, es posible que quiera restringir el acceso a un pequeño conjunto de usuarios mediante la realización de asignaciones a usuarios específicos mediante la asignación manual de usuarios. 

### <a name="more-about-office-add-ins-security"></a>Más información sobre la seguridad de los complementos de Office 
Los complementos de Office combinan un archivo de manifiesto XML que contiene algunos metadatos sobre el complemento, pero lo más importante apunta a una aplicación web que contiene todo el código y la lógica. Las funcionalidades de los complementos pueden variar. Estos son algunos ejemplos de las acciones que pueden realizar los complementos:
- Mostrar datos. 
- Leer el documento de un usuario para proporcionar servicios contextuales. 
- Leer datos del documento de un usuario y escribir datos en él para proporcionar valor a ese usuario.  

Para obtener más información sobre los tipos y funcionalidades de los complementos de Office, vea [Información general sobre la plataforma de complementos de Office](/office/dev/add-ins/overview/office-add-ins), especialmente la sección "Anatomía de un complemento de Office". 

Para poder interactuar con el documento del usuario, el complemento debe declarar qué permisos necesita en el manifiesto. Un modelo de permisos de acceso de la API de JavaScript de cinco niveles proporciona la base para la privacidad y la seguridad de los usuarios de los complementos de panel de tareas. La mayoría de los complementos de la Tienda Office son del nivel ReadWriteDocument y casi todos los complementos admiten, como mínimo, el nivel ReadDocument. Para obtener más información sobre los niveles de permisos, consulte [Solicitar permisos para el uso de la API en los complementos del panel de tareas y de contenido](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins). 

Cuando se actualiza un manifiesto, los cambios típicos se aplican al icono de un complemento y al texto. En ocasiones, los comandos del complementos cambian. Sin embargo, los permisos del complemento no cambian. La aplicación web en la que se ejecutan todo el código y la lógica del complemento puede cambiar en cualquier momento, lo que forma parte de la naturaleza de las aplicaciones web. 

Las actualizaciones de los complementos se producen de la siguiente manera: 
- **Complemento de línea de negocio: en** este caso, donde un administrador cargó explícitamente un manifiesto, el complemento requiere que el administrador cargue un nuevo archivo de manifiesto para admitir los cambios de metadatos. La próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento. 

- Complemento de la **Tienda Office**: cuando un administrador seleccionó un complemento de la Tienda Office, si un complemento se actualiza en la Tienda Office, la próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento. 

> [!NOTE]
> Para Word, Excel y PowerPoint, use un catálogo de aplicaciones de [SharePoint](/sharepoint/dev/sp-add-ins/publish-sharepoint-add-ins) para implementar complementos en los usuarios de un entorno local sin conexión a Microsoft 365 ni compatibilidad con complementos de SharePoint necesarios. Para Outlook, use el panel de control de Exchange para implementarlo en un entorno local sin una conexión a Microsoft 365.  

## <a name="add-in-states"></a>Estados del complemento
Un complemento puede estar en estado **Activado** o **Desactivado** . 

| Estado | Cómo se produce el estado | Impacto |
|:-----|:-----|:-----|
|**Activo**  <br/> |Administración cargó el complemento y lo asignó a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
 
Considere la posibilidad de eliminar un complemento si ya no lo usa nadie. Por ejemplo, desactivar un complemento podría tener sentido si un complemento se usa solo durante horas específicas del año. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Administración de un complemento de Office mediante el Centro de administración

Después de la implementación, los administradores también pueden administrar el acceso de los usuarios a los complementos. 

1. En el Centro de administración, seleccione **Configuración** y, después, **Aplicaciones integradas**. 
2. En la página Aplicaciones integradas, mostrará una lista de aplicaciones que serán complementos únicos o complementos que se han vinculado a otras aplicaciones. 
3. Seleccione una aplicación con **Estado** de **Más aplicaciones disponibles** para abrir el panel **Administrar** . El estado de **más aplicaciones disponibles** le permite saber que hay más integraciones de los ISV que aún no se han implementado. 
4. En la pestaña **Información general** , seleccione **Implementar**. Algunas aplicaciones requieren que agregue usuarios para poder seleccionar Implementar. 
5. Seleccione **Usuarios**, seleccione **Es una implementación de prueba** y, a continuación, seleccione **Toda la organización**, **Usuarios o grupos específicos** o **Solo yo**. También puede seleccionar **Probar implementación** si prefiere esperar a implementar la aplicación en toda la organización. Los usuarios o grupos específicos pueden ser un grupo de Microsoft 365, un grupo de seguridad o un grupo de distribución. 
6. Seleccione **Actualizar** y, a continuación, haga **clic en Listo**. Ahora puede seleccionar **Implementar** en la pestaña **Información general** . 
7. Revise la información de la aplicación y, a continuación, seleccione **Implementar**.
8. Seleccione **Listo** en la página **Implementación completada** y revise los detalles de la prueba o la implementación completa en la pestaña **Información general** . 
9. Si la aplicación tiene un estado de **Actualización pendiente**, puede hacer clic en la aplicación para abrir el panel **Administrar** y actualizar la aplicación. 
10. Para actualizar los usuarios, seleccione la pestaña **Usuarios** y realice el cambio adecuado. Seleccione **Actualizar** después de realizar los cambios.  

> [!NOTE]
> Solo el administrador que implementó el complemento o un administrador global puede administrar ese complemento.

## <a name="delete-an-add-in"></a>Eliminar un complemento

También puede eliminar un complemento que se implementó.

1. En el Centro de administración, seleccione **Configuración** y, después, **Aplicaciones integradas** .
2. Seleccione cualquier fila para mostrar el panel de administración. 
3. Seleccione la pestaña **Configuración** . 
4. Seleccione el complemento que desea eliminar y, a continuación, seleccione **Quitar**.  

> [!NOTE]
>  Si otro administrador ha implementado el complemento, se deshabilitará el botón Quitar. Solo el administrador que ha implementado la aplicación o un administrador global puede eliminar el complemento.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Escenarios en los que el administrador de Exchange no puede implementar un complemento 

Hay dos casos en los que un Administración de Exchange no podrá implementar un complemento:

- Si un complemento necesita permiso para las API de MS Graph y necesita el consentimiento de un administrador global.
- Si un complemento está vinculado a dos o más complementos y aplicaciones web, y al menos uno de estos complementos lo implementa otro administrador (exchange/global) y la asignación de usuario no es uniforme. Solo se permite la implementación de complementos cuando la asignación de usuario es la misma para todas las aplicaciones ya implementadas.  


## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>¿Qué rol de administrador necesito para acceder a las aplicaciones integradas?

Solo los administradores globales y los administradores de Exchange pueden acceder a las aplicaciones integradas. Las aplicaciones integradas no se mostrarán en el panel de navegación izquierdo para otros administradores.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>¿Por qué veo el complemento en el panel de navegación izquierdo en Configuración pero no Aplicaciones integradas?

Puede haber algunas razones:

- El administrador que ha iniciado sesión es un administrador de Exchange.
- El cliente está en la nube soberana y la experiencia de aplicaciones integradas está disponible para los clientes de nube soberana.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>¿Qué aplicaciones puedo implementar desde aplicaciones integradas?

Las aplicaciones integradas permiten la implementación de Web Apps, aplicaciones de Teams, Excel, PowerPoint, Word, complementos de Outlook y aplicaciones SPFx. En el caso de los complementos, las aplicaciones integradas admiten la implementación en buzones de Exchange online y no en buzones de Exchange locales.

### <a name="can-administrators-delete-or-remove-apps"></a>¿Pueden los administradores eliminar o quitar aplicaciones?

Solo el administrador que implementó la aplicación o el complemento o un administrador global puede eliminarla o quitarla.

- Seleccione una aplicación en la vista de lista. En la pestaña **Configuración** , seleccione las aplicaciones que desea quitar.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>¿Están disponibles las aplicaciones integradas en la nube soberana?

No. Las aplicaciones integradas no están disponibles para los clientes de nube soberana.

### <a name="is-integrated-apps-available-in-government-clouds"></a>¿Están disponibles las aplicaciones integradas en las nubes gubernamentales?

No. Las aplicaciones integradas no están disponibles para los clientes de la nube gubernamental.
