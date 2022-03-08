---
title: Configurar un conector DataParser de 17a-4 para archivar datos Conectar FX en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector DataParser de 17a-4 FX Conectar para importar y archivar fx Conectar datos en Microsoft 365.
ms.openlocfilehash: 129d5f6836d8cf447b77bf068a4c6b5f33b33703
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63311807"
---
# <a name="set-up-a-connector-to-archive-data-from-fx-connect"></a>Configurar un conector para archivar datos de FX Conectar

Use [el objeto DataParser de FX Conectar](https://www.17a-4.com/dataparser-roadmap/) de 17a-4 LLC para importar y archivar datos de FX Conectar buzones de usuario de su Microsoft 365 organización. DataParser incluye un conector de Conectar FX que está configurado para capturar elementos de un origen de datos de terceros e importar esos elementos a Microsoft 365. El conector DataParser de fx Conectar convierte los datos Conectar FX a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Después de almacenar Conectar fx en buzones de usuario, puede aplicar características de cumplimiento Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector Conectar FX para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-fx-connect-data"></a>Información general sobre el archivado de datos Conectar FX

En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar los Conectar FX en Microsoft 365.

![Flujo de trabajo de archivado para fx Conectar datos de 17a-4.](../media/FXConnectDataParserConnectorWorkflow.png)

1. Su organización trabaja con 17a-4 para configurar y configurar el objeto Fx Conectar DataParser.

2. De forma regular, el DataParser recopila Conectar de fx. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector Conectar DataParser de FX que crea en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **FX Conectar DataParser en los buzones** de usuario y los elementos Conectar FX se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email* . Cada elemento Conectar FX contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta dataParser para conectores de Microsoft. Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector DataParser de FX Conectar en el paso 1 (y lo completa en el paso 3) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos 17a-4 está disponible en GCC entornos en la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-a-fx-connect-dataparser-connector"></a>Paso 1: Configurar un conector Conectar DataParser

El primer paso es obtener acceso a la página Conectores de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para fx Conectar datos.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, haga clic en **Conectores** >  **de datosFX Conectar DataParser**.

2. En la página Conectar descripción del producto **DataParser de FX**, haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de 17a-4 y complete los pasos del Asistente para la conexión Conectar DataParser de FX.

## <a name="step-2-configure-the-fx-connect-dataparser-connector"></a>Paso 2: Configurar el conector Conectar DataParser de FX

Trabaje con la compatibilidad de 17a-4 para configurar el conector Conectar DataParser.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El conector Conectar DataParser de FX asignará automáticamente a los usuarios a sus Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-fx-connect-dataparser-connector"></a>Paso 4: Supervisar el conector Conectar DataParser

Después de crear un conector Conectar DataParser de FX, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector DataParser de FX Conectar que creó para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
