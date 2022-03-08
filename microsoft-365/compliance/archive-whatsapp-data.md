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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos de WhatsApp en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: b94d22b787e88de241bee404774caaabf5ac02ca
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313235"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Configurar un conector para archivar datos de WhatsApp

Use el conector de TeleMessage en el Centro de cumplimiento de Microsoft 365 importar y archivar llamadas de WhatsApp, chats, datos adjuntos, archivos y mensajes eliminados. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de la organización una vez al día e importa la comunicación móvil de los empleados mediante el Archivador de WhatsApp Teléfono de TeleMessage o el Archivador en la nube de WhatsApp de TeleMessage a los buzones de correo de Microsoft 365.

Una vez que los datos de WhatsApp se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido y directivas de retención Microsoft 365 a los datos de WhatsApp. Por ejemplo, puede buscar mensajes de WhatsApp mediante la búsqueda de contenido o asociar el buzón que contiene mensajes de WhatsApp con un custodio en un Advanced eDiscovery caso. El uso de un conector de WhatsApp para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-whatsapp-data"></a>Información general sobre el archivado de datos de WhatsApp

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de WhatsApp en Microsoft 365.

![Flujo de trabajo de archivado de WhatsApp.](../media/WhatsAppConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage para configurar un conector de archivador de WhatsApp. Para obtener más información, [consulta WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. En tiempo real, los datos de WhatsApp de la organización se copian en el sitio de TeleMessage.

3. El conector de WhatsApp que cree en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los datos de WhatsApp de las 24 horas anteriores a una ubicación Azure Storage segura en la nube de Microsoft. El conector también convierte los datos de WhatsApp de contenido en un formato de mensaje de correo electrónico.

4. El conector importa datos de WhatsApp al buzón de un usuario específico. Se crea una nueva carpeta denominada **WhatsApp Archiver** en el buzón del usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la *propiedad Dirección de correo electrónico del* usuario. Cada mensaje de WhatsApp contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor  de la propiedad Dirección de correo electrónico del usuario, también puede implementar la asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección Microsoft 365 de correo electrónico correspondiente para los usuarios de la organización. Si habilita la asignación automática de usuarios y la asignación personalizada, por cada elemento de WhatsApp, el conector primero mira el archivo de asignación personalizado. Si no encuentra un usuario de Microsoft 365 válido que corresponda al número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que está intentando importar. Si el conector no encuentra un usuario Microsoft 365 válido en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento de WhatsApp, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar los datos de comunicación de WhatsApp son externos a Microsoft 365 y deben completarse antes de poder crear el conector en el centro de cumplimiento.

- Ordene [el servicio archiver de WhatsApp desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Registrar todos los usuarios que requieren archivado de WhatsApp en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta Microsoft 365 usuario.

- Instala la aplicación [Teléfono Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) de TeleMessage en los teléfonos móviles de tus empleados y actívala. Como alternativa, puedes instalar las aplicaciones regulares de WhatsApp o WhatsApp Empresa en los teléfonos móviles de tus empleados y activar el servicio WhatsApp Cloud Archiver mediante el examen de un código QR en el sitio web de TeleMessage. Para obtener más información, [consulta WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- El usuario que crea un conector de red de Verizon debe tener asignado el rol de administrador de Conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de TeleMessage está disponible en GCC entornos en la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-whatsapp-archiver-connector"></a>Crear un conector de Archivador de WhatsApp

Después de completar los requisitos previos descritos en la sección anterior, puede crear el conector de WhatsApp en el Centro de cumplimiento de Microsoft 365. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir los datos de WhatsApp a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, haga clic en **Conectores de** **datosWhatsApp** >  Archiver.

2. En la página **descripción del producto Archiver de WhatsApp** , haga clic **en Agregar conector**

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. En la **página Iniciar sesión en TeleMessage** , en paso 3, escriba la información necesaria en los siguientes cuadros y, a continuación, haga clic en **Siguiente**.

   - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

   - **Contraseña:** Su contraseña de TeleMessage.

5. Después de crear el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios y haga clic en **Siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **Siguiente**.

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la **página Conectores de** datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
