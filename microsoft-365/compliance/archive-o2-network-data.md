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
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos DE SMS y MMS desde la red móvil de O2 en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 79223b06c05d34d5c131208d01051c8a44e23e1d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906130"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Configurar un conector para archivar datos de red de O2

Use un conector de TeleMessage en el Centro de cumplimiento de Microsoft 365 para importar y archivar mensajes de servicio de mensajería corta (SMS) y llamadas de voz desde la red móvil de O2. Después de configurar y configurar un conector, se conecta a la red O2 de la organización una vez al día e importa SMS y llamadas de voz a buzones de Microsoft 365.

Una vez que los mensajes SMS y las llamadas de voz se almacenan en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido y directivas de retención de Microsoft 365 a los datos de la red de O2. Por ejemplo, puede buscar mensajes SMS de red O2 y llamadas de voz mediante búsqueda de contenido o asociar el buzón que contiene datos de red O2 con un custodio en un caso de exhibición de documentos electrónicos avanzada. El uso de un conector de red O2 para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-o2-network-data"></a>Información general sobre el archivado de datos de red O2

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de red de O2 en Microsoft 365.

![Flujo de trabajo de archivado de red de O2](../media/O2NetworkConnectorWorkflow.png)

1. Su organización funciona con TeleMessage y O2 para configurar un conector de red de O2. Para obtener más información, vea [O2 Network Archiver](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. Una vez cada 24 horas, los mensajes SMS y las llamadas de voz de la red O2 de la organización se copian en el sitio de TeleMessage.

3. El conector de red O2 que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes SMS y las llamadas de voz de las 24 horas anteriores a una ubicación segura de Azure Storage en Microsoft Cloud. El conector también convierte el contenido de los mensajes SMS y las llamadas de voz a un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de usuarios específicos. Se crea una nueva carpeta denominada **SMS de O2** y el archivador de red de voz en el buzón de un usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada mensaje SMS y llamada de voz contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico correspondiente de Microsoft 365 para los usuarios de la organización. Si habilita la asignación automática de usuarios y la asignación personalizada, por cada elemento de O2, el conector primero mira el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda al número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que está intentando importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento O2, el elemento no se importará.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de red de O2 son externos a Microsoft 365 y deben completarse antes de poder crear un conector en el centro de cumplimiento.

- Ordene el servicio de archivador de red de [O2 desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Obtenga los detalles de contacto de facturación y cuenta de red de O2 para poder rellenar los formularios de incorporación de TeleMessage y ordenar el servicio de archivado de mensajes desde O2.

- Registre todos los usuarios que requieran el archivado de SMS de O2 y red de voz en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Los empleados deben tener teléfonos móviles corporativos y de responsabilidad corporativa en la red móvil de O2. El archivado de mensajes en Microsoft 365 no está disponible para dispositivos de propiedad de los empleados o "Traer sus propios dispositivos (BYOD).

- Al usuario que crea un conector de red de O2 se le debe asignar el rol De exportación de importación de buzones en Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** del Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="create-an-o2-network-connector"></a>Crear un conector de red de O2

Después de completar los requisitos previos descritos en la sección anterior, puede crear un conector de red de O2 en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes SMS y llamadas de voz a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic **en Conectores de datos** \> **O2 Red**.

2. En la página **Descripción del producto O2 Network,** haga clic **en Agregar conector**

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. En la **página Iniciar sesión en TeleMessage,** en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.

   - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

   - **Contraseña:** Su contraseña de TeleMessage.

5. Después de crear el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios y haga clic **en Siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **Siguiente**.

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la **página Conectores de** datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.