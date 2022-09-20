---
title: Configuración de un conector para archivar datos de WeChat en Microsoft 365
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
ms.collection: M365-security-compliance
description: Configure y use un conector en el portal de cumplimiento Microsoft Purview para importar y archivar datos de WeChat en Microsoft 365.
ms.openlocfilehash: 50a508fa13cb3e51314354a6a8cc2d1033d8422c
ms.sourcegitcommit: 433f5b448a0149fcf462996bc5c9b45d17bd46c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2022
ms.locfileid: "67820777"
---
# <a name="set-up-a-connector-to-archive-wechat-data"></a>Configuración de un conector para archivar datos de WeChat

Use el conector TeleMessage en el portal de cumplimiento Microsoft Purview para importar y archivar llamadas a WeChat y WeCom, chats, datos adjuntos, archivos y mensajes recuperados. Después de configurar y configurar un conector, se conecta a la cuenta de TeleMessage de su organización e importa la comunicación móvil de los empleados que usan El archivador de WeChat de TeleMessage a buzones de Microsoft 365.

Una vez que los datos del conector de WeChat Archiver se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview como suspensión por juicio, exhibición electrónica, archivado de In-Place, auditoría, cumplimiento de comunicaciones y directivas de retención de Microsoft 365 a los datos de comunicación de WeChat. Por ejemplo, puede buscar la comunicación de WeChat mediante búsqueda de contenido o asociar el buzón que contiene los datos del conector de WeChat Archiver con un custodio en un caso de eDiscovery (Premium). El uso de un conector de WeChat Archiver para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las normas de gobernanza corporativa y las directivas reglamentarias.

## <a name="overview-of-archiving-wechat-communication-data"></a>Información general sobre el archivado de datos de comunicación de WeChat

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de comunicaciones de WeChat en Microsoft 365.

![Flujo de trabajo de archivado de datos de WeChat Archiver.](../media/WeChatConnectorWorkflow.png)

1. Su organización trabaja con TeleMessage para configurar un conector de WeChat Archiver.

2. En tiempo real, los datos de WeChat de su organización se copian en el sitio de TeleMessage.

3. El conector de WeChat Archiver que se crea en el portal de cumplimiento se conecta al sitio de TeleMessage todos los días y transfiere los mensajes de correo electrónico de las 24 horas anteriores a un área de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos de comunicación móviles al buzón de un usuario específico. Se creará una nueva carpeta denominada WeChat Archiver en el buzón de correo del usuario específico y los elementos se importarán en él. El conector realiza la asignación mediante el valor de la propiedad de *dirección Email del usuario*. Cada mensaje de correo electrónico contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje de correo electrónico. Además de la asignación automática de usuarios mediante el valor de la propiedad de *dirección Email del usuario*, también puede definir una asignación personalizada mediante la carga de un archivo de asignación CSV. Este archivo de asignación debe contener el número de móvil del usuario y la dirección de buzón de Microsoft 365 correspondiente para cada usuario. Si habilita la asignación automática de usuarios y proporciona una asignación personalizada, para cada elemento de correo electrónico, el conector examinará primero el archivo de asignación personalizado. Si no encuentra un usuario válido de Microsoft 365 que se corresponda con el número de móvil de un usuario, el conector usará la propiedad de dirección de correo electrónico del usuario del elemento de correo electrónico. Si el conector no encuentra un usuario válido de Microsoft 365 en el archivo de asignación personalizado o en la propiedad *de dirección de correo electrónico del usuario* del elemento de correo electrónico, el elemento no se importará.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Trabaje con TeleMessage para configurar un conector de archivo de WeChat. Para obtener más información, consulte [Activación del archivador de WeChat de TeleMessage para Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-wechat-archiver/).

- Configure un conector de TeleMessage para Microsoft 365 y obtenga una cuenta de administración de empresa válida. Para obtener más información, vea [Ordenar archivado de Microsoft 365 Mobile](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-microsoft-365/).

- Registre todos los usuarios que requieran el archivado de WeChat en la cuenta de TeleMessage con la misma dirección de correo electrónico que se usa para la cuenta de Microsoft 365 del usuario.

- Tendrá que instalar la aplicación Tencent WeCom en los teléfonos móviles de los usuarios de su organización y activarla. La aplicación WeCom permite a los usuarios comunicarse y chatear con otros usuarios de WeChat y WeCom.

- Al usuario que crea un conector de WeChat Archiver en el portal de cumplimiento se le debe asignar el rol Administración Conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administración conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de TeleMessage está disponible en entornos GCC en la nube de Microsoft 365 US Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="create-a-wechat-archiver-connector"></a>Creación de un conector de WeChat Archiver

Siga los pasos de esta sección para crear un conector de WeChat Archiver en el portal de cumplimiento. El conector usa la información que proporciona para conectarse al sitio de TeleMessage y transferir datos de comunicaciones de WeChat a los buzones de usuario correspondientes de Microsoft 365.

1. Vaya a y, a <https://compliance.microsoft.com> continuación, haga clic en **Conectores** >  de datos **De WeChat Archiver**.

2. En la página de descripción del producto **WeChat Archiver** , haga clic en **Agregar conector.**

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. En la página **Iniciar sesión en TeleMessage** , en el paso 3, escriba la información necesaria en los cuadros siguientes y, a continuación, haga clic en **Siguiente**.

    - **Nombre de usuario**: nombre de usuario de TeleMessage.

    - **Contraseña**: la contraseña de TeleMessage.

5. Una vez creado el conector, puede cerrar la ventana emergente para ir a la página siguiente.

6. En la página **Asignación de** usuarios, habilite la asignación automática de usuarios. También puede cargar un archivo CSV de asignación de usuario personalizado.

7. Haga clic en **Siguiente**, revise la configuración y, a continuación, haga clic en **Finalizar** para crear el conector.

8. Vaya a la pestaña **Conectores** de la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
