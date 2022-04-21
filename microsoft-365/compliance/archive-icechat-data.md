---
title: Configuración de un conector para archivar datos de ICE Chat
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector para importar y archivar datos de la herramienta ICE Chat en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 55af0567fc5cb8dbdeb571209fb7d9f863561900
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "65001706"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Configuración de un conector para archivar datos de ICE Chat

[!include[Purview banner](../includes/purview-rebrand-banner.md)]V

Use un conector nativo en el portal de cumplimiento de Microsoft Purview para importar y archivar datos de chat de servicios financieros desde la herramienta de colaboración ICE Chat. Después de configurar y configurar un conector, se conecta al sitio FTP seguro de ICE Chat (SFTP) de su organización una vez al día, convierte el contenido de los mensajes de chat a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos en buzones de Microsoft 365.

Una vez almacenados los datos de chat de ICE en buzones de usuario, puede aplicar las características de Microsoft Purview, como la suspensión por juicio, eDiscovery, archivado, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de ICE Chat. Por ejemplo, puede buscar mensajes de chat de ICE mediante la búsqueda de contenido o asociar el buzón que contiene los datos de ICE Chat con un custodio en un caso de exhibición de documentos electrónicos (Premium). El uso de un conector ICE Chat para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-ice-chat-data"></a>Introducción al archivado de datos de ICE Chat

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de chat de ICE en Microsoft 365.

![Flujo de trabajo de archivado de ice chat.](../media/ICEChatConnectorWorkflow.png)

1. Su organización trabaja con ICE Chat para configurar un sitio de ICE Chat SFTP. También trabajará con ICE Chat para configurar ICE Chat para copiar mensajes de chat en su sitio de ICE Chat SFTP.

2. Una vez cada 24 horas, los mensajes de chat de ICE Chat se copian en su sitio de ICE Chat SFTP.

3. El conector ICE Chat que crea en el portal de cumplimiento se conecta al sitio ICE Chat SFTP todos los días y transfiere los mensajes de chat de las 24 horas anteriores a una ubicación de Azure Storage segura en la nube de Microsoft. El conector también convierte el contenido de un masaje de chat en un formato de mensaje de correo electrónico.

4. El conector importa elementos de mensaje de chat a los buzones de correo de usuarios específicos. Se crea una nueva carpeta denominada **ICE Chat** en los buzones de usuario y los elementos de mensaje de chat se importan a esa carpeta. El conector usa el valor de las propiedades *SenderEmail* y *RecipientEmail* . Cada mensaje de chat contiene estas propiedades, que se rellenan con la dirección de correo electrónico del remitente y todos los destinatarios o participantes del mensaje de chat.

   Además de la asignación automática de usuarios que usa los valores de la propiedad *SenderEmail* y *RecipientEmail* (lo que significa que el conector importa un mensaje de chat al buzón del remitente y a los buzones de cada destinatario), también puede definir la asignación de usuarios personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el *imId* de chat de ICE y la dirección de buzón de Microsoft 365 correspondiente para cada usuario de la organización. Si habilita la asignación automática de usuarios y proporciona un archivo de asignación personalizada, para cada elemento de chat, el conector examinará primero el archivo de asignación personalizada. Si no encuentra una cuenta de usuario Microsoft 365 válida que se corresponda con el id. de chat ice de un usuario, el conector usará las propiedades *SenderEmail* y *RecipientEmail* del elemento de chat para importar el elemento a los buzones de los participantes del chat. Si el conector no encuentra un usuario Microsoft 365 válido en el archivo de asignación personalizada o en las propiedades *SenderEmail* y *RecipientEmail*, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar los datos de ICE Chat son externos a Microsoft 365 y deben completarse para poder crear el conector en el centro de cumplimiento.

- ICE Chat cobra a sus clientes una tarifa por cumplimiento externo. Su organización debe ponerse en contacto con el grupo de ventas de ICE Chat para analizar y firmar el contrato de servicios de datos de ICE Chat, que puede obtener en [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf). Este acuerdo está entre ICE Chat y su organización y no implica a Microsoft. Después de configurar un sitio de ICE Chat SFTP en el paso 2, ICE Chat proporciona las credenciales FTP directamente a su organización. A continuación, quién proporcionaría esas credenciales a Microsoft al configurar el conector en el paso 3.

