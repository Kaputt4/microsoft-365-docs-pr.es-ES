---
title: Configurar un conector para archivar datos de chat de ICE
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
description: Los administradores pueden configurar un conector para importar y archivar datos de la herramienta de chat de hielo en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: 590f9b3b119ee261ec2ff6c4b5196bd9fea42697
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620407"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurar un conector para archivar datos de chat de ICE

Use un conector nativo en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de chat de servicios financieros desde la herramienta de colaboración de chat de ICE. Después de configurar y configurar un conector, se conecta al sitio de chat de ICE Secure FTP (SFTP) de la organización una vez al día, convierte el contenido de los mensajes de chat a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones en Microsoft 365.

Una vez que se almacenan los datos de los chats de los usuarios, puede aplicar características de cumplimiento de Microsoft 365, como retención por juicio, exhibición de documentos electrónicos, archivado, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a datos de chat de ICE. Por ejemplo, puede buscar mensajes de chat de ICE mediante la búsqueda de contenido o asociar el buzón de correo que contiene los datos de chats de hielo con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector de chat de ICE para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-ice-chat-data"></a>Información general sobre el archivado de datos de chat de ICE

La siguiente descripción general explica el proceso de uso de un conector para archivar datos de chat de ICE en Microsoft 365.

![Flujo de trabajo de archivado de chat de ICE](../media/ICEChatConnectorWorkflow.png)

1. La organización trabaja con chat de ICE para configurar un sitio de SFTP de chat de ICE. También trabajará con chat de hielo para configurar el chat de hielo para copiar los mensajes de chat en el sitio de SFTP de chat de ICE.

2. Una vez cada 24 horas, los mensajes de chat de chat por ICE se copian en el sitio de SFTP de chat de ICE.

3. El conector de chat de hielo que crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de SFTP chat de ICE todos los días y transfiere los mensajes de chat de las 24 horas anteriores a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte el contenido de un chat en un formato de mensaje de correo electrónico.

4. El conector importa los elementos de mensajes de chat a los buzones de usuarios específicos. Se crea una nueva carpeta llamada **ICE chat** en los buzones de usuario y se importan los elementos de mensajes de chat a esa carpeta. El conector usa el valor de las propiedades *SenderEmail* y *RecipientEmail* . Todos los mensajes de chat contienen estas propiedades, que se rellenan con la dirección de correo electrónico del remitente y de todos los destinatarios o participantes del mensaje de chat.

   Además de la asignación automática de usuarios que usa los valores de la propiedad *SenderEmail* y *RecipientEmail* (lo que significa que el conector importa un mensaje de chat al buzón de correo del remitente y a los buzones de todos los destinatarios), también puede definir la asignación de usuarios personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el *ImId* de chat de ICE y la dirección de buzón de correo de Microsoft 365 correspondiente a cada usuario de la organización. Si habilita la asignación automática de usuarios y proporciona un archivo de asignación personalizada, para cada elemento de chat el conector examinará primero el archivo de asignación personalizada. Si no encuentra una cuenta de usuario de Microsoft 365 válida que corresponda a la ImId de chat de ICE de un usuario, el conector usará las propiedades *SenderEmail* y *RecipientEmail* del elemento chat para importar el elemento a los buzones de los participantes del chat. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizada o en las propiedades *SenderEmail* y *RecipientEmail* , no se importará el elemento.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar los datos de los chats de ICE son externos a Microsoft 365 y deben completarse antes de que pueda crear el conector en el centro de cumplimiento.

