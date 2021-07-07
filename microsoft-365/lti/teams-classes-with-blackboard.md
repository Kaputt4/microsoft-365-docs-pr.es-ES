---
title: Integrar Microsoft Teams clases con Blackboard Learn Ultra
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Integrar Microsoft Teams clases con Blackboard Learn Ultra
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314500"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a>Usar Microsoft Teams clases con Blackboard Learn Ultra

El trabajo en equipo es el núcleo de todas las organizaciones modernas. Al fomentar la colaboración, es una característica definitoria de todas las instituciones exitosas. Puedes mejorar todas las capacidades y características de Blackboard Learn Ultra al emparejarlos con Microsoft Teams clases.

Las clases pueden incluir conversaciones en tiempo real, reuniones de vídeo o interacciones asincrónicas. Puede agregar experiencias de cocreación y uso compartido de archivos para sus alumnos, todo en un solo lugar. Microsoft Teams clases con Learn Ultra redefinen la dinámica de la enseñanza y lo que significa un aprendizaje eficaz.

> [!IMPORTANT]
> Asegúrese de que ha configurado correctamente el campo Correo electrónico de la institución en el Sistema de información de estudiantes (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`
>
>La integración Microsoft Teams clases de Microsoft Teams se basa en el campo de correo electrónico de la institución en el SIS para asignarse al nombre principal de usuario (UPN) de Microsoft Azure Active Directory (AAD) correcto. Si no se ha aprovisionado ningún correo electrónico de la institución, este valor predeterminado será el correo electrónico existente. Se recomienda establecer este campo para que todos los usuarios se aseguren de que sus datos estén sincronizados correctamente y de que no haya conflictos de datos de correo electrónico entre Microsoft AAD y Blackboard Learn Ultra.
>
> Si no ha establecido este campo correctamente en la asignación de SIS, la integración seguirá funcionando, pero es posible que los usuarios no aparezcan en las clases Teams creadas y que se produzcan errores.

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a>Compatibilidad con la asignación de datos institucionales: campo SIS de correo electrónico de la institución

Como parte de la evolución con las integraciones de  proveedores en la nube, Blackboard Learn Ultra ha creado un nuevo campo de correo electrónico de la institución, tanto en la integración de Student Information System Framework como en las API públicas de REST, lo que permite a las instituciones administrar el proceso de sincronización de datos de forma eficaz entre Blackboard Learn Ultra y Microsoft AAD.

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a>¿Qué significa el correo electrónico de la institución y qué admite?

El **campo Correo electrónico de** la institución permite asignaciones de campos personalizadas entre los orígenes de datos admitidos externamente de un cliente y Blackboard Learn Ultra. Si los orígenes de datos son proveedores de nube, como Microsoft, el nombre de principio de usuario (UPN) es un identificador único principal para cada usuario que consta de un prefijo UPN (nombre de cuenta del usuario) y un sufijo UPN (un nombre de dominio DNS) unidos con un símbolo @. Esto crea una dirección de correo electrónico única para cada usuario específico dentro del Microsoft Azure Active Directory.

Para asegurarse de que los datos son precisos y de que las inscripciones o pertenencias entre las clases Desinscripción Ultra y Microsoft Teams de Blackboard se logran correctamente, la dirección de correo electrónico de un usuario debe coincidir entre ambos sistemas. En Blackboard Learn Ultra, los usuarios pueden cambiar o invalidar su dirección de correo electrónico existente en la interfaz de usuario, lo que podría provocar errores de sincronización y que el usuario no se agregara correctamente a un equipo de clase. La **asignación** del campo Correo electrónico de la institución garantiza que este nivel de comprobación de seguridad y validación se pueda administrar correctamente, independientemente de si los usuarios han cambiado su correo electrónico dentro de Blackboard Learn Ultra o no.

 Cuando dos direcciones de correo electrónico son diferentes:

- Se debe tomar una decisión sobre qué origen tiene prioridad y se tomarán como correos electrónicos de persona e institución.
  O bien
- Una institución puede establecer una asignación de campo personalizada en su correo electrónico de la institución, que puede resolver un posible conflicto.

La **asignación de campo** De correo electrónico de la institución ya está disponible para todos los tipos de integración de SIS existentes en Configuración avanzada **Configuración**  >  **usuarios aprendan asignación de** campo de tipo de  >  **objeto**.

> [!NOTE]
> Es importante tener en cuenta que,  de forma predeterminada, el correo electrónico de la institución se establece en el correo electrónico de persona para todos los formatos de SIS y debe ser único para cada persona.  Todas las integraciones existentes que estén configuradas y en ejecución tendrán esta asignación de datos en su lugar, ya que SIS no podrá importar usuarios si su correo electrónico está duplicado. Si una institución requiere la capacidad de cambiar el correo electrónico de la institución a **personalizado,** tendrá que administrarlo a través de la configuración avanzada **Configuración** en el SIS.

## <a name="requirements"></a>Requirements

La integración Microsoft Teams clases de curso está disponible solo para los cursos **de vista de curso ultra.** La institución debe completar estos requisitos para usarlo:

- Tener Habilitado El SaaS de Aprendizaje Ultra de Blackboard con navegación ultra base

- Habilitar LTI para su uso en cursos.

  a. Vaya al **Panel de administrador**  >  **LTI Tool Providers** Manage Global  >  **Properties**.

  b. Seleccione **LTI habilitado en cursos y,** opcionalmente, seleccione **Habilitado en organizaciones**.

  c. Seleccione **Enviar**.

- Debe haber configurado LTI

- Agregar integración de LTI Teams Clases de Aprendizaje de Blackboard

- Agregar Microsoft Teams clases de complemento LTI 1.3 Tool

- Agregar la herramienta api de REST y el uso compartido de recursos entre orígenes

- Configurar y aprobar clases Microsoft Teams integración

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a>Agregar la herramienta LTI 1.3 Teams Clases de aprendizaje ultra de Blackboard Learn

1. En el **Panel de administrador,** seleccione **Proveedores de herramientas LTI**.

2. Seleccione **Registrar herramienta LTI 1.3**.

3. En el **campo Id.** de cliente, escriba o copie y pegue este identificador:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Revise todas las opciones de configuración que se han rellenado previamente y en **Estado de** la herramienta y, a continuación, seleccione **Habilitado**.

5. En **Directivas de entidad**, seleccione Rol en Curso, Nombre y Dirección de correo **electrónico** **y,** a continuación, **seleccione Sí** para ambos.

6. Seleccione **Permitir acceso al servicio de calidad** y Permitir acceso al servicio de **pertenencia.**

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a>Agregar la herramienta Microsoft Teams clases de trabajo LTI 1.3

1. En el **Panel de administrador,** seleccione **Proveedores de herramientas LTI**.

2. Seleccione **Registrar herramienta LTI 1.3**.

3. En el **campo Id.** de cliente, escriba o copie y pegue este identificador:

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. Revise todas las configuraciones que se han rellenado previamente y en *Estado de la* herramienta y seleccione *Habilitado.*

5. En **Directivas de la** institución, seleccione Rol en **Curso, Nombre y** Dirección de correo **electrónico**. Seleccione **Sí** para ambos.

6. Seleccione **Permitir acceso al servicio de calidad** y Permitir acceso al servicio de **pertenencia.**

## <a name="add-the-rest-api-tool"></a>Agregar la herramienta API de REST

1. En el **Panel de administrador,** vaya a **Integraciones** y seleccione **Integraciones de la API de Rest**.

2. Seleccione **Crear integración**.

3. En el **campo Id. de** aplicación, escriba o copie y pegue este identificador:

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. Escriba un usuario para esta integración.

   Este usuario será el que tenga acceso a la API principal desde la que está asociada la aplicación.

5. Seleccione **Enviar**.

## <a name="add-the-cross-origin-resource-sharing"></a>Agregar el uso compartido de recursos entre orígenes

1. En el **panel Administrador,** vaya a **Integraciones** y seleccione * Uso compartido de *recursos entre orígenes*.

2. Seleccione **Crear configuración**.

3. En el **campo Origen,** escriba copiar y pegar esta dirección URL:

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. En el **campo Encabezados permitidos,** escriba **Autorización**.

5. Establezca **Disponible** en **Sí**.

6. Seleccione **Enviar**.

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a>Configurar y aprobar clases Microsoft Teams integración

Para integrar correctamente la instancia de Blackboard Learn Ultra con las clases Microsoft Teams, deberá asegurarse de que la aplicación Descúes de Blackboard Learn Ultra esté aprobada para el acceso en el espacio empresarial Microsoft Azure usuario. Este es un proceso que deberá completar el administrador global Microsoft 365 la entidad.

Este proceso se puede realizar antes o después de configurar las aplicaciones LTI en la instancia ultra de Blackboard Learn.

### <a name="before-configuring-the-lti-applications"></a>Antes de configurar las aplicaciones LTI

Si decide aprobar la aplicación Azure de Clases de Aprendizaje ultra Teams de Blackboard Learn antes de configurar las integraciones de LTI, deberá redirigir al extremo de consentimiento de administrador de la plataforma de identidades de **Microsoft**. Se muestra la dirección URL:

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> Reemplazará **{Tenant}** por su identificador de inquilino Microsoft Azure institucional específico.

### <a name="after-configuring-the-lti-applications"></a>Después de configurar las aplicaciones LTI

1. En el **Panel de administrador,** vaya **a Herramientas y** utilidades y seleccione Microsoft Teams Administrador de **integración.**

2. Seleccione **Habilitar Microsoft Teams**.

3. Agregue el **identificador de inquilino de Microsoft** al campo de texto disponible.

4. Elija una de las siguientes opciones:

   - Si la aplicación tiene el consentimiento previo, mostrará una pequeña marca de verificación. Si aparece la marca de verificación, seleccione **Enviar**.

   - Si no se ha aprobado el consentimiento, siga los pasos descritos para generar la dirección URL para el consentimiento y enviarla al administrador global Microsoft 365 para su aprobación.

5. Una vez que haya confirmado la aprobación, seleccione **Reintentar** para confirmar y, a continuación, **seleccione Enviar**.