- Debe configurar un sitio de ICE Chat SFTP antes de crear el conector en el paso 3. Después de trabajar con ICE Chat para configurar el sitio SFTP, los datos de ICE Chat se cargan en el sitio SFTP todos los días. El conector que cree en el paso 3 se conecta a este sitio SFTP y transfiere los datos de chat a Microsoft 365 buzones. SFTP también cifra los datos de ICE Chat que se envían a los buzones durante el proceso de transferencia.

- Para configurar un conector ICE Chat, debe usar claves y frases de contraseña para Pretty Good Privacy (PGP) y Secure Shell (SSH). Estas claves se usan para configurar el sitio ICE Chat SFTP y las usa el conector para conectarse al sitio DE SFTP de ICE Chat para importar datos a Microsoft 365. La clave PGP se usa para configurar el cifrado de datos que se transfieren desde el sitio de ICE Chat SFTP a Microsoft 365. La clave SSH se usa para configurar el shell seguro para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio de ICE Chat SFTP.

  Al configurar un conector, tiene la opción de usar claves públicas y contraseñas de clave proporcionadas por Microsoft o puede usar sus propias claves privadas y frases de contraseña. Se recomienda usar las claves públicas proporcionadas por Microsoft. Sin embargo, si su organización ya ha configurado un sitio de ICE Chat SFTP mediante claves privadas, puede crear un conector con estas mismas claves privadas.

- El conector ICE Chat puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos en el sitio SFTP, ninguno de esos elementos se importará a Microsoft 365.

- Al administrador que crea el conector ice chat en el paso 3 (y quién descarga las claves públicas y la dirección IP en el paso 1) se le debe asignar el rol administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="set-up-a-connector-using-public-keys"></a>Configuración de un conector mediante claves públicas

En los pasos de esta sección se muestra cómo configurar un conector ICE Chat mediante las claves públicas para Pretty Good Privacy (PGP) y Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Paso 1: Obtener claves públicas PGP y SSH

El primer paso es obtener una copia de las claves públicas para Pretty Good Privacy (PGP) y Secure Shell (SSH). Estas claves se usan en el paso 2 para configurar el sitio ICE Chat SFTP para permitir que el conector (que se crea en el paso 3) se conecte al sitio SFTP y transfiera los datos de ICE Chat a Microsoft 365 buzones. También obtendrá una dirección IP en este paso, que usará al configurar el sitio de ICE Chat SFTP.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** en **Ice Chat**, haga clic en **Ver**.

3. En la página **Chat de ICE** , haga clic en **Agregar conector**.

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar las claves públicas PGP y SSH proporcionadas por Microsoft**.

   ![Seleccione la opción para usar claves públicas.](../media/ICEChatPublicKeysOption.png)

6. En el paso 1, haga clic en los vínculos **Descargar clave SSH**, **Descargar clave PGP** y **Descargar dirección IP** para guardar una copia de cada archivo en el equipo local.

   ![Vínculos para descargar claves públicas y dirección IP.](../media/ICEChatPublicKeyDownloadLinks.png)

   Estos archivos contienen los siguientes elementos que se usan para configurar el sitio de ICE Chat SFTP en el paso 2:

   - Clave pública PGP: esta clave se usa para configurar el cifrado de datos que se transfieren desde el sitio de ICE Chat SFTP a Microsoft 365.

   - Clave pública SSH: esta clave se usa para configurar SSH seguro para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio de ICE Chat SFTP.

   - Dirección IP: el sitio ICE Chat SFTP está configurado para aceptar una solicitud de conexión solo desde esta dirección IP, que usa el conector ice chat que se crea en el paso 3.

7. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 3 para crear el conector.

### <a name="step-2-configure-the-ice-chat-sftp-site"></a>Paso 2: Configurar el sitio de ICE Chat SFTP

