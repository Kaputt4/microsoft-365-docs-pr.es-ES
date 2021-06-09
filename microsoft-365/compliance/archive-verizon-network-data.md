---
title: Configurar un conector para archivar datos de Red Verizon en Microsoft 365
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
description: Los administradores pueden configurar un conector de TeleMessage para importar y archivar datos SMS MMS y de la red de Verizon en Microsoft 365. Esto le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: c72f17c21439827cf0c00e32a427eb1d6fd0c20c
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821396"
---
# <a name="set-up-a-connector-to-archive-verizon-network-data"></a>Configurar un conector para archivar datos de Red De Verizon

Use el conector TeleMessage en el centro de cumplimiento de Microsoft 365 para importar y archivar datos del Servicio de mensajería corta (SMS) y del Servicio de mensajería multimedia (MMS) de Verizon Network. Después de configurar y configurar un conector, se conecta a la red de Verizon de la organización una vez al día e importa SMS y mms a buzones de correo en Microsoft 365.

Después de almacenar los datos del conector de red De Verizon en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, búsqueda de contenido y directivas de retención Microsoft 365 a los datos de Verizon. Por ejemplo, puede buscar en los mensajes SMS y MMS de Verizon mediante búsqueda de contenido o asociar el buzón que contiene datos de Red De Verizon con un administrador en un Advanced eDiscovery caso. El uso de un conector de red de Verizon para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-verizon-network-data"></a>Información general sobre el archivado de datos de Red De Verizon

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Red De Verizon en Microsoft 365.

![Flujo de trabajo de archivado de Red De Verizon](../media/VerizonNetworkConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage y Verizon para configurar un conector de red de Verizon. Para obtener más información, vea [Verizon Network Archiver](https://www.telemessage.com/office365-activation-for-verizon-network-archiver/).

2. Una vez cada 24 horas, los mensajes SMS MMS y de la red Verizon de su organización se copian en el sitio de TeleMessage.

3. El conector de red de Verizon que cree en el centro de cumplimiento de Microsoft 365 se conecta al sitio de TeleMessage todos los días y transfiere los mensajes de SMS y MMS de las 24 horas anteriores a una ubicación Azure Storage segura en la nube de Microsoft. El conector también convierte el contenido de los mensajes SMS MMS a un formato de mensaje de correo electrónico.

4. El conector importa los elementos de comunicación móvil al buzón de un usuario específico. Se crea una nueva carpeta denominada **Verizon SMS/MMS Network Archiver** en el buzón del usuario específico y los elementos se importan a él. El conector realiza esta asignación mediante el valor de la *propiedad Dirección de correo* electrónico del usuario. Cada SMS y mms contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

   Además de la asignación automática  de usuarios mediante el valor de la propiedad Dirección de correo electrónico del usuario, también puede implementar la asignación personalizada cargando un archivo de asignación CSV. Este archivo de asignación contiene el número de teléfono móvil y la dirección Microsoft 365 de correo electrónico correspondiente para los usuarios de la organización. Si habilita la asignación automática de usuarios y la asignación personalizada, por cada elemento de Verizon, el conector primero busca el archivo de asignación personalizado. Si no encuentra un usuario Microsoft 365 válido que corresponda al número de teléfono móvil de un usuario, el conector usará los valores de la propiedad de dirección de correo electrónico del elemento que está intentando importar. Si el conector no encuentra un usuario Microsoft 365 válido en el archivo de asignación personalizado o en la propiedad de dirección de correo electrónico del elemento de Verizon, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

Algunos de los pasos de implementación necesarios para archivar datos de Red De Verizon son externos a Microsoft 365 y deben completarse antes de poder crear un conector en el centro de cumplimiento.

- Ordene [el servicio de archivador de red de Verizon desde TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) y obtenga una cuenta de administración válida para su organización. Deberá iniciar sesión en esta cuenta al crear el conector en el centro de cumplimiento.

- Obtén tu cuenta de Red De Verizon y los detalles de contacto de facturación para que puedas rellenar los formularios de incorporación de TeleMessage y ordenar el servicio de archivado de mensajes de Verizon.

- Registrar todos los usuarios que requieren el archivado SMS y MMS de Verizon en la cuenta de TeleMessage. Al registrar usuarios, asegúrese de usar la misma dirección de correo electrónico que se usa para su Microsoft 365 usuario.

- Sus empleados deben tener teléfonos móviles corporativos y de responsabilidad corporativa en la red móvil de Verizon. El archivado de mensajes Microsoft 365 no está disponible para dispositivos de propiedad de los empleados o Bring Your Own Devices (BYOD).

- Al usuario que crea un conector de red de Verizon se le debe asignar el rol De importación de buzones de Exchange Online. Esto es necesario para agregar conectores en la **página Conectores de datos** del centro de Microsoft 365 cumplimiento. Este rol no está asignado a ningún grupo de roles de Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

- Este conector de datos está disponible en GCC entornos en la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-verizon-network-connector"></a>Crear un conector de red de Verizon

Después de completar los requisitos previos descritos en la sección anterior, puede crear el conector de red de Verizon en el centro de Microsoft 365 cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir mensajes de SMS MMS a los cuadros de buzón de usuario correspondientes en Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y, a continuación, haga clic **en Conectores de datos** de Verizon  >  **Network**.

2. En la página Descripción del producto de **Red De Verizon,** haga clic **en Agregar conector**

3. En la **página Términos de** servicio, haga clic **en Aceptar**.

4. En la **página Iniciar sesión en TeleMessage,** en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.
  
   - **Nombre de usuario:** Su nombre de usuario de TeleMessage.

   - **Contraseña:** Su contraseña de TeleMessage.

5. Después de crear el conector, puede cerrar la ventana emergente y pasar a la página siguiente.

6. En la **página Asignación de** usuarios, habilite la asignación automática de usuarios y haga clic **en Siguiente**. En caso de que necesite una asignación personalizada, cargue un archivo CSV y haga clic en **Siguiente**.

7. Revise la configuración y, a continuación, haga clic **en Finalizar** para crear el conector.

8. Vaya a la pestaña Conectores de la **página Conectores de** datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.