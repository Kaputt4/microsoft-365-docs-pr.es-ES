---
title: Configurar un conector para archivar datos móviles de Android
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
description: Los administradores pueden configurar un conector de Telemensaje para importar y archivar llamadas SMS, MMS y de voz desde teléfonos móviles Android. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: 35ff69ec3b8f0af5ed86350862bb7b0917a98909
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200265"
---
# <a name="set-up-a-connector-to-archive-android-mobile-data"></a>Configurar un conector para archivar datos móviles de Android

Use un conector de teleservicio en el centro de cumplimiento de Microsoft 365 para importar y archivar llamadas SMS, MMS, de voz y registros de llamadas desde teléfonos móviles Android. Una vez que haya instalado y configurado un conector, se conectará a la cuenta de mensajes de su organización una vez al día e importará la comunicación móvil de los empleados mediante el Telemensaje Android Archiver a los buzones de correo de Microsoft 365.

Una vez que los datos de los teléfonos móviles Android se almacenan en los buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de Android Archiver. Por ejemplo, puede buscar comunicaciones móviles de Android Archiver mediante la búsqueda de contenido o asociar el buzón que contiene los datos del conector de Android Archiver con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector de Android Archiver para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-android-mobile-data"></a>Información general sobre el archivado de datos móviles de Android

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos móviles de Android en Microsoft 365.

![Flujo de trabajo de conector de Android Archiver](../media/AndroidArchiverConnectorWorkflow.png)

1. La organización trabaja con Telemensaje para configurar un conector de Android Archiver. Para obtener más información, consulte [Android Archiver](https://www.telemessage.com/office365-activation-for-android-archiver/).

2. Una vez cada 24 horas, SMS, MMS, llamadas de voz y registros de llamadas de los teléfonos móviles Android de la organización se copian en el sitio de Telemensaje.

3. El conector de Android Archiver que ha creado en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Telemensaje todos los días y transfiere los datos de Android de las 24 horas anteriores a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte los datos de Android en un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se creará una nueva carpeta denominada Android Archiver en el buzón de correo del usuario específico y se importarán los elementos en ella. El conector se asigna mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* . Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática de usuarios mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* , también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación debe contener el número de teléfono móvil del usuario y la dirección de buzón de correo de Microsoft 365 correspondiente a cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de correo electrónico el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que corresponda a un número de móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de *dirección de correo electrónico del usuario* del elemento de correo electrónico, no se importará el elemento.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de comunicación de Android son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Solicite el [servicio de Android Archiver desde telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta cuando cree el conector.

- Registre todos los usuarios que requieran el servicio de Android Archiver en la cuenta de Telemensaje. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Instale y active la aplicación telemessage Android Archiver en los teléfonos móviles de sus empleados.

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Tendrá que proporcionar este consentimiento cuando cree el conector. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de Microsoft 365 global admin y, a continuación, acepte la solicitud. Debe completar este paso para poder crear correctamente un conector de red en&T.

- El usuario que crea un conector de Android Archiver debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para agregar conectores en la página **conectores de datos** en el centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="create-an-android-archiver-connector"></a>Crear un conector de Android Archiver

El último paso consiste en crear un conector de Android Archiver en el centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de Telemensaje y transferir la comunicación de Android a los cuadros del buzón de usuario correspondiente en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **conectores de datos**  >  **Android Archiver**.

2. En la página Descripción de producto de **Android Archiver** , haga clic en **Agregar conector**.

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **iniciar sesión en Telemensaje** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

   - **Nombre de usuario:** El nombre de usuario de Telemensaje.

   - **Contraseña:** La contraseña de Telemensaje.

5. Una vez creado el conector, cierre la ventana emergente y haga clic en **siguiente**.

6. En la página **asignación de usuarios** , habilite la asignación automática de usuarios y haga clic en **siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **siguiente**.

7. Proporcione el consentimiento del administrador y haga clic en **siguiente**.

   Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Office 365 y, a continuación, aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

8. Revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

9. Vaya a la ficha conectores en la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
