---
title: Configurar un conector para archivar datos de comunicaciones de Telegram en Microsoft 365
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
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos de comunicaciones de Telegram en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: d3fbe02dce56bec01d66351aa69500a3d5d93a37
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054882"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data-preview"></a>Configurar un conector para archivar datos de comunicaciones de Telegram (versión preliminar)

Use el conector de TeleMessage en el Centro de cumplimiento de Microsoft 365 para importar y archivar chats de Telegram, datos adjuntos, archivos y mensajes y llamadas eliminados. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de la organización e importa la comunicación móvil de los empleados que usan el Archivador de Telegram a buzones de correo de Microsoft 365.

Una vez que los datos del conector del archivador de Telegram se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido y directivas de retención Microsoft 365 a los datos de comunicación de Telegram. Por ejemplo, puede buscar en la comunicación de Telegram mediante búsqueda de contenido o asociar el buzón que contiene los datos del conector del archivador de Telegram con un custodio en un Advanced eDiscovery caso. El uso de un conector de archivador de Telegram para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las normativas de gobierno corporativo y las directivas reglamentarias.

## <a name="overview-of-archiving-telegram-communications-data"></a>Información general sobre el archivado de datos de comunicaciones de Telegram

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de comunicaciones de Telegram en Microsoft 365.

![Flujo de trabajo de archivado de comunicaciones de Telegram](../media/TelegramConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage para configurar un conector de archivador de Telegram. Para obtener más información, vea [Activating the TeleMessage Telegram Archiver for Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).

2. En tiempo real, los datos de Telegram de su organización se copian en el sitio de TeleMessage.

3. El conector del archivador de Telegram que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área de Azure Storage segura en Microsoft Cloud.

4. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se creará una nueva carpeta denominada Archivador de Telegram en el buzón del usuario específico y los elementos se importarán a él. El conector realiza esta asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico.

> Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación debe contener el número de teléfono móvil del usuario y la dirección Microsoft 365 buzón de correo correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, por cada elemento de correo electrónico, el conector primero buscará el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que corresponda al número de teléfono móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario Microsoft 365 válido en el  archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Ordene [el servicio de archivado de Telegram desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Registra todos los usuarios que requieren el archivado de Telegram en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su Microsoft 365 usuario.

- Instala la aplicación Archivador de Telegram en los teléfonos móviles de tus empleados y actívala. La aplicación Archiver de Telegram les permite comunicarse y chatear con otros usuarios de Telegram.

- El usuario que crea un conector de archivador de Telegram en el paso 3 debe tener asignado el rol De importación de buzones de Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="create-a-telegram-archiver-connector"></a>Crear un conector de archivador de Telegram

Después de completar los requisitos previos descritos en la sección anterior, puede crear el conector del archivador de Telegram en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transfiere los datos de comunicaciones de Telegram a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a y, a continuación, haga clic en <https://compliance.microsoft.com> **Conectores** > archivo de **elegrama de** T .

2. En la página **Descripción del producto del Archivador** de Telegram, haga clic en Agregar **conector**.

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. En la **página Iniciar sesión en TeleMessage,** en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.

    - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

    - **Contraseña:** Su contraseña de TeleMessage.

5. Después de crear el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios. Para habilitar la asignación personalizada, cargue un archivo CSV que contenga la información de asignación de usuarios y, a continuación, haga clic **en Siguiente**.

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la **página Conectores de** datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
