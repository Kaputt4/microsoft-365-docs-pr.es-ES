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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Aprenda a implementar complementos para los usuarios y grupos de su organización mediante la implementación centralizada en el centro de administración.
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102865"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implementar complementos en el centro de administración

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Los complementos de Office le ayudan a personalizar los documentos y simplificar la forma en que accede a la información en la web (vea [Empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, puede implementar complementos de Office para los usuarios de su organización mediante el uso de la característica de implementación centralizada en el centro de administración de Microsoft 365. La implementación centralizada es la forma recomendada y con más características para la mayoría de los administradores de implementar complementos para usuarios y grupos dentro de una organización. 

Para obtener más información sobre cómo determinar si su organización puede admitir la implementación centralizada, vea [determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).

Para obtener más información sobre la administración de complementos tras la implementación, consulte [Manage Add-Ins in the admin Center](manage-addins-in-the-admin-center.md) .
  
> [!NOTE]
>  Para Word, Excel y PowerPoint usan un [Catálogo de aplicaciones de SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implementar complementos para los usuarios en un entorno local sin conexión a Microsoft 365 y/o compatibilidad con complementos de SharePoint necesarios. Para Outlook, use el panel de control de Exchange para implementar en un entorno local sin una conexión a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar complementos de Office

Para implementar complementos con un enfoque por fases, le recomendamos lo siguiente:
  
1. Implemente el complemento en un pequeño conjunto de participantes empresariales y miembros del Departamento de ti. Si la implementación se realiza correctamente, vaya al paso 2.
    
2. Implemente el complemento en más personas dentro de la empresa. Una vez más, evalúe los resultados y, si es correcto, continúe con la implementación completa.
    
3. Realizar una implementación completa para todos los usuarios.
    
En función del tamaño de la audiencia de destino, puede Agregar o quitar pasos de la implementación.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementar un complemento de Office con el centro de administración

Antes de comenzar, vea [determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).
  
1. En el centro de administración, vaya a la página **configuración** \> **de complementos** .
    
2. Seleccione **implementar complemento** en la parte superior de la página y, a continuación, seleccione **siguiente**.
    
3. Seleccione una opción y siga las instrucciones.
  
4. Si seleccionó la opción de agregar un complemento de la tienda Office, realice la selección del complemento. </br>

    Puede ver los complementos disponibles por categorías: **sugeridas para usted**, **calificación**o **nombre**. Solo los complementos gratuitos están disponibles en la tienda Office. Los complementos de pago no son compatibles en estos momentos. Después de seleccionar un complemento, acepte los términos y condiciones para continuar. <br/> 

    > [!NOTE] 
    > Con la opción de la tienda Office, las actualizaciones y las mejoras se refuerzan automáticamente a los usuarios.

5. En la página siguiente, seleccione **todos** **los usuarios, grupos o usuarios específicos**, o **solo** para especificar con quién se ha implementado el complemento. Use el cuadro de búsqueda para buscar usuarios o grupos específicos. <br/>

    > [!NOTE] 
    > Para obtener información sobre otros Estados que se aplican a un complemento, vea [Estados de complementos](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).
  
6. Seleccione **Implementar**.
  
7. Cuando se implementa el complemento, aparece una marca de verde. Siga las instrucciones de la página para probar el complemento.

    > [!NOTE]
    > Es posible que los usuarios deban volver a iniciar Office para ver el icono del complemento en la cinta de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de la aplicación.
    
8. Cuando termine, seleccione **siguiente**. Si ha implementado solo en usted, puede seleccionar **cambiar quién tiene acceso al complemento** para implementarlo en más usuarios.

    Si ha implementado el complemento en otros miembros de la organización, siga las instrucciones para anunciar la implementación del complemento. <br/>
  
    Es aconsejable informar a los usuarios y grupos de que el complemento implementado está disponible. Considere la posibilidad de enviar un correo electrónico que describa Cuándo y cómo usar el complemento. Incluya o vincule el contenido de la ayuda o las preguntas más frecuentes que puedan ayudar a los usuarios si tienen problemas con el complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Consideraciones al asignar un complemento a usuarios y grupos

Los administradores pueden asignar un complemento para todos los usuarios o para usuarios y grupos específicos. Cada opción tiene implicaciones:
  
- **Todos los usuarios** Esta opción asigna el complemento a todos los usuarios de la organización. Use esta opción con moderación y solo para los complementos que realmente sean de uso universal en su organización. 
    
- **Usuarios** de Si asigna un complemento a un usuario individual y, a continuación, implementa el complemento en un usuario nuevo, primero debe agregar el nuevo usuario.
    
- **Grupos** Si asigna un complemento a un grupo, se asignará automáticamente el complemento a los usuarios que se agreguen al grupo. Cuando se quita un usuario de un grupo, el usuario pierde el acceso al complemento. En cualquier caso, no se requiere ninguna acción adicional del administrador. 

- **Solo para mí** Si asigna solo un complemento, el complemento solo se asigna a su cuenta, lo que es ideal para probar el complemento de la aplicación.
    
La opción adecuada para su organización depende de su configuración. Sin embargo, se recomienda realizar asignaciones con grupos. Como administrador, es posible que le resulte más fácil administrar los complementos mediante grupos y controlar la pertenencia de esos grupos en lugar de asignar cada vez usuarios individuales. En algunas situaciones, es posible que desee restringir el acceso a un pequeño conjunto de usuarios realizando asignaciones a usuarios específicos mediante la asignación manual de usuarios.
  
## <a name="more-about-office-add-ins-security"></a>Más información sobre la seguridad de complementos de Office

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Mostrar datos.
    
- Leer el documento de un usuario para proporcionar servicios contextuales.
    
- Leer datos del documento de un usuario y escribir datos en él para proporcionar valor a ese usuario.
    
Para obtener más información sobre los tipos y las funcionalidades de los complementos de Office, consulte [Información general sobre la plataforma de complementos de Office](https://go.microsoft.com/fwlink/p/?linkid=846362), especialmente la sección "Anatomía de un complemento de Office".
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Las actualizaciones de los complementos se producen de la siguiente manera:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > El administrador no necesita quitar un complemento de LOB para realizar una actualización.   En la sección complementos, el administrador puede simplemente hacer clic en el complemento de LOB y elegir el **botón actualizar** en la esquina inferior derecha. La actualización solo funcionará si la versión del complemento nuevo es mayor que la del complemento existente.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
  
## <a name="learn-more"></a>Obtén más información

Crear y crear [Complementos de Office](https://go.microsoft.com/fwlink/p/?linkid=846362)

[Administrar complementos en el centro de administración](manage-addins-in-the-admin-center.md)

[Menores y adquisición de complementos desde la tienda](minors-and-acquiring-addins-from-the-store.md)
  
[Usar los cmdlets de PowerShell de implementación centralizada para administrar complementos](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Solución de problemas: el usuario no ve complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
