---
title: Configurar un conector para archivar datos móviles de Android
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
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar SMS, MMS y llamadas de voz desde teléfonos móviles Android. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: d0c0043f598d81ae314d39e839111fd0aaad1150
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919988"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurar un conector para archivar datos móviles de Android

Use un conector de TeleMessage en el Centro de cumplimiento de Microsoft 365 para importar y archivar SMS, MMS, llamadas de voz y registros de llamadas desde teléfonos móviles Android. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de la organización una vez al día e importa la comunicación móvil de los empleados con el Archivador Android de TeleMessage a los buzones de Microsoft 365.

Una vez que los datos de teléfonos móviles Android se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, búsqueda de contenido y directivas de retención de Microsoft 365 a los datos del archivador de Android. Por ejemplo, puede buscar en la comunicación móvil de Archiver de Android mediante la búsqueda de contenido o asociar el buzón que contiene los datos del conector del archivador de Android con un custodio en un caso de exhibición de documentos electrónicos avanzada. El uso de un conector archiver de Android para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-android-mobile-data"></a>Información general sobre el archivado de datos móviles de Android

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos móviles de Android en Microsoft 365.

![Flujo de trabajo del conector de archivador de Android](../media/AndroidArchiverConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage para configurar un conector de archivador de Android. Para obtener más información, consulta [Archivador de Android](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. Una vez cada 24 horas, sms, MMS, llamadas de voz y registros de llamadas desde los teléfonos móviles Android de la organización se copian en el sitio de TeleMessage.

3. El conector de Archivador de Android que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los datos de Android de las 24 horas anteriores a una ubicación segura de Azure Storage en Microsoft Cloud. El conector también convierte los datos de Android a un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se crea una nueva carpeta denominada Archivador de Android en el buzón del usuario específico y los elementos se importan a él. El conector realiza la asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación debe contener el número de teléfono móvil del usuario y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, por cada elemento de correo electrónico, el conector primero buscará el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda al número de móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico, el elemento no se importará. 

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de comunicación de Android son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Ordene [el servicio Archiver de Android desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Tendrás que iniciar sesión en esta cuenta al crear el conector.

- Registra todos los usuarios que requieren el servicio Archiver de Android en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Instala y activa la aplicación Archiver Android de TeleMessage en los teléfonos móviles de tus empleados.

- El usuario que crea un conector de archivador de Android debe tener asignado el rol De importación de buzones de exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** del Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="create-an-android-archiver-connector"></a>Crear un conector de archivador de Android

El último paso es crear un conector de Archivador de Android en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir la comunicación de Android a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** archivo  >  **android**.

2. En la página **descripción del producto Archiver** de Android, haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. En la **página Iniciar sesión en TeleMessage,** en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.

   - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

   - **Contraseña:** Su contraseña de TeleMessage.

5. Después de crear el conector, cierre la ventana emergente y haga clic en **Siguiente**.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios y haga clic **en Siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **Siguiente**.

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la **página Conectores de** datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.