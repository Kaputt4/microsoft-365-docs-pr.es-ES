---
title: Configurar un conector para archivar datos de red tail Speak en Microsoft 365
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
description: Los administradores pueden configurar un conector para importar y archivar datos de Red tail Speak de Globanet a Microsoft 365. Este conector le permite archivar datos de orígenes de datos de terceros en Microsoft 365. Después de archivar estos datos, puede usar características de cumplimiento como retención legal, búsqueda de contenido y directivas de retención para administrar datos de terceros.
ms.openlocfilehash: 89b90fd29e089bf61632b22b38e6e10335fda2a8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906064"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Configurar un conector para archivar datos de Redtail Speak

Use un conector de Globanet en el Centro de cumplimiento de Microsoft 365 para importar y archivar datos de Redtail Speak a buzones de usuario de su organización de Microsoft 365. Globanet le proporciona un conector [Redtail Speak](https://globanet.com/redtail/) configurado para capturar elementos del servidor SFTP de su organización donde se reciben los elementos de Redtail. El conector convierte el contenido de Redtail Speak a un formato de mensaje de correo electrónico y, a continuación, importa esos elementos al buzón del usuario en Microsoft 365.

Después de almacenar los datos de Redtail Speak en buzones de usuario, puede aplicar características de cumplimiento de Microsoft 365 como retención por juicio, exhibición de documentos electrónicos, directivas de retención y etiquetas de retención. El uso de un conector Redtail Speak para importar y archivar datos en Microsoft 365 puede ayudar a su organización a cumplir con las directivas gubernamentales y reglamentarias.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Información general sobre el archivado de los datos de Redtail Speak

En la siguiente introducción se explica el proceso de uso de un conector para archivar los datos de Redtail Speak en Microsoft 365.

![Flujo de trabajo de archivado para datos de Redtail Speak](../media/RedtailSpeakConnectorWorkflow.png)

1. Su organización trabaja con Redtail Speak para configurar y configurar una puerta de enlace SMTP donde los mensajes se reenvan desde Redtail Speak al servidor SFTP de su organización a diario.

2. Una vez cada 24 horas, los elementos de Redtail Speak se copian en el sitio de Globanet Merge1. El conector también convierte los elementos de Redtail Speak a un formato de mensaje de correo electrónico.

3. El conector Redtail Speak que crea en el Centro de cumplimiento de Microsoft 365 se conecta al sitio de Globanet Merge1 todos los días y transfiere los mensajes a una ubicación segura de Azure Storage en la nube de Microsoft.

4. El conector importa los elementos convertidos de Redtail Speak a los buzones de usuarios específicos mediante el valor de la propiedad *Email* de la asignación automática de usuarios, tal como se describe en [el paso 3](#step-3-map-users-and-complete-the-connector-setup). Se crea una subcarpeta en la carpeta Bandeja de entrada denominada **Redtail Speak** en los buzones de usuario y los elementos se importan a esa carpeta. El conector determina a qué buzón se importarán los elementos mediante el valor de la *propiedad Email.* Cada elemento de Redtail Speak contiene esta propiedad, que se rellena con la dirección de correo electrónico de cada participante del elemento.

## <a name="before-you-begin"></a>Antes de empezar

- Crear una cuenta de Globanet Merge1 para conectores de Microsoft. Para crear una cuenta, póngase en contacto [con el servicio de soporte al cliente de Globanet](https://globanet.com/contact-us/). Debe iniciar sesión en esta cuenta al crear el conector en el paso 1.

- En el paso 2, debe especificar el servidor SFTP de la organización. Este paso es necesario para que Globanet Merge1 pueda ponerse en contacto con él para recopilar datos de Redtail Speak a través de SFTP.

- El usuario que crea el conector de importador de Redtail Speak en el paso 1 (y lo completa en el paso 3) debe estar asignado al rol De importación de buzones de correo exportar en Exchange Online. Este rol es necesario para agregar conectores en la página Conectores de datos del Centro de cumplimiento de Microsoft 365. Esta función no se asigna a ningún grupo de roles en Exchange Online de forma predeterminada. Puede agregar el rol Exportación de importación de buzones al grupo de roles Administración de la organización en Exchange Online. O bien, puede crear un grupo de roles, asignar el rol Importación de buzones de correo Exportar y, a continuación, agregar los usuarios adecuados como miembros. Para obtener más información, vea [](/Exchange/permissions-exo/role-groups#modify-role-groups) las secciones [Crear](/Exchange/permissions-exo/role-groups#create-role-groups) grupos de roles o Modificar grupos de roles en el artículo "Administrar grupos de roles en Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Paso 1: Configurar el conector Redtail Speak

El primer paso es acceder a la página **Conectores** de datos en el Centro de cumplimiento de Microsoft 365 y crear un conector para los datos de Redtail Speak.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y seleccione **Conectores de datos** &gt; **Redtail Speak**.

2. En la **página Descripción del producto Redtail Speak,** seleccione Agregar nuevo **conector**.

3. En la **página Términos de** servicio, seleccione **Aceptar**.

4. Escriba un nombre único que identifique el conector y, a continuación, seleccione **Siguiente**.

5. Inicie sesión en su cuenta merge1 para configurar el conector.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>Paso 2: Configurar el conector de Redtail Speak en el sitio de Globanet Merge1

El segundo paso es configurar el conector Redtail Speak en el sitio Merge1. Para obtener información sobre cómo configurar el conector de Redtail Speak, vea [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Después de seleccionar **Guardar &**  finalizar , se muestra la página Asignación de usuario en el asistente para conectores en el Centro de cumplimiento de Microsoft 365.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Paso 3: Asignar usuarios y completar la configuración del conector

Para asignar usuarios y completar la configuración del conector, siga estos pasos:

1. En la página Asignar usuarios de Redtail Speak a usuarios de **Microsoft 365,** habilite la asignación automática de usuarios. Los elementos de Redtail Speak incluyen una propiedad denominada *Email*, que contiene direcciones de correo electrónico para los usuarios de la organización. Si el conector puede asociar esta dirección con un usuario de Microsoft 365, los elementos se importan al buzón de ese usuario.

2. Seleccione **Siguiente**, revise la configuración y vaya a la página **Conectores** de datos para ver el progreso del proceso de importación del nuevo conector.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Paso 4: Supervisar el conector Redtail Speak

Después de crear el conector Redtail Speak, puede ver el estado del conector en el Centro de cumplimiento de Microsoft 365.

1. Vaya a [https://compliance.microsoft.com](https://compliance.microsoft.com/) y seleccione **Conectores de datos** en la navegación izquierda.

2. Seleccione la **pestaña Conectores** y, a continuación, seleccione el **conector Redtail Speak** para mostrar la página desplegable. Esta página muestra propiedades e información sobre el conector.

3. En **Estado del conector con origen,** seleccione el vínculo Descargar **registro** para abrir (o guardar) el registro de estado del conector. Este registro contiene datos que se han importado a la nube de Microsoft.

## <a name="known-issues"></a>Problemas conocidos

- En este momento, no se admite la importación de datos adjuntos o elementos de más de 10 MB. La compatibilidad con elementos más grandes estará disponible en una fecha posterior.