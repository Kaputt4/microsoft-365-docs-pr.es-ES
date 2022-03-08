---
title: Dispositivos compartidos
description: Cómo y cuándo usar el modo de dispositivo compartido
keywords: Escritorio administrado de Microsoft, Microsoft 365, servicio, documentación
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
ms.openlocfilehash: 45729a40ecab2548b3125559ac3a971e5134f190
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/08/2022
ms.locfileid: "63320807"
---
# <a name="shared-devices"></a>Dispositivos compartidos

Microsoft Managed Desktop te permite registrar dispositivos en "modo de dispositivo compartido", similar al modo de dispositivo compartido ofrecido por [Microsoft Intune](/mem/intune/configuration/shared-user-device-settings).

Los dispositivos de este modo están optimizados para situaciones en las que los usuarios no están vinculados a un solo escritorio y cambian con frecuencia los dispositivos. Por ejemplo, los trabajadores de primera línea, como los responsables de los bancos o el personal de enfermería. Puede aplicar cualquiera de los perfiles de Escritorio administrado de Microsoft a [dispositivos](profiles.md) en este modo. Los dispositivos registrados en este modo tienen algunas diferencias importantes:

- [El almacenamiento de](#device-storage) dispositivos está optimizado para usuarios compartidos.
- [Se eliminan las cuentas](#deletion-of-inactive-accounts) inactivas.
- [Las cuentas de](#guest-accounts) invitado no son compatibles de forma predeterminada.
- [Microsoft 365 aplicaciones para](#microsoft-365-apps-for-enterprise) licencias empresariales está optimizada para dispositivos compartidos.

Dado que eliges usar el modo de dispositivo compartido en el punto de registro en el Escritorio administrado de Microsoft, si quieres cambiar de este modo más adelante, debes desinscribilo y volver a registrarlo.

## <a name="when-to-use-shared-device-mode"></a>Cuándo usar el modo de dispositivo compartido

Cualquier situación en la que los usuarios cambian de dispositivos con frecuencia.

Por ejemplo, los administradores de cuentas bancarias pueden estar en una ubicación administrando depósitos, pero se mueven a una oficina back office para ayudar a los clientes con una hipoteca. En cada una de estas ubicaciones, el dispositivo ejecuta diferentes aplicaciones y está optimizado para esas tareas, aunque son usadas por varias personas.

El personal de enfermería suele moverse entre las salas y las oficinas a medida que interactúan con los pacientes. Pueden iniciar sesión en una estación de trabajo en una oficina, pero conectarse a su escritorio remoto y tomar notas, y repetir este proceso en una sala diferente con un paciente diferente.

## <a name="when-not-to-use-shared-device-mode"></a>Cuándo no usar el modo de dispositivo compartido

El modo de dispositivo compartido no es una buena opción en estas situaciones:

- Cuando los archivos de un usuario necesitan almacenarse localmente en lugar de en la nube
- Si la experiencia del usuario debe ser diferente para diferentes usuarios en el dispositivo
- Si el conjunto de aplicaciones que necesita cada usuario es muy diferente

## <a name="enroll-new-devices-in-shared-device-mode"></a>Inscribir nuevos dispositivos en modo de dispositivo compartido

Tanto si tú como un partner administras la inscripción, puedes elegir usar el modo de dispositivo compartido.

Si estás inscribiendo dispositivos tú mismo, sigue los pasos del registro manual [y, a](../get-started/manual-registration.md) continuación, agréguelos al grupo Dispositivos modernos del lugar de trabajo **: modo de dispositivo compartido** .

> [!WARNING]
> No intente convertir ningún dispositivo de Escritorio administrado de Microsoft existente en modo de dispositivo compartido simplemente agregándolos a este grupo. Las directivas que se aplican pueden provocar que OneDrive archivos se pierdan permanentemente.

Si tienes dispositivos de inscripción de partners, sigue los pasos del registro de [partners, pero](../get-started/partner-registration.md) anexa **-Shared** a la etiqueta de grupo, como se muestra en la tabla siguiente:

| Perfil de dispositivo | Etiqueta de grupo Autopilot (modo estándar) | Etiqueta de grupo (modo de dispositivo compartido) |
| ----- | ----- | ----- |
| Datos confidenciales | Microsoft365Managed_SensitiveData |  Microsoft365Managed_SensitiveData-Shared |
| Power user | Microsoft365Managed_PowerUser | No se admite |
| Estándar  | Microsoft365Managed_Standard | Microsoft365Managed_Standard-Shared |

## <a name="consequences-of-shared-device-mode"></a>Consecuencias del modo de dispositivo compartido

### <a name="device-storage"></a>Almacenamiento de dispositivos

Los usuarios de dispositivos compartidos deben hacer una copia de seguridad de sus datos en la nube para poder seguirlos a otros dispositivos. Una vez que hayas registrado dispositivos en modo de dispositivo compartido, asegúrate de habilitar las características de redireccionamiento de [](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e#:~:text=%20Turn%20on%20Files%20On-Demand%20%201%20Make,files%20as%20you%20use%20them%20box.%20More%20) archivos a petición y carpetas [conocidas](/onedrive/redirect-known-folders) de OneDrive. Este enfoque minimiza el efecto que tiene cada perfil de usuario en el almacenamiento del dispositivo. Los dispositivos en modo de dispositivo compartido eliminan automáticamente los perfiles de usuario si el espacio libre en disco cae por debajo del 25 %. Esta actividad está programada para medianoche en la hora local del dispositivo, a menos que el almacenamiento se vuelva críticamente limitado.

Microsoft Managed Desktop usa [el CSP de SharedPC](/mem/intune/configuration/shared-user-device-settings-windows) para realizar estas operaciones, así que asegúrese de que no los usa usted mismo.

> [!IMPORTANT]
> Indóquele a los usuarios que después de descargar un archivo grande deben confirmar que ven el icono de comprobación verde en el archivo antes de cerrar la sesión. Si su cuenta se elimina como parte de las operaciones de limpieza y el archivo no se carga completamente en OneDrive, el archivo se perderá permanentemente.

### <a name="deletion-of-inactive-accounts"></a>Eliminación de cuentas inactivas

El modo de dispositivo compartido quita las cuentas que no han iniciado sesión durante más de 30 días.

### <a name="guest-accounts"></a>Cuentas de invitado

Los dispositivos en modo de dispositivo compartido solo permiten cuentas unidas a un dominio. Si necesitas cuentas de invitado en un dispositivo, puedes presentar una solicitud de [cambio](../working-with-managed-desktop/admin-support.md) para solicitar que se habiliten.

### <a name="microsoft-365-apps-for-enterprise"></a>Aplicaciones de Microsoft 365 para empresas

[Aplicaciones Microsoft 365 para empresas](/microsoft-365/managed-desktop/get-started/m365-apps) permite a un usuario determinado instalar esas aplicaciones en solo cinco dispositivos al mismo tiempo. En el modo de dispositivo compartido, las aplicaciones no cuentan con el límite, por lo que pueden usarlas mientras se roaming entre dispositivos. La implementación y las actualizaciones de Aplicaciones Microsoft 365 para empresas funcionan como de costumbre.

### <a name="device-profiles"></a>Perfiles de dispositivo

En el modo de dispositivo compartido, solo puedes tener un perfil [de dispositivo](profiles.md) en un dispositivo determinado. Además, el perfil de dispositivo de usuario avanzado no se admite actualmente en el modo de dispositivo compartido.

### <a name="apps-and-policies-assigned-to-users"></a>Aplicaciones y directivas asignadas a los usuarios

En dispositivos compartidos, debes asignar cualquier aplicación o directivas que te estés administrando a los grupos *de dispositivos*, no a los grupos de usuarios. La asignación a grupos de dispositivos garantiza que cada usuario tenga una experiencia más coherente. La excepción [es Portal de empresa](#deploying-apps-with-company-portal).

## <a name="limitations-of-shared-device-mode"></a>Limitaciones del modo de dispositivo compartido

### <a name="windows-hello"></a>Windows Hello

Windows Hello la emulación de tarjetas inteligentes para almacenar en caché los [PIN de](/windows/security/identity-protection/hello-for-business/hello-faq) usuario de forma segura, lo que minimiza el número de veces que los usuarios tienen que autenticarse. Sin embargo, Windows solo permite 10 tarjetas inteligentes a la vez en un dispositivo determinado. Cuando un undécimo usuario inicia sesión por primera vez, una de las cuentas existentes perderá su tarjeta inteligente. Podrán iniciar sesión, pero su PIN no se almacenará en caché.

### <a name="universal-print"></a>Impresión universal

Cuando impresión universal instala una impresora para un único usuario en un dispositivo compartido, la impresora estará disponible para todos los usuarios de ese dispositivo. No hay forma de aislar impresoras entre usuarios en dispositivos compartidos.

## <a name="limitations-of-shared-device-mode-in-the-public-preview-release"></a>Limitaciones del modo de dispositivo compartido en la versión preliminar pública

### <a name="primary-user"></a>Usuario principal

Cada Microsoft Intune dispositivo tiene un usuario principal, que se asigna cuando Autopilot configura un dispositivo. Pero cuando los dispositivos se comparten, Intune requiere que se quite el usuario principal.

> [!IMPORTANT]
> Mientras el modo de dispositivo compartido está en versión preliminar pública, asegúrese de quitar el usuario principal siguiendo estos pasos: inicie sesión en el Centro de administración de Microsoft Endpoint Manager, seleccione **DispositivosTodos**> dispositivos **, seleccione** un dispositivo, después seleccione **PropiedadesRemove**> al usuario principal y elimine el usuario que aparece allí.

### <a name="deploying-apps-with-company-portal"></a>Implementación de aplicaciones con Portal de empresa

Es probable que algunas aplicaciones no necesiten estar presentes en todos los dispositivos, por lo que es posible que prefieras que los usuarios solo instalen esas aplicaciones cuando las necesiten de [Portal de empresa](/mem/intune/user-help/install-apps-cpapp-windows).

Microsoft Managed Desktop deshabilita las Portal de empresa de forma predeterminada para dispositivos en modo de dispositivo compartido. Si desea habilitar el Portal de empresa, puede presentar una [solicitud de cambio](../working-with-managed-desktop/admin-support.md). Sin embargo, debe tener en cuenta algunas limitaciones de esta característica en esta versión preliminar pública:

- Para que una aplicación esté disponible para los usuarios de Portal de empresa, asigne un grupo de usuarios a esa aplicación en Intune y, a continuación, agregue cada usuario [a](/mem/intune/apps/apps-deploy) ese grupo de usuarios.
- Los dispositivos no pueden tener un [usuario principal](#primary-user).
- Para desinstalar una aplicación que un usuario instaló a través de Portal de empresa, debes desinstalar la aplicación de todos los usuarios de ese dispositivo.

> [!CAUTION]
> Portal de empresa no admite aplicaciones asignadas a grupos de dispositivos como disponibles.

### <a name="redeployment-of-microsoft-365-apps-for-enterprise"></a>Reimplementación de Aplicaciones Microsoft 365 para Enterprise

Durante la versión preliminar pública, Aplicaciones Microsoft 365 debe volver a implementarse, los usuarios deben ponerse en contacto con su personal de soporte técnico local para solicitar que un agente eleve y vuelva a instalar Aplicaciones Microsoft 365 para empresas en ese dispositivo.

### <a name="microsoft-teams"></a>Microsoft Teams

Cuando un usuario Teams por primera vez, se le pedirá que actualice la aplicación antes de poder usarla. Una vez que permiten la actualización, Teams se mantendrá actualizado en segundo plano.
