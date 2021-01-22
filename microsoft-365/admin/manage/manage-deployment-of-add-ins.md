---
title: Implementar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Aprenda a implementar complementos para usuarios y grupos de su organización mediante la implementación centralizada en el centro de administración.
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926359"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implementar complementos en el centro de administración

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Los complementos de Office le ayudan a personalizar los documentos y simplificar la forma en que accede a la información en la web (vea [Empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, puede implementar complementos de Office para los usuarios de su organización mediante la característica Implementación centralizada en el Centro de administración de Microsoft 365. La implementación centralizada es la forma recomendada y con más características para que la mayoría de los administradores implemente complementos para usuarios y grupos dentro de una organización. 

Para obtener más información sobre cómo determinar si su organización puede admitir la implementación centralizada, vea Determinar si la implementación centralizada de complementos funciona [para su organización.](centralized-deployment-of-add-ins.md)

Para obtener más información sobre la administración de complementos después de la implementación, vea Administrar complementos [en el Centro de administración](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Para Word, Excel y PowerPoint usan un Catálogo de aplicaciones de [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implementar complementos para los usuarios en un entorno local sin conexión a Microsoft 365 ni compatibilidad con complementos de SharePoint necesarios. Para que Outlook use el panel de control de Exchange para implementar en un entorno local sin conexión a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar complementos de Office

Para implantar complementos mediante un enfoque por fases, se recomienda lo siguiente:
  
1. Roll out the add-in to a small set of business stakeholders and members of the IT department. Si la implementación se realiza correctamente, pase al paso 2.
    
2. Roll out the add-in to more individuals within the business. De nuevo, evalúe los resultados y, si se realiza correctamente, continúe con la implementación completa.
    
3. Realizar una implementación completa para todos los usuarios.
    
Según el tamaño de la audiencia de destino, puede agregar o quitar pasos de implementación.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementar un complemento de Office con el Centro de administración

Antes de empezar, vea Determinar si la implementación centralizada de complementos [funciona para su organización.](centralized-deployment-of-add-ins.md)
  
1. En el centro de administración, vaya a **la** \> **página Complementos de** configuración. Si no ve la página **del** complemento,  vaya a la página Complementos de aplicaciones \>  \> **integradas de configuración.**
    
2. Seleccione **Implementar complemento en** la parte superior de la página y, a continuación, seleccione **Siguiente**.
 
    > [!NOTE]
    > El centro de administración se está actualizando a la experiencia de implementación con aplicaciones integradas. Si no ves los pasos anteriores, ve a la sección Implementación centralizada yendo **a** Aplicaciones integradas  >  **de configuración.** En la parte superior de la **página Aplicaciones** **integradas,** elija Complementos.
    
3. Seleccione una opción y siga las instrucciones.
  
4. Si seleccionó la opción para agregar un complemento desde la Tienda Office, haga la selección del complemento. </br>

    Puede ver los complementos disponibles por categorías: **Sugerido para usted,** **Clasificación** o **Nombre.** Solo los complementos gratuitos están disponibles en la Tienda Office. Los complementos de pago no son compatibles en estos momentos. Después de seleccionar un complemento, acepte los términos y condiciones para continuar. <br/> 

    > [!NOTE] 
    > Con la opción Tienda Office, las actualizaciones y mejoras se implementan automáticamente para los usuarios.

5. En la página siguiente, seleccione **Todos,**  Usuarios **o** grupos específicos, o Solo yo para especificar en quién se implementa el complemento. Use el cuadro de búsqueda para buscar usuarios o grupos específicos. <br/>

    > [!NOTE] 
    > Para obtener información sobre otros estados que se aplican a un complemento, vea [Estados de complemento.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)
  
6. Seleccione **Implementar**.
  
7. Cuando se implementa el complemento, aparece una marca de graduación verde. Siga las instrucciones en la página para probar el complemento.

    > [!NOTE]
    > Es posible que los usuarios deba reiniciar Office para ver el icono del complemento en la cinta de opciones de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de opciones de la aplicación.
    
8. Cuando haya terminado, seleccione **Siguiente**. Si se ha implementado solo en  usted mismo, puede seleccionar Cambiar quién tiene acceso al complemento para implementarlo para más usuarios.

    Si ha implementado el complemento en otros miembros de la organización, siga las instrucciones para anunciar la implementación del complemento. <br/>
  
    Es una buena práctica informar a los usuarios y grupos de que el complemento implementado está disponible. Considere la posibilidad de enviar un correo electrónico que describa cuándo y cómo usar el complemento. Incluir o vincular contenido de ayuda o preguntas frecuentes que pueden ayudar a los usuarios si tienen problemas con el complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Consideraciones al asignar un complemento a usuarios y grupos

Los administradores pueden asignar un complemento para todos los usuarios o para usuarios y grupos específicos. Cada opción tiene implicaciones:
  
- **Todos** Esta opción asigna el complemento a todos los usuarios de la organización. Use esta opción con moderación y solo para los complementos que realmente sean de uso universal en su organización. 
    
- **Usuarios** Si asigna un complemento a un usuario individual y, a continuación, implementa el complemento en un nuevo usuario, primero debe agregar el nuevo usuario.
    
- **Grupos** Si asigna un complemento a un grupo, se asigna automáticamente el complemento a los usuarios que se agregan al grupo. Cuando se quita un usuario de un grupo, el usuario pierde el acceso al complemento. En cualquier caso, no se requiere ninguna acción adicional del administrador. 

- **Solo yo** Si asigna un complemento solo a usted mismo, el complemento se asigna solo a su cuenta, lo que es ideal para probar el complemento.
    
La opción adecuada para su organización depende de la configuración. Sin embargo, se recomienda realizar asignaciones mediante grupos. Como administrador, es posible que le resulte más fácil administrar complementos mediante el uso de grupos y el control de la pertenencia a esos grupos en lugar de asignar usuarios individuales cada vez. En algunas situaciones, es posible que desee restringir el acceso a un pequeño conjunto de usuarios mediante la asignación manual de asignaciones a usuarios específicos.
  
## <a name="more-about-office-add-ins-security"></a>Más información sobre la seguridad de los complementos de Office

Los complementos de Office combinan un archivo de manifiesto XML que contiene algunos metadatos sobre el complemento, pero lo más importante es que apunta a una aplicación web que contiene todo el código y la lógica. Las funcionalidades de los complementos pueden variar. Estos son algunos ejemplos de las acciones que pueden realizar los complementos:
  
- Mostrar datos.
    
- Leer el documento de un usuario para proporcionar servicios contextuales.
    
- Leer datos del documento de un usuario y escribir datos en él para proporcionar valor a ese usuario.
    
Para obtener más información sobre los tipos y las funcionalidades de los complementos de Office, consulte [Información general sobre la plataforma de complementos de Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), especialmente la sección "Anatomía de un complemento de Office".
  
Para poder interactuar con el documento del usuario, el complemento debe declarar qué permisos necesita en el manifiesto. Un modelo de permisos de acceso de la API de JavaScript de cinco niveles proporciona la base para la privacidad y la seguridad de los usuarios de los complementos de panel de tareas. La mayoría de los complementos de la Tienda Office son del nivel ReadWriteDocument y casi todos los complementos admiten, como mínimo, el nivel ReadDocument. Para obtener más información sobre los niveles de permisos, consulte [Solicitar permisos para el uso de la API en los complementos del panel de tareas y de contenido](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Cuando se actualiza un manifiesto, los cambios típicos se aplican al icono de un complemento y al texto. En ocasiones, los comandos del complementos cambian. Sin embargo, los permisos del complemento no cambian. La aplicación web en la que se ejecutan todo el código y la lógica del complemento puede cambiar en cualquier momento, lo que forma parte de la naturaleza de las aplicaciones web.
  
Las actualizaciones de los complementos se producen de la siguiente manera:
  
- **Complemento de línea de negocio:** en este caso, en el que un administrador cargó explícitamente un manifiesto, el complemento requiere que el administrador cargue un nuevo archivo de manifiesto para admitir los cambios de metadatos. La próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento. 

    > [!NOTE]
    > El administrador no necesita quitar un complemento de LOB para realizar una actualización.   En la sección Complementos, el administrador puede simplemente hacer clic en  el complemento de LÍNEA de base de datos y elegir el botón Actualizar en la esquina inferior derecha. La actualización solo funcionará si la versión del nuevo complemento es mayor que la del complemento existente.   
    
- **Complemento de la Tienda Office:** si un administrador seleccionó un complemento de la Tienda Office y el complemento se actualiza en la Tienda Office, se actualizará más tarde en Implementación centralizada. La próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento. 
  
## <a name="learn-more"></a>Más información

[Administrar complementos en el centro de administración](manage-addins-in-the-admin-center.md)

[Cree el primer complemento de panel de tareas de Word.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Menores de edad y adquisición de complementos de la tienda](minors-and-acquiring-addins-from-the-store.md)
  
[Usar cmdlets de PowerShell de implementación centralizada para administrar complementos](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Solución de problemas: el usuario no ve los complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
