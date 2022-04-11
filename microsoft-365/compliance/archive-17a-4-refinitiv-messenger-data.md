---
title: Configurar un conector para archivar los datos de Refinitiv Eikon Messenger en Microsoft 365
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
description: Aprenda a configurar y usar un conector 17a-4 Refinitiv Eikon Messenger DataParser para importar y archivar estos datos en Microsoft 365.
ms.openlocfilehash: c508ee245b23a66e54c71b3351421b7d1ff8490e
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/11/2022
ms.locfileid: "64761337"
---
# <a name="set-up-a-connector-to-archive-refinitiv-eikon-messenger-data"></a>Configuración de un conector para archivar datos de Refinitiv Eikon Messenger

Use [Refinitiv Eikon Messenger DataParser](https://www.17a-4.com/refinitiv-messenger-dataparser/) de 17a-4 LLC para importar y archivar datos de Refinitiv Eikon Messenger a buzones de correo de usuario en su organización de Microsoft 365. DataParser incluye un conector Refinitiv Eikon Messenger configurado para capturar elementos de un origen de datos de terceros e importarlos a Microsoft 365. El conector Refinitiv Eikon Messenger DataParser convierte los datos de Refinitiv Eikon Messenger en un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez que los datos de Refinitiv Eikon Messenger se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como suspensión por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector de Refinitiv Eikon Messenger para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-refinitiv-eikon-messenger-data"></a>Información general sobre el archivado de datos de Refinitiv Eikon Messenger

En la información general siguiente se explica el proceso de uso de un conector de datos para archivar los datos de Refinitiv Eikon Messenger en Microsoft 365.

![Flujo de trabajo de archivado de datos de Refinitiv Eikon Messenger de 17a-4.](../media/RefinitivMessengerDataParserConnectorWorkflow.png)

1. Su organización funciona con 17a-4 para configurar y configurar el DataParser de Refinitiv Eikon Messenger.

2. Regularmente, los elementos de Refinitiv Eikon Messenger son recopilados por el DataParser. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector de DataParser de Refinitiv Eikon Messenger que se crea en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Refinitiv Eikon Messenger DataParser en los buzones** de usuario y los elementos de Refinitiv Eikon Messenger se importan a esa carpeta. El conector determina a qué buzón se van a importar elementos mediante el valor de la propiedad *Email* . Cada elemento Refinitiv Eikon Messenger contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Cree una cuenta de DataParser para los conectores de Microsoft. Para crear una cuenta, póngase en contacto con [17a-4 LLC](https://www.17a-4.com/contact/). Tendrá que iniciar sesión en esta cuenta al crear el conector en el paso 1.

- Al usuario que crea el conector de DataParser de Refinitiv Eikon Messenger en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos 17a-4 está disponible en entornos de GCC en la nube Microsoft 365 us Government. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-a-refinitiv-eikon-messenger-dataparser-connector"></a>Paso 1: Configurar un conector de DataParser de Refinitiv Eikon Messenger

El primer paso consiste en acceder a la página Conectores de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector 17a-4 para los datos de Refinitiv Eikon Messenger.

1. Vaya a y, a <https://compliance.microsoft.com> continuación, haga clic en **Conectores** >  de **datosRefinitiv Eikon Messenger DataParser**.

2. En la página de descripción del producto **Refinitiv Eikon Messenger DataParser** , haga clic en **Agregar conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta 17a-4 y complete los pasos del Asistente para conexión de DataParser de Refinitiv Eikon Messenger.

## <a name="step-2-configure-the-refinitiv-eikon-messenger-dataparser-connector"></a>Paso 2: Configuración del conector de DataParser de Refinitiv Eikon Messenger

Trabaje con compatibilidad con 17a-4 para configurar el conector DataParser de Refinitiv Eikon Messenger.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El conector de DataParser de Refinitiv Eikon Messenger asignará automáticamente los usuarios a sus direcciones de correo electrónico Microsoft 365 antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-refinitiv-eikon-messenger-dataparser-connector"></a>Paso 4: Supervisión del conector DataParser de Refinitiv Eikon Messenger

Después de crear un conector DataParser de Refinitiv Eikon Messenger, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector Refinitiv Eikon Messenger DataParser que creó para mostrar la página de control flotante, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
