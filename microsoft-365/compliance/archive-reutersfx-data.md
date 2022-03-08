---
title: Configurar un conector para archivar datos de Reuters FX en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Reuters FX de Veritas a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: afc8ef93179259597c1113791c318f3b115c3561
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312381"
---
# <a name="set-up-a-connector-to-archive-reuters-fx-data"></a>Configurar un conector para archivar datos de Reuters FX

Use un conector Veritas en el Centro de cumplimiento de Microsoft 365 importar y archivar datos de la plataforma Reuters FX a los buzones de usuario de su Microsoft 365 organización. Veritas le proporciona un conector [Fx de Reuters](https://globanet.com/reuters-fx/) que está configurado para capturar elementos del origen de datos de terceros (de forma regular) y, a continuación, importar esos elementos a Microsoft 365. El conector convierte las monedas y las tasas fx de la cuenta Reuters FX a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Una vez que los datos de Reuters FX se almacenan en buzones de usuario, puede aplicar Microsoft 365 características de cumplimiento como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención y cumplimiento de comunicaciones. El uso de un conector fx de Reuters para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-reuters-fx-data"></a>Información general sobre el archivado de datos de Reuters FX

En la siguiente introducción se explica el proceso de uso de un conector para archivar datos de Reuters FX en Microsoft 365.

![Flujo de trabajo de archivado para datos de Reuters FX.](../media/ReutersFXConnectorWorkflow.png)

1. Su organización trabaja con Reuters FX para configurar y configurar un sitio de Reuters FX.

2. Una vez cada 24 horas, los elementos de Reuters FX se copian en el sitio Veritas Merge1. El conector también convierte los elementos en un formato de mensaje de correo electrónico.

3. El conector fx de Reuters que crea en el Centro de cumplimiento de Microsoft 365, se conecta al sitio Veritas Merge1 todos los días y transfiere el contenido a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Reuters FX en los buzones** de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email* . Cada elemento de Reuters FX contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto con [el Servicio de soporte al cliente de Veritas](https://globanet.com/contact-us). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- El usuario que crea el conector Fx de Reuters en el paso 1 (y lo completa en el paso 3) debe tener asignado el rol de administrador del conector de datos. Este rol es necesario para agregar conectores en la **página Conectores de datos** de la Centro de cumplimiento de Microsoft 365. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, vea la sección "Roles en los centros de seguridad y cumplimiento" en Permisos en el [Centro de seguridad & cumplimiento](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de la organización puede crear un grupo de roles personalizado, asignar el rol de administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, vea la sección "Crear un grupo de roles personalizado" en [Permisos en el Centro de cumplimiento de Microsoft 365](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas se encuentra en versión preliminar pública en GCC entornos de la Microsoft 365 us government cloud. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por lo tanto, no están cubiertos por los compromisos de cumplimiento y protección de datos de Microsoft 365. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-the-reuters-fx-connector"></a>Paso 1: Configurar el conector Reuters FX

El primer paso es obtener acceso a la página **Conectores** de datos de la Microsoft 365 y crear un conector para los datos de Reuters FX.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y, a continuación, **haga clic en Conectores** **de datosReuters** >  FX.

2. En la página **Descripción del producto Reuters FX** , haga clic **en Agregar conector**.

3. En la **página Términos de** servicio, haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-reuters-fx-connector-on-the-veritas-merge1-site"></a>Paso 2: Configurar el conector reuters FX en el sitio veritas merge1

El segundo paso consiste en configurar el conector De Reuters FX en el sitio Veritas Merge1. Para obtener información sobre cómo configurar el conector Reuters FX, consulte [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20FX%20User%20Guide%20.pdf).

Después de hacer **clic en Guardar & finalizar**, se muestra  la página Asignación de usuario en el asistente para conector en Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector en el Centro de cumplimiento de Microsoft 365, siga los pasos siguientes:

1. En la **página Asignar usuarios de Reuters FX a Microsoft 365 usuarios**, habilite la asignación automática de usuarios.

   Los elementos de Reuters FX incluyen una propiedad denominada *Correo* electrónico, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Haga **clic en** Siguiente, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-reuters-fx-connector"></a>Paso 4: Supervisar el conector Reuters FX

Después de crear el conector Reuters FX, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a <https://compliance.microsoft.com/> y haga clic **en Conectores de datos** en la navegación izquierda.

2. Haga clic **en la pestaña Conectores** y, a continuación, seleccione el conector **Reuters FX** para mostrar la página desplegable, que contiene las propiedades e información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.