El siguiente paso es usar las claves públicas PGP y SSH y la dirección IP que obtuvo en el paso 1 para configurar el cifrado PGP y la autenticación SSH para el sitio ICE Chat SFTP. Esto permite que el conector ICE Chat que crea en el paso 3 se conecte al sitio de ICE Chat SFTP y transfiera los datos de ICE Chat a Microsoft 365. Debe trabajar con el servicio de atención al cliente de ICE Chat para configurar su sitio de ICE Chat SFTP.

### <a name="step-3-create-an-ice-chat-connector"></a>Paso 3: Creación de un conector ice chat

El último paso es crear un conector ICE Chat en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio ICE Chat SFTP y transferir mensajes de chat a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** en **Ice Chat**, haga clic en **Ver**.

3. En la página **Chat de ICE** , haga clic en **Agregar conector**.

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar claves públicas PGP y SSH**.

6. En el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Validar conexión**.

   - **Código firme:** El identificador de su organización, que se usa como nombre de usuario para el sitio DE SFTP de CHAT DE ICE.

   - **Contraseña:** La contraseña de su sitio de ICE Chat SFTP.

   - **DIRECCIÓN URL de SFTP:** Dirección URL del sitio de ICE Chat SFTP (por ejemplo, `sftp.theice.com`). También puede usar una dirección IP para este valor.

   - **Puerto SFTP:** Número de puerto para el sitio de ICE Chat SFTP. El conector usa este puerto para conectarse al sitio SFTP.

7. Una vez validada correctamente la conexión, haga clic en **Siguiente**.

8. En la página **Definir usuario** , especifique los usuarios para los que desea importar datos.

     - **Todos los usuarios de la organización**. Seleccione esta opción para importar datos para todos los usuarios.

     - **Solo usuarios en suspensión por juicio**. Seleccione esta opción para importar datos solo para los usuarios cuyos buzones están en suspensión por juicio. Esta opción importa datos a buzones de usuario que tienen la propiedad LitigationHoldEnabled establecida en True. Para obtener más información, consulte [Creación de una suspensión por litigio](create-a-litigation-hold.md).

9. En la página **Asignar usuarios externos a Microsoft 365 usuarios**, habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario. Puede descargar una copia del archivo CSV de asignación de usuario en esta página. Puede agregar las asignaciones de usuario al archivo y, a continuación, cargarlo.

   > [!NOTE]
   > Como se explicó anteriormente, el archivo CSV del archivo de asignación personalizado contiene el ímido ice chat y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de chat, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que se corresponda con el imid ice chat de un usuario, el conector importará el elemento a los buzones de los usuarios especificados en las propiedades *SenderEmail* y *RecipientEmail* del elemento de chat. Si el conector no encuentra un usuario Microsoft 365 válido mediante la asignación automática o personalizada de usuarios, el elemento no se importará.

10. Haga clic en **Siguiente**, revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

11. Vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="set-up-a-connector-using-private-keys"></a>Configuración de un conector mediante claves privadas

En los pasos de esta sección se muestra cómo configurar un conector ICE Chat mediante claves privadas PGP y SSH. Esta opción de configuración del conector está pensada para organizaciones que ya han configurado un sitio de ICE Chat SFTP mediante claves privadas.

### <a name="step-1-obtain-an-ip-address-to-configure-the-ice-chat-sftp-site"></a>Paso 1: Obtener una dirección IP para configurar el sitio de ICE Chat SFTP

Si su organización ha usado claves privadas PGP y SSH para configurar un sitio de ICE Chat SFTP, tendrá que obtener una dirección IP y proporcionarla al servicio de atención al cliente de ICE Chat. El sitio de ICE Chat SFTP debe configurarse para aceptar solicitudes de conexión de esta dirección IP. El conector ICE Chat usa la misma dirección IP para conectarse al sitio SFTP y transferir datos de ICE Chat a Microsoft 365.

Para obtener la dirección IP:

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** en **Ice Chat**, haga clic en **Ver**.

