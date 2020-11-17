---
title: Configurar un conector para archivar datos de WhatsApp en Microsoft 365
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
description: Los administradores pueden configurar un conector de Telemensaje para importar y archivar datos de WhatsApp en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: 2600356fc2628d5832f93f7dbe4fc247d8812410
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087187"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Configurar un conector para archivar datos de WhatsApp

Use el conector de Telemensaje en el centro de cumplimiento de Microsoft 365 para importar y archivar llamadas de WhatsApp, chats, datos adjuntos, archivos y mensajes eliminados. Una vez que haya instalado y configurado un conector, se conectará a la cuenta de mensajes de su organización una vez al día e importará la comunicación móvil de los empleados mediante el WhatsApp Phone Archiver o telemessage WhatsApp Cloud Archiver a los buzones de Microsoft 365.

Una vez que los datos de WhatsApp se almacenan en buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de WhatsApp. Por ejemplo, puede buscar mensajes de WhatsApp mediante la búsqueda de contenido o asociar el buzón que contiene los mensajes de WhatsApp con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector de WhatsApp para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-whatsapp-data"></a>Información general sobre el archivado de datos de WhatsApp

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de WhatsApp en Microsoft 365.

![Flujo de trabajo de archivado de WhatsApp](../media/WhatsAppConnectorWorkflow.png)

1. Su organización trabaja con Telemensaje para configurar un conector de WhatsApp Archiver. Para obtener más información, consulte [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. Una vez cada 24 horas, los datos de WhatsApp de su organización se copian en el sitio de Telemensaje.

3. El conector WhatsApp que se crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Telemensaje cada día y transfiere datos de WhatsApp de las 24 horas anteriores a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte el contenido WhatsApp datos en un formato de mensaje de correo electrónico.

4. El conector importa los datos de WhatsApp al buzón de un usuario específico. Se crea una nueva carpeta llamada **WhatsApp Archiver** en el buzón de correo del usuario específico y los elementos se importan a ella. El conector realiza esta asignación mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* . Cada mensaje de WhatsApp contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* , también puede implementar una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico de Microsoft 365 correspondiente a los usuarios de su organización. Si habilita la asignación automática de usuarios y la asignación personalizada, para cada elemento de WhatsApp, el conector examina primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de teléfono móvil de un usuario, el conector usará los valores de la propiedad dirección de correo electrónico del elemento que intenta importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento WhatsApp, no se importará el elemento.

## <a name="before-you-begin"></a>Antes de empezar

Algunos de los pasos de implementación necesarios para archivar datos de comunicación de WhatsApp son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Solicite el [servicio de WhatsApp Archiver desde telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta cuando cree el conector en el centro de cumplimiento.

- Registre todos los usuarios que requieran el archivado de WhatsApp en la cuenta de Telemensaje. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Instale la aplicación telemessage [WhatsApp Phone Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) en los teléfonos móviles de sus empleados y actívelo. Como alternativa, puede instalar las aplicaciones empresariales normales de WhatsApp o WhatsApp en los teléfonos móviles de sus empleados y activar el servicio de WhatsApp Cloud Archiver examinando un código QR en el sitio web de Telemensaje. Para obtener más información, consulte [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Tendrá que proporcionar este consentimiento cuando cree el conector. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de Microsoft 365 global admin y, a continuación, acepte la solicitud. Debe completar este paso para poder crear correctamente Verizon Network Connector.

- El usuario que crea un conector de Verizon Network Connector debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para agregar conectores en la página **conectores de datos** en el centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="create-a-whatsapp-archiver-connector"></a>Crear un conector de WhatsApp Archiver

Una vez que haya completado los requisitos previos descritos en la sección anterior, puede crear el conector de WhatsApp en el centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de Telemensaje y transferir los datos de WhatsApp a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y haga clic en **Data Connectors**  >  **WhatsApp Archiver**.

2. En la página Descripción de producto de **WhatsApp Archiver** , haga clic en **Agregar conector** .

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **iniciar sesión en Telemensaje** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

   - **Nombre de usuario:** El nombre de usuario de Telemensaje.

   - **Contraseña:** La contraseña de Telemensaje.

5. Una vez creado el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la página **asignación de usuarios** , habilite la asignación automática de usuarios y haga clic en **siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **siguiente**.

7. Proporcione el consentimiento del administrador y haga clic en **siguiente**.

   Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Office 365 y, a continuación, aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) e iniciar sesión con las credenciales de administrador global para aceptar la solicitud.

8. Revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

9. Vaya a la ficha conectores en la página **conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
