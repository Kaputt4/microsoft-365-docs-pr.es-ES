---
title: Configuración de un conector para archivar datos XSLT/XML en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos XSLT/XML desde Veritas en Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365 para que pueda usar características de cumplimiento como la suspensión legal, la búsqueda de contenido y las directivas de retención para administrar los datos de terceros de su organización.
ms.openlocfilehash: 92932e3e18c8f43c46cf71e43ec02306d78a2f60
ms.sourcegitcommit: caedcf7f16eed23596487d97c375d4bc4c8f3566
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64995742"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Configuración de un conector para archivar datos XSLT/XML

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

Use un conector de Veritas en el portal de cumplimiento de Microsoft Purview para importar y archivar datos desde el origen de la página web a los buzones de usuario de la organización de Microsoft 365. Veritas proporciona un [conector XSLT/XML](https://globanet.com/xslt-xml) que permite el desarrollo rápido de archivos creados mediante transformacións de lenguaje de hoja de estilos extensibles (XSLT) para transformar archivos XML en otros formatos de archivo (como HTML o texto) que se pueden importar a Microsoft 365. El conector convierte el contenido de un elemento del origen XSLT/XML en un formato de mensaje de correo electrónico y, a continuación, importa el elemento convertido a Microsoft 365 buzones.

Una vez que los datos XSLT/XML se almacenan en buzones de usuario, puede aplicar características de Microsoft Purview, como la suspensión por juicio, la exhibición de documentos electrónicos y las directivas de retención y las etiquetas de retención. El uso de un conector XSLT/XML para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir las directivas gubernamentales y normativas.

## <a name="overview-of-archiving-xsltxml-data"></a>Introducción al archivado de datos XSLT/XML

En la información general siguiente se explica el proceso de uso de un conector para archivar los datos de origen XSLT/XML en Microsoft 365.

![Flujo de trabajo de archivado para datos XSLT/XML.](../media/XSLT-XMLConnectorWorkflow.png)

1. Su organización funciona con el origen XSLT/XML para configurar y configurar un sitio XSLT/XML.

2. Una vez cada 24 horas, los mensajes de chat del origen XSLT/XML se copian en el sitio de Veritas Merge1. El conector también convierte el contenido en un formato de mensaje de correo electrónico.

3. El conector XSLT/XML que se crea en el portal de cumplimiento, se conecta al sitio Veritas Merge1 todos los días y transfiere los mensajes a una ubicación de Azure Storage segura en la nube de Microsoft.

4. El conector importa los elementos de mensaje convertidos a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en el paso 3. Se crea una nueva subcarpeta en la carpeta Bandeja de entrada denominada **XSLT/XML** en los buzones de usuario y los elementos de mensaje se importan a esa carpeta. Para ello, el conector usa el valor de la propiedad *Email* . Cada mensaje contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del mensaje.

## <a name="before-you-begin"></a>Antes de empezar

- Cree una cuenta de Veritas Merge1 para los conectores de Microsoft. Para crear esta cuenta, póngase en contacto con [el servicio de atención al cliente de Veritas](https://www.veritas.com/content/support/). Iniciará sesión en esta cuenta al crear el conector en el paso 1.

- Al usuario que crea el conector XSLT/XML en el paso 1 (y lo completa en el paso 3) se le debe asignar el rol Administrador del conector de datos. Este rol es necesario para agregar conectores en la página **Conectores de datos** del portal de cumplimiento. Este rol se agrega de forma predeterminada a varios grupos de roles. Para obtener una lista de estos grupos de roles, consulte la sección "Roles en los centros de seguridad y cumplimiento" de [Permisos en el Centro de cumplimiento de & seguridad](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center). Como alternativa, un administrador de su organización puede crear un grupo de roles personalizado, asignar el rol Administrador del conector de datos y, a continuación, agregar los usuarios adecuados como miembros. Para obtener instrucciones, consulte la sección "Crear un grupo de roles personalizado" en [Permisos en el portal de cumplimiento de Microsoft Purview](microsoft-365-compliance-center-permissions.md#create-a-custom-role-group).

- Este conector de datos de Veritas está en versión preliminar pública en entornos de GCC en la nube Microsoft 365 administración pública de EE. UU. Las aplicaciones y servicios de terceros pueden implicar almacenar, transmitir y procesar los datos de clientes de su organización en sistemas de terceros que están fuera de la infraestructura de Microsoft 365 y, por tanto, no están cubiertos por los compromisos de protección de datos y Microsoft Purview. Microsoft no hace ninguna representación de que el uso de este producto para conectarse a aplicaciones de terceros implica que esas aplicaciones de terceros son compatibles con FEDRAMP.

## <a name="step-1-set-up-an-xsltxml-connector"></a>Paso 1: Configurar un conector XSLT/XML

El primer paso consiste en acceder a los **conectores de datos** en el portal de cumplimiento y crear un conector para los datos XSLT/XML.

1. Vaya a y, a [https://compliance.microsoft.com](https://compliance.microsoft.com/) continuación, haga clic en **Conectores** >  de **datosXSLT/XML**.

2. En la página de descripción del producto **XSLT/XML** , haga clic en **Agregar nuevo conector**.

3. En la página **Términos de servicio** , haga clic en **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, haga clic en **Siguiente**.

5. Inicie sesión en su cuenta de Merge1 para configurar el conector.

## <a name="step-2-configure-an-xsltxml-connector"></a>Paso 2: Configuración de un conector XSLT/XML

El segundo paso es configurar el conector XSLT/XML en el sitio Merge1. Para obtener información sobre cómo configurar el conector XSLT/XML en el sitio Veritas Merge1, vea [Merge1 Third-Party Connectors User Guide(Guía del usuario de conectores de terceros de Merge1](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)).

Después de hacer clic en **Guardar & finalizar**, se muestra la página **Asignación** de usuarios del asistente del conector en el portal de cumplimiento.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

1. Para asignar usuarios y completar la configuración del conector en el portal de cumplimiento, siga estos pasos:

2. En la página **Asignar usuarios XSLT/XML a Microsoft 365 usuarios**, habilite la asignación automática de usuarios. Los elementos XSLT/XML incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección a un usuario Microsoft 365, los elementos se importan al buzón de ese usuario.

3. Haga clic en **Siguiente**, revise la configuración y vaya a la página **Conectores de datos** para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Paso 4: Supervisión del conector XSLT/XML

Después de crear el conector XSLT/XML, puede ver el estado del conector en el portal de cumplimiento.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com) y haga clic en **Conectores de datos** en el panel de navegación izquierdo.

2. Haga clic en la pestaña **Conectores** y, a continuación, seleccione el conector **XSLT/XML** para mostrar la página de control flotante. Esta página contiene las propiedades y la información sobre el conector.

3. En **Estado del conector con origen**, haga clic en el vínculo **Descargar registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admiten la importación de datos adjuntos o elementos que superen los 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.