3. En la página de descripción del producto **ICE Chat** , haga clic en **Agregar conector.**

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar claves privadas PGP y SSH**.

   ![Seleccione la opción para usar claves privadas.](../media/ICEChatPrivateKeysOption.png)

6. En el paso 1, haga clic en **Descargar dirección IP** para guardar una copia del archivo de dirección IP en el equipo local.

   ![Descargue la dirección IP.](../media/ICEChatConnectorIPAddress.png)

7. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 2 para crear el conector.

Debe trabajar con el servicio de atención al cliente de ICE Chat para configurar su sitio de ICE Chat SFTP para aceptar solicitudes de conexión desde esta dirección IP.

### <a name="step-2-create-an-ice-chat-connector"></a>Paso 2: Creación de un conector ice chat

Una vez configurado el sitio de ICE Chat SFTP, el siguiente paso consiste en crear un conector ice chat en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de ICE Chat SFTP y transferir mensajes de correo electrónico a los cuadros de buzón de usuario correspondientes en Microsoft 365. Para completar este paso, asegúrese de tener copias de las mismas claves privadas y contraseñas de clave que usó para configurar el sitio de ICE Chat SFTP.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** en **Ice Chat**, haga clic en **Ver**.

3. En la página de descripción del producto **ICE Chat** , haga clic en **Agregar conector.**

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar claves privadas PGP y SSH**.

6. En el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Validar conexión**.

      - **Nombre:** Nombre del conector. Debe ser único en su organización.

      - **Código firme:** Identificador de la organización que se usa como nombre de usuario para el sitio de ICE Chat SFTP.

      - **Contraseña:** La contraseña del sitio DE SFTP de ICE Chat de su organización.

      - **DIRECCIÓN URL de SFTP:** Dirección URL del sitio de ICE Chat SFTP (por ejemplo, `sftp.theice.com`). También puede usar una dirección IP para este valor.

      - **Puerto SFTP:** Número de puerto para el sitio de ICE Chat SFTP. El conector usa este puerto para conectarse al sitio SFTP.

      - **Clave privada PGP:** Clave privada PGP para el sitio de ICE Chat SFTP. Asegúrese de incluir todo el valor de clave privada, incluidas las líneas inicial y final del bloque de claves.

      - **Frase de contraseña de clave PGP:** Frase de contraseña de la clave privada PGP.

      - **Clave privada SSH:** Clave privada SSH para el sitio de ICE Chat SFTP. Asegúrese de incluir todo el valor de clave privada, incluidas las líneas inicial y final del bloque de claves.

      - **Frase de contraseña de clave SSH:** Frase de contraseña de la clave privada SSH.

7. Una vez validada correctamente la conexión, haga clic en **Siguiente**.

8. En la página **Definir usuario** , especifique los usuarios para los que desea importar datos.

     - **Todos los usuarios de la organización**. Seleccione esta opción para importar datos para todos los usuarios.

     - **Solo usuarios en suspensión por juicio**. Seleccione esta opción para importar datos solo para los usuarios cuyos buzones están en suspensión por juicio. Esta opción importa datos a buzones de usuario que tienen la propiedad LitigationHoldEnabled establecida en True. Para obtener más información, consulte [Creación de una suspensión por litigio](create-a-litigation-hold.md).

9. En la página **Asignar usuarios de ICE Chat a Microsoft 365 usuarios**, habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario.

   > [!NOTE]
   > Como se explicó anteriormente, el archivo CSV del archivo de asignación personalizado contiene el ímido ice chat y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de chat, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que se corresponda con el imid ice chat de un usuario, el conector importará el elemento a los buzones de los usuarios especificados en las propiedades *SenderEmail* y *RecipientEmail* del elemento de chat. Si el conector no encuentra un usuario Microsoft 365 válido mediante la asignación automática o personalizada de usuarios, el elemento no se importará.

10. Haga clic en **Siguiente**, revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

11. Vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector. Haga clic en el conector para mostrar la página de control flotante, que contiene información sobre el conector.
