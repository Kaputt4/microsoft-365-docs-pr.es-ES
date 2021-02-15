---
title: Configurar un conector para archivar datos de Instant Bloomberg
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Obtenga información sobre cómo los administradores pueden configurar y usar un conector de datos para importar y archivar datos de la herramienta de chat Instant Bloomberg en Microsoft 365.
ms.openlocfilehash: b7cd35e0613d9c278e8f36efc194de9dc9b5a5f2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790098"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Configurar un conector para archivar datos de Instant Bloomberg

Use un conector nativo en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de chat de servicios financieros de la herramienta de colaboración [Instant Bloomberg.](https://www.bloomberg.com/professional/product/collaboration/) Después de configurar y configurar un conector, se conecta al sitio FTP seguro (SFTP) de Bloomberg de su organización una vez al día, convierte el contenido de los mensajes de chat en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a los buzones de Microsoft 365.

Después de almacenar los datos de Instant Bloomberg en los buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como retención por juicio, búsqueda de contenido, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de Instant Bloomberg. Por ejemplo, puede buscar mensajes de chat de Instant Bloomberg mediante la búsqueda de contenido o asociar el buzón que contiene los datos de Instant Bloomberg con un administrador en un caso de eDiscovery avanzado. El uso de un conector Instant Bloomberg para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Información general sobre el archivado de datos de Instant Bloomberg

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de chat de Instant Bloomberg en Microsoft 365. 

![Proceso de importación y archivo de Instant Bloomberg](../media/InstantBloombergDataArchiving.png)

1. Su organización trabaja con Bloomberg para configurar un sitio SFTP de Bloomberg. También trabajará con Bloomberg para configurar Instant Bloomberg para copiar mensajes de chat en su sitio SFTP de Bloomberg.

2. Una vez cada 24 horas, los mensajes de chat de Instant Bloomberg se copian en el sitio SFTP de Bloomberg.

3. El conector Instant Bloomberg que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio SFTP de Bloomberg todos los días y transfiere los mensajes de chat de las 24 horas anteriores a un área segura de Azure Storage en Microsoft Cloud. El conector también convierte el contenido de un chat en formato de mensaje de correo electrónico.

4. El conector importa los elementos del mensaje de chat al buzón de un usuario específico. Se crea una nueva carpeta denominada InstantBloomberg en el buzón del usuario específico y los elementos se importarán en él. Para ello, el conector usa el valor de la *propiedad CorporateEmailAddress.* Cada mensaje de chat contiene esta propiedad, que se rellena con la dirección de correo electrónico de todos los participantes del mensaje de chat. Además de la asignación automática de usuarios mediante el valor de la propiedad *CorporateEmailAddress,* también puede definir una asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación debe contener un UUID de Bloomberg y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de chat, el conector primero buscará el archivo de asignación personalizada. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el UUID de Bloomberg de un usuario, el conector usará la propiedad *CorporateEmailAddress* del elemento de chat. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizada o en la propiedad *CorporateEmailAddress* del elemento de chat, el elemento no se importará.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de Instant Bloomberg son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Suscríbase [a Bloomberg anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Esto es necesario para que pueda iniciar sesión en Bloomberg anywhere para obtener acceso al sitio SFTP de Bloomberg que tiene que configurar y configurar.

- Configurar un sitio sftp de Bloomberg (protocolo de transferencia segura de archivos). Después de trabajar con Bloomberg para configurar el sitio SFTP, los datos de Instant Bloomberg se cargan en el sitio SFTP todos los días. El conector que cree en el paso 2 se conecta a este sitio SFTP y transfiere los datos de chat a los buzones de Microsoft 365. SFTP también cifra los datos de chat de Instant Bloomberg que se envían a los buzones durante el proceso de transferencia.

  Para obtener información sobre Bloomberg SFTP (también denominado *BB-SFTP):*

  - Consulte el documento "Estándares de conectividad SFTP" en [el soporte técnico de Bloomberg.](https://www.bloomberg.com/professional/support/documentation/)

  - Póngase en [contacto con el soporte al cliente de Bloomberg.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

  Después de trabajar con Bloomberg para configurar un sitio SFTP, Bloomberg le proporcionará información después de responder al mensaje de correo electrónico de implementación de Bloomberg. Guarde una copia de la siguiente información. Se usa para configurar un conector en el paso 3.

  - Código firme, que es un identificador de su organización y se usa para iniciar sesión en el sitio sftp de Bloomberg.

  - Contraseña para el sitio sftp de Bloomberg

  - Dirección URL del sitio SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com)

  - Número de puerto para el sitio SFTP de Bloomberg

- El conector Instant Bloomberg puede importar un total de 200 000 elementos en un solo día. Si hay más de 200 000 elementos en el sitio SFTP, ninguno de esos elementos se importará a Microsoft 365.

- El usuario que crea un conector Instant Bloomberg en el paso 3 (y que descarga las claves públicas y la dirección IP en el paso 1) debe tener asignado el rol de importación y exportación de buzones en Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de** datos en el Centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol De importación y exportación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones Crear grupos de [roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Paso 1: Obtener claves públicas SSH y PGP

El primer paso es obtener una copia de las claves públicas del Shell seguro (SSH) y la Privacidad bastante buena (PGP). Estas claves se usan en el paso 2 para configurar el sitio SFTP de Bloomberg para permitir que el conector (que crea en el paso 3) se conecte al sitio SFTP y transfiera los datos de chat de Instant Bloomberg a los buzones de Microsoft 365. También obtendrá una dirección IP en este paso, que usará al configurar el sitio SFTP de Bloomberg.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, **haga clic en Conectores** de datos  >  **Instant Bloomberg**.

2. En la página **de descripción del producto Instant Bloomberg,** haga clic en Agregar **conector**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. En el sitio Agregar credenciales para **Bloomberg SFTP** en el paso 1, haga clic en la tecla **SSH** de descarga, descargue la clave **PGP** y descargue los vínculos de dirección **IP** para guardar una copia de cada archivo en el equipo local. Estos archivos contienen los siguientes elementos que se usan para configurar el sitio SFTP de Bloomberg en el paso 2:

   - Clave pública SSH: esta clave se usa para configurar el Shell seguro (SSH) para habilitar un inicio de sesión remoto seguro cuando el conector se conecta al sitio SFTP de Bloomberg.

   - Clave pública PGP: esta clave se usa para configurar el cifrado de datos que se transfieren desde el sitio SFTP de Bloomberg a Microsoft 365.

   - Dirección IP: el sitio SFTP de Bloomberg está configurado para aceptar una solicitud de conexión solo desde esta dirección IP, que usa el conector Instant Bloomberg que se crea en el paso 3. 

5. Haga **clic en** Cancelar para cerrar el asistente. Volverá a este asistente en el paso 3 para crear el conector.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Paso 2: Configurar el sitio sftp de Bloomberg

El siguiente paso es usar las claves públicas SSH y PGP y la dirección IP que obtuvo en el paso 1 para configurar la autenticación SSH y el cifrado PGP para el sitio SFTP de Bloomberg. Esto permite que el conector Instant Bloomberg que cree en el paso 3 se conecte al sitio SFTP de Bloomberg y transfiera los datos de Instant Bloomberg a Microsoft 365. Debe trabajar con el soporte al cliente de Bloomberg para configurar su sitio sftp de Bloomberg. Póngase [en contacto con el soporte técnico de Bloomberg](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) para obtener ayuda. 

> [!IMPORTANT]
> Bloomberg recomienda adjuntar los tres archivos que descargó en el paso 1 a un mensaje de correo electrónico y enviarlos a su equipo de soporte técnico al trabajar con ellos para configurar el sitio SFTP de Bloomberg.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Paso 3: Crear un conector Instant Bloomberg

El último paso es crear un conector Instant Bloomberg en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio SFTP de Bloomberg y transferir mensajes de chat a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, **haga clic en Conectores** de datos  >  **Instant Bloomberg**.

2. En la página **de descripción del producto Instant Bloomberg,** haga clic en Agregar **conector**

3. En la **página Términos de** servicio, haga clic **en Aceptar.**

4. En la página Agregar credenciales para el sitio SFTP de **Bloomberg,** en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **Siguiente**.

    - **Código firme:** El identificador de su organización que se usa como nombre de usuario para el sitio SFTP de Bloomberg.

    - **Contraseña:** Contraseña para el sitio SFTP de Bloomberg.

    - **DIRECCIÓN URL de SFTP:** La dirección URL del sitio SFTP de Bloomberg (por ejemplo, sftp.bloomberg.com).

    - **Puerto SFTP:** Número de puerto del sitio SFTP de Bloomberg. El conector usa este puerto para conectarse al sitio SFTP.

5. En la **página Seleccionar tipos de datos para importar,** seleccione los tipos de datos necesarios que se importarán aparte de Los **mensajes**

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios y proporcione la asignación de usuarios personalizada según sea necesario.

   > [!NOTE]
   > El conector importa los elementos del mensaje de chat al buzón de un usuario específico. Se crea una nueva **carpeta denominada InstantBloomberg** en el buzón del usuario específico y los elementos se importarán en él. El conector usa el valor de la *propiedad CorporateEmailAddress.* Cada mensaje de chat contiene esta propiedad y la propiedad se rellena con la dirección de correo electrónico de todos los participantes del mensaje de chat. Además de la asignación automática de usuarios mediante el valor de la propiedad *CorporateEmailAddress,* también puede definir la asignación personalizada cargando un archivo de asignación CSV. El archivo de asignación debe contener el UUID de Bloomberg y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de chat, el conector primero buscará el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el UUID de Bloomberg de un usuario, el conector usará la propiedad *CorporateEmailAddress* del elemento de chat. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad *CorporateEmailAddress* del elemento de chat, el elemento no se importará.

7. Haga **clic en Siguiente,** revise la configuración y, a continuación, **haga** clic en Preparar para crear el conector.

8. Vaya a la **página Conectores de** datos para ver el progreso del proceso de importación para el nuevo conector.
