---
title: Creación de directivas de seguridad de dispositivos en Basic Mobility and Security
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: microsoft-365-business
ms.localizationpriority: medium
ms.collection:
- Tier3
- scotvorg
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkEXCHANGE
search.appverid:
- MET150
description: Use Basic Mobility and Security para crear directivas de dispositivo que protejan la información de su organización.
ms.openlocfilehash: da81f8b002d6bc2292f5067110de368004e4a1ff
ms.sourcegitcommit: 181a0aff54842dcbafd834647c6e9ee47304d10f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2022
ms.locfileid: "68727639"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Creación de directivas de seguridad de dispositivos en Basic Mobility and Security

Puede usar Basic Mobility and Security para crear directivas de dispositivo que ayuden a proteger la información de su organización en Microsoft 365 frente al acceso no autorizado. Puede aplicar directivas a cualquier dispositivo móvil de su organización en el que el usuario del dispositivo tenga una licencia de Microsoft 365 aplicable y haya inscrito el dispositivo en Basic Mobility and Security.

## <a name="before-you-begin"></a>Antes de empezar

> [!IMPORTANT]
> Para poder crear una directiva de dispositivo móvil, debe activar y configurar Basic Mobility and Security. Para obtener más información, consulte Información general sobre la movilidad y la seguridad básicas.

- Obtenga información sobre los dispositivos, las aplicaciones de dispositivos móviles y la configuración de seguridad que admite Basic Mobility and Security. Consulte [Funcionalidades de movilidad y seguridad básicas](capabilities.md).
- Cree grupos de seguridad que incluyan usuarios de Microsoft 365 en los que quiera implementar directivas en y para los usuarios que quiera excluir de que se bloquee el acceso a Microsoft 365. Antes de implementar una nueva directiva en la organización, se recomienda probarla implementándola para un número reducido de usuarios. Puede crear y usar un grupo de seguridad que incluya solo a usted o a un número pequeño de usuarios de Microsoft 365 que puedan probar la directiva automáticamente. Para más información sobre los grupos de seguridad, consulte [Creación, edición o eliminación de un grupo de seguridad](../email/create-edit-or-delete-a-security-group.md).
- Para crear e implementar directivas básicas de movilidad y seguridad en Microsoft 365, debe ser administrador global de Microsoft 365. Para obtener más información, consulte [Permisos en el Centro de cumplimiento de seguridad &](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md).
- Antes de implementar directivas, informe a su organización de los posibles impactos de inscribir un dispositivo en Basic Mobility and Security. En función de cómo configure las directivas, se puede impedir que los dispositivos no conformes accedan a Microsoft 365 y a los datos, incluidas las aplicaciones instaladas, las fotos y la información personal en un dispositivo inscrito, y se pueden eliminar los datos.

