---
title: Crear directivas de seguridad de dispositivos en la movilidad y la seguridad básicas
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Use la movilidad y la seguridad básicas para crear directivas de dispositivo que protejan la información de la organización.
ms.openlocfilehash: 7bbc4a128505ce6e569db4b4d7d98e132c503965
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337102"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Crear directivas de seguridad de dispositivos en la movilidad y la seguridad básicas 

Puede usar la movilidad y la seguridad básicas para crear directivas de dispositivo que ayuden a proteger la información de la organización en Microsoft 365 de acceso no autorizado. Puede aplicar directivas a cualquier dispositivo móvil de la organización en el que el usuario del dispositivo tenga una licencia aplicable de Microsoft 365 y haya inscrito el dispositivo en la movilidad y la seguridad básicas.

## <a name="before-you-begin"></a>Antes de empezar

>[!IMPORTANT]
>Antes de poder crear una directiva de dispositivo móvil, debe activar y configurar la movilidad y la seguridad básicas. Para obtener más información, vea información general sobre la movilidad y la seguridad básicas.

- Obtenga información sobre los dispositivos, las aplicaciones para dispositivos móviles y la configuración de seguridad que admite la movilidad y la seguridad básicos. Consulte [capacidades básicas de movilidad y seguridad](capabilities-of-basic-mobility-and-secruity.md).
- Cree grupos de seguridad que incluyan a los usuarios de Microsoft 365 que desea que implementen directivas y para los usuarios que tal vez desee excluir del bloqueo de acceso a Microsoft 365. Antes de implementar una nueva directiva en la organización, se recomienda probarla implementándola para un número reducido de usuarios. Puede crear y usar un grupo de seguridad que incluya solo o un pequeño número de usuarios de Microsoft 365 que puedan probar la Directiva por usted. Para obtener más información acerca de los grupos de seguridad, vea [crear, editar o eliminar un grupo de seguridad](https://go.microsoft.com/fwlink/p/?LinkId=518555).
- Para crear e implementar directivas básicas de movilidad y seguridad en Microsoft 365, debe ser un administrador global de Microsoft 365. Para obtener más información, consulte [permisos en el centro de seguridad & cumplimiento](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Antes de implementar directivas, permita a su organización saber los posibles impactos de inscribir un dispositivo en la movilidad y la seguridad básicas. En función de cómo configure las directivas, se puede bloquear el acceso a los dispositivos no compatibles a Microsoft 365 y a los datos, incluidas las aplicaciones instaladas, las fotos y la información personal en un dispositivo inscrito, y los datos se pueden eliminar.

>[!NOTE]
>Las directivas y reglas de acceso creadas en MDM para Microsoft 365 Business Standard reemplazan las directivas de buzón de dispositivo móvil de Exchange ActiveSync y las reglas de acceso de dispositivo creadas en el centro de administración de Exchange. Una vez que un dispositivo está inscrito en MDM para Microsoft 365 Business Standard, se ignora cualquier directiva de buzón de dispositivo móvil de Exchange ActiveSync o regla de acceso de dispositivo aplicada al dispositivo. Para obtener más información acerca de Exchange ActiveSync, vea [Exchange ActiveSync en Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Paso 1: crear una directiva de dispositivo e implementarla en un grupo de prueba

Antes de empezar, asegúrese de que ha activado y configurado la movilidad y la seguridad básicas. Para obtener instrucciones, consulte [Overview of Basic Mobility and Security](overview-of-basic-mobility-and-security-for-microsoft-365.md).

1. En el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleccione **crear una directiva**.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración básica de la Directiva de movilidad y seguridad":::

3. En la página **configuración de directiva** , especifique los requisitos que desea aplicar a los dispositivos móviles de la organización.

4. **Requerir el perfil de correo electrónico de administración**: cuando está habilitado, los dispositivos que no tienen un perfil de correo electrónico administrado por la movilidad y la seguridad básica no se consideran compatibles. Un dispositivo no puede tener un perfil de correo electrónico administrado cuando no es el destino correcto, o si el usuario configura manualmente la cuenta de correo electrónico en el dispositivo. Si **no está habilitada** (opción predeterminada), esta configuración no se evalúa para cumplimiento o no cumplimiento. Para obtener instrucciones sobre cómo los usuarios pueden obtener compatibilidad cuando se selecciona esta opción, vea se [encontró una cuenta de correo electrónico existente](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

5. En la página **¿desea aplicar esta directiva ahora?** , elija los grupos a los que desea aplicar esta Directiva.

6. Seleccione **crear esta directiva**.

La Directiva se inserta en el dispositivo de cada usuario a la que se aplica la Directiva la próxima vez que inicie sesión en Microsoft 365 usando su dispositivo móvil. Si los usuarios no tenían una directiva aplicada a su dispositivo móvil antes, después de implementar la Directiva, recibirán una notificación en el dispositivo que incluye los pasos para inscribir y activar la movilidad y la seguridad básicas. Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device-using-basic-mobility-and-security.md). Hasta que finalice la inscripción en la movilidad y la seguridad básicas hospedadas por el servicio Intune, el acceso al correo electrónico, a OneDrive y a otros servicios estará restringido. Una vez completada la inscripción mediante la aplicación del portal de empresa de Intune, pueden usar los servicios y la Directiva se aplica a su dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Paso 2: comprobar que la Directiva funciona

Una vez que haya creado una directiva de dispositivo, compruebe que la Directiva funciona según lo previsto antes de implementarla en la organización.

1. En el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Seleccione **ver la lista de dispositivos administrados**.
3. Compruebe el estado de los dispositivos de usuario a los que se ha aplicado la directiva. Desea que el **Estado** de los dispositivos se **administre.**
4. También puede realizar una limpieza completa o selectiva en un dispositivo haciendo clic en el botón **restablecimiento de fábrica** o **Quitar datos** de la compañía del botón **administrar** después de seleccionar un dispositivo. Para obtener instrucciones, consulte [borrar un dispositivo móvil en Microsoft 365.

Paso 3: implementar una directiva en su organización

Una vez que haya creado una directiva de dispositivo y haya comprobado que funciona según lo esperado, impleméntela en su organización.

1. En el explorador, escriba: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Seleccione la Directiva que desea implementar y elija **Editar** junto a **grupos aplicados a.**
3. Busque un grupo para agregarlo y haga clic en **seleccionar**.
4. Seleccione **cerrar** y **Cambiar configuración.**
5. Seleccione **cerrar** y **Editar Directiva.**

La Directiva se inserta en el dispositivo móvil de cada usuario a la que se aplica la Directiva la próxima vez que inicie sesión en Microsoft 365 desde su dispositivo móvil. Si los usuarios no han aplicado una directiva a su dispositivo móvil, reciben una notificación en su dispositivo con los pasos para inscribirse y activarlas para la movilidad y la seguridad básicas. Una vez completada la inscripción, la Directiva se aplica a su dispositivo. Para obtener más información, vea [inscribir un dispositivo móvil con la seguridad y la movilidad básicos](enroll-your-mobile-device-using-basic-mobility-and-security.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Paso 4: bloquear el acceso al correo electrónico para dispositivos no compatibles

Para ayudar a proteger la información de la organización, debe bloquear el acceso de la aplicación al correo electrónico de Microsoft 365 para dispositivos móviles que no son compatibles con la movilidad y la seguridad básicas. Para obtener una lista de los dispositivos compatibles, consulte [dispositivos compatibles](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices). 

**Para bloquear el acceso a las aplicaciones:**

1. En el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Seleccione **administrar la configuración de acceso de dispositivo en toda la organización**.
3. Para bloquear dispositivos no compatibles, elija **bloquear** en **si MDM no es compatible con Microsoft 365**y, a continuación, seleccione **Guardar**.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Movilidad básica y opción de acceso a bloque de seguridad":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Paso 5: Elija los grupos de seguridad que desea excluir de las comprobaciones de acceso condicional

Si desea excluir algunas personas de las comprobaciones de acceso condicional en sus dispositivos móviles y ha creado uno o más grupos de seguridad para estas personas, agregue los grupos de seguridad aquí. Las personas de estos grupos no tendrán ninguna directiva aplicada para los dispositivos móviles compatibles. Esta es la opción recomendada si ya no desea usar la movilidad y la seguridad básicas en su organización.

1. En el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleccione **administrar la configuración de acceso de dispositivo en toda la organización**.

    :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Aspectos básicos de la movilidad y la seguridad crear una opción de Directiva":::

3. Seleccione **Agregar** para agregar el grupo de seguridad que tiene usuarios que desea excluir de bloquear el acceso a Microsoft 365. Cuando se agrega un usuario a esta lista, puede acceder al correo electrónico de Microsoft 365 cuando usa un dispositivo no compatible.

4. Seleccione el grupo de seguridad que desea usar en el panel **Seleccionar grupo** .

5. Seleccione el nombre y, a continuación, **Agregar**  >  **Guardar**.

6. En el panel **configuración de acceso de dispositivo en toda la organización** , elija **Guardar**.

    :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Opción básica de movilidad y seguridad permitir acceso":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>¿Cuál es el impacto de las directivas de seguridad en distintos tipos de dispositivos?

Cuando se aplica una directiva a los dispositivos de usuario, el impacto en cada dispositivo varía en cierta medida entre los tipos de dispositivo. Consulte la siguiente tabla para obtener ejemplos del impacto de las directivas en diferentes dispositivos.

|**Directiva de seguridad**|**Android 4 y versiones posteriores**|**Samsung KNOX**|**iOS 6 y versiones posteriores**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada|No|Sí|Sí|se requiere la copia de seguridad cifrada de iOS.|
|Bloquear copia de seguridad de la nube|Sí|Sí|Sí|Bloquear copia de seguridad de Google en Android (atenuado), copia de seguridad de la nube en iOS.|
|Bloquear sincronización de documentos|No|No|Sí|iOS: Bloquear documentos en la nube.|
|Bloquear sincronización de fotos |No|No|Sí|iOS (nativo): Bloquear Photo Stream.|
|Bloquear captura de pantalla |No|Sí|Sí|Se bloquea cuando se intenta.|
|Bloquear videoconferencia |No|No|Sí|FaceTime bloqueado en iOS, no en Skype u otros.|
|Bloquear el envío de datos de diagnóstico |No|Sí|Sí|Bloquear el envío de informes de bloqueo de Google en Android.|
|Bloquear el acceso a la tienda de aplicaciones |No|Sí|Sí|Falta el icono de la tienda de aplicaciones en la página principal de Android, está deshabilitado en Windows, falta en iOS.|
|Requerir contraseña para la tienda de aplicaciones |No|No|Sí|iOS: Contraseña necesaria para las compras de iTunes.|
|Bloquear conexión a almacenamiento extraíble |No|Sí|N/D|Android: la tarjeta SD está atenuada en configuración, Windows notifica al usuario, las aplicaciones instaladas no están disponibles|
|Bloquear conexión Bluetooth |Ver notas|Ver notas|Sí|No se puede deshabilitar BlueTooth como una configuración en Android. En su lugar, se deshabilitan todas las transacciones que requieren BlueTooth: distribución de audio avanzada, control remoto de audio/vídeo, dispositivos de manos libres, auriculares, acceso a la libreta de teléfonos y puerto serie. Cuando se usa cualquiera de estas opciones, aparece un pequeño mensaje de aviso en la parte inferior de la página.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>¿Qué ocurre al eliminar una directiva o quitar un usuario de la directiva?

Cuando se elimina una directiva o se quita un usuario de un grupo en el que se ha implementado la Directiva, la configuración de la Directiva, el perfil de correo electrónico de Microsoft 365 y los correos electrónicos almacenados en caché podrían quitarse del dispositivo del usuario. Consulte la tabla siguiente para ver lo que se ha quitado para los distintos tipos de dispositivos.

|**Elementos quitados**|**iOS 6 y versiones posteriores**|**Android 4 y posterior (incluido Samsung KNOX**|
|:-----|:-----|:----------------------|
|Perfiles de correo electrónico administrado<sup>1</sup>|Sí|No|
|Bloquear copia de seguridad de la nube|Sí|No|
<sup>1</sup> Si la Directiva se implementó con la opción el **Perfil de correo electrónico se administra** seleccionada, el perfil de correo electrónico administrado y los correos electrónicos almacenados en caché de ese perfil se eliminan del dispositivo del usuario.

La Directiva se quita del dispositivo móvil para cada usuario a la que se aplica la Directiva la próxima vez que el dispositivo se desprotege con la movilidad y la seguridad básicas. Si implementa una nueva directiva que se aplica a estos dispositivos de usuario, se le pedirá que vuelva a inscribirse en la movilidad y la seguridad básicas.

También puede borrar un dispositivo, ya sea completamente o borrando selectivamente la información de la organización del dispositivo. Para obtener más información, consulte [borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md). 

## <a name="related-topics"></a>Temas relacionados

[Introducción a la movilidad y la seguridad básicas](overview-of-basic-mobility-and-security-for-microsoft-365.md)

[Capacidades de movilidad y seguridad básicas](capabilities-of-basic-mobility-and-secruity.md)
