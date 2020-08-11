---
title: Configurar un conector para archivar datos de red SMS/MMS de Bell
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
description: Los administradores pueden configurar un conector de Telemensaje para importar y archivar datos de SMS y MMS desde la red Bell. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para poder usar las características de cumplimiento, como la retención legal, la búsqueda de contenido y las directivas de retención, para administrar los datos de terceros de su organización.
ms.openlocfilehash: df89ff9e078ef8439ddc8258de5cf5dfc88c6450
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/10/2020
ms.locfileid: "46602299"
---
# <a name="set-up-a-connector-to-archive-bell-network-data-preview"></a>Configurar un conector para archivar datos de la red de Bell (versión preliminar)

Use un conector de teleservicio en el centro de cumplimiento de Microsoft 365 para importar y archivar mensajes de servicio de mensajería breve (SMS) y servicio de mensajería multimedia (MMS) desde la red Bell. Después de configurar y configurar un conector, se conecta a la red de Bell de la organización una vez al día e importa mensajes SMS y MMS a los buzones de correo de Microsoft 365.

Una vez que los mensajes SMS y MMS se almacenan en buzones de usuario, puede aplicar las características de cumplimiento de Microsoft 365, como la retención por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de red Bell. Por ejemplo, puede buscar en Bell Network SMS/MMS mediante la búsqueda de contenido o asociar el buzón que contiene los datos del conector de red de Bell con un custodio en un caso de exhibición avanzada de documentos electrónicos. El uso de un conector de Bell Network para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y regulatorias.

## <a name="overview-of-archiving-bell-network-data"></a>Información general sobre el archivado de datos de red de Bell

La información general siguiente explica el proceso de uso de un conector para archivar datos de la red de Bell en Microsoft 365.

![Flujo de trabajo de archivo de Bell Network](../media/BellNetworkConnectorWorkflow.png)

1. La organización trabaja con telemessage y Bell para configurar un conector de red Bell. Para obtener más información, consulte [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. Una vez cada 24 horas, los mensajes SMS y MMS de la red de Bell de la organización se copian en el sitio de Telemensaje.

3. El conector de red Bell que crea en el centro de cumplimiento de Microsoft 365 se conecta al sitio de Telemensaje cada día y transfiere los mensajes SMS y MMS de las 24 horas anteriores a una ubicación de almacenamiento seguro de Azure en la nube de Microsoft. El conector también convierte el contenido de los mensajes de SMS y MMS en un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se crea una nueva carpeta denominada **Bell SMS/MMS Network Archiver** en el buzón de un usuario específico y los elementos se importan a ella. El conector realiza esta asignación mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* . Todos los mensajes SMS y MMS contienen esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor de la propiedad de la *dirección de correo electrónico del usuario* , también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico de Microsoft 365 correspondiente a los usuarios de su organización. Si habilita la asignación automática de usuarios y la asignación personalizada, para cada elemento de red Bell, el conector examina primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de teléfono móvil de un usuario, el conector usará los valores de la propiedad dirección de correo electrónico del elemento que intenta importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento de red Bell, no se importará el elemento.

## <a name="before-you-begin"></a>Antes de empezar

Muchos de los pasos de implementación necesarios para archivar datos de la red de Bell son externos a Microsoft 365 y deben completarse antes de poder crear un conector en el centro de cumplimiento.

- Solicite el [servicio Bell Network Archiver desde telemessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta cuando cree el conector en el centro de cumplimiento.

- Obtenga la cuenta de la red de Bell y los detalles de contacto de facturación para poder completar los formularios de incorporación de mensajes y solicitar el servicio de archivado de mensajes de Bell.

- Registre todos los usuarios que requieran el archivado de red Bell SMS/MMS en la cuenta de Telemensaje. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Los empleados deben tener teléfonos móviles que sean responsables de la empresa y de la empresa en la red de Bell Mobile. Los mensajes de archivado en Microsoft 365 no están disponibles para los dispositivos de propiedad del empleado o "traer sus propios dispositivos (BYOD).

- La organización debe permitir que el servicio de importación de Office 365 obtenga acceso a los datos de buzones de la organización. Tendrá que proporcionar este consentimiento cuando cree el conector. Para dar su consentimiento a esta solicitud, vaya a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), inicie sesión con las credenciales de un administrador global de Office 365 y, a continuación, acepte la solicitud. Debe completar este paso para poder crear correctamente un conector de campana de red.

- El usuario que crea un conector de red Bell debe tener asignado el rol importación y exportación de buzones de correo en Exchange Online. Esto es necesario para agregar conectores en la página **conectores de datos** en el centro de cumplimiento de Microsoft 365. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede Agregar el rol importación y exportación de buzones al grupo de funciones de administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol de importación y exportación de buzones de correo y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea las secciones [crear grupos](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) de roles o [modificar grupos de roles](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) en el artículo sobre la administración de grupos de roles en Exchange Online.

## <a name="create-a-bell-network-connector"></a>Crear un conector de red Bell

El último paso consiste en crear un conector de Bell Network en el centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de Telemensaje y transferir los mensajes SMS/MMS a los cuadros de buzón de usuario correspondientes de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic en **Data Connectors**  >  **Bell SMS/MMS Network Archiver**.

2. En la página Descripción de producto de la **red Bell** , haga clic en **Agregar conector** .

3. En la página **condiciones de servicio** , haga clic en **Aceptar**.

4. En la página **iniciar sesión en Telemensaje** , en el paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **siguiente**.

   - **Nombre de usuario:** El nombre de usuario de Telemensaje.

   - **Contraseña:** La contraseña de Telemensaje.

5. Una vez creado el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la página **asignación de usuarios** , habilite la asignación automática de usuarios. Para habilitar la asignación personalizada, cargue un archivo CSV que contenga la información de asignación de usuarios y, a continuación, haga clic en **siguiente**.

7. Proporcione el consentimiento del administrador y haga clic en **siguiente**.

   Para proporcionar el consentimiento del administrador, debe haber iniciado sesión con las credenciales de un administrador global de Office 365 y, a continuación, aceptar la solicitud de consentimiento. Si no ha iniciado sesión como administrador global, puede ir a [esta página](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) y iniciar sesión con credenciales de administrador global para aceptar la solicitud.

8. Revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

9. Vaya a la pestaña **conectores** en la página **conectores de datos** en el centro de cumplimiento para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- El conector no importa ningún elemento de más de 10 MB.
