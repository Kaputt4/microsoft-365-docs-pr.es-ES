---
title: Administrador de cumplimiento de Microsoft y el RGPD
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: El Administrador de cumplimiento de Microsoft es una herramienta gratuita de evaluación de riesgos basada en el flujo de trabajo que se encuentra dentro del Portal de confianza de servicios de Microsoft. El Administrador de cumplimiento le permite realizar un seguimiento, asignar y verificar las actividades de cumplimiento reglamentarias de su organización en relación con los servicios en la nube de Microsoft.
ms.openlocfilehash: b4a648c43fb20f557b85e24e9e67de036cc4f2e0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2021
ms.locfileid: "60168667"
---
# <a name="microsoft-compliance-manager-and-the-gdpr"></a>Administrador de cumplimiento de Microsoft y el RGPD

El Reglamento general de protección de datos (RGPD), aprobado por la Unión Europea, puede afectar a la estrategia de cumplimiento e implantar acciones específicas para administrar la información del usuario y del cliente que se usa en el Administrador de cumplimiento.

## <a name="user-privacy-settings"></a>Configuración de privacidad del usuario

Algunos reglamentos exigen que una organización pueda eliminar los datos del historial del usuario. Para facilitar esto, el Administrador de cumplimiento proporciona las funciones de **Configuración de privacidad del usuario**, que permiten a los administradores:
  
- [Buscar un usuario](#search-for-a-user)
- [Exportar un informe de historial de datos de cuenta](#export-a-report-of-account-data-history)
- [Eliminar el historial de datos del usuario](#delete-user-data-history)
  
## <a name="search-for-a-user"></a>Buscar un usuario

Para buscar una cuenta de usuario:
  
1. Escriba el alias de la dirección de correo electrónico del usuario (la información a la izquierda del símbolo @) y, después, seleccione el nombre de dominio de la lista de sufijos de dominio en la parte derecha. En el caso de las organizaciones con varios dominios registrados, compruebe el sufijo del nombre de dominio para asegurarse de que sea el correcto.

2. Después de especificar correctamente el nombre de usuario, seleccione **Buscar**.

3. Para las cuentas de usuario que no se devuelven en la búsqueda, la página muestra **Usuario no encontrado**. Revise la información de dirección de correo electrónico del usuario y realice las correcciones necesarias. Para reintentar, seleccione **Buscar**.

4. Para las cuentas de usuario que se devuelven en la búsqueda, el texto del botón cambia de **Buscar** a **Borrar**. Esto indica que la cuenta de usuario devuelta es el contexto operativo para las funciones adicionales, las cuales se aplican a dicha cuenta de usuario.

5. Para borrar los resultados de la búsqueda y buscar otro usuario, seleccione **Borrar**.

## <a name="export-a-report-of-account-data-history"></a>Exportar un informe del historial de datos de la cuenta

Para cada cuenta de usuario identificada, puede generar un informe de dependencias vinculadas a la cuenta. Esta información le permitirá reasignar las Acciones abiertas o garantizar el acceso a evidencias cargadas anteriormente.
  
 Para generar y exportar un informe:
  
1. Seleccione **Exportar** para generar y descargar un informe de los elementos de acciones de control del Administrador de cumplimiento que estén asignados actualmente a la cuenta de usuario devuelta, así como la lista de documentos que ese usuario ha cargado. Si no hay acciones asignadas ni documentos cargados, se mostrará el mensaje de error “No hay datos para este usuario”.

2. El informe se descargará en segundo plano desde la ventana del explorador activa. Si no ve un mensaje emergente de descarga, consulte el historial de descargas del explorador.

3. Abra el documento para revisar los datos del informe.

> [!IMPORTANT]
> Los datos del informe no son una lista histórica que conserva y muestra los cambios de estado en el historial de asignaciones de las Acciones. El informe generado es una instantánea de informe de las Acciones de control asignadas en el momento en que se ejecutó el informe (con la marca de fecha y hora escrita en el informe). Por ejemplo, si, posteriormente, se reasignan Acciones y vuelve a generarse el informe para el mismo usuario, se obtendrá una instantánea de informe con datos distintos.
  
## <a name="delete-user-data-history"></a>Eliminar el historial de datos del usuario

Establece en "no asignadas" todas las Acciones de control asignadas al usuario devuelto. Establece en "eliminado por el usuario" el valor **cargado por** para los documentos cargados por el usuario devuelto.
  
Para eliminar el historial de carga de documentos y las Acciones de la cuenta de usuario:
  
1. Seleccione **Eliminar**.

    Se muestra un cuadro de diálogo de confirmación: "*Se eliminarán todas las asignaciones de Acciones de control y el historial de carga de documentos del usuario seleccionado. Esta acción no se puede deshacer. ¿Está seguro de que quiere continuar?*"

2. Para continuar, seleccione **Aceptar**, en caso contrario, seleccione **Cancelar**.
