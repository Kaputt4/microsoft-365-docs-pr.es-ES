---
title: Configuración de un conector para archivar datos de O2 Network en Microsoft 365
description: Los administradores pueden configurar un conector TeleMessage para importar y archivar datos DE SMS y MMS desde la red móvil de O2 en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 04/06/2022
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- tier3
- purview-compliance
- data-connectors
ms.openlocfilehash: 949f9c9bd479c8ac22702ed3cbbf1b2429343128
ms.sourcegitcommit: ab45f2963e0635ff2cb9670f6f7b4c784f6a250e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/02/2022
ms.locfileid: "68812756"
---
# <a name="set-up-a-connector-to-archive-o2-network-data"></a>Configuración de un conector para archivar datos de red de O2

Use un conector TeleMessage en el portal de cumplimiento Microsoft Purview para importar y archivar mensajes de Servicio de mensajería breve (SMS) y llamadas de voz desde la red móvil de O2. Después de configurar y configurar un conector, se conecta a la red de O2 de su organización una vez al día e importa sms y llamadas de voz a buzones de Correo de Microsoft 365.

Después de almacenar mensajes SMS y llamadas de voz en buzones de usuario, puede aplicar características de Microsoft Purview como la suspensión por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de red de O2. Por ejemplo, puede buscar mensajes SMS de red de O2 y llamadas de voz mediante búsqueda de contenido o asociar el buzón de correo que contiene datos de red de O2 con un custodio en un caso de eDiscovery (Premium). El uso de un conector de red de O2 para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

[!INCLUDE [purview-preview](../includes/purview-preview.md)]

## <a name="overview-of-archiving-o2-network-data"></a>Información general sobre el archivado de datos de red de O2

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de O2 Network en Microsoft 365.

![Flujo de trabajo de archivado de red de O2.](../media/O2NetworkConnectorWorkflow.png)

1. Su organización funciona con TeleMessage y O2 para configurar un conector de red de O2. Para obtener más información, consulte [Archivor de red de O2](https://www.telemessage.com/office365-activation-for-o2-network-archiver).

2. Una vez cada 24 horas, los mensajes SMS y las llamadas de voz de la red O2 de su organización se copian en el sitio de TeleMessage.

3. El conector de red de O2 que se crea en el portal de cumplimiento se conecta al sitio de TeleMessage todos los días y transfiere los mensajes SMS y las llamadas de voz de las 24 horas anteriores a una ubicación segura de Azure Storage en la nube de Microsoft. El conector también convierte el contenido de mensajes SMS y llamadas de voz a un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móviles al buzón de correo de usuarios específicos. Se crea una nueva carpeta denominada **O2 SMS y Voice Network Archiver** en el buzón de un usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la propiedad de *dirección Email del usuario*. Cada mensaje SMS y llamada de voz contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor de la propiedad de *dirección Email del usuario*, también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico de Microsoft 365 correspondiente para los usuarios de su organización. Si habilita tanto la asignación automática de usuarios como la asignación personalizada, para cada elemento de O2, el conector primero examina el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que intenta importar. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento O2, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar los datos de red de O2 son externos a Microsoft 365 y deben completarse para poder crear un conector en el centro de cumplimiento.

- Solicite el [servicio O2 Network Archiver de TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Obtenga la cuenta de red de O2 y los detalles de contacto de facturación para que pueda rellenar los formularios de incorporación de TeleMessage y solicitar el servicio de archivado de mensajes desde O2.

- Registre todos los usuarios que requieran el archivado de SMS y voice network de O2 en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Los empleados deben tener teléfonos móviles corporativos y corporativos responsables en la red móvil de O2. El archivado de mensajes en Microsoft 365 no está disponible para dispositivos propiedad de los empleados o "Traiga sus propios dispositivos (BYOD).

- Al usuario que crea un conector de red de O2 se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los portales de defender y cumplimiento" de [Roles y grupos de roles en los portales de cumplimiento de Microsoft 365 Defender y Microsoft Purview](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-defender-and-compliance-portals). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de TeleMessage está disponible en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-an-o2-network-connector"></a>Creación de un conector de red de O2

Después de completar los requisitos previos descritos en la sección anterior, puede crear un conector de red de O2 en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes SMS y llamadas de voz a los cuadros de buzón de usuario correspondientes de Microsoft 365.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, seleccione **Conectores** \> de datos **O2 Network**.

2. En la página Descripción del producto **de red de O2**, seleccione **Agregar conector**.

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
