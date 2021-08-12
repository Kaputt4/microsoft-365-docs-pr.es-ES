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
ms.openlocfilehash: dc07acab3d58f8449f01f09f45c3bc78b66d0e3e
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541210"
---
# <a name="get-started-with-app-governance-in-preview"></a>Introducción a la gobernanza de aplicaciones (en versión preliminar)

Para empezar a usar el complemento de gobernanza de aplicaciones para Microsoft Cloud App Security:

1. Compruebe que su cuenta tenga el nivel de licencia adecuado. La gobernanza de aplicaciones es una característica complementaria para Microsoft Cloud App Security (MCAS) y, por tanto, MCAS debe estar presente en su cuenta como un producto independiente o como parte de los distintos paquetes de licencia que se enumeran a continuación.
1. Debe tener uno de los roles de administrador que se enumeran a continuación para acceder a las páginas de gobernanza de la aplicación en el portal.
1. El registro de inquilinos de su organización debe estar dentro de una de las [áreas admitidas de Norteamérica, Europa o África](app-governance-countries.md).

## <a name="licensing-for-app-governance"></a>Licencias para la gobernanza de aplicaciones

Antes de empezar a trabajar con la gobernanza de aplicaciones, debería confirmar [Centro de administración de Microsoft 365: suscripciones](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions) y los complementos. Para obtener acceso y usar la gobernanza de aplicaciones, su organización debe tener una de las siguientes suscripciones:

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

## <a name="add-integration-with-mcas"></a>Incorporación de la integración con MCAS 

Requisitos previos:

- Office 365 está conectado en Cloud App Security
- Las aplicaciones de Microsoft Office 365 Azure AD están habilitadas

Para habilitar la sincronización de gobernanza de aplicaciones con Cloud App Security siga estos pasos:

1. Vaya al portal de Microsoft Cloud App Security: [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. Haga clic en el icono de engranaje (esquina superior derecha) y seleccione **Configuración**.
1. En **Protección contra amenazas**, seleccione **Gobernanza de aplicaciones**.
1. Haga clic en **Habilitar la integración de Gobernanza de aplicaciones** y, a continuación, seleccione **Guardar**.

A continuación, revise las directivas recién habilitadas en MCAS. Las nuevas directivas pueden tardar unos minutos en aparecer una vez habilitada la integración.

- Reputación de la aplicación de OAuth Microsoft 365
- Microsoft 365 detección de suplantación de identidad (phishing) de OAuth
- Microsoft 365 gobernanza de aplicaciones de OAuth
- Revisión del widget de gobernanza de aplicaciones en el panel de MCAS
- Revisión de las alertas de gobernanza de aplicaciones recién generadas en las alertas de MCAS
- Revisión de las directivas de MCAS M365 OAuth en la lista de directivas de gobernanza de aplicaciones
- Revisión de las alertas de OAuth de MCAS M365 recién generadas en las alertas de gobernanza de aplicaciones

## <a name="canceling-your-trial"></a>Para cancelar la versión de prueba

Si no ha participado en la versión preliminar privada y desea cancelar la versión de prueba de gobernanza de aplicaciones, puede comunicarse con el contacto de CXE o seguir estos pasos:

1. En el Centro de administración de Microsoft 365, vaya a **Facturación** > **Sus productos**.
1. Vaya a la prueba de gobernanza de aplicaciones, haga clic en los tres puntos y seleccione **Cancelar suscripción**.
1. En el panel flotante resultante, proporcione un motivo para la cancelación, cualquier comentario adicional y seleccione **Cancelar suscripción**.
1. Seleccione **Cancelar suscripción** en la pantalla emergente resultante. La versión de prueba se ha cancelado, perderá el acceso a la gobernanza de aplicaciones y se eliminarán los datos de gobernanza de aplicaciones (datos de registro que se usan para crear la información y detecciones de gobernanza de aplicaciones; ningún correo electrónico ni otros archivos se verán afectados).
