---
title: Configuración de un conector para archivar datos de red SMS/MMS de Bell
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
description: Los administradores pueden configurar un conector TeleMessage para importar y archivar datos SMS y MMS desde Bell Network. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 5d1b44df9a343020419d684c9a91a982a0f0df57
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2022
ms.locfileid: "65095086"
---
# <a name="set-up-a-connector-to-archive-bell-network-data"></a>Configuración de un conector para archivar datos de Bell Network

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Use un conector de TeleMessage en el portal de cumplimiento de Microsoft Purview para importar y archivar mensajes de Servicio de mensajería breve (SMS) y Servicio de mensajería multimedia (MMS) de Bell Network. Después de configurar y configurar un conector, se conecta a bell network de la organización una vez al día e importa mensajes SMS y MMS a buzones de Microsoft 365.

Una vez que los mensajes SMS y MMS se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como la suspensión por juicio, la búsqueda de contenido y las directivas de retención de Microsoft 365 a los datos de Bell Network. Por ejemplo, puede buscar SMS/MMS de Bell Network mediante Búsqueda de contenido o asociar el buzón que contiene los datos del conector de Bell Network con un custodio en un caso de eDiscovery (Premium). El uso de un conector de Bell Network para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-bell-network-data"></a>Información general sobre el archivado de datos de Bell Network

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de Bell Network en Microsoft 365.

![Flujo de trabajo de archivado de Bell Network.](../media/BellNetworkConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage y Bell para configurar un conector de Bell Network. Para obtener más información, consulte [Bell Network Archiver](https://www.telemessage.com/office365-activation-for-bell-network-archiver).

2. En tiempo real, los mensajes SMS y MMS de bell network de su organización se copian en el sitio de TeleMessage.

3. El conector de Bell Network que se crea en el portal de cumplimiento se conecta al sitio de TeleMessage todos los días y transfiere los mensajes SMS y MMS de las 24 horas anteriores a una ubicación de Azure Storage segura en la nube de Microsoft. El conector también convierte el contenido de los mensajes SMS y MMS en un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móviles al buzón de correo de usuarios específicos. Se crea una nueva carpeta denominada **Bell SMS/MMS Network Archiver** en el buzón de un usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la propiedad Dirección *de correo electrónico del usuario* . Cada mensaje SMS y MMS contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática de usuarios mediante el valor de la propiedad Dirección *de correo electrónico del usuario* , también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección de correo electrónico Microsoft 365 correspondiente para los usuarios de la organización. Si habilita tanto la asignación automática de usuarios como la asignación personalizada, para cada elemento de Bell Network, el conector primero examina el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que se corresponda con el número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que intenta importar. Si el conector no encuentra un usuario Microsoft 365 válido en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento Bell Network, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar los datos de Bell Network son externos a Microsoft 365 y deben completarse para poder crear un conector en el centro de cumplimiento.

- Solicite el [servicio Bell Network Archiver desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) y obtenga una cuenta de administración válida para su organización. Tendrá que iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Obtenga su cuenta de Bell Network y los detalles de contacto de facturación para que pueda rellenar los formularios de incorporación de TeleMessage y solicitar el servicio de archivado de mensajes de Bell.

- Registre todos los usuarios que requieran el archivado de Bell SMS/MMS Network en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su cuenta de Microsoft 365.

- Sus empleados deben tener teléfonos móviles corporativos y corporativos responsables en la red móvil de Bell. El archivado de mensajes en Microsoft 365 no está disponible para dispositivos propiedad de los empleados o "Traiga sus propios dispositivos (BYOD).

- Al usuario que crea un conector de Bell Network se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de TeleMessage está disponible en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-bell-network-connector"></a>Creación de un conector de Bell Network

El último paso es crear un conector de Bell Network en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes SMS/MMS a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com) continuación, haga clic en **Conectores** >  de **datosBell SMS/MMS Network Archiver**.

2. En la página de descripción **del producto Bell Network** , haga clic en **Agregar conector.**

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. En la página **Iniciar sesión en TeleMessage** , en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.

   - **Nombre de usuario:** Nombre de usuario de TeleMessage.

   - **Contraseña:** La contraseña de TeleMessage.

5. Una vez creado el conector, puede cerrar la ventana emergente y ir a la página siguiente.

6. En la página **Asignación de** usuarios, habilite la asignación automática de usuarios. Para habilitar la asignación personalizada, cargue un archivo CSV que contenga la información de asignación de usuarios y, a continuación, haga clic en **Siguiente**.

7. Revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

8. Vaya a la pestaña **Conectores** de la página **Conectores de datos** del centro de cumplimiento para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
