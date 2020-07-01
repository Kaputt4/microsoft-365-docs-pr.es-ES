---
title: Configurar un conector para archivar datos de mensajes de Bloomberg
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de datos para importar y archivar datos de la herramienta de correo electrónico de mensajes de Bloomberg en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: 700a0619d2299fc7254628059787478cc0e168fa
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937380"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data-preview"></a>Configurar un conector para archivar datos de mensajes de Bloomberg (versión preliminar)

Use un conector de datos en el centro de cumplimiento de Microsoft 365 para importar y archivar datos de correo electrónico de servicios financieros desde la herramienta de colaboración de [mensajes de Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) . Después de configurar y configurar un conector, se conecta al sitio Bloomberg Secure FTP (SFTP) de su organización una vez al día e importa los elementos de correo electrónico a los buzones en Microsoft 365.

Una vez que los datos de los mensajes de Bloomberg se almacenan en buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido, el archivado local, la auditoría, el cumplimiento de comunicaciones y las directivas de retención de Microsoft 365 a los datos de mensajes de Bloomberg. Por ejemplo, puede buscar correos electrónicos de mensajes de Bloomberg mediante la herramienta de búsqueda de contenido o asociar el buzón de correo que contiene los datos de mensajes de Bloomberg con un custodio en un caso de eDiscovery avanzado. El uso de un conector de mensajes de Bloomberg para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Información general sobre el archivado de datos de mensajes de Bloomberg

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de mensajes de Bloomberg en Microsoft 365.

![Proceso de importación y archivo de mensajes de Bloomberg](../media/BloombergMessageArchiving.png)

1. Su organización trabaja con Bloomberg para configurar un sitio de SFTP de Bloomberg. También trabajará con Bloomberg para configurar el mensaje de Bloomberg para copiar mensajes de correo electrónico al sitio Bloomberg de SFTP.

2. Una vez cada 24 horas, los mensajes de correo electrónico de un mensaje de Bloomberg se copian en el sitio de SFTP de Bloomberg.

3. El conector de mensajes de Bloomberg que se crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio Bloomberg SFTP todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área de almacenamiento seguro de Azure en la nube de Microsoft.

4. El conector importa los elementos del mensaje de correo electrónico al buzón de un usuario específico. Se creará una nueva carpeta llamada BloombergMessage en el buzón de correo del usuario específico y se importarán los elementos en ella. 

   El conector lo hace mediante el valor de la propiedad CorporateEmailAddress. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática de usuarios mediante el valor de la propiedad *CorporateEmailAddress* , también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene un UUID de Bloomberg y la dirección de buzón de correo de Microsoft 365 correspondiente a cada usuario de la organización. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de correo electrónico, el conector buscará primero en el archivo de asignación personalizada. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el UUID del usuario, el conector usa la propiedad *CorporateEmailAddress* del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizada o en la propiedad *CorporateEmailAddress* del elemento de correo electrónico, no se importará el elemento.

## <a name="before-you-begin"></a>Antes de empezar

Muchos de los pasos de implementación necesarios para archivar datos de mensajes de Bloomberg son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Office 365 y, a continuación, acepte la solicitud. Debe completar este paso para poder crear correctamente el conector de mensajes de Bloomberg en el paso 3.

