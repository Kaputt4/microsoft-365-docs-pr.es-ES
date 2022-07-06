---
title: Configuración de un conector para archivar los datos del mensaje de Bloomberg
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de datos para importar y archivar datos desde la herramienta de correo electrónico bloomberg message en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como suspensión legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 43dd41c8a0d1aa438ed978e86fc0a45da01d7835
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66630805"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Configuración de un conector para archivar los datos del mensaje de Bloomberg

Use un conector de datos en el portal de cumplimiento Microsoft Purview para importar y archivar datos de correo electrónico de servicios financieros desde la herramienta [de colaboración de mensajes de Bloomberg](https://www.bloomberg.com/professional/product/collaboration/). Después de configurar y configurar un conector, se conecta al sitio ftp seguro (SFTP) de Bloomberg de su organización una vez al día e importa elementos de correo electrónico a buzones de Correo de Microsoft 365.

Una vez almacenados los datos del mensaje de Bloomberg en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, búsqueda de contenido, archivado local, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de Bloomberg Message. Por ejemplo, puede buscar mensajes de correo electrónico de Bloomberg Message mediante la herramienta de búsqueda de contenido o asociar el buzón que contiene los datos del mensaje de Bloomberg con un custodio en un caso de eDiscovery (Premium). El uso de un conector de mensajes de Bloomberg para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Información general sobre el archivado de datos de mensajes de Bloomberg

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos del mensaje de Bloomberg en Microsoft 365.

![Proceso de importación y archivo de mensajes de Bloomberg.](../media/BloombergMessageArchiving.png)

1. Su organización trabaja con Bloomberg para configurar un sitio de Bloomberg SFTP. También trabajará con Bloomberg para configurar Bloomberg Message para copiar mensajes de correo electrónico en el sitio de Bloomberg SFTP.

2. Una vez cada 24 horas, los mensajes de correo electrónico de Bloomberg Message se copian en el sitio de Bloomberg SFTP.

3. El conector de mensajes de Bloomberg que se crea en el portal de cumplimiento se conecta al sitio DE SFTP de Bloomberg todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos de mensaje de correo electrónico al buzón de un usuario específico. Se crea una nueva carpeta denominada BloombergMessage en el buzón de correo del usuario específico y los elementos se importarán a ella.

   Para ello, el conector usa el valor de la propiedad CorporateEmailAddress. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática de usuarios mediante el valor de la propiedad *CorporateEmailAddress* , también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene un UUID de Bloomberg y la dirección de buzón de Microsoft 365 correspondiente para cada usuario de la organización. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de correo electrónico, el conector examinará primero el archivo de asignación personalizada. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el UUID de Bloomberg de un usuario, el conector usa la propiedad *CorporateEmailAddress* del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizada o en la propiedad *CorporateEmailAddress* del elemento de correo electrónico, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar los datos del mensaje de Bloomberg son externos a Microsoft 365 y deben completarse para poder crear el conector en el centro de cumplimiento.

- Para configurar un conector de mensajes de Bloomberg, debe usar claves y frases de contraseña para Pretty Good Privacy (PGP) y Secure Shell (SSH). Estas claves se usan para configurar el sitio DE SFTP de Bloomberg y las usa el conector para conectarse al sitio de Bloomberg SFTP con el fin de importar datos a Microsoft 365. La clave PGP se usa para configurar el cifrado de datos que se transfieren desde el sitio de Bloomberg SFTP a Microsoft 365. La clave SSH se usa para configurar el shell seguro para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio de Bloomberg SFTP.

  Al configurar un conector, tiene la opción de usar claves públicas y contraseñas de clave proporcionadas por Microsoft o puede usar sus propias claves privadas y frases de contraseña. Se recomienda usar las claves públicas proporcionadas por Microsoft. Sin embargo, si su organización ya ha configurado un sitio de Bloomberg SFTP mediante claves privadas, puede crear un conector con estas mismas claves privadas.

- Suscríbase a [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Esto es necesario para que pueda iniciar sesión en Bloomberg Anywhere para acceder al sitio de Bloomberg SFTP que tiene que configurar.

- Configure un sitio de Bloomberg SFTP (protocolo seguro de transferencia de archivos). Después de trabajar con Bloomberg para configurar el sitio SFTP, los datos de Bloomberg Message se cargan en el sitio SFTP todos los días. El conector que cree en el paso 2 se conecta a este sitio SFTP y transfiere los datos de correo electrónico a buzones de Microsoft 365. SFTP también cifra los datos del mensaje de Bloomberg que se envían a los buzones durante el proceso de transferencia.

  Para obtener información sobre Bloomberg SFTP (también llamado *BB-SFTP*):

  - Consulte el documento "Estándares de conectividad SFTP" en [Soporte técnico de Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Póngase en contacto con [el servicio de atención al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

- Después de trabajar con Bloomberg para configurar un sitio SFTP, Bloomberg le proporcionará información después de responder al mensaje de correo electrónico de implementación de Bloomberg. Guarde una copia de la siguiente información. Se usa para configurar un conector en el paso 3.

  - Código firme, que es un identificador para su organización y se usa para iniciar sesión en el sitio de Bloomberg SFTP.

  - Contraseña para el sitio de Bloomberg SFTP

  - Dirección URL del sitio SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com). Además, Bloomberg también puede proporcionar una dirección IP correspondiente para el sitio de Bloomberg SFTP, que también se puede usar para configurar el conector.

  - Número de puerto para el sitio de Bloomberg SFTP

- El conector bloomberg message puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos en el sitio SFTP, ninguno de esos elementos se importará a Microsoft 365.

- Al usuario que crea un conector de mensajes de Bloomberg en el paso 3 (y que descarga las claves públicas y la dirección IP en el paso 1) se le debe asignar el rol de Administración conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

## <a name="set-up-a-connector-using-public-keys"></a>Configuración de un conector mediante claves públicas

Los pasos de esta sección muestran cómo configurar un conector de mensajes de Bloomberg mediante las claves públicas para Pretty Good Privacy (PGP) y Secure Shell (SSH).

### <a name="step-1-obtain-pgp-and-ssh-public-keys"></a>Paso 1: Obtener claves públicas PGP y SSH

El primer paso es obtener una copia de las claves públicas PGP y SSH. Estas claves se usan en el paso 2 para configurar el sitio de Bloomberg SFTP para permitir que el conector (que se crea en el paso 3) se conecte al sitio SFTP y transfiera los datos de correo electrónico del mensaje bloomberg a buzones de Microsoft 365. También obtendrá una dirección IP en este paso, que usará al configurar el sitio de Bloomberg SFTP.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** , en **Mensaje de Bloomberg**, haga clic en **Ver**.

3. En la página **Bloomberg Message product description (Descripción del producto del mensaje de Bloomberg** ), haga clic en **Agregar conector.**

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar las claves públicas PGP y SSH proporcionadas por Microsoft**.

   ![Seleccione la opción para usar claves públicas.](../media/BloombergMessagePublicKeysOption.png)

6. En el paso 1, haga clic en los vínculos **Descargar clave SSH**, **Descargar clave PGP** y **Descargar dirección IP** para guardar una copia de cada archivo en el equipo local.

   ![Vínculos para descargar claves públicas y dirección IP.](../media/BloombergMessagePublicKeyDownloadLinks.png)

   Estos archivos contienen los siguientes elementos que se usan para configurar el sitio de Bloomberg SFTP en el paso 2:

   - Clave pública PGP: esta clave se usa para configurar el cifrado de datos que se transfieren desde el sitio de Bloomberg SFTP a Microsoft 365.

   - Clave pública SSH: esta clave se usa para configurar el shell seguro para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio de Bloomberg SFTP.

   - Dirección IP: el sitio de Bloomberg SFTP está configurado para aceptar solicitudes de conexión de esta dirección IP. El conector de mensajes bloomberg usa la misma dirección IP para conectarse al sitio SFTP y transferir datos de Bloomberg Message a Microsoft 365.

7. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 3 para crear el conector.

### <a name="step-2-configure-the-bloomberg-sftp-site"></a>Paso 2: Configuración del sitio de Bloomberg SFTP

> [!NOTE]
> Si su organización ha configurado previamente un sitio SFTP de Bloomberg para archivar datos de Instant Bloomberg mediante claves PGP y SSH públicas, no es necesario configurar otro. Puede especificar el mismo sitio SFTP al crear el conector en el paso 3.

El siguiente paso es usar las claves públicas PGP y SSH y la dirección IP que obtuvo en el paso 1 para configurar el cifrado PGP y la autenticación SSH para el sitio SFTP de Bloomberg. Esto permite que el conector bloomberg message que se crea en el paso 3 se conecte al sitio DE SFTP de Bloomberg y transfiera los datos de Bloomberg Message a Microsoft 365. Debe trabajar con el servicio de atención al cliente de Bloomberg para configurar su sitio de Bloomberg SFTP. Póngase en contacto con [el servicio de atención al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obtener ayuda.

> [!IMPORTANT]
> Bloomberg recomienda adjuntar los tres archivos que descargó en el paso 1 a un mensaje de correo electrónico y enviarlo a su equipo de soporte al cliente cuando trabaje con ellos para configurar su sitio de Bloomberg SFTP.

### <a name="step-3-create-a-bloomberg-message-connector"></a>Paso 3: Crear un conector de mensajes de Bloomberg

El último paso es crear un conector bloomberg message en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de Bloomberg SFTP y transferir mensajes de correo electrónico a los cuadros de buzón de usuario correspondientes de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** , en **Mensaje de Bloomberg**, haga clic en **Ver**.

3. En la página **Bloomberg Message product description (Descripción del producto del mensaje de Bloomberg** ), haga clic en **Agregar conector.**

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar las claves públicas PGP y SSH proporcionadas por Microsoft**.

6. En el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Validar conexión**.

      - **Nombre:** Nombre del conector. Debe ser único en su organización.

      - **Código firme:** Identificador de la organización que se usa como nombre de usuario para el sitio de Bloomberg SFTP.

      - **Contraseña:** La contraseña del sitio SFTP de Bloomberg de la organización.

      - **DIRECCIÓN URL de SFTP:** Dirección URL del sitio DE SFTP de Bloomberg (por ejemplo, `sftp.bloomberg.com`). También puede usar una dirección IP para este valor.

      - **Puerto SFTP:** Número de puerto del sitio de Bloomberg SFTP. El conector usa este puerto para conectarse al sitio SFTP.

7. Una vez validada correctamente la conexión, haga clic en **Siguiente**.

8. En la página **Definir usuario** , especifique los usuarios para los que desea importar datos.

     - **Todos los usuarios de la organización**. Seleccione esta opción para importar datos para todos los usuarios.

     - **Solo usuarios en suspensión por juicio**. Seleccione esta opción para importar datos solo para los usuarios cuyos buzones están en suspensión por juicio. Esta opción importa datos a buzones de usuario que tienen la propiedad LitigationHoldEnabled establecida en True. Para obtener más información, consulte [Creación de una suspensión por litigio](create-a-litigation-hold.md).

9. En la página **Asignar mensajes de Bloomberg a usuarios de Microsoft 365** , habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario.

   > [!NOTE]
   > El conector importa elementos de mensaje al buzón de un usuario específico. Se crea una nueva carpeta denominada **BloombergMessage** en el buzón de correo del usuario específico y los elementos se importarán a ella. El conector lo hace mediante el valor de la propiedad *CorporateEmailAddress* . Cada mensaje de chat contiene esta propiedad y la propiedad se rellena con la dirección de correo electrónico de cada participante del mensaje de chat. Además de la asignación automática de usuarios mediante el valor de la propiedad *CorporateEmailAddress* , también puede definir la asignación personalizada mediante la carga de un archivo de asignación CSV. El archivo de asignación debe contener el UUID de Bloomberg y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de mensaje, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda al UUID de Bloomberg de un usuario, el conector usará la propiedad *CorporateEmailAddress* del elemento de chat. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad *CorporateEmailAddress* del elemento de mensaje, el elemento no se importará.

10. Haga clic en **Siguiente**, revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

11. Vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector. Haga clic en el conector para mostrar la página de control flotante, que contiene información sobre el conector.

## <a name="set-up-a-connector-using-private-keys"></a>Configuración de un conector mediante claves privadas

En los pasos de esta sección se muestra cómo configurar un conector de mensajes bloomberg mediante claves privadas PGP y SSH. Esta opción de configuración del conector está pensada para organizaciones que ya han configurado un sitio de Bloomberg SFTP mediante claves privadas.

### <a name="step-1-obtain-an-ip-address-to-configure-the-bloomberg-sftp-site"></a>Paso 1: Obtener una dirección IP para configurar el sitio de Bloomberg SFTP

> [!NOTE]
> Si su organización ha configurado previamente un sitio de Bloomberg SFTP para archivar datos de Instant Bloomberg mediante claves privadas PGP y SSH, no es necesario configurar otro. Puede especificar el mismo sitio SFTP al crear el conector en el paso 2.

Si su organización ha usado claves privadas PGP y SSH para configurar un sitio de Bloomberg SFTP, tendrá que obtener una dirección IP y proporcionarla al servicio de atención al cliente de Bloomberg. El sitio DE SFTP de Bloomberg debe configurarse para aceptar solicitudes de conexión de esta dirección IP. El conector de mensajes bloomberg usa la misma dirección IP para conectarse al sitio SFTP y transferir datos de Bloomberg Message a Microsoft 365.

Para obtener la dirección IP:

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** , en **Mensaje de Bloomberg**, haga clic en **Ver**.

3. En la página **Bloomberg Message product description (Descripción del producto del mensaje de Bloomberg** ), haga clic en **Agregar conector.**

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar claves privadas PGP y SSH**.

6. En el paso 1, haga clic en **Descargar dirección IP** para guardar una copia del archivo de dirección IP en el equipo local.

   ![Descargue la dirección IP.](../media/BloombergMessageConnectorIPAddress.png)

7. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 2 para crear el conector.

Debe trabajar con el servicio de atención al cliente de Bloomberg para configurar su sitio de Bloomberg SFTP para aceptar solicitudes de conexión desde esta dirección IP. Póngase en contacto con [el servicio de atención al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obtener ayuda.

### <a name="step-2-create-a-bloomberg-message-connector"></a>Paso 2: Crear un conector de mensajes de Bloomberg

Una vez configurado el sitio DE SFTP de Bloomberg, el siguiente paso es crear un conector de mensajes de Bloomberg en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de Bloomberg SFTP y transferir mensajes de correo electrónico a los cuadros de buzón de usuario correspondientes de Microsoft 365. Para completar este paso, asegúrese de tener copias de las mismas claves privadas y contraseñas de clave que usó para configurar el sitio de Bloomberg SFTP.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. En la página **Conectores de datos** , en **Mensaje de Bloomberg**, haga clic en **Ver**.

3. En la página **Bloomberg Message product description (Descripción del producto del mensaje de Bloomberg** ), haga clic en **Agregar conector.**

4. En la página **Términos de servicio** , haga clic en **Aceptar**.

5. En la página **Agregar credenciales para el origen de contenido** , haga clic en **Quiero usar claves privadas PGP y SSH**.

   ![Seleccione la opción para usar claves privadas.](../media/BloombergMessagePrivateKeysOption.png)

6. En el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Validar conexión**.

      - **Nombre:** Nombre del conector. Debe ser único en su organización.

      - **Código firme:** Identificador de la organización que se usa como nombre de usuario para el sitio de Bloomberg SFTP.

      - **Contraseña:** La contraseña del sitio SFTP de Bloomberg de la organización.

      - **DIRECCIÓN URL de SFTP:** Dirección URL del sitio DE SFTP de Bloomberg (por ejemplo, `sftp.bloomberg.com`). También puede usar una dirección IP para este valor.

      - **Puerto SFTP:** Número de puerto del sitio de Bloomberg SFTP. El conector usa este puerto para conectarse al sitio SFTP.

      - **Clave privada PGP:** Clave privada PGP para el sitio de Bloomberg SFTP. Asegúrese de incluir todo el valor de clave privada, incluidas las líneas inicial y final del bloque de claves.

      - **Frase de contraseña de clave PGP:** Frase de contraseña de la clave privada PGP.

      - **Clave privada SSH:** Clave privada SSH para el sitio de Bloomberg SFTP. Asegúrese de incluir todo el valor de clave privada, incluidas las líneas inicial y final del bloque de claves.

      - **Frase de contraseña de clave SSH:** Frase de contraseña de la clave privada SSH.

7. Una vez validada correctamente la conexión, haga clic en **Siguiente**.

8. En la página **Definir usuario** , especifique los usuarios para los que desea importar datos.

     - **Todos los usuarios de la organización**. Seleccione esta opción para importar datos para todos los usuarios.

     - **Solo usuarios en suspensión por juicio**. Seleccione esta opción para importar datos solo para los usuarios cuyos buzones están en suspensión por juicio. Esta opción importa datos a buzones de usuario que tienen la propiedad LitigationHoldEnabled establecida en True. Para obtener más información, consulte [Creación de una suspensión por litigio](create-a-litigation-hold.md).

9. En la página **Asignar mensajes de Bloomberg a usuarios de Microsoft 365** , habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario.

   > [!NOTE]
   > El conector importa elementos de mensaje al buzón de un usuario específico. Se crea una nueva carpeta denominada **BloombergMessage** en el buzón de correo del usuario específico y los elementos se importarán a ella. El conector lo hace mediante el valor de la propiedad *CorporateEmailAddress* . Cada mensaje de chat contiene esta propiedad y la propiedad se rellena con la dirección de correo electrónico de cada participante del mensaje de chat. Además de la asignación automática de usuarios mediante el valor de la propiedad *CorporateEmailAddress* , también puede definir la asignación personalizada mediante la carga de un archivo de asignación CSV. El archivo de asignación debe contener el UUID de Bloomberg y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de mensaje, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda al UUID de Bloomberg de un usuario, el conector usará la propiedad *CorporateEmailAddress* del elemento de chat. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad *CorporateEmailAddress* del elemento de mensaje, el elemento no se importará.

10. Haga clic en **Siguiente**, revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

11. Vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector. Haga clic en el conector para mostrar la página de control flotante, que contiene información sobre el conector.

## <a name="known-issues"></a>Problemas conocidos

- No se admite el subproceso del correo electrónico de mensaje de Bloomberg importado a Microsoft 365. Los mensajes individuales enviados a una persona se importan, pero no se presentan en una conversación en subproceso. Microsoft está trabajando para admitir el subproceso en versiones posteriores del conector de datos de Bloomberg Message.
