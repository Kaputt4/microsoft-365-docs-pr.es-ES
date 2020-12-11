---
title: Configurar un conector para archivar datos de red de O2 en Microsoft 365
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
description: Los administradores pueden configurar un conector de Telemensaje para importar y archivar datos de SMS y MMS desde la red móvil de O2 en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: 35dc19089a60f058583ce50350b803df5c894d92
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619966"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Configurar un conector para archivar datos de red de O2

Use un conector de Telemensaje en el centro de cumplimiento de Microsoft 365 para importar y archivar mensajes de servicio de mensajes cortos (SMS) y llamadas de voz desde la red móvil de O2. Después de configurar y configurar un conector, se conecta a la red de O2 de su organización una vez al día e importa las llamadas de voz y SMS a los buzones en Microsoft 365.

Una vez almacenados los mensajes SMS y las llamadas de voz en los buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de red de O2. Por ejemplo, puede buscar mensajes SMS y llamadas de voz de la red de O2 mediante la búsqueda de contenido o asociar el buzón de correo que contiene los datos de red de O2 con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector de red de O2 para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-o2-network-data"></a>Información general sobre el archivado de datos de red de O2

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de red de O2 en Microsoft 365.

![Flujo de trabajo de archivado de red de O2](../media/O2NetworkConnectorWorkflow.png)

1. La organización trabaja con telemessage y O2 para configurar un conector de red de O2. Para obtener más información, consulte [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. Una vez cada 24 horas, los mensajes SMS y las llamadas de voz de la red de O2 de su organización se copian en el sitio de Telemensaje.

3. El conector de red de O2 que se crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Telemensaje cada día y transfiere los mensajes SMS y las llamadas de voz de las 24 horas anteriores a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte el contenido de los mensajes SMS y las llamadas de voz en un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se crea una nueva carpeta llamada **O2 SMS y el archivador de red de voz** en el buzón de un usuario específico y los elementos se importan a ella. El conector realiza esta asignación mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* . Cada mensaje SMS y llamada de voz contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* , también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico de Microsoft 365 correspondiente a los usuarios de su organización. Si habilita la asignación automática de usuarios y la asignación personalizada, para cada elemento de O2, el conector examina primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de teléfono móvil de un usuario, el conector usará los valores de la propiedad dirección de correo electrónico del elemento que intenta importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento de O2, no se importará el elemento.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar los datos de la red de O2 son externos a Microsoft 365 y deben completarse antes de poder crear un conector en el centro de cumplimiento.

- Solicite el [servicio de archivado de red de O2 desde telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta cuando cree el conector en el centro de cumplimiento.

- Obtenga la cuenta de red de O2 y los detalles de contacto de facturación para poder completar los formularios de incorporación de mensajes y solicitar el servicio de archivado de mensajes desde O2.

- Registre todos los usuarios que requieran el archivado de la red de voz y SMS en la cuenta de Telemensaje. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Los empleados deben tener teléfonos móviles que sean responsables de la empresa y de la empresa en la red móvil de O2. Los mensajes de archivado en Microsoft 365 no están disponibles para los dispositivos de propiedad del empleado o "traer sus propios dispositivos (BYOD).

- El usuario que crea un conector de red de O2 debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para agregar conectores en la página **conectores de datos** en el centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="create-an-o2-network-connector"></a>Crear un conector de red de O2

Una vez que haya completado los requisitos previos descritos en la sección anterior, puede crear un conector de red de O2 en el centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de Telemensaje y transferir los mensajes SMS y las llamadas de voz a los cuadros del buzón de usuario correspondiente en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en red de **conectores de datos** \> **O2**.

2. En la página Descripción del producto de la **red de O2** , haga clic en **Agregar conector** .

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **iniciar sesión en Telemensaje** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

   - **Nombre de usuario:** El nombre de usuario de Telemensaje.

   - **Contraseña:** La contraseña de Telemensaje.

5. Una vez creado el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la página **asignación de usuarios** , habilite la asignación automática de usuarios y haga clic en **siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **siguiente**.

7. Revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

8. Vaya a la ficha conectores en la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
