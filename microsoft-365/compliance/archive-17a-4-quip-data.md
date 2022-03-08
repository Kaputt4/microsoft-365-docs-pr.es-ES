---
title: Configurar un conector para archivar datos quip en Microsoft 365
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
description: Obtenga información sobre cómo configurar y usar un conector DataParser quip de 17a-4 para importar y archivar datos quip en Microsoft 365.
ms.openlocfilehash: c3b781fcf7027bd3bdcd57db0e23165a3c33c940
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318289"
---
# <a name="set-up-a-connector-to-archive-quip-data"></a>Configurar un conector para archivar datos quip

Use [Quip DataParser](https://www.17a-4.com/quip-dataparser/) de 17a-4 LLC para importar y archivar datos de Quip a buzones de usuario de su Microsoft 365 organización. DataParser incluye un conector Quip configurado para capturar elementos de un origen de datos de terceros e importar esos elementos a Microsoft 365. El conector DataParser de Quip convierte los datos quip a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos a buzones de usuario en Microsoft 365.

Una vez almacenados los datos quip en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector quip para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-quip-data"></a>Información general sobre los datos quip de archivado

En la siguiente introducción se explica el proceso de uso de un conector de datos para archivar datos quip en Microsoft 365.

![Flujo de trabajo de archivado para datos quip de 17a-4.](../media/QuipDataParserConnectorWorkflow.png)

1. Su organización funciona con 17a-4 para configurar el DataParser quip y configurarlo.

2. De forma regular, el DataParser recopila los elementos Quip. DataParser también convierte el contenido de un mensaje en un formato de mensaje de correo electrónico.

3. El conector DataParser quip que se crea en el Centro de cumplimiento de Microsoft 365 se conecta a DataParser y transfiere los mensajes a una ubicación Azure Storage segura en la nube de Microsoft.

4. Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Quip DataParser en los buzones** de usuario y los elementos Quip se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email* . Cada elemento Quip contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante.

## <a name="before-you-set-up-a-connector"></a>Antes de configurar un conector

- Crear una cuenta dataParser para conectores de Microsoft. Para ello, póngase en [contacto con 17a-4 LLC](https://www.17a-4.com/contact/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector DataParser quip en el paso 1 (y lo completa en el paso 3) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos 17a-4 está disponible en GCC entornos en la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-a-quip-dataparser-connector"></a>Paso 1: Configurar un conector DataParser quip

El primer paso es obtener acceso a la página Conectores de datos de la Centro de cumplimiento de Microsoft 365 y crear un conector de 17a-4 para datos quip.

1. Vaya a <https://compliance.microsoft.com> y, a continuación, **haga clic en Conectores de datosQuip** >  **DataParser**.

2. En la página **Descripción del producto Quip DataParser** , haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de 17a-4 y complete los pasos del Asistente para la conexión de Quip DataParser.

## <a name="step-2-configure-the-quip-dataparser-connector"></a>Paso 2: Configurar el conector DataParser quip

Trabaje con la compatibilidad con 17a-4 para configurar el conector DataParser quip.

## <a name="step-3-map-users"></a>Paso 3: Asignar usuarios

El conector DataParser de Quip asignará automáticamente a los usuarios a sus Microsoft 365 de correo electrónico antes de importar datos a Microsoft 365.

## <a name="step-4-monitor-the-quip-dataparser-connector"></a>Paso 4: Supervisar el conector DataParser quip

Después de crear un conector DataParser quip, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com> y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector Quip DataParser que creó para mostrar la página desplegable, que contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.
