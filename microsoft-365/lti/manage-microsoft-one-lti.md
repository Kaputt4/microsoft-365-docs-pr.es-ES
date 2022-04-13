---
title: Administración de Microsoft OneLTI para cualquier LMS
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Obtenga información sobre cómo llevar a cabo tareas clave de administración de Microsoft OneLTI, incluida la visualización, eliminación, edición y solución de problemas.
ms.openlocfilehash: 8b788028a453969f13c31bbe72962c1b7df955a6
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823464"
---
# <a name="manage-microsoft-onelti-for-any-lms"></a>Administración de Microsoft OneLTI para cualquier LMS

Microsoft OneLTI se integra con varios LMS, como Canvas, Blackboard y Moodle.

En este artículo, los administradores de TI encontrarán instrucciones sobre las tareas clave de administración de OneLTI.

- [Ver un registro LTI](#view-an-lti-registration).
- [Elimine un registro LTI](#delete-an-lti-registration).
- [Edite un registro LTI](#edit-an-lti-registration).
- [Solución de problemas con OneLTI](#troubleshoot-issues-with-onelti).
- [Informe de problemas con OneLTI](#report-problems-with-onelti).

## <a name="view-an-lti-registration"></a>Visualización de un registro LTI

Si desea ver los detalles de un registro LTI, siga los pasos que se indican a continuación.

1. Visite [el Portal de Microsoft LTI](https://lti.microsoft.com/).
2. Inicie sesión con una cuenta de administrador de Microsoft 365.
3. En la lista de registros, busque el registro de LTI que desea ver.
4. Seleccione el **icono de ojo** situado junto a la lista.
5. Se abrirá el panel de detalles del registro.

## <a name="delete-an-lti-registration"></a>Eliminación de un registro LTI

Si desea eliminar un registro de Microsoft OneLTI, siga estos pasos.

1. Visite [el Portal de Microsoft LTI](https://lti.microsoft.com/).
2. Inicie sesión con una cuenta de administrador de Microsoft 365.
3. En la lista de registros, busque el registro de LTI que desea eliminar.
4. Seleccione el **icono de la papelera** junto a la lista.
5. En el cuadro de diálogo de confirmación, seleccione **Eliminar** para confirmar la eliminación.
6. Verá un mensaje correcto una vez que se elimine.

## <a name="edit-an-lti-registration"></a>Edición de un registro LTI

Actualmente, no se admite la edición de un registro LTI existente después de agregarlo.

Para cambiar un registro LTI, deberá hacer lo siguiente:

1. [Elimine el registro existente](#delete-an-lti-registration).
2. Agregue un nuevo registro.

## <a name="troubleshoot-issues-with-onelti"></a>Solución de problemas con OneLTI

Si usted o sus educadores experimentan problemas con Microsoft OneLTI, estas son algunas cosas que puede hacer para solucionar problemas.

### <a name="issues-while-launching-an-lti-tool-from-the-lms"></a>Problemas al iniciar una herramienta LTI desde LMS

Los educadores pueden experimentar problemas al iniciar una herramienta LTI de Microsoft en su LMS.

Si es así, estos son algunos problemas comunes y cómo resolverlos.

- **No se pueden encontrar cookies**
  - Las cookies de terceros deben permitirse para la **dirección URL de LMS** en la configuración del explorador.
  - Estas cookies son necesarias para completar el protocolo de enlace LTI 1.3 según las especificaciones de IMS.

- **No se encontraron detalles de registro**
  - Este problema se produce cuando no se completó el registro de la herramienta LTI o si el registro se eliminó en el portal de administración de OneLTI.
  - El administrador de TI deberá completar el registro de la herramienta LTI.

- **Algunos detalles de LMS no son válidos**
  - Este problema se produce cuando los detalles enviados desde LMS en la solicitud de inicio de la herramienta no se alinean con la especificación de IMS LTI 1.3.
  - El administrador de TI tendrá que ponerse en contacto con el [equipo de soporte técnico educativo de Microsoft](https://edusupport.microsoft.com/support?product_id=lti_apps&platform_id=web) si el problema persiste.

### <a name="issues-with-signing-in-to-the-registration-portal"></a>Problemas con el inicio de sesión en el portal de registro

Al iniciar sesión en el portal de registro de Microsoft LTI, es posible que tenga problemas para acceder a la página de registro o reciba un error de inicio de sesión.

Estos son algunos problemas comunes de inicio de sesión y cómo resolverlos.

- **Error de autorización**
  - Si ve el mensaje de error "Su cuenta no tiene permiso para acceder a esta página", haga lo siguiente:
    - La cuenta no pertenece a un inquilino registrado, o
    - La cuenta no pertenece a un educador ni a un administrador.

  - En ambos casos, verá un botón **Cerrar sesión & cambiar cuentas** .
    - Seleccione este botón o seleccione el botón **Cerrar sesión** en el menú perfil de usuario.
    - Inicie sesión con una cuenta que pertenezca al inquilino, un educador o un administrador.

  - Si el inquilino no está registrado, el administrador de TI debe registrarlo antes de intentar registrar las integraciones de LTI.

  - Si después de probar estos pasos, sigue viendo este error, cierre la sesión e inicie sesión de nuevo.
    - También puede borrar las cookies y el almacenamiento local para el portal de registro de LTI y `https://login.microsoftonline.com/`.
    - Intente iniciar sesión de nuevo.
    - Si el problema persiste, para notificar el problema, seleccione el vínculo **Notificar un problema** en la parte superior derecha.

- **Error de autenticación**
  - Si ve el mensaje de error, "Error de autenticación. Inténtelo de nuevo", es posible que la sesión de inicio de sesión haya expirado.
    - Cierre la sesión y vuelva a iniciar sesión.
    - También puede borrar las cookies y el almacenamiento local para el portal de registro de LTI y `https://login.microsoftonline.com/`.
    - Intente iniciar sesión de nuevo.
    - Si el problema persiste, para notificar el problema, seleccione el vínculo **Notificar un problema** en la parte superior derecha.

- **Otros errores**
  - Para todos los demás errores, verá el mensaje de error "Algo salió mal. Inténtelo de nuevo más tarde".
    - Podría tratarse de un error de procesamiento interno.
    - Intente iniciar sesión de nuevo después de unas horas.
      - Seleccione el botón **Ir a la página principal** . Esto volverá a la página de aterrizaje.
      - Seleccione el botón **Ir al portal de registro** para volver al portal de registro de LTI.

## <a name="report-problems-with-onelti"></a>Notificar problemas con OneLTI

Para notificar cualquier problema o enviar comentarios para Microsoft OneLTI, siga los pasos que se indican a continuación.

1. En el portal de registro de Microsoft OneLTI, seleccione el **icono de signo de interrogación** en el encabezado de página.
2. En la lista desplegable, seleccione **Notificar un problema**.
3. Se abrirá la página Soporte técnico de Microsoft Education. Inicie sesión con sus credenciales de Microsoft 365.
4. Rellene el formulario y envíelo.
