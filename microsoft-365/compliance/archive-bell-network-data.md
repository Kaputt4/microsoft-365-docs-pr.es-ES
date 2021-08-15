---
title: Configurar un conector para archivar datos de red SMS/MMS de Bell
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos DE SMS y MMS desde la red de Bell. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: e2de8bdbeb5acb5b4bca4876d8d1fd3d639e666021016fa0281e9de7f136e4e6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "53886962"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configurar un conector para archivar datos de red de Bell

Use un conector de TeleMessage en el Centro de cumplimiento de Microsoft 365 para importar y archivar mensajes del Servicio de mensajería corta (SMS) y del Servicio de mensajería multimedia (MMS) de la red de Bell. Después de configurar y configurar un conector, se conecta a la red de Bell de la organización una vez al día e importa mensajes SMS y MMS a buzones de correo en Microsoft 365.

Después de almacenar los mensajes SMS y MMS en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido y directivas de retención Microsoft 365 a los datos de red de Bell. Por ejemplo, puede buscar sms/MMS de red de Bell con búsqueda de contenido o asociar el buzón que contiene los datos del conector de red de Bell con un custodio en un Advanced eDiscovery caso. El uso de un conector de red de Bell para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-bell-network-data"></a>Información general sobre el archivado de datos de Bell Network

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de red de Bell en Microsoft 365.

![Flujo de trabajo de archivado de Bell Network](../media/BellNetworkConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage y Bell para configurar un conector de red de Bell. Para obtener más información, vea [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. En tiempo real, los mensajes SMS y MMS de la red de Bell de su organización se copian en el sitio de TeleMessage.

3. El conector de red de Bell que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes SMS y MMS de las 24 horas anteriores a una ubicación de Azure Storage segura en la nube de Microsoft. El conector también convierte el contenido de los mensajes SMS y MMS a un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de usuarios específicos. Se crea una nueva carpeta denominada **Bell SMS/MMS Network Archiver** en el buzón de un usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada mensaje SMS y MMS contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección Microsoft 365 de correo electrónico correspondiente para los usuarios de la organización. Si habilita la asignación automática de usuarios y la asignación personalizada, para cada elemento de red de Bell, el conector primero busca el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que corresponda al número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que está intentando importar. Si el conector no encuentra un usuario Microsoft 365 válido en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento red de Bell, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar datos de red de Bell son externos a Microsoft 365 y deben completarse antes de poder crear un conector en el centro de cumplimiento.

- Ordene el servicio archivador de red [de Bell desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Obtén tu cuenta de Red de Bell y los detalles de contacto de facturación para que puedas rellenar los formularios de incorporación de TeleMessage y ordenar el servicio de archivado de mensajes de Bell.

- Registre todos los usuarios que requieran el archivado de la red de SMS/MMS de Bell en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su Microsoft 365 usuario.

- Los empleados deben tener teléfonos móviles corporativos y de responsabilidad corporativa en la red móvil de Bell. Los mensajes de archivado Microsoft 365 no están disponibles para dispositivos de propiedad de los empleados o "Traer sus propios dispositivos (BYOD).

- Al usuario que crea un conector de red de Bell se le debe asignar el rol De importación de buzones de Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Este conector de datos está disponible en GCC entornos en la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-bell-network-connector"></a>Crear un conector de red de Bell

El último paso es crear un conector de red de Bell en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes SMS/MMS a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Conectores de datos** Bell  >  **SMS/MMS Network Archiver**.

2. En la página Descripción del producto de red de **Bell,** haga clic **en Agregar conector**

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. En la **página Iniciar sesión en TeleMessage,** en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.

   - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

   - **Contraseña:** Su contraseña de TeleMessage.

5. Después de crear el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios. Para habilitar la asignación personalizada, cargue un archivo CSV que contenga la información de asignación de usuarios y, a continuación, haga clic **en Siguiente**.

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la **pestaña Conectores** de la página **Conectores** de datos del Centro de cumplimiento para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
