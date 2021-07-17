---
title: Introducción a la gobernanza de aplicaciones
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Introducción a las funcionalidades de gobernanza de aplicaciones para controlar sus aplicaciones.
ms.openlocfilehash: 80487298f2c3c3a93f0083337ddb223bd68e2611
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438041"
---
# <a name="get-started-with-app-governance-in-preview"></a>Introducción a la gobernanza de aplicaciones (en versión preliminar)

Para empezar a usar el complemento de gobernanza de aplicaciones para Microsoft Cloud App Security:

1. Compruebe que su cuenta tenga el nivel de licencia adecuado. La gobernanza de aplicaciones es una característica complementaria para Microsoft Cloud App Security (MCAS) y, por tanto, MCAS debe estar presente en su cuenta como un producto independiente o como parte de los distintos paquetes de licencia que se enumeran a continuación.
1. Debe tener uno de los roles de administrador que se enumeran a continuación para acceder a las páginas de gobernanza de la aplicación en el portal.

## <a name="licensing-for-app-governance"></a>Licencias para la gobernanza de aplicaciones

Antes de empezar a trabajar con la gobernanza de aplicaciones, debería confirmar [Centro de administración de Microsoft 365: suscripciones](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) y los complementos. Para obtener acceso y usar la gobernanza de aplicaciones, su organización debe tener una de las siguientes suscripciones:

- Microsoft Cloud App Security
- Microsoft 365 E5
- Cumplimiento de Microsoft 365 E5
- Microsoft 365 E5 Developer (sin Windows ni audioconferencia)
- Gobierno y protección de información de Microsoft 365 E5
- Seguridad de Microsoft 365 E5
- Microsoft 365 E5 con minutos de llamada
- Microsoft 365 E5 sin audioconferencia
- Cumplimiento de Microsoft 365 A5 para profesores
- Cumplimiento de Microsoft 365 A5 para estudiantes
- Microsoft 365 A5 para profesores
- Microsoft 365 A5 para estudiantes
- Gobierno y protección de información de Microsoft 365 A5 para profesores
- Gobierno y protección de información de Microsoft 365 A5 para estudiantes
- Seguridad de Microsoft 365 A5 para profesores
- Seguridad de Microsoft 365 A5 para estudiantes
- Ventajas de uso para estudiantes de Microsoft 365 A5
- Microsoft 365 A5 con minutos de llamada para profesores
- Microsoft 365 A5 con minutos de llamada para estudiantes
- Microsoft 365 A5 sin audioconferencia para profesores
- Microsoft 365 A5 sin audioconferencia para estudiantes
- Ventajas de uso de Microsoft 365 A5 sin audioconferencia para estudiantes

## <a name="administrator-roles"></a>Roles de administrador

Se requiere uno de los siguientes roles de administrador para ver las páginas de gobernanza de aplicaciones o administrar las directivas y la configuración:

- Administrador de la aplicación
- Administrador de aplicaciones en la nube
- Administrador de la empresa
- Administrador de cumplimiento
- Administrador de datos de cumplimiento
- Lector de cumplimiento (solo lectura)
- Lector global
- Administrador de seguridad
- Operador de seguridad
- Lector de seguridad (solo lectura)

> [!NOTE]
> Solo un administrador global puede activar la evaluación gratuita de gobernanza de aplicaciones.

Estas son las funcionalidades de cada rol.

| Rol | Leer del panel | Leer todas las aplicaciones |Leer directivas | Crear, actualizar o eliminar directivas | Leer alertas | Actualizar alertas | Leer la configuración | Actualizar configuración | Leer corrección | Actualizar corrección |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Administrador de la aplicación | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Administrador de aplicaciones en la nube | ![Marca de verificación](..\media\checkmark.png) | | | | | | | | | |
| Administrador de la empresa | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |
| Administrador de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Administrador de datos de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Lector de cumplimiento | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | | |
| Lector global  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | | |
| Administrador de seguridad | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Operador de seguridad | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | |
| Lector de seguridad  | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) |  | ![Marca de verificación](..\media\checkmark.png) | |
|||||||||| | |

Para obtener información adicional acerca de cada rol, consulte[permisos de rol de administrador](/azure/active-directory/roles/permissions-reference).

## <a name="add-app-governance-to-your-microsoft-365-account"></a>Incorpore la gobernanza de aplicaciones a su cuenta de Microsoft 365

Para los clientes existentes de Microsoft 365:

1. En su [centro de administración de Microsoft 365](https://admin.microsoft.com), diríjase a **Facturación- Adquirir servicios** y haga clic en **Complementos**.
1. En la tarjeta de gobernanza de aplicaciones, haga clic en **Detalles**.
1. Haga clic en **Comenzar prueba gratuita**.
1. Complete la información solicitada para agregar la gobernanza de aplicaciones a su usuario seleccionado. Si usted es un cliente nuevo, primero debe proporcionar información para establecer una cuenta y crear un usuario para el período de prueba. Una vez hecho esto, puede agregar la gobernanza de aplicaciones a la versión de prueba.

Para los clientes nuevos de Microsoft 365:

1. En la parte superior de esta página, haga clic en el botón **Cuenta gratuita**.
1. En **pruebe Microsoft 365 para empresas** haga clic en **Probar 1 mes gratis**.

Para ambos:

1. En el portal de registro, proporcione su dirección de correo electrónico para usarlo para la versión de prueba. Si es un cliente existente, use el correo electrónico asociado a su cuenta. Haga clic en **Siguiente**.
1. Una vez que haya iniciado sesión, haga clic en **Probar ahora** para obtener la versión de prueba gratuita.
1. Haga clic en **Continuar** para cerrar la página e iniciar la configuración de la prueba. Para los nuevos clientes de gobernanza de aplicaciones, la instancia de gobernanza de aplicaciones tardará hasta dos horas en estar disponible. Para los clientes existentes, no habrá ninguna interrupción de los servicios existentes.
  > [!NOTE]
Si aún no tiene una cuenta, se le pedirá que configure una nueva cuenta para poder continuar con la versión de prueba.

1. Escriba un nombre de dominio disponible para su usuario AAD y haga clic en **Comprobar la disponibilidad**. Se le asignará automáticamente un rol de administrador (si no tiene un rol existente para la gobernanza de aplicaciones) y siempre puede cambiar el nombre de dominio y/o comprar más usuarios más adelante a través del centro de administración de Microsoft 365.
1. Escriba el nombre de usuario y la contraseña que desea usar para iniciar sesión en su cuenta. Haga clic en **Iniciar sesión**.
1. Haga clic en **Introducción** para ir al portal de gobernanza de aplicaciones o **Administrar la suscripción** para ir al centro de administración de Microsoft 365.
