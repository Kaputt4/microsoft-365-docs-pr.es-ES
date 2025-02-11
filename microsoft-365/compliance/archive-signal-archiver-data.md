---
title: Configuración de un conector para archivar datos de comunicaciones de Signal en Microsoft 365
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos de comunicaciones de Signal en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: a5530e1d6d94978b4b49fd54c25ef476cdd39641
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68813583"
---
# <a name="set-up-a-connector-to-archive-signal-communications-data"></a>Configuración de un conector para archivar datos de comunicaciones de Signal

Use el conector TeleMessage en el portal de cumplimiento Microsoft Purview para importar y archivar chats, datos adjuntos, archivos y mensajes y llamadas eliminados de Signal. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de su organización e importa la comunicación móvil de los empleados que usan TeleMessage Signal Archiver a buzones de Correo de Microsoft 365.

Una vez que los datos del conector de Signal Archiver se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview, como la suspensión por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365, a los datos de comunicaciones de Signal. Por ejemplo, puede buscar la comunicación de Signal mediante búsqueda de contenido o asociar el buzón que contiene los datos del conector de Signal Archiver con un custodio en un caso de exhibición de documentos electrónicos (Premium). El uso de un conector de Signal Archiver para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las normas de gobernanza corporativa y las directivas reglamentarias.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-signal-communications-data"></a>Introducción al archivado de datos de comunicaciones de Signal

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de comunicación de Signal en Microsoft 365.

![Flujo de trabajo de archivado de comunicaciones de señales.](../media/SignalConnectorWorkflow.png)

1. Su organización funciona con TeleMessage para configurar un conector de Signal Archiver. Para obtener más información, consulte [Activación del archivador de señales de TeleMessage para Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/).

2. En tiempo real, los datos de Signal de su organización se copian en el sitio de TeleMessage.

3. El conector de Signal Archiver que se crea en el portal de cumplimiento se conecta al sitio TeleMessage todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos de comunicación móviles al buzón de un usuario específico. Se creará una nueva carpeta denominada Signal Archiver en el buzón de correo del usuario específico y los elementos se importarán en él. El conector realiza la asignación mediante el valor de la propiedad de *dirección Email del usuario*. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico.

   Además de la asignación automática de usuarios mediante el valor de la propiedad de *dirección Email del usuario*, también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación debe contener el número de móvil del usuario y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de correo electrónico, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad *de dirección de correo electrónico del usuario* del elemento de correo electrónico, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Solicite el [servicio Signal Archiver de TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Registre todos los usuarios que requieran el archivado de Signal en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Instale la aplicación Signal Archiver en los teléfonos móviles de sus empleados y actívela. La aplicación Signal Archiver les permite comunicarse y chatear con otros usuarios de Signal.

- Al usuario que crea un conector de Signal Archiver en el paso 3 se le debe asignar el rol de Administración conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de TeleMessage está disponible en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-signal-archiver-connector"></a>Creación de un conector de Signal Archiver

Después de completar los requisitos previos descritos en la sección anterior, puede crear el conector de Signal Archiver en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transfiere los datos de comunicaciones de Signal a los cuadros de buzón de usuario correspondientes de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y seleccione **Conectores** >  de datos **Signal Archiver**.

2. En la página de descripción **del producto Signal Archiver** , seleccione **Agregar conector.**

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. En la página **Iniciar sesión en TeleMessage** , en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, seleccione **Siguiente**.

    - **Nombre de usuario:** Nombre de usuario de TeleMessage.

    - **Contraseña:** La contraseña de TeleMessage.

5. Una vez creado el conector, puede cerrar la ventana emergente y ir a la página siguiente.

6. En la página **Asignación de** usuarios, habilite la asignación automática de usuarios. Para habilitar la asignación personalizada, cargue un archivo CSV que contenga la información de asignación de usuario y, a continuación, seleccione **Siguiente**.

7. Revise la configuración y, a continuación, seleccione **Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