- Suscríbase a [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Esto es necesario para que pueda iniciar sesión en Bloomberg Anywhere para acceder al sitio Bloomberg SFTP que debe configurar y configurar.

- Configure un sitio Bloomberg SFTP (protocolo seguro de transferencia de archivos). Después de trabajar con Bloomberg para configurar el sitio de SFTP, los datos de un mensaje de Bloomberg se cargan al sitio de SFTP todos los días. El conector que se crea en el paso 2 se conecta a este sitio de SFTP y transfiere los datos de correo electrónico a los buzones de Microsoft 365. SFTP también cifra los datos de mensajes de Bloomberg que se envían a los buzones durante el proceso de transferencia.

  Para obtener información sobre Bloomberg SFTP (también denominado *BB-SFTP*):

  - Consulte el documento "estándares de conectividad de SFTP" en el [soporte de Bloomberg](https://www.bloomberg.com/professional/support/documentation/).

  - Póngase en contacto con el [soporte al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

   > [!NOTE]
   > Si su organización ya ha implementado un conector para archivar datos instantáneos de Bloomberg, no es necesario que configure otro sitio de SFTP. Puede usar el mismo sitio de SFTP para el conector de mensajes de Bloomberg.

- Después de trabajar con Bloomberg para configurar un sitio de SFTP, Bloomberg le proporcionará cierta información después de que responda al mensaje de correo electrónico de implementación de Bloomberg. Guarde una copia de la siguiente información. Se usa para configurar un conector en el paso 3.

  - Código de empresa, que es un identificador de su organización y se usa para iniciar sesión en el sitio de SFTP de Bloomberg.

  - Contraseña para el sitio de SFTP de Bloomberg

  - Dirección URL para el sitio de SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com). Además, Bloomberg también puede proporcionar una dirección IP correspondiente para el sitio de SFTP de Bloomberg, que también se puede usar para configurar el conector.

  - Número de puerto para el sitio de SFTP de Bloomberg

- El usuario que crea un conector de mensajes para Bloomberg en el paso 3 (y que descarga las claves públicas y la dirección IP en el paso 1) debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para agregar conectores en la página **conectores de datos** en el centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.


## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Paso 1: obtener las claves públicas SSH y PGP

El primer paso es obtener una copia de las claves públicas para el shell seguro (SSH) y Pretty Good Privacy (PGP). Use estas claves en el paso 2 para configurar el sitio de SFTP de Bloomberg para permitir que el conector (creado en el paso 3) se conecte al sitio de SFTP y transfiera los datos de correo electrónico del mensaje de Bloomberg a los buzones de Microsoft 365. También puede obtener una dirección IP en este paso, que se usa al configurar el sitio Bloomberg de SFTP.

1. Vaya a [ https://compliance.microsoft.com\ ] ( https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos** en el **mensaje Bloomberg**, haga clic en **Ver**.

3. En la página Descripción del producto de **Bloomberg Message** , haga clic en **Agregar conector**

4. En la página **condiciones de servicio** , haga clic en **Aceptar**.

5. En el paso 1 del **sitio de agregar credenciales para Bloomberg SFTP** , haga clic en **Descargar clave ssh**, **Descargar clave PGP**y descargar vínculos de **dirección IP** para guardar una copia de cada archivo en el equipo local. Estos archivos contienen los siguientes elementos que se usan para configurar el sitio Bloomberg de SFTP en el paso 2:

   - Clave pública SSH: esta clave se usa para configurar Secure Shell (SSH) para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio Bloomberg de SFTP.

   - Clave pública PGP: esta clave se usa para configurar el cifrado de datos que se transfieren desde el sitio de SFTP de Bloomberg a Microsoft 365.

   - Dirección IP: el sitio Bloomberg de SFTP está configurado para aceptar una solicitud de conexión solo desde esta dirección IP, que se usa en el conector de mensajes Bloomberg que se crea en el paso 3.

6. Haga clic en **Cancelar** para cerrar el asistente. Vuelva a este asistente en el paso 3 para crear el conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Paso 2: configurar el sitio de SFTP de Bloomberg

> [!NOTE]
> Como se mencionó anteriormente, si la organización ha configurado anteriormente un sitio de SFTP de Bloomberg para archivar datos instantáneos de Bloomberg, no es necesario configurar otro. Puede especificar el mismo sitio de SFTP al crear el conector en el paso 3.

El siguiente paso es usar las claves públicas SSH y PGP y la dirección IP que obtuvo en el paso 1 para configurar la autenticación SSH y el cifrado PGP para el sitio de SFTP de Bloomberg. Esto permite que el conector de mensajes de Bloomberg que ha creado en el paso 3 se conecte al sitio Bloomberg de SFTP y transfiera los datos de mensajes de Bloomberg a Microsoft 365. Debe trabajar con el servicio de soporte al cliente de Bloomberg para configurar su sitio de SFTP. Póngase en contacto con el [soporte al cliente de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obtener ayuda.

> [!IMPORTANT]
> Bloomberg recomienda adjuntar los tres archivos que descargó en el paso 1 a un mensaje de correo electrónico y enviarlo a su equipo de atención al cliente cuando trabaja con ellos para configurar el sitio de SFTP de Bloomberg.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Paso 3: crear un conector de mensajes de Bloomberg

El último paso consiste en crear un conector de mensajes de Bloomberg en el centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio Bloomberg de SFTP y transferir los mensajes de correo electrónico a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos** en el panel de navegación izquierdo.

2. En la página **conectores de datos** en el **mensaje Bloomberg**, haga clic en **Ver**.

3. En la página Descripción del producto de **Bloomberg Message** , haga clic en **Agregar conector**

4. En la página **condiciones de servicio** , haga clic en **Aceptar**.

5. En la página **agregar credenciales para Bloomberg SFTP** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

      - **Código de empresa:** El identificador de la organización que se usa como nombre de usuario para el sitio de SFTP de Bloomberg.

      - **Contraseña:** La contraseña del sitio Bloomberg de SFTP de su organización.

      - **dirección URL de SFTP:** La URL para el sitio de SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com).

      - **Puerto SFTP:** El número de puerto para el sitio de SFTP de Bloomberg. El conector usa este puerto para conectarse al sitio de SFTP.

6. En la página **asignación de usuarios** , habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario.

7. Haga clic en **siguiente**, revise la configuración y, a continuación, haga clic en preparar para crear el conector.

8. Vaya a la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- No se admite el subproceso del correo electrónico de mensajes de Bloomberg importado a Microsoft 365. Se importan los mensajes individuales enviados a una persona, pero no se presentan en una conversación encadenada. Microsoft está trabajando para admitir el subprocesamiento en versiones posteriores del conector de datos de mensajes de Bloomberg.
