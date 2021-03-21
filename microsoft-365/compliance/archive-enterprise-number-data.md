---
title: Configurar un conector para archivar datos del Archivador de números de empresa de TeleMessage
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
description: Los administradores pueden configurar un conector para importar y archivar datos DE SMS y MMS desde el Archivador de números de empresa de TeleMessage. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 1322cafad94c8b2163c38e3c988feefc4ff1221a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921750"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Configurar un conector para archivar datos de número de empresa

Use un conector de TeleMessage en el Centro de cumplimiento de Microsoft 365 para importar y archivar mensajes del Servicio de mensajería corta (SMS) y del Servicio de mensajería multimedia (MMS), mensajes de chat, grabaciones de llamadas de voz y registros de llamadas de voz del Archivador de números de empresa. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de la organización una vez al día e importa los datos de comunicación móvil de los empleados mediante el Archivador de números de empresa de TeleMessage a buzones de Microsoft 365.

Después de almacenar los datos del conector del archivador de números de empresa de TeleMessage en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos del archivador de números de empresa. Por ejemplo, puede buscar en el archivo de números de empresa de TeleMessage SMS, MMS y llamadas de voz mediante la búsqueda de contenido o asociar el buzón que contiene los datos del conector del archivador de números de empresa con un administrador en un caso de exhibición de documentos electrónicos avanzada. El uso de un conector de archivador de números de empresa para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-enterprise-number-data"></a>Información general sobre el archivado de datos de número de empresa

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Enterprise Network en Microsoft 365.

![Flujo de trabajo de archivado de números de empresa](../media/EnterpriseNumberConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage para configurar un conector de archivador de números de empresa. Para obtener más información, consulte [aquí](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. El conector del archivador de números de empresa que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área segura de Azure Storage en Microsoft Cloud.

3. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se crea una nueva carpeta denominada Enterprise Number Archiver en el buzón del usuario específico y los elementos se importan a él. El conector realiza la asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación debe contener el número de teléfono móvil del usuario y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, por cada elemento de correo electrónico, el conector primero buscará el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda al número de móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico, el elemento no se importará. 

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos del archivador de números de empresa son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Ordene [el servicio de archivador de números de empresa desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Registre todos los usuarios que requieran el archivado de la red SMS/MMS de número de empresa en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Instale y active la aplicación Archivador de números de empresa de TeleMessage en los teléfonos móviles de sus empleados.

- Al usuario que crea un conector de archivador de números de empresa se le debe asignar el rol De exportación de importación de buzones en Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** del Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="create-an-enterprise-number-archiver-connector"></a>Crear un conector de archivador de números de empresa

Después de completar los requisitos previos descritos en la sección anterior, puede crear un conector de archivador de números de empresa en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir sms, MMS y mensajes de llamadas de voz a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Conectores de datos** \> **Archivador de números de empresa**.

2. En la página Descripción del producto **archivador de números** de empresa, haga clic **en Agregar conector**

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