> [!NOTE]
> Las directivas y las reglas de acceso creadas en Basic Mobility and Security para Microsoft 365 Empresa Estándar invalidan Exchange ActiveSync directivas de buzón de dispositivo móvil y reglas de acceso a dispositivos creadas en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Centro de administración de Exchange</a>. Después de inscribir un dispositivo en Basic Mobility and Security para Microsoft 365 Empresa Estándar, se omite cualquier directiva de buzón de dispositivo móvil Exchange ActiveSync o regla de acceso de dispositivo aplicada al dispositivo. Para más información sobre Exchange ActiveSync, consulte [Exchange ActiveSync en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Paso 1: Creación de una directiva de dispositivo e implementación en un grupo de prueba

Antes de empezar, asegúrese de que ha activado y configurado Basic Mobility and Security. Para obtener instrucciones, consulte [Información general sobre la movilidad y la seguridad básicas](overview.md).

1. En el explorador, escriba <https://compliance.microsoft.com/basicmobilityandsecurity>.

2. Seleccione **Crear directiva**.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="Configuración de directivas básicas de movilidad y seguridad.":::

3. En la página **Configuración de** directiva, especifique los requisitos que desea aplicar a los dispositivos móviles de su organización.

4. **Requerir la administración del perfil de correo electrónico**: cuando está habilitado, los dispositivos que no tienen un perfil de correo electrónico administrado por Basic Mobility and Security se consideran no compatibles. Un dispositivo no puede tener un perfil de correo electrónico administrado cuando no está dirigido correctamente o si el usuario configura manualmente la cuenta de correo electrónico en el dispositivo. Cuando se deja **no habilitado** (valor predeterminado), esta configuración no se evalúa para el cumplimiento o el incumplimiento. Para obtener instrucciones sobre cómo los usuarios pueden cumplir esta opción cuando se selecciona esta opción, consulte [Se encontró una cuenta de correo electrónico existente](/intune-user-help/existing-company-email-account-found).

5. En la página **¿Desea aplicar esta directiva ahora?** , elija los grupos a los que desea aplicar esta directiva.

6. Seleccione **Crear esta directiva**.

La directiva se inserta en el dispositivo de cada usuario a la que se aplica la directiva la próxima vez que inicie sesión en Microsoft 365 mediante su dispositivo móvil. Si los usuarios no han aplicado una directiva a su dispositivo móvil antes, después de implementar la directiva, reciben una notificación en su dispositivo que incluye los pasos para inscribir y activar Basic Mobility and Security. Para obtener más información, consulta [Inscribir tu dispositivo móvil con Basic Mobility and Security](enroll-your-mobile-device.md). Hasta que completen la inscripción en Basic Mobility and Security hospedada por el servicio Intune, el acceso al correo electrónico, OneDrive y otros servicios está restringido. Después de completar la inscripción mediante la aplicación Portal de empresa de Intune, pueden usar los servicios y la directiva se aplica a su dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Paso 2: Comprobar que la directiva funciona

Después de crear una directiva de dispositivo, compruebe que la directiva funciona como espera antes de implementarla en su organización.

1. En el explorador, escriba [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).
2. Seleccione **Ver la lista de dispositivos administrados**.
3. Compruebe el estado de los dispositivos de usuario a los que se ha aplicado la directiva. Quiere que el **estado** de los dispositivos se **administre.**
4. También puede realizar un borrado completo o selectivo en un dispositivo si hace clic en **el botón Restablecer** fábrica o **Quitar datos de la empresa** del botón **Administrar** después de seleccionar un dispositivo. Para obtener instrucciones, consulte [Borrar un dispositivo móvil en Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Paso 3: Implementación de una directiva en la organización

Después de crear una directiva de dispositivo y comprobar que funciona según lo esperado, impleméntela en su organización.

1. En el explorador, escriba: [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).
2. Seleccione la directiva que desea implementar y elija **Editar** junto a **Grupos aplicados.**
3. Busque un grupo para agregar y haga clic en **Seleccionar**.
4. Seleccione **Cerrar** y **cambiar la configuración.**
5. Seleccione **Cerrar** y **editar directiva.**

La directiva se inserta en el dispositivo móvil de cada usuario a la que se aplica la directiva la próxima vez que inicie sesión en Microsoft 365 desde su dispositivo móvil. Si los usuarios no han aplicado una directiva a su dispositivo móvil, reciben una notificación en su dispositivo con los pasos necesarios para inscribirla y activarla para Basic Mobility and Security. Una vez completada la inscripción, la directiva se aplica a su dispositivo. Para obtener más información, consulta [Inscribir tu dispositivo móvil con Basic Mobility and Security](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Paso 4: Bloquear el acceso al correo electrónico para dispositivos no compatibles

Para ayudar a proteger la información de su organización, debe bloquear el acceso de la aplicación al correo electrónico de Microsoft 365 para dispositivos móviles que no son compatibles con Basic Mobility and Security. Para obtener una lista de los dispositivos admitidos, consulte [Dispositivos compatibles](../../admin/basic-mobility-security/capabilities.md).

**Para bloquear el acceso a la aplicación:**

1. En el explorador, escriba [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).
2. Seleccione **Administrar la configuración de acceso a dispositivos de toda la organización**.
3. Para bloquear dispositivos no admitidos, elija **Acceso** en **Si un dispositivo no es compatible con Basic Mobility and Security para Microsoft 365** y, a continuación, seleccione **Guardar**.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-access.png" alt-text="Opción de acceso de bloque de movilidad y seguridad básica.":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Paso 5: Elija los grupos de seguridad que desea excluir de las comprobaciones de acceso condicional

Si desea excluir algunas personas de las comprobaciones de acceso condicional en sus dispositivos móviles y ha creado uno o más grupos de seguridad para estas personas, agregue los grupos de seguridad aquí. Las personas de estos grupos no tendrán ninguna directiva aplicada para sus dispositivos móviles compatibles. Esta es la opción recomendada si ya no desea usar Basic Mobility and Security en su organización.

1. En el explorador, escriba [https://compliance.microsoft.com/basicmobilityandsecurity](https://compliance.microsoft.com/basicmobilityandsecurity).

2. Seleccione **Administrar la configuración de acceso a dispositivos de toda la organización**.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-microsoft-purview.png" alt-text="Basic Mobility and Security crea una opción de directiva.":::

3. Seleccione **Agregar** para agregar el grupo de seguridad que tiene usuarios que desea excluir de tener bloqueado el acceso a Microsoft 365. Cuando se ha agregado un usuario a esta lista, puede acceder al correo electrónico de Microsoft 365 cuando usa un dispositivo no compatible.

4. Seleccione el grupo de seguridad que desea usar en el panel **Seleccionar grupo** .

5. Seleccione el nombre y, a continuación, **Agregar** > **guardar**.

6. En el panel **Configuración de acceso a dispositivos de toda la organización** , elija **Guardar**.

   :::image type="content" source="../../media/basic-mobility-security/basic-mobility-groups.png" alt-text="Opción de acceso permitir movilidad y seguridad básicas.":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>¿Cuál es el impacto de las directivas de seguridad en distintos tipos de dispositivos?

Al aplicar una directiva a los dispositivos de usuario, el impacto en cada dispositivo varía un poco entre los tipos de dispositivo. Consulte la siguiente tabla para obtener ejemplos del impacto de las directivas en diferentes dispositivos.

|**Directiva de seguridad**|**Android**|**Samsung KNOX**|**iOS**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada|No|Sí|Sí|Se requiere una copia de seguridad cifrada de iOS.|
|Bloquear copia de seguridad de la nube|Sí|Sí|Sí|Bloquee la copia de seguridad de Google en Android (atenuado), la copia de seguridad en la nube en iOS supervisado.|
|Bloquear sincronización de documentos|No|No|Sí|iOS: bloquee documentos en la nube en dispositivos iOS supervisados.|
|Bloquear sincronización de fotos |No|No|Sí|iOS (nativo): Bloquear Photo Stream.|
|Bloquear captura de pantalla |No|Sí|Sí|Se bloquea cuando se intenta.|
|Bloquear videoconferencia |No|No|Sí|FaceTime bloqueado en dispositivos iOS supervisados, no en Skype u otros usuarios.|
|Bloquear el envío de datos de diagnóstico |No|Sí|Sí|Bloquear el envío de informes de bloqueo de Google en Android.|
|Bloquear el acceso a la tienda de aplicaciones |No|Sí|Sí|Icono de la tienda de aplicaciones que falta en la página principal de Android, deshabilitado en Windows y dispositivos iOS supervisados.|
|Requerir contraseña para la tienda de aplicaciones |No|No|Sí|iOS: Contraseña necesaria para las compras de iTunes.|
|Bloquear conexión a almacenamiento extraíble |No|Sí|N/D|Android: la tarjeta SD está atenuada en la configuración, Windows notifica al usuario, las aplicaciones instaladas no están disponibles|
|Bloquear conexión Bluetooth |Ver notas|Ver notas|Yes|No se puede deshabilitar BlueTooth como una configuración en Android. En su lugar, deshabilitamos todas las transacciones que requieren BlueTooth: distribución avanzada de audio, control remoto de audio y vídeo, dispositivos manos libres, auriculares, acceso a la libreta de teléfonos y puerto serie. Cuando se usa cualquiera de estas opciones, aparece un pequeño mensaje de aviso en la parte inferior de la página.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>¿Qué ocurre al eliminar una directiva o quitar un usuario de la directiva?

Al eliminar una directiva o quitar un usuario de un grupo en el que se implementó la directiva, la configuración de la directiva, el perfil de correo electrónico de Microsoft 365 y los correos electrónicos almacenados en caché podrían quitarse del dispositivo del usuario. Consulte la tabla siguiente para ver qué se quita para los diferentes tipos de dispositivo.

|**Lo que se ha quitado**|**iOS**|**Android (incluido Samsung KNOX)**|
|:-----|:-----|:-----|
|Perfiles de correo electrónico administrado<sup>1</sup>|Yes|No|
|Bloquear copia de seguridad de la nube|Sí|No|

<sup>1</sup> Si la directiva se implementó con la opción **Email perfil está seleccionada**, el perfil de correo electrónico administrado y los correos electrónicos almacenados en caché en ese perfil se eliminan del dispositivo de usuario.

La directiva se quita del dispositivo móvil para cada usuario a la que se aplica la directiva la próxima vez que el dispositivo se registra con Basic Mobility and Security. Si implementa una nueva directiva que se aplica a estos dispositivos de usuario, se les pedirá que vuelvan a inscribirse en Basic Mobility and Security.

También puede borrar un dispositivo por completo o borrar selectivamente la información de la organización del dispositivo. Para obtener más información, consulta [Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-content"></a>Contenido relacionado

[Introducción a la movilidad y la seguridad básicas](overview.md) (artículo)\
[Funcionalidades de movilidad y seguridad básicas](capabilities.md) (artículo)