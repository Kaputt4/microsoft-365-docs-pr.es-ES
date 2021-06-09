---
title: Configurar un conector para archivar datos desde el Archivador de números Enterprise TeleMessage
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
description: Los administradores pueden configurar un conector para importar y archivar datos SMS MMS y de TeleMessage Enterprise Number Archiver. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 1615aaed21eca6d0c8c22343e19c1ea93b693aaa
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822207"
---
# <a name="set-up-a-connector-to-archive-enterprise-number-data"></a>Configurar un conector para archivar datos Enterprise número

Use un conector de TeleMessage en el centro de cumplimiento de Microsoft 365 para importar y archivar mensajes del Servicio de mensajería corta (SMS) y del Servicio de mensajería multimedia (MMS), mensajes de chat, grabaciones de llamadas de voz y registros de llamadas de voz desde el archivador de números de Enterprise. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de la organización una vez al día e importa los datos de comunicación móvil de los empleados mediante el Archivador de números de TeleMessage Enterprise a los buzones de correo de Microsoft 365.

Después de almacenar los datos del conector del archivador de números de TeleMessage Enterprise en buzones de usuario, puede aplicar Microsoft 365 las características de cumplimiento como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 Enterprise datos del archivador de números. Por ejemplo, puede buscar en el archivador de números de TeleMessage Enterprise SMS, MMS y llamada de voz mediante búsqueda de contenido o asociar el buzón que contiene los datos del conector del archivador de números de Enterprise con un administrador en un caso Advanced eDiscovery. El uso de un Enterprise de archivador de números para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-enterprise-number-data"></a>Información general sobre el archivado Enterprise datos de número

En la siguiente introducción se explica el proceso de uso de un conector para archivar Enterprise de red en Microsoft 365.

![Enterprise Flujo de trabajo de archivado de números](../media/EnterpriseNumberConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage para configurar un conector Enterprise archivo de números. Para obtener más información, consulte [aquí](https://www.telemessage.com/office365-activation-for-enterprise-number-archiver/).

2. El conector del archivador de números de Enterprise que cree en el centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área de Azure Storage segura en Microsoft Cloud.

3. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se crea una nueva carpeta denominada Enterprise archivo de números en el buzón del usuario específico y los elementos se importan a él. El conector realiza la asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación debe contener el número de teléfono móvil del usuario y la dirección Microsoft 365 buzón de correo correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, por cada elemento de correo electrónico, el conector primero buscará el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que corresponda al número de teléfono móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario Microsoft 365 válido en el  archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar Enterprise datos del archivador de números son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Ordene el Enterprise archivo de números de [teléfono desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Registrar todos los usuarios que requieren Enterprise número SMS/MMS Network archivado en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su Microsoft 365 usuario.

- Instale y active la aplicación Enterprise Archivo de números de TeleMessage en los teléfonos móviles de sus empleados.

- Al usuario que crea un Enterprise de archivador de números de correo se le debe asignar el rol De importación de buzones de Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** del centro de Microsoft 365 cumplimiento. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Este conector de datos está disponible en GCC entornos en la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-an-enterprise-number-archiver-connector"></a>Crear un conector Enterprise archivo de números

Después de completar los requisitos previos descritos en la sección anterior, puede crear un conector de archivador de números Enterprise en el centro de Microsoft 365 cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes de SMS, MMS y llamadas de voz a los cuadros de buzón de usuario correspondientes de Microsoft 365.

1. Vaya a y, a continuación, haga clic en [https://compliance.microsoft.com](https://compliance.microsoft.com/) **Conectores** \> **de datos Enterprise Archivo de números**.

2. En la página Enterprise descripción del producto **del archivador de números,** haga clic **en Agregar conector**

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