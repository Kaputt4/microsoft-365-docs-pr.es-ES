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
description: Los administradores pueden configurar un conector para importar y archivar datos de la herramienta de chat ICE en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 79a18017ce7aa3c646fa6c7230bde4b001ddc4c8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790174"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configurar un conector para archivar datos de chat de ICE

Use un conector nativo en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de chat de servicios financieros de la herramienta de colaboración de chat ICE. Después de configurar y configurar un conector, se conecta al sitio FTP seguro (SFTP) del chat ICE de su organización una vez al día, convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de Microsoft 365.

Después de almacenar los datos de chat de ICE en buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, exhibición de documentos electrónicos, archivado, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de chat de ICE. Por ejemplo, puede buscar mensajes de chat de ICE mediante la búsqueda de contenido o asociar el buzón que contiene los datos de chat de ICE con un administrador en un caso de eDiscovery avanzado. El uso de un conector de chat ICE para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-ice-chat-data"></a>Información general sobre el archivado de datos de chat de ICE

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de chat de ICE en Microsoft 365.

![Flujo de trabajo de archivado de chat ice](../media/ICEChatConnectorWorkflow.png)

1. Su organización trabaja con ice chat para configurar un sitio DE SFTP de chat ice. También trabajará con ice chat para configurar el chat de ICE para copiar mensajes de chat en su sitio DE SFTP de ice chat.

2. Una vez cada 24 horas, los mensajes de chat de ICE Chat se copian en su sitio DE SFTP de chat de ICE.

3. El conector de chat ICE que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio SFTP de chat de ICE todos los días y transfiere los mensajes de chat de las 24 horas anteriores a una ubicación segura de Azure Storage en Microsoft Cloud. El conector también convierte el contenido de un chat en formato de mensaje de correo electrónico.

4. El conector importa elementos de mensajes de chat a los buzones de usuarios específicos. Se crea una nueva carpeta llamada **ICE Chat** en los buzones de usuario y los elementos del mensaje de chat se importan a esa carpeta. El conector usa el valor de las *propiedades SenderEmail* y *RecipientEmail.* Cada mensaje de chat contiene estas propiedades, que se rellenan con la dirección de correo electrónico del remitente y todos los destinatarios o participantes del mensaje de chat.

   Además de la asignación automática de usuarios que usa los valores de la propiedad *SenderEmail* y *RecipientEmail* (lo que significa que el conector importa un mensaje de chat al buzón del remitente y a los buzones de todos los destinatarios), también puede definir la asignación de usuarios personalizada cargando un archivo de asignación CSV. Este archivo de asignación contiene el *ImId* de chat de ICE y la dirección de buzón de Microsoft 365 correspondiente para cada usuario de su organización. Si habilita la asignación automática de usuarios y proporciona un archivo de asignación personalizada, por cada elemento de chat, el conector primero buscará el archivo de asignación personalizada. Si no encuentra una cuenta de usuario válida de Microsoft 365 que corresponda al ImId de chat ICE de un usuario, el conector usará las propiedades *SenderEmail* y *RecipientEmail* del elemento de chat para importar el elemento a los buzones de los participantes del chat. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizada o en las propiedades *SenderEmail* y *RecipientEmail,* el elemento no se importará.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de chat de ICE son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Ice Chat cobra a sus clientes una tarifa por cumplimiento externo. Su organización debe ponerse en contacto con el grupo de ventas de chat de ICE para hablar y firmar el contrato de servicios de datos de chat de ICE, que puede obtener en [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Este contrato está entre ICE Chat y su organización y no implica a Microsoft. Después de configurar un sitio SFTP de chat ice en el paso 2, ice chat proporciona las credenciales ftp directamente a su organización. A continuación, usted que proporcionaría esas credenciales a Microsoft al configurar el conector en el paso 3.

- Debe configurar un sitio SFTP de chat ice antes de crear el conector en el paso 3. Después de trabajar con el chat de ICE para configurar el sitio SFTP, los datos del chat de ICE se cargan en el sitio SFTP todos los días. El conector que cree en el paso 3 se conecta a este sitio SFTP y transfiere los datos de chat a los buzones de Microsoft 365. SFTP también cifra los datos de chat de ICE que se envían a los buzones durante el proceso de transferencia.

- El conector de chat ice puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos en el sitio SFTP, ninguno de esos elementos se importará a Microsoft 365.

- El administrador que crea el conector de chat ICE en el paso 3 (y quién descarga las claves públicas y la dirección IP en el paso 1) debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Este rol es necesario para agregar conectores en la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Paso 1: Obtener claves públicas SSH y PGP

El primer paso es obtener una copia de las claves públicas del Shell seguro (SSH) y la Privacidad bastante buena (PGP). Estas claves se usan en el paso 2 para configurar el sitio DE SFTP de chat ice para permitir que el conector (que crea en el paso 3) se conecte al sitio SFTP y transfiera los datos del chat de ICE a los buzones de Microsoft 365. También obtendrá una dirección IP en este paso, que usará al configurar el sitio SFTP de chat de ICE.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. En la página **Conectores de datos,** en **Chat ice**, haga clic **en Ver**.

3. En la página **Chat de ICE,** haga clic **en Agregar conector.**

4. En la **página Términos de** servicio, haga clic **en Aceptar.**

5. En la página Agregar credenciales para el sitio **SFTP** de chat ICE en el paso 1, haga clic en la tecla **SSH** de descarga, la clave **PGP** de descarga y los vínculos descargar dirección **IP** para guardar una copia de cada archivo en el equipo local. Estos archivos contienen los siguientes elementos que se usan para configurar el sitio SFTP de chat de ICE en el paso 2:

   - Clave pública SSH: esta clave se usa para configurar Secure SSH para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio SFTP de chat de ICE.

   - Clave pública PGP: esta clave se usa para configurar el cifrado de los datos que se transfieren desde el sitio SFTP de chat ice a Microsoft 365.

   - Dirección IP: el sitio SFTP de chat ICE está configurado para aceptar una solicitud de conexión solo desde esta dirección IP, que usa el conector de chat ICE que crea en el paso 3.

6. Haga **clic en** Cancelar para cerrar el asistente. Volverá a este asistente en el paso 3 para crear el conector.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Paso 2: Configurar el sitio DE SFTP de chat de ICE

El siguiente paso es usar las claves públicas SSH y PGP y la dirección IP que obtuvo en el paso 1 para configurar la autenticación SSH y el cifrado PGP para el sitio SFTP de chat ice. Esto permite que el conector de chat ICE que cree en el paso 3 se conecte al sitio SFTP de chat de ICE y transfiera los datos del chat de ICE a Microsoft 365. Debe trabajar con el servicio de soporte al cliente de chat de ICE para configurar el sitio DE SFTP de chat de ICE.

## <a name="step-3-create-an-ice-chat-connector"></a>Paso 3: Crear un conector de chat ICE

El último paso es crear un conector de chat ICE en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio SFTP de chat ice y transferir mensajes de chat a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) conectores de **datos y haga clic en** conectores de datos en el panel de navegación izquierdo.

2. En la página **Conectores de datos,** en **Chat ice**, haga clic **en Ver**.

3. En la página **Chat de ICE,** haga clic **en Agregar conector.**

4. En la **página Términos de** servicio, haga clic **en Aceptar.**

5. En la página Agregar credenciales para el sitio **SFTP** de chat ICE, en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **Validar conexión.**

   - **Código firme:** El identificador de su organización, que se usa como nombre de usuario para el sitio SFTP de chat de ICE.

   - **Contraseña:** La contraseña del sitio SFTP de chat de ICE.

   - **DIRECCIÓN URL de SFTP:** La dirección URL del sitio SFTP de chat ice (por ejemplo, sftp.theice.com).

   - **Puerto SFTP:** El número de puerto del sitio DE SFTP de chat de ICE. El conector usa este puerto para conectarse al sitio SFTP.

6. Después de validar la conexión, haga clic **en Siguiente**.

7. En la página Asignar usuarios externos a **usuarios de Microsoft 365,** habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario. Puede descargar una copia del archivo CSV de asignación de usuarios en esta página. Puede agregar las asignaciones de usuario al archivo y, a continuación, cargarlo.

   > [!NOTE]
   > Como se ha explicado anteriormente, el archivo CSV del archivo de asignación personalizado contiene el imid de chat de ICE y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de chat, el conector primero buscará el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el imid de chat ICE de un usuario, el conector importará el elemento a los buzones de los usuarios especificados en las propiedades *SenderEmail* y *RecipientEmail* del elemento de chat. Si el conector no encuentra un usuario válido de Microsoft 365 mediante una asignación de usuario automática o personalizada, el elemento no se importará.

8. Haga **clic en Siguiente,** revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

9. Vaya a la **página Conectores de** datos para ver el progreso del proceso de importación para el nuevo conector.
