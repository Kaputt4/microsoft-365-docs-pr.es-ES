---
title: Administrar la implementación de complementos en el centro de administración
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
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780126"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>Administrar la implementación de complementos en el Centro de administración de Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> El Centro de administración está cambiando. Si su experiencia no coincide con los detalles presentados aquí, consulte [Acerca del nuevo Centro de administración de Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Los complementos de Office le ayudan a personalizar los documentos y simplificar la forma en que accede a la información en la web (vea [Empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, puede implementar complementos de Office para los usuarios de su organización. Para ello, use la característica de implementación centralizada en el centro de administración de Microsoft 365.
  
La implementación centralizada es la forma recomendada y con más características para la mayoría de los administradores de implementar complementos para usuarios y grupos dentro de una organización. Para obtener más información sobre cómo determinar si su organización puede admitir la implementación centralizada, vea [determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).
  
Implementación centralizada proporciona las siguientes ventajas:
  
- Un administrador global puede asignar un complemento directamente a un usuario, a varios usuarios a través de un grupo o a todos los usuarios del inquilino.
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- Los complementos ya no aparecerán para los usuarios si el administrador desactiva o elimina el complemento, o si se quita el usuario de Azure Active Directory o de un grupo al que el complemento está asignado.
    
> [!NOTE]
>  Para Word, Excel y PowerPoint usan un [Catálogo de aplicaciones de SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implementar complementos para los usuarios en un entorno local sin conexión a Microsoft 365 y/o compatibilidad con complementos de SharePoint necesarios. > para Outlook use el panel de control de Exchange para implementar en un entorno local sin una conexión a Microsoft 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar complementos de Office

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. Distribúyalo por completo entre los usuarios objetivo.
    
Dependiendo del tamaño del público objetivo, puede que quiera agregar o eliminar pasos de la implementación.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementar un complemento de Office con el centro de administración

Antes de comenzar, vea [determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).

  
1. En el centro de administración, vaya a la página **configuración** \> **de complementos** .
    
2. Seleccione **implementar complemento** en la parte superior de la página. En la página información general, seleccione **siguiente**.
    
3. Seleccione una opción y siga las instrucciones.
  
4. Si seleccionó la opción de agregar un complemento de la tienda Office, ahora puede realizar la selección del complemento. Observe que puede ver los complementos disponibles en las categorías **Sugerencias**, **Valoración** o **Nombre**. Solo los complementos gratuitos están disponibles en la Tienda Office. Los complementos de pago no son compatibles en estos momentos. Una vez que haya seleccionado el complemento, tendrá que aceptar algunos términos y condiciones adicionales para poder continuar. <br/><br/> Nota: con la opción de la tienda Office, las actualizaciones y las mejoras realizadas en el complemento estarán disponibles automáticamente para los usuarios sin su intervención.

5. En la página siguiente, seleccione **todos**, **usuarios o grupos específicos** o **solo yo** para especificar con quién se implementará el complemento. Use el cuadro de búsqueda para encontrar los usuarios o grupos a los que se implementará el complemento. <br/>Nota: Obtenga información sobre los demás Estados que se aplican a un complemento. Vea [Estados de complementos](#add-in-states) más adelante en este tema.
  
6. Seleccione **Implementar**.
  
7. Una marca de graduación verde aparecerá cuando se haya implementado el complemento. Puede seguir las instrucciones que se indican en la página para comprobar que el complemento se ha implementado correctamente.

> [!NOTE]
> Es posible que los usuarios necesiten volver a iniciar Office para ver que el icono del complemento aparece en la cinta de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de los usuarios.
    
8. Cuando termine, seleccione **siguiente**. Si ha implementado solo en usted, puede seleccionar **cambiar quién tiene acceso al complemento** para implementarlo en más usuarios.



Si ha implementado el complemento en miembros de su organización que no sean usted, siga las instrucciones que se muestran para anunciar con eficacia la implementación del complemento. <br/>Ahora verá el complemento junto con otras aplicaciones en Microsoft 365.
  
Es una buena idea informar a los usuarios y grupos a los que ha implementado el complemento para que sepan que está disponible. Considere la posibilidad de enviarles un correo electrónico que describa cuándo y cómo usar el complemento y explique cómo el complemento puede ayudarles a hacer mejor su trabajo. Incluya o vincule el contenido de ayuda relevante o las preguntas más frecuentes que puedan ayudar si los usuarios tienen algún problema con el complemento.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Consideraciones al asignar un complemento a usuarios y grupos

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- **Solo para mí**: Si asigna un complemento solo a usted mismo, se asignará el complemento solo a su cuenta. Esto es ideal si desea probar el complemento primero.
    
La opción adecuada para su organización depende de su configuración. Sin embargo, recomendamos realizar las asignaciones a través de grupos. Como administrador, puede resultarle fácil administrar los complementos mediante grupos y controlar la suscripción a esos grupos en lugar de tener que ir cambiando los usuarios asignados en cada ocasión. Por otro lado, en algunas situaciones, puede que quiera restringir el acceso a un conjunto muy limitado de usuarios y, por tanto, realizar asignaciones a usuarios específicos. Como resultado, necesitará administrar los usuarios asignados de forma manual.
  
### <a name="add-in-states"></a>Estados del complemento

Un complemento puede estar en el estado **activado** o **desactivado** .
  
|**Estado**|**Cómo se produce el estado**|**Impacto**|
|:-----|:-----|:-----|
|**Active**  <br/> |El administrador ha cargado el complemento y lo ha asignado a usuarios o grupos.  <br/> |Los usuarios y grupos asignados al complemento lo ven en los clientes relevantes.  <br/> |
|**Desactivado**  <br/> |El administrador ha desactivado el complemento.  <br/> |Los usuarios y los grupos asignados al complemento ya no tienen acceso al mismo.  <br/> Si se cambia el estado del complemento a "activado", los usuarios y grupos tendrán acceso de nuevo.  <br/> |
|**Eliminado**  <br/> |El administrador ha eliminado el complemento.  <br/> |Los usuarios y grupos asignados al complemento ya no tienen acceso al mismo.  <br/> |
   
Considere la posibilidad de eliminar un complemento si nadie lo está usando. Desactivar un complemento puede ser útil si solo se usa en determinados momentos del año.
  
### <a name="security-of-office-add-ins"></a>Seguridad de los complementos de Office

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

### <a name="edit-add-in-access"></a>Editar el acceso del complemento

Después de la implementación, los administradores también pueden modificar el acceso del usuario a los complementos.

1. En el centro de administración, vaya a **Settings**la página de los  >  **Complementos &** de los servicios de configuración.

2. Seleccione el complemento implementado.

3. Haga clic en **Editar** en la sección **¿quién tiene acceso**?
4. Guarde los cambios.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedir las descargas del complemento desactivando la tienda Office en todos los clientes (excepto Outlook)

> [!NOTE]
> La instalación de complementos de Outlook se administra mediante un [proceso diferente](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).

Como organización, puede que quiera impedir la descarga de nuevos complementos de Office desde la tienda Office. Esto puede usarse junto con la implementación centralizada para garantizar que solo los complementos aprobados por la organización se implementan para los usuarios de la organización.
  
Para desactivar la adquisición de complementos:
  
1. En el centro de administración, vaya a la página **Configuración** \>[de servicios &amp;complementos](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Seleccione **aplicaciones y servicios de propiedad del usuario**.
    
4. Desactive la opción para permitir que los usuarios tengan acceso a la tienda Office.

Esto impedirá que todos los usuarios adquieran los siguientes complementos de la tienda.
  
- Complementos para Word, Excel y PowerPoint 2016 desde:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Adquisiciones que comienzan dentro de **AppSource**
    
- Complementos en Microsoft 365
    
Un usuario que intente obtener acceso a la tienda verá el siguiente mensaje: **lo sentimos, Microsoft 365 se ha configurado para impedir la adquisición individual de complementos de la tienda Office.**
  
La compatibilidad para desactivar la tienda Office está disponible en las siguientes versiones:
  
- Windows: 16.0.9001: actualmente disponible.
    
- Mac: 16.10.18011401: actualmente disponible.
    
- iOS: 2.9.18010804-actualmente disponible.
    
- El Web actualmente disponible.
    
Esto no impide que un administrador use la implementación centralizada para asignar un complemento de la tienda Office.
  
Para evitar que un usuario inicie sesión con una cuenta de Microsoft, puede restringir el inicio de sesión para usar solo la cuenta de la organización. Para obtener más información, mire [aquí](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Menores y adquisición de complementos desde la tienda

El Reglamento General de protección de datos (RGPD) es un Reglamento de la Unión Europea que se hace efectivo el 25 de mayo de 2018. Proporciona a los usuarios derechos y protección de sus datos. Uno de los aspectos de la RGPD es que los menores no pueden tener sus datos personales enviados a las partes que su padre o tutor no han aprobado. La antigüedad específica definida como un menor depende de la región en la que se encuentra la persona.
  
Las regiones que tienen regulaciones legales sobre el consentimiento paterno incluyen los Estados Unidos, Corea del sur, Reino Unido y la Unión Europea. Para esas regiones, un menor se bloquea (a través de Azure Active Directory) desde la obtención de nuevos complementos de Office de la tienda y la ejecución de complementos adquiridos anteriormente. En el caso de los países sin las regulaciones legales, no habrá ninguna restricción de descarga.
  
Un usuario se determina como secundario en función de los datos especificados en Azure Active Directory. El administrador de inquilinos es responsable de declarar el grupo de edad legal y el consentimiento paterno para ese usuario.
  
Si el tutor o el tutor consiente a un menor con un complemento específico, el administrador de inquilinos puede usar la implementación centralizada para implementar ese complemento en todos los menores que tengan el consentimiento del usuario.
  
Para que RGPD cumpla con los menores, debe asegurarse de que una de las siguientes compilaciones de Office está implementada en su centro educativo o de organización.
  
 **Para Word, Excel, PowerPoint y Project**: 
  
|||
|:-----|:-----|
|**Plataforma** <br/> |**Número de compilación** <br/> |
|Microsoft 365 apps for Enterprise (canal actual)  <br/> |9001,2138   <br/> |
|Microsoft 365 aplicaciones para empresas (canal empresarial semestral)  <br/> |8431,2159  <br/> |
|Office 2016 para Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 para Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 para Mac  <br/> |16.11.18020200  <br/> |
|Office para la Web  <br/> |N/D  <br/> |
   
 **Para Outlook**: 
  
|||
|:-----|:-----|
|**Plataforma** <br/> |**Número de compilación** <br/> |
|Outlook 2016 para Windows (MSI)  <br/> |Compilación sin TBD  <br/> |
|Outlook 2016 para Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 para Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile para iOS  <br/> |2.75.0  <br/> |
|Outlook Mobile para Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |N/D  <br/> |
   
 **Requisitos de Office 2013**
  
Word, Excel y PowerPoint 2013 para Windows serán compatibles con las mismas comprobaciones menores si la biblioteca de autenticación de Active Directory (ADAL) está habilitada. Hay dos opciones para el cumplimiento normativo, tal como se explica a continuación.
  
- **Habilitar Adal**. En este artículo se explica cómo habilitar ADAL para Office 2013: [usar la autenticación moderna de Microsoft 365 con clientes de Office](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>También debe configurar las claves del registro para habilitar ADAL, tal y como se explica en [enable Modern Authentication for Office 2013 on Windows Devices](../security-and-compliance/enable-modern-authentication.md).<br/>Además, debe instalar las siguientes actualizaciones de abril para Office 2013:
    
  - [Descripción de la actualización de seguridad para Office 2013:10 de abril de 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3 de abril de 2018, actualización para Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **No habilite Adal**. Si no puede habilitar ADAL en Office 2013, nuestra recomendación es usar la Directiva de grupo para desactivar la tienda para los clientes de Office. [Aquí](https://technet.microsoft.com/library/cc178992.aspx)encontrará información sobre cómo desactivar la aplicación para la configuración de Office.
    
## <a name="end-user-experience-with-add-ins"></a>Experiencia del usuario final con complementos

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). The add-in will appear on all platforms that the add-in supports.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![Cinta de Office con citas de búsqueda](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Si el complemento implementado no es compatible con los comandos de complemento o si desea ver todos los complementos implementados, puede verlos a través **de mis complementos**. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>En Word 2016, Excel 2016 o PowerPoint 2016

1. Seleccione **Insertar \> mis complementos**. 
    
2. Seleccione la pestaña **Gestionado por el administrador** en la ventana Complementos de Office. 
    
3. Haga doble clic en el complemento que ha implementado antes (en este ejemplo, **Citas** ). <br/>![Pestaña administrada de administración de la página de complementos de Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>En Outlook

1. En la cinta de opciones **Inicio** , seleccione **obtener complementos**.<br/>![Botón Tienda en Outlook](../../media/getaddinsicon.png)
  
2. Seleccione **administrada por el administrador** en el panel de navegación izquierdo.

## <a name="delete-the-add-in"></a>Eliminar el complemento

También puede eliminar un complemento que se ha implementado.

1. En el centro de administración, vaya a **Settings**la página de los  >  **Complementos &** de los servicios de configuración.

2. Seleccione el complemento implementado.

3. Haga clic en **eliminar complemento**. Quite el botón del complemento en la esquina inferior derecha.
4. Valide las selecciones y elija **quitar complemento**.
  
## <a name="learn-more"></a>Más información

Obtenga más información sobre la creación y generación de [complementos de Office](https://go.microsoft.com/fwlink/p/?linkid=846362).
  
[Use cmdlets de PowerShell de implementación centralizada para administrar complementos](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Solución de problemas: el usuario no ve complementos](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
