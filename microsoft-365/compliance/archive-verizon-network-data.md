---
title: Configurar un conector para archivar datos de Verizon Network en Microsoft 365
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
description: Los administradores pueden configurar un conector TeleMessage para importar y archivar datos SMS y MMS de Verizon Network en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 2628a373a0232d5cadbb54db7253e56e35596b04
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619776"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Configurar un conector para archivar datos de Verizon Network

Use el conector TeleMessage en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos del Servicio de mensajería corta (SMS) y el Servicio de mensajería multimedia (MMS) de Verizon Network. Después de configurar y configurar un conector, se conecta a Verizon Network de su organización una vez al día e importa datos SMS y MMS a los buzones de Microsoft 365.

Después de almacenar los datos del conector de Verizon Network en los buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido y directivas de retención de Microsoft 365 a los datos de Verizon. Por ejemplo, puede buscar mensajes SMS y MMS de Verizon mediante búsqueda de contenido o asociar el buzón que contiene datos de Verizon Network con un administrador en un caso de eDiscovery avanzado. El uso de un conector de Verizon Network para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-verizon-network-data"></a>Información general sobre el archivado de datos de Verizon Network

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Verizon Network en Microsoft 365.

![Flujo de trabajo de archivado de Verizon Network](../media/VerizonNetworkConnectorWorkflow.png)

1. Tu organización trabaja con TeleMessage y Verizon para configurar un conector de Verizon Network. Para obtener más información, consulta [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).

2. Una vez cada 24 horas, los mensajes SMS y MMS de Verizon Network de la organización se copian en el sitio de TeleMessage.

3. El conector de Verizon Network que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes SMS y MMS de las 24 horas anteriores a una ubicación segura de Azure Storage en Microsoft Cloud. El conector también convierte el contenido de los mensajes SMS y MMS en un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móviles al buzón de un usuario específico. Se crea una nueva carpeta denominada **Verizon SMS/MMS Network Archiver** en el buzón del usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la *propiedad de dirección de correo electrónico del* usuario. Cada mensaje SMS y MMS contiene esta propiedad, que se rellena con la dirección de correo electrónico de todos los participantes del mensaje.

   Además de la asignación automática  de usuarios mediante el valor de la propiedad de dirección de correo electrónico del usuario, también puede implementar la asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico de Microsoft 365 correspondiente para los usuarios de su organización. Si habilita la asignación automática de usuarios y la asignación personalizada, para cada elemento de Verizon, el conector primero examina el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda al número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que está intentando importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento de Verizon, el elemento no se importará.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de Verizon Network son externos a Microsoft 365 y deben completarse antes de poder crear un conector en el centro de cumplimiento.

- Ordena el [servicio de Archiver de red de Verizon desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtén una cuenta de administración válida para tu organización. Deberá iniciar sesión en esta cuenta cuando cree el conector en el centro de cumplimiento.

- Obtén tu cuenta de Verizon Network y los detalles de contacto de facturación para que puedas rellenar los formularios de incorporación de TeleMessage y solicitar el servicio de archivado de mensajes de Verizon.

- Registra todos los usuarios que requieran el archivado de SMS y MMS de Verizon en la cuenta TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Los empleados deben tener teléfonos móviles corporativos y responsables corporativos en la red móvil de Verizon. El archivado de mensajes en Microsoft 365 no está disponible para dispositivos propiedad de los empleados o Bring Your Own Devices (BYOD).

- El usuario que crea un conector de Verizon Network debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de** datos en el Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="create-a-verizon-network-connector"></a>Crear un conector de Verizon Network

Después de completar los requisitos previos descritos en la sección anterior, puede crear el conector de Verizon Network en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes SMS y MMS a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Ve a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haz **clic en Conectores de datos** de Verizon  >  **Network.**

2. En la página de descripción del producto de **Verizon Network,** haga clic **en Agregar conector**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. En la **página Iniciar sesión en TeleMessage,** en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **Siguiente**.
  
   - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

   - **Contraseña:** La contraseña de TeleMessage.

5. Después de crear el conector, puede cerrar la ventana emergente y ir a la página siguiente.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios y haga clic en **Siguiente.** En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **Siguiente.**

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores en la página **Conectores** de datos para ver el progreso del proceso de importación para el nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
