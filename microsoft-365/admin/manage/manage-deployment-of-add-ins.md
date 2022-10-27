---
title: Implementar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Aprenda a implementar complementos en usuarios y grupos de su organización mediante la implementación centralizada en el centro de administración.
ms.openlocfilehash: ad44b5c415507dfbd9944f460da963e39b582b36
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68733865"
---
# <a name="deploy-add-ins-in-the-microsoft-365-admin-center"></a>Implementación de complementos en el Centro de administración de Microsoft 365

Los complementos de Office le ayudan a personalizar sus documentos y a simplificar la forma en que accede a la información en la web (consulte [Inicio del uso de su complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, puede implementar complementos de Office para los usuarios de su organización mediante la característica Implementación centralizada en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. La implementación centralizada es la manera recomendada y más rica en características para que la mayoría de los administradores implementen complementos en usuarios y grupos dentro de una organización.

Para obtener más información sobre cómo determinar si su organización puede admitir la implementación centralizada, consulte [Determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).

Para más información sobre la administración de complementos después de la implementación, consulte [Administración de complementos en el Centro de administración](manage-addins-in-the-admin-center.md).
  
> [!NOTE]
>  Para Word, Excel y PowerPoint, use un catálogo de aplicaciones de [SharePoint](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implementar complementos en los usuarios de un entorno local sin conexión a Microsoft 365 ni compatibilidad con complementos de SharePoint necesarios. Para Outlook, use el panel de control de Exchange para implementarlo en un entorno local sin una conexión a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar complementos de Office

Para implementar complementos mediante un enfoque por fases, se recomienda lo siguiente:
  
1. Implemente el complemento en un pequeño conjunto de participantes y miembros del departamento de TI. Si la implementación se realiza correctamente, vaya al paso 2.
    
2. Implemente el complemento para más personas dentro de la empresa. De nuevo, evalúe los resultados y, si se ejecuta correctamente, continúe con la implementación completa.
    
3. Realice una implementación completa para todos los usuarios.
    
En función del tamaño de la audiencia de destino, puede agregar o quitar pasos de implementación.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementación de un complemento de Office mediante el Centro de administración

Antes de empezar, consulte [Determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).
  
1. En el centro de administración, vaya a la página **Complementos de** **aplicaciones** \> integradas **de configuración**\>.

2. Seleccione **Distribuir complemento** en la parte superior de la página y, a continuación, seleccione **Siguiente**.

    > [!NOTE]
    > También puede implementar complementos en el centro de administración a través de [Aplicaciones integradas](test-and-deploy-microsoft-365-apps.md). Las aplicaciones integradas son visibles para los administradores de Global y de Exchange. Si no ve los pasos anteriores, vaya a la sección Implementación centralizada. Para ello, vaya a **Configuración Aplicaciones** > **integradas**. En la parte superior de la página **Aplicaciones integradas** , elija **Complementos**.

3. Seleccione una opción y siga las instrucciones.
  
4. Si seleccionó la opción para agregar un complemento desde la Tienda Office, realice la selección del complemento. </br>

    Puede ver los complementos disponibles por categorías: **Sugeridos para usted**, **Clasificación** o **Nombre**. Solo los complementos gratuitos están disponibles en la Tienda Office. Los complementos de pago no son compatibles en estos momentos. Después de seleccionar un complemento, acepte los términos y condiciones para continuar. <br/> 

    > [!NOTE]
    > Con la opción Tienda Office, las actualizaciones y mejoras se implementan automáticamente para los usuarios.

5. En la página siguiente, seleccione **Todos los usuarios**, **Usuarios o grupos específicos** o **Solo yo** para especificar a quién se implementará el complemento. Use el cuadro Buscar para buscar usuarios o grupos específicos. <br/>

    > [!NOTE]
    > Para obtener información sobre otros estados que se aplican a un complemento, consulte [Estados de complemento](./manage-addins-in-the-admin-center.md).
  
6. Seleccione **Implementar**.
  
7. Aparece un tic verde cuando se implementa el complemento. Siga las instrucciones de la página para probar el complemento.

    > [!NOTE]
    > Es posible que los usuarios necesiten volver a iniciar Office para ver el icono del complemento en la cinta de opciones de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de las aplicaciones.

8. Cuando termine, seleccione **Siguiente**. Si ha implementado solo en sí mismo, puede seleccionar **Cambiar quién tiene acceso al complemento** para implementarlo en más usuarios.

    Si ha implementado el complemento en otros miembros de la organización, siga las instrucciones para anunciar la implementación del complemento. <br/>
  
    Se recomienda informar a los usuarios y grupos de que el complemento implementado está disponible. Considere la posibilidad de enviar un correo electrónico que describa cuándo y cómo usar el complemento. Incluya o vincule al contenido de ayuda o preguntas más frecuentes que podrían ayudar a los usuarios si tienen problemas con el complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Consideraciones al asignar un complemento a usuarios y grupos

Los administradores globales y los administradores de Exchange pueden asignar un complemento a todos o a usuarios y grupos específicos. Cada opción tiene implicaciones:
  
- **Todos** Esta opción asigna el complemento a todos los usuarios de la organización. Use esta opción con moderación y solo para los complementos que realmente sean de uso universal en su organización.

- **Usuarios** Si asigna un complemento a un usuario individual y, a continuación, implementa el complemento en un nuevo usuario, primero debe agregar el nuevo usuario.

- **Grupos** Si asigna un complemento a un grupo, a los usuarios que se agregan al grupo se les asigna automáticamente el complemento. Cuando se quita un usuario de un grupo, el usuario pierde el acceso al complemento. En cualquier caso, el administrador no requiere ninguna acción adicional.

- **Sólo yo** Si asigna un complemento solo a usted mismo, el complemento se asigna solo a su cuenta, lo que es ideal para probar el complemento.

La opción adecuada para su organización depende de la configuración. Sin embargo, se recomienda realizar asignaciones mediante grupos. Como administrador, es posible que le resulte más fácil administrar complementos mediante el uso de grupos y el control de la pertenencia de esos grupos en lugar de asignar usuarios individuales cada vez. En algunas situaciones, es posible que quiera restringir el acceso a un pequeño conjunto de usuarios mediante la realización de asignaciones a usuarios específicos mediante la asignación manual de usuarios.
  
## <a name="more-about-office-add-ins-security"></a>Más información sobre la seguridad de los complementos de Office

Los complementos de Office combinan un archivo de manifiesto XML que contiene algunos metadatos sobre el complemento, pero lo más importante apunta a una aplicación web que contiene todo el código y la lógica. Las funcionalidades de los complementos pueden variar. Estos son algunos ejemplos de las acciones que pueden realizar los complementos:
  
- Mostrar datos.

- Leer el documento de un usuario para proporcionar servicios contextuales.

- Leer datos del documento de un usuario y escribir datos en él para proporcionar valor a ese usuario.

Para obtener más información sobre los tipos y funcionalidades de los complementos de Office, vea [Información general sobre la plataforma de complementos de Office](/office/dev/add-ins/overview/office-add-ins), especialmente la sección "Anatomía de un complemento de Office".
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Las actualizaciones de los complementos se producen de la siguiente manera:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.

    > [!NOTE]
    > Administración no es necesario quitar un complemento de LOB para realizar una actualización.   En la sección Complementos, Administración simplemente puede hacer clic en el complemento de LOB y elegir el **botón Actualizar** en la esquina inferior derecha. La actualización solo funcionará si la versión del nuevo complemento es mayor que la del complemento existente.

- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time.
  
## <a name="related-content"></a>Contenido relacionado

[Administrar complementos en el Centro de administración](manage-addins-in-the-admin-center.md) (artículo)\
[Compilación del primer complemento de panel de tareas de Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (artículo\
[Menores y adquisición de complementos de la tienda](minors-and-acquiring-addins-from-the-store.md) (artículo)\
[Uso de cmdlets de PowerShell de implementación centralizada para administrar complementos](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (artículo)\
[Solución de problemas: El usuario no ve complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artículo)
