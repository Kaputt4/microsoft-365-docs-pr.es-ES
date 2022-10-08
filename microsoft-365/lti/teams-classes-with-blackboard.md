---
title: Uso de clases de Microsoft Teams con Blackboard Learn Ultra
ms.author: danismith
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: microsoft-365-business
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Use clases de Microsoft Teams con Blackboard Learn Ultra.
ms.openlocfilehash: c6170c60b7a9fe0f00c30c1d3ec07a0a65e31731
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68169219"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Uso de clases de Microsoft Teams con Blackboard Learn Ultra

El trabajo en equipo es el núcleo de todas las organizaciones modernas. Al fomentar la colaboración, es una característica definitoria de todas las instituciones de éxito. Puede mejorar todas las funcionalidades y características de Blackboard Learn Ultra si las empareja con las clases de Microsoft Teams.

Las clases pueden incluir conversaciones en tiempo real, reuniones de vídeo o interacciones asincrónicas. Puede agregar experiencias de uso compartido de archivos y cocreación para los alumnos, todo en un solo lugar. Las clases de Microsoft Teams con Learn Ultra redefinen la dinámica de la enseñanza y lo que significa el aprendizaje eficaz.

> [!IMPORTANT]
> Asegúrese de que ha configurado correctamente el campo Email de la institución en el [sistema de información de estudiantes (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)
>
>La integración de clases de Microsoft Teams se basa en el campo de correo electrónico de la institución en el SIS para asignarse al [nombre principal de usuario (UPN](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes)) correcto del Microsoft Azure Active Directory (AAD). Si no se ha aprovisionado ningún correo electrónico de la institución, el valor predeterminado será el correo electrónico existente. Se recomienda establecer este campo para que todos los usuarios se aseguren de que sus datos se sincronicen correctamente y de que no haya ningún conflicto de datos de correo electrónico entre AAD y Blackboard Learn Ultra.
>
> Si no ha establecido este campo correctamente en la asignación de SIS, la integración seguirá funcionando, pero es posible que los usuarios no aparezcan en las clases de Teams creadas y que se produzcan errores.

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>Compatibilidad con la asignación de datos institucionales: campo de SIS de Email de instituciones

Como parte de la evolución con las integraciones de proveedores en la nube, Blackboard Learn Ultra ha creado un nuevo campo de **Email de instituciones**, tanto en la integración de Student Information System Framework como en las API REST públicas, lo que permite a las instituciones administrar el proceso de sincronización de datos de forma eficaz entre Blackboard Learn Ultra y AAD.

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>¿Qué significa la Institución Email y qué admite?

El campo **Institution Email** permite asignaciones de campos personalizadas entre los orígenes de datos compatibles externamente de un cliente y Blackboard Learn Ultra. Si los orígenes de datos son proveedores de nube, como Microsoft, el nombre principal de usuario (UPN) es un identificador único principal para cada usuario que consta de un prefijo UPN (nombre de cuenta del usuario) y un sufijo UPN (un nombre de dominio DNS) unido a un símbolo @. Esto crea una dirección de correo electrónico única para cada usuario específico dentro de la Microsoft Azure Active Directory.

Para asegurarse de que los datos son precisos y que las inscripciones o pertenencias entre las clases Blackboard Learn Ultra y Microsoft Teams se logran correctamente, la dirección de correo electrónico de un usuario debe coincidir entre ambos sistemas. En Blackboard Learn Ultra, los usuarios pueden cambiar o invalidar su dirección de correo electrónico existente en la interfaz de usuario, lo que podría dar lugar a que se produzcan errores de sincronización y que el usuario no se agregue correctamente a un equipo de clase. La asignación de campos **de La institución Email** garantiza que este nivel de seguridad y comprobación de validación se pueda administrar correctamente, independientemente de si los usuarios han cambiado su correo electrónico en Blackboard Learn Ultra o no.

 Cuando dos direcciones de correo electrónico son diferentes, ya sea:

- Se debe tomar una decisión sobre qué origen tiene prioridad y se tomará como correos electrónicos de persona e institución.
  O bien
- Una institución puede establecer una asignación de campos personalizada en su Email De institución, lo que puede resolver un posible conflicto.

La asignación de campos **de Institution Email** ya está disponible para todos los tipos de integración de SIS existentes en **Configuración de** >  configuración avanzada **Los usuarios aprenden asignación de campos de tipo** >  de objeto.

> [!NOTE]
> Es importante tener en cuenta que, de forma predeterminada, el **Email de la institución** se establece en la **Email Person** para todos los formatos SIS y debe ser único para cada persona. Todas las integraciones existentes que estén configuradas y en ejecución tendrán esta asignación de datos en su lugar, ya que SIS no podrá importar usuarios si su correo electrónico está duplicado. Si una institución requiere la capacidad de cambiar el Email de la institución a **personalizado**, tendrá que administrarlo a través de la **configuración avanzada** del SIS.

## <a name="requirements"></a>Requisitos

La integración de clases de Microsoft Teams solo está disponible para **los cursos de vista de cursos Ultra**. La institución debe completar estos requisitos para usarla:

- Tener Blackboard Learn Ultra Learn SaaS con navegación base Ultra habilitada

  ![un ejemplo de la característica está habilitado en los cursos.](media/feature-availability.png)

- Habilitar LTI para su uso en cursos.

  a. Vaya al Panel  > **de administrador****Proveedores de herramientas LTI****Administrar propiedades globales** > .

  b. Seleccione **LTI habilitado en Cursos** y, opcionalmente, seleccione **Habilitado en Organizaciones**.

  c. Seleccione **Enviar**.

- Debe tener LTI configurado

- Incorporación de la integración de las clases LTI de Blackboard Learn Ultra Teams

- Agregar la herramienta LTI 1.3 de las clases de Microsoft Teams

- Adición de la herramienta de API REST y el uso compartido de recursos entre orígenes

- Configuración y aprobación de la integración de clases de Microsoft Teams

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Incorporación de la herramienta Blackboard Learn Ultra Teams Classes LTI 1.3

1. En el **Panel de administrador**, seleccione **Proveedores de herramientas LTI**.

2. Seleccione **Register LTI 1.3 Tool (Registrar herramienta LTI 1.3).**

3. En el campo **Id. de cliente** , escriba o copie y pegue este identificador:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Revise todas las configuraciones que se han rellenado previamente y en **Estado de la herramienta** y, a continuación, seleccione **Habilitado**.

5. En **Directivas de institución**, seleccione **Rol en Curso, Nombre** y **dirección Email** y, a continuación, seleccione **Sí** para ambos.

6. Seleccione **Allow grade service access (Permitir acceso al servicio de calificación**) y **Allow Membership Service Access (Permitir acceso al servicio de pertenencia).**

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Agregar la herramienta LTI de clases de Microsoft Teams 1.3

1. En el **Panel de administrador**, seleccione **Proveedores de herramientas LTI**.

2. Seleccione **Register LTI 1.3 Tool (Registrar herramienta LTI 1.3).**

3. En el campo **Id. de cliente** , escriba o copie y pegue este identificador:

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. Revise todas las configuraciones que se han rellenado previamente y en *Estado de la herramienta* y seleccione *Habilitado.*

5. En **Directivas de institución**, seleccione **Rol en Curso, Nombre** y **dirección Email**. Seleccione **Sí** para ambos.

6. Seleccione **Allow grade service access (Permitir acceso al servicio de calificación**) y **Allow Membership Service Access (Permitir acceso al servicio de pertenencia).**

## <a name="add-the-rest-api-tool"></a>Incorporación de la herramienta DE API REST

1. En el **Panel de administrador**, vaya a **Integraciones** y seleccione **Integraciones de API rest**.

2. Seleccione **Crear integración**.

3. En el campo **Id. de aplicación** , escriba o copie y pegue este identificador:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Escriba un usuario para esta integración.

   Este usuario será el que tenga acceso a la API principal desde el que está asociada la aplicación.

5. Seleccione **Enviar**.

## <a name="add-the-cross-origin-resource-sharing"></a>Adición del uso compartido de recursos entre orígenes

1. En el **panel Administrador**, vaya a **Integraciones** y seleccione **Uso compartido de recursos entre orígenes*.

2. Seleccione **Crear configuración**.

3. En el campo **Origen** , escriba copiar y pegar esta dirección URL:

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. En el campo **Encabezados permitidos** , escriba **Autorización**.

5. Establezca **Disponible en** **Sí**.

6. Seleccione **Enviar**.

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>Configuración y aprobación de la integración de clases de Microsoft Teams

Para integrar correctamente la instancia de Blackboard Learn Ultra con las clases de Microsoft Teams, deberá asegurarse de que la aplicación Blackboard Learn Ultra está aprobada para el acceso dentro de su inquilino de Microsoft Azure. Este es un proceso que deberá completar la Administración global de Microsoft 365 de su institución.

Este proceso se puede realizar antes o después de haber configurado las aplicaciones LTI en la instancia de Blackboard Learn Ultra.

### <a name="before-configuring-the-lti-applications"></a>Antes de configurar las aplicaciones LTI

Si decide aprobar la aplicación Blackboard Learn Ultra Teams Classes azure antes de configurar las integraciones de LTI, deberá redirigirla al **punto de conexión de consentimiento de Microsoft Identity Platform Administración**. Se muestra la dirección URL:

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> Reemplazará **{Tenant}** por el identificador de inquilino de Microsoft Azure institucional específico.

Verá una ventana de permisos que explica que está dando permiso a Blackboard Learn Ultra para acceder a Microsoft Teams.

![la ventana de permisos para Microsoft y Blackboard.](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a>Después de configurar las aplicaciones LTI

1. En el **Panel de administrador**, vaya a **Herramientas y utilidades** y seleccione **Integración de Microsoft Teams Administración**.

2. Seleccione **Habilitar Microsoft Teams**.

3. Agregue el **identificador de inquilino de Microsoft** al campo de texto disponible.

4. Seleccione una de las opciones siguientes:

   - Si la aplicación tiene consentimiento previo, mostrará una marca de verificación pequeña. Si aparece la marca de verificación, seleccione **Enviar**.

   - Si no se ha aprobado el consentimiento, siga los pasos descritos para generar la dirección URL de consentimiento y enviarlo al Administración global de Microsoft 365 para su aprobación.

5. Una vez que haya confirmado la aprobación, seleccione **Reintentar** para confirmar y, a continuación, seleccione **Enviar**.
