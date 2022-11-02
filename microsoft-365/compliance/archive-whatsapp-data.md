---
title: Configuración de un conector para archivar datos de WhatsApp en Microsoft 365
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos de WhatsApp en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
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
ms.openlocfilehash: dd22187a4c3cd34b0a2291064a3a49bec998dd08
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68813314"
---
# <a name="set-up-a-connector-to-archive-whatsapp-data"></a>Configuración de un conector para archivar datos de WhatsApp

Use el conector TeleMessage en el portal de cumplimiento Microsoft Purview para importar y archivar llamadas de WhatsApp, chats, datos adjuntos, archivos y mensajes eliminados. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de su organización una vez al día e importa la comunicación móvil de los empleados mediante TeleMessage WhatsApp Phone Archiver o TeleMessage WhatsApp Cloud Archiver a buzones de Microsoft 365.

Una vez que los datos de WhatsApp se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como la suspensión por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de WhatsApp. Por ejemplo, puede buscar mensajes de WhatsApp mediante búsqueda de contenido o asociar el buzón que contiene mensajes de WhatsApp con un custodio en un caso de exhibición de documentos electrónicos (Premium). El uso de un conector de WhatsApp para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-whatsapp-data"></a>Introducción al archivado de datos de WhatsApp

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de WhatsApp en Microsoft 365.

![Flujo de trabajo de archivado de WhatsApp.](../media/WhatsAppConnectorWorkflow.png)

1. Su organización funciona con TeleMessage para configurar un conector de WhatsApp Archiver. Para obtener más información, vea [WhatsApp Archiver](https://www.telemessage.com/office365-activation-for-whatsapp-archiver).

2. En tiempo real, los datos de WhatsApp de la organización se copian en el sitio de TeleMessage.

3. El conector de WhatsApp que se crea en el portal de cumplimiento se conecta al sitio de TeleMessage todos los días y transfiere los datos de WhatsApp de las 24 horas anteriores a una ubicación segura de Azure Storage en la nube de Microsoft. El conector también convierte los datos de WhatsApp de contenido en un formato de mensaje de correo electrónico.

4. El conector importa los datos de WhatsApp al buzón de un usuario específico. Se crea una nueva carpeta denominada **WhatsApp Archiver** en el buzón de correo del usuario específico y los elementos se importan en él. El conector realiza esta asignación mediante el valor de la propiedad de *dirección Email del usuario*. Cada mensaje de WhatsApp contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor de la propiedad de *dirección Email del usuario*, también puede implementar la asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico de Microsoft 365 correspondiente para los usuarios de su organización. Si habilita la asignación automática de usuarios y la asignación personalizada, para cada elemento de WhatsApp, el conector primero examina el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que intenta importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento WhatsApp, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar los datos de comunicación de WhatsApp son externos a Microsoft 365 y deben completarse para poder crear el conector en el centro de cumplimiento.

- Solicite el [servicio WhatsApp Archiver de TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Registre todos los usuarios que requieran el archivado de WhatsApp en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Instala la aplicación TeleMessage [WhatsApp Phone Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-phone-archiver-2/) en los teléfonos móviles de tus empleados y actívela. Como alternativa, puede instalar las aplicaciones habituales de WhatsApp o WhatsApp Business en los teléfonos móviles de sus empleados y activar el servicio WhatsApp Cloud Archiver escaneando un código QR en el sitio web de TeleMessage. Para obtener más información, consulte [WhatsApp Cloud Archiver](https://www.telemessage.com/mobile-archiver/whatsapp-archiver/whatsapp-cloud-archiver/).

- Al usuario que crea un conector de Verizon Network se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de TeleMessage está disponible en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-whatsapp-archiver-connector"></a>Creación de un conector de WhatsApp Archiver

Después de completar los requisitos previos descritos en la sección anterior, puede crear el conector de WhatsApp en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir los datos de WhatsApp a los cuadros de buzón de usuario correspondientes de Microsoft 365.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, seleccione **Conectores** >  de datos **WhatsApp Archiver**.

2. En la página de descripción del producto **WhatsApp Archiver**, seleccione **Agregar conector**.

3. En la página **Términos de servicio** , seleccione **Aceptar**.

4. En la página **Iniciar sesión en TeleMessage** , en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, seleccione **Siguiente**.

   - **Nombre de usuario:** Nombre de usuario de TeleMessage.

   - **Contraseña:** La contraseña de TeleMessage.

5. Una vez creado el conector, puede cerrar la ventana emergente y ir a la página siguiente.

6. En la página **Asignación de** usuarios, habilite la asignación automática de usuarios y seleccione **Siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y seleccione **Siguiente**.

7. Revise la configuración y, a continuación, seleccione **Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
