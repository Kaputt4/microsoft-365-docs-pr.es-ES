---
title: Implementar complementos en el centro de administración
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
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
ms.openlocfilehash: 2dfd92e2dd38487a444362cdbb88ec217e62ca28
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093732"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Implementar complementos en el centro de administración

Office Complementos le ayudan a personalizar los documentos y a simplificar la forma en que accede a la información en la web (consulte [Empezar a usar el complemento de Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Como administrador, puede implementar complementos de Office para los usuarios de su organización mediante la característica Implementación centralizada en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a>. La implementación centralizada es la manera recomendada y más rica en características para que la mayoría de los administradores implementen complementos en usuarios y grupos dentro de una organización.

Para obtener más información sobre cómo determinar si su organización puede admitir la implementación centralizada, consulte [Determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).

Para más información sobre la administración de complementos después de la implementación, consulte [Administración de complementos en el Centro de administración](manage-addins-in-the-admin-center.md).
  
> [!NOTE]
>  Para Word, Excel y PowerPoint usar un [catálogo de aplicaciones de SharePoint](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) para implementar complementos en los usuarios de un entorno local sin conexión a Microsoft 365 ni compatibilidad con SharePoint complementos necesarios. Para Outlook use Exchange panel de control para implementar en un entorno local sin conexión a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Enfoque recomendado para implementar complementos de Office

Para implementar complementos mediante un enfoque por fases, se recomienda lo siguiente:
  
1. Implemente el complemento en un pequeño conjunto de participantes y miembros del departamento de TI. Si la implementación se realiza correctamente, vaya al paso 2.
    
2. Implemente el complemento para más personas dentro de la empresa. De nuevo, evalúe los resultados y, si se ejecuta correctamente, continúe con la implementación completa.
    
3. Realice una implementación completa para todos los usuarios.
    
En función del tamaño de la audiencia de destino, puede agregar o quitar pasos de implementación.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Implementación de un complemento de Office mediante el Centro de administración

Antes de empezar, consulte [Determinar si la implementación centralizada de complementos funciona para su organización](centralized-deployment-of-add-ins.md).
  
1. En el centro de administración, vaya a la página **Configuración** \> **Complementos**. Si no ve la página **de complementos**, vaya a la página **Configuración** \> **Complementos de** **aplicaciones** \> integradas.

2. Seleccione **Distribuir complemento** en la parte superior de la página y, a continuación, seleccione **Siguiente**.

    > [!NOTE]
    > También puede implementar complementos en el centro de administración a través de [Aplicaciones integradas](test-and-deploy-microsoft-365-apps.md). Las aplicaciones integradas son visibles para los administradores de Global y de Exchange. Si no ve los pasos anteriores, vaya a la sección Implementación centralizada; para ello, vaya a **Configuración** >  **Integración de aplicaciones**. En la parte superior de la página **Aplicaciones integradas** , elija **Complementos**.

3. Seleccione una opción y siga las instrucciones.
  
4. Si seleccionaste la opción para agregar un complemento desde la Tienda Office, selecciona el complemento. </br>

    Puede ver los complementos disponibles por categorías: **Sugeridos para usted**, **Clasificación** o **Nombre**. Solo los complementos gratuitos están disponibles en la Tienda Office. Los complementos de pago no son compatibles en estos momentos. Después de seleccionar un complemento, acepte los términos y condiciones para continuar. <br/> 

    > [!NOTE]
    > Con la opción Office Store, las actualizaciones y mejoras se implementan automáticamente en los usuarios.

5. En la página siguiente, seleccione **Todos los usuarios**, **Usuarios o grupos específicos** o **Solo yo** para especificar a quién se implementará el complemento. Use el cuadro Buscar para buscar usuarios o grupos específicos. <br/>

    > [!NOTE]
    > Para obtener información sobre otros estados que se aplican a un complemento, consulte [Estados de complemento](./manage-addins-in-the-admin-center.md).
  
6. Seleccione **Implementar**.
  
7. Aparece un tic verde cuando se implementa el complemento. Siga las instrucciones de la página para probar el complemento.

    > [!NOTE]
    > Es posible que los usuarios tengan que volver a iniciar Office para ver el icono del complemento en la cinta de opciones de la aplicación. Los complementos de Outlook pueden tardar hasta 24 horas en aparecer en las cintas de las aplicaciones.

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
  
## <a name="more-about-office-add-ins-security"></a>Más información sobre Office seguridad de complementos

Office complementos combinan un archivo de manifiesto XML que contiene algunos metadatos sobre el complemento, pero lo más importante apunta a una aplicación web que contiene todo el código y la lógica. Las funcionalidades de los complementos pueden variar. Estos son algunos ejemplos de las acciones que pueden realizar los complementos:
  
- Mostrar datos.

- Leer el documento de un usuario para proporcionar servicios contextuales.

- Leer datos del documento de un usuario y escribir datos en él para proporcionar valor a ese usuario.

Para obtener más información sobre los tipos y funcionalidades de los complementos de Office, consulte [Office introducción a la plataforma de complementos](/office/dev/add-ins/overview/office-add-ins), especialmente la sección "Anatomía de un complemento de Office".
  
Para poder interactuar con el documento del usuario, el complemento debe declarar qué permisos necesita en el manifiesto. Un modelo de permisos de acceso de la API de JavaScript de cinco niveles proporciona la base para la privacidad y la seguridad de los usuarios de los complementos de panel de tareas. La mayoría de los complementos de la Tienda Office son del nivel ReadWriteDocument y casi todos los complementos admiten, como mínimo, el nivel ReadDocument. Para obtener más información sobre los niveles de permisos, consulte [Solicitar permisos para el uso de la API en los complementos del panel de tareas y de contenido](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Cuando se actualiza un manifiesto, los cambios típicos se aplican al icono de un complemento y al texto. En ocasiones, los comandos del complementos cambian. Sin embargo, los permisos del complemento no cambian. La aplicación web en la que se ejecutan todo el código y la lógica del complemento puede cambiar en cualquier momento, lo que forma parte de la naturaleza de las aplicaciones web.
  
Las actualizaciones de los complementos se producen de la siguiente manera:
  
- **Complemento de línea de negocio:** en este caso, en el que un administrador cargó explícitamente un manifiesto, el complemento requiere que el administrador cargue un nuevo archivo de manifiesto para admitir los cambios de metadatos. La próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento.

    > [!NOTE]
    > El administrador no necesita quitar un complemento de LOB para realizar una actualización.   En la sección Complementos, el administrador puede simplemente hacer clic en el complemento de LOB y elegir el **botón Actualizar** en la esquina inferior derecha. La actualización solo funcionará si la versión del nuevo complemento es mayor que la del complemento existente.

- **Complemento de la Tienda Office:** si un administrador seleccionó un complemento de la Tienda Office y el complemento se actualiza en la Tienda Office, se actualizará más tarde en Implementación centralizada. La próxima vez que se inicien las aplicaciones de Office pertinentes, el complemento se actualizará. La aplicación web puede cambiar en cualquier momento.
  
## <a name="related-content"></a>Contenido relacionado

[Administrar complementos en el Centro de administración](manage-addins-in-the-admin-center.md) (artículo)\
[Compilación del primer complemento de panel de tareas de Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (artículo\
[Menores y adquisición de complementos de la tienda](minors-and-acquiring-addins-from-the-store.md) (artículo)\
[Uso de cmdlets de PowerShell de implementación centralizada para administrar complementos](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (artículo)\
[Solución de problemas: El usuario no ve complementos](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artículo)