- El chat de hielo cobra a sus clientes una tarifa por el cumplimiento externo. Su organización debe ponerse en contacto con el grupo de ventas de chats de ICE para discutir y firmar el contrato de servicios de datos de chat de ICE, que puede obtener en [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Este contrato está entre el chat de ICE y su organización, y no implica a Microsoft. Después de configurar un sitio de SFTP de chat de ICE en el paso 2, el chat de ICE proporciona las credenciales FTP directamente a su organización. A continuación, le proporcionará esas credenciales a Microsoft cuando configure el conector en el paso 3.

- Debe configurar un sitio de SFTP de chat de ICE antes de crear el conector en el paso 3. Después de trabajar con chat de ICE para configurar el sitio de SFTP, los datos de chat de hielo se cargan al sitio de SFTP todos los días. El conector que se crea en el paso 3 se conecta a este sitio de SFTP y transfiere los datos de chat a buzones de correo de Microsoft 365. SFTP también cifra los datos de los chats de hielo que se envían a los buzones durante el proceso de transferencia.

- El administrador que crea el conector ICE chat en el paso 3 (y en el que se descargan las claves públicas y la dirección IP en el paso 1) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Este rol es necesario para agregar conectores en la página **conectores de datos** del centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Paso 1: obtener las claves públicas SSH y PGP

El primer paso es obtener una copia de las claves públicas para el shell seguro (SSH) y Pretty Good Privacy (PGP). Use estas claves en el paso 2 para configurar el sitio de SFTP de chat de ICE para permitir que el conector (que ha creado en el paso 3) se conecte al sitio de SFTP y transfiera los datos de chat de hielo a los buzones de Microsoft 365. También obtendrá una dirección IP en este paso, que se usa al configurar el sitio de SFTP de chat de ICE.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos** en chat de **ICE**, haga clic en **Ver**.

3. En la página de **chat de ICE** , haga clic en **Agregar conector**.

4. En la página **condiciones de servicio** , haga clic en **Aceptar**.

5. En la página **agregar credenciales para chat de ICE del sitio de SFTP** , en el paso 1, haga clic en **Descargar clave ssh**, **Descargar clave PGP** y descargar vínculos de **dirección IP** para guardar una copia de cada archivo en el equipo local. Estos archivos contienen los siguientes elementos que se usan para configurar el sitio de SFTP de chat de ICE en el paso 2:

   - Clave pública SSH: esta clave se usa para configurar el SSH seguro para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio de SFTP de chat de ICE.

   - Clave pública PGP: esta clave se usa para configurar el cifrado de datos que se transfieren desde el sitio de SFTP de chat de ICE a Microsoft 365.

   - Dirección IP: el sitio de SFTP de chat de ICE está configurado para aceptar una solicitud de conexión solo desde esta dirección IP, que se usa en el conector de chat de hielo que se crea en el paso 3.

6. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 3 para crear el conector.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Paso 2: configurar el sitio de SFTP de chat de ICE

El paso siguiente es usar las claves públicas SSH y PGP y la dirección IP que obtuvo en el paso 1 para configurar la autenticación SSH y el cifrado PGP para el sitio de SFTP de chat de ICE. Esto permite que el conector de chat de hielo que crea en el paso 3 se conecte al sitio de SFTP chat y transfiera los datos de chat de ICE a Microsoft 365. Debe trabajar con el soporte técnico al cliente de chat de ICE para configurar el sitio de SFTP de chat de ICE.

## <a name="step-3-create-an-ice-chat-connector"></a>Paso 3: crear un conector de chat de ICE

El último paso consiste en crear un conector de chat de ICE en el centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de correo de chat de ICE y transferir mensajes de chat a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos** en chat de **ICE**, haga clic en **Ver**.

3. En la página de **chat de ICE** , haga clic en **Agregar conector**.

4. En la página **condiciones de servicio** , haga clic en **Aceptar**.

5. En la página **agregar credenciales para chat de ICE del sitio de SFTP** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **validar conexión**.

   - **Código de empresa:** El identificador de la organización, que se usa como nombre de usuario para el sitio de SFTP de chat de ICE.

   - **Contraseña:** La contraseña para el sitio de SFTP de chat de ICE.

   - **dirección URL de SFTP:** La URL del sitio de SFTP de chat de ICE (por ejemplo, sftp.theice.com).

   - **Puerto SFTP:** El número de puerto para el sitio de SFTP de chat de ICE. El conector usa este puerto para conectarse al sitio de SFTP.

6. Una vez validada la conexión, haga clic en **siguiente**.

7. En la página **asignar usuarios externos a Microsoft 365 usuarios** , habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario. Puede descargar una copia del archivo CSV de asignación de usuarios en esta página. Puede Agregar las asignaciones de usuario al archivo y luego cargarlas.

   > [!NOTE]
   > Como se explicó anteriormente, el archivo CSV de asignación personalizada contiene el IMiD de chat de hielo y la dirección de buzón de correo de Microsoft 365 correspondiente a cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de chat, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda a la IMiD de chat de ICE de un usuario, el conector importará el elemento a los buzones de correo de los usuarios especificados en las propiedades *SenderEmail* y *RecipientEmail* del elemento de chat. Si el conector no encuentra un usuario válido de Microsoft 365 mediante una asignación de usuario automática o personalizada, no se importará el elemento.

8. Haga clic en **siguiente**, revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

9. Vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.
