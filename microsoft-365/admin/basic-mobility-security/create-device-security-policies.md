---
title: Crear directivas de seguridad de dispositivos en Movilidad y seguridad básicas
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
description: Usa Movilidad y seguridad básicas para crear directivas de dispositivo que protejan la información de la organización.
ms.openlocfilehash: f31930f1a753259622520e50da8c255e7cd410e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904293"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Crear directivas de seguridad de dispositivos en Movilidad y seguridad básicas

Puedes usar Movilidad y seguridad básicas para crear directivas de dispositivo que ayuden a proteger la información de la organización en Microsoft 365 contra el acceso no autorizado. Puedes aplicar directivas a cualquier dispositivo móvil de la organización donde el usuario del dispositivo tenga una licencia de Microsoft 365 aplicable y haya inscrito el dispositivo en Movilidad y seguridad básicas.

## <a name="before-you-begin"></a>Antes de empezar

> [!IMPORTANT]
> Para poder crear una directiva de dispositivo móvil, debes activar y configurar La movilidad y la seguridad básicas. Para obtener más información, consulta Overview of Basic Mobility and Security.

- Obtén información sobre los dispositivos, las aplicaciones de dispositivos móviles y la configuración de seguridad que admite movilidad básica y seguridad. Vea [Capabilities of Basic Mobility and Security](capabilities.md).
- Cree grupos de seguridad que incluyan usuarios de Microsoft 365 a los que desee implementar directivas y para los usuarios que desee excluir del acceso bloqueado a Microsoft 365. Antes de implementar una nueva directiva en la organización, se recomienda probarla implementándola para un número reducido de usuarios. Puede crear y usar un grupo de seguridad que incluya solo usted o un número reducido de usuarios de Microsoft 365 que puedan probar la directiva por usted. Para obtener más información acerca de los grupos de seguridad, vea [Crear, editar o eliminar un grupo de seguridad.](../email/create-edit-or-delete-a-security-group.md)
- Para crear e implementar directivas básicas de movilidad y seguridad en Microsoft 365, debe ser administrador global de Microsoft 365. Para obtener más información, consulta [Permisos en el Centro de seguridad & cumplimiento](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Antes de implementar directivas, haga que su organización conozca los posibles impactos de inscribir un dispositivo en Movilidad y seguridad básicas. Según cómo configure las directivas, los dispositivos no compatibles pueden bloquearse para acceder a Microsoft 365 y los datos, incluidas las aplicaciones instaladas, las fotos y la información personal de un dispositivo inscrito, y los datos se pueden eliminar.

>[!NOTE]
>Las directivas y las reglas de acceso creadas en Basic Mobility and Security for Microsoft 365 Business Standard invalidan Exchange ActiveSync directivas de buzón de dispositivo móvil y reglas de acceso de dispositivos creadas en el Centro de administración de Exchange. Una vez que un dispositivo se inscribe en Basic Mobility and Security for Microsoft 365 Business Standard Exchange ActiveSync, se omite cualquier directiva de buzón de dispositivo móvil o regla de acceso de dispositivo que se aplique al dispositivo. Para obtener más información sobre Exchange ActiveSync, vea [Exchange ActiveSync en Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Paso 1: Crear una directiva de dispositivo e implementarla en un grupo de pruebas

Antes de empezar, asegúrese de que ha activado y configurado La movilidad y la seguridad básicas. Para obtener instrucciones, vea [Overview of Basic Mobility and Security](overview.md).

1. Desde el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Seleccione **Crear una directiva**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Configuración de directivas básicas de movilidad y seguridad":::

3. En la **página Configuración de directiva,** especifique los requisitos que desea aplicar a los dispositivos móviles de su organización.

4. **Requerir la administración de perfiles de** correo electrónico: cuando se habilita, los dispositivos que no tienen un perfil de correo electrónico administrado por Basic Mobility and Security se consideran no compatibles. Un dispositivo no puede tener un perfil de correo electrónico administrado cuando no está dirigido correctamente o si el usuario configura manualmente la cuenta de correo electrónico en el dispositivo. Cuando lo deja **No** habilitado (predeterminado), esta configuración no se evalúa para el cumplimiento o el incumplimiento. Para obtener instrucciones sobre cómo los usuarios pueden cumplir con esta opción cuando se selecciona esta opción, vea [Se encontró una cuenta de correo electrónico existente.](/intune-user-help/existing-company-email-account-found)

5. En la página ¿Desea aplicar esta directiva **ahora?,** elija los grupos a los que desea aplicar esta directiva.

6. Seleccione **Crear esta directiva**.

La directiva se inserta en el dispositivo de cada usuario que la directiva se aplica a la próxima vez que inicie sesión en Microsoft 365 con su dispositivo móvil. Si los usuarios no han aplicado una directiva a su dispositivo móvil antes, después de implementar la directiva, obtienen una notificación en su dispositivo que incluye los pasos para inscribirse y activar la movilidad y seguridad básicas. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md) Hasta que completen la inscripción en Movilidad básica y seguridad hospedada por el servicio de Intune, el acceso al correo electrónico, OneDrive y otros servicios está restringido. Después de completar la inscripción mediante la aplicación Portal de empresa de Intune, pueden usar los servicios y la directiva se aplica a su dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Paso 2: Comprobar que la directiva funciona

Después de crear una directiva de dispositivo, comprueba que la directiva funciona como esperas antes de implementarla en tu organización.

1. Desde el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Seleccione **Ver la lista de dispositivos administrados**.
3. Compruebe el estado de los dispositivos de usuario a los que se ha aplicado la directiva. Desea que el **estado de** los dispositivos sea **Administrado.**
4. También puedes realizar una eliminación completa o selectiva en  un dispositivo  haciendo clic en Restablecimiento de fábrica o Quitar datos de la empresa desde el botón Administrar después de seleccionar un dispositivo.  Para obtener instrucciones, consulta [Borrar un dispositivo móvil en Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Paso 3: Implementar una directiva en su organización

Después de crear una directiva de dispositivo y comprobar que funciona según lo esperado, impleméntela en su organización.

1. Desde el tipo de explorador: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Seleccione la directiva que desea implementar y elija **Editar** junto a **Grupos aplicados.**
3. Busque un grupo para agregar y haga clic en **Seleccionar**.
4. Seleccione **Cerrar** y **cambiar la configuración.**
5. Seleccione **Cerrar** y **editar directiva.**

La directiva se inserta en el dispositivo móvil de cada usuario que la directiva se aplica a la próxima vez que inicie sesión en Microsoft 365 desde su dispositivo móvil. Si los usuarios no han aplicado una directiva a su dispositivo móvil, obtienen una notificación en su dispositivo con los pasos necesarios para inscribirla y activarla para movilidad y seguridad básicas. Una vez completada la inscripción, la directiva se aplica a su dispositivo. Para obtener más información, consulta [Inscribir el dispositivo móvil con Movilidad y seguridad básicas.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Paso 4: Bloquear el acceso de correo electrónico para dispositivos no compatibles

Para ayudar a proteger la información de la organización, debes bloquear el acceso de la aplicación al correo electrónico de Microsoft 365 para dispositivos móviles que no son compatibles con movilidad y seguridad básicas. Para obtener una lista de dispositivos compatibles, consulta [Dispositivos compatibles.](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices)

**Para bloquear el acceso a la aplicación:**

1. Desde el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selecciona **Administrar la configuración de acceso de dispositivos en toda la organización.**
3. Para bloquear dispositivos no  compatibles, elija Bloquear en Si un dispositivo no es compatible con Movilidad básica y seguridad para **Microsoft 365** y, a continuación, **seleccione Guardar**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Opción de acceso bloqueado de movilidad básica y seguridad":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Paso 5: Elija los grupos de seguridad que desea excluir de las comprobaciones de acceso condicional

Si desea excluir algunas personas de las comprobaciones de acceso condicional en sus dispositivos móviles y ha creado uno o más grupos de seguridad para estas personas, agregue los grupos de seguridad aquí. Las personas de estos grupos no tendrán directivas aplicadas para sus dispositivos móviles compatibles. Esta es la opción recomendada si ya no desea usar movilidad y seguridad básicas en su organización.

1. Desde el explorador, escriba [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selecciona **Administrar la configuración de acceso de dispositivos en toda la organización.**

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Movilidad básica y seguridad crear una opción de directiva":::

3. Seleccione **Agregar** para agregar el grupo de seguridad que tiene usuarios que desea excluir de haber bloqueado el acceso a Microsoft 365. Cuando un usuario se ha agregado a esta lista, puede tener acceso al correo electrónico de Microsoft 365 cuando usa un dispositivo no compatible.

4. Seleccione el grupo de seguridad que desea usar en el **panel Seleccionar** grupo.

5. Seleccione el nombre y, a **continuación,**  >  **Agregue Guardar**.

6. En el panel **Configuración de acceso a dispositivos de toda la** organización, elija **Guardar**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Opción básica de movilidad y seguridad para permitir el acceso":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>¿Cuál es el impacto de las directivas de seguridad en distintos tipos de dispositivos?

Cuando aplicas una directiva a los dispositivos de usuario, el impacto en cada dispositivo varía un poco entre los tipos de dispositivo. Consulte la siguiente tabla para obtener ejemplos del impacto de las directivas en diferentes dispositivos.

|**Directiva de seguridad**|**Android 4 y versiones posteriores**|**Samsung KNOX**|**iOS 6 y versiones posteriores**|**Notas**|
|:-----|:-----|:-----|:-----|:-----|
|Requerir copia de seguridad cifrada|No|Sí|Sí|Se requiere una copia de seguridad cifrada de iOS.|
|Bloquear copia de seguridad de la nube|Sí|Sí|Sí|Bloquear copia de seguridad de Google en Android (atenuado), copia de seguridad de la nube en iOS.|
|Bloquear sincronización de documentos|No|No|Sí|iOS: Bloquear documentos en la nube.|
|Bloquear sincronización de fotos |No|No|Sí|iOS (nativo): Bloquear Photo Stream.|
|Bloquear captura de pantalla |No|Sí|Sí|Se bloquea cuando se intenta.|
|Bloquear videoconferencia |No|No|Sí|FaceTime bloqueado en iOS, no en Skype u otros usuarios.|
|Bloquear el envío de datos de diagnóstico |No|Sí|Sí|Bloquear el envío de informes de bloqueo de Google en Android.|
|Bloquear el acceso a la tienda de aplicaciones |No|Sí|Sí|Falta el icono de la tienda de aplicaciones en la página principal de Android, está deshabilitado en Windows, falta en iOS.|
|Requerir contraseña para la tienda de aplicaciones |No|No|Sí|iOS: Contraseña necesaria para las compras de iTunes.|
|Bloquear conexión a almacenamiento extraíble |No|Sí|N/D|Android: la tarjeta SD está atenuada en la configuración, Windows notifica al usuario, las aplicaciones instaladas no están disponibles|
|Bloquear conexión Bluetooth |Ver notas|Ver notas|Sí|No podemos deshabilitar BlueTooth como una configuración en Android. En su lugar, deshabilitamos todas las transacciones que requieren BlueTooth: Distribución avanzada de audio, control remoto de audio y vídeo, dispositivos manos libres, auriculares, acceso a la libreta de teléfonos y puerto serie. Cuando se usa cualquiera de estas opciones, aparece un pequeño mensaje de aviso en la parte inferior de la página.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>¿Qué ocurre al eliminar una directiva o quitar un usuario de la directiva?

Al eliminar una directiva o quitar un usuario de un grupo en el que se implementó la directiva, la configuración de la directiva, el perfil de correo electrónico de Microsoft 365 y los correos electrónicos almacenados en caché podrían quitarse del dispositivo del usuario. Consulta la tabla siguiente para ver qué se quita para los distintos tipos de dispositivos.

|**Lo que se quitó**|**iOS 6 y versiones posteriores**|**Android 4 y versiones posteriores (incluido Samsung KNOX**|
|:-----|:-----|:-----|
|Perfiles de correo electrónico<sup>administrados 1</sup>|Sí|No|
|Bloquear copia de seguridad de la nube|Sí|No|

<sup>1</sup> Si la directiva se implementó con la opción **Perfil** de correo electrónico seleccionado, el perfil de correo electrónico administrado y los correos electrónicos almacenados en caché en ese perfil se eliminarán del dispositivo de usuario.

La directiva se quita del dispositivo móvil para cada usuario, la directiva se aplica a la próxima vez que el dispositivo se comprueba con movilidad y seguridad básicas. Si implementas una nueva directiva que se aplica a estos dispositivos de usuario, se les pedirá que vuelvan a inscribirse en Movilidad y seguridad básicas.

También puedes borrar un dispositivo completamente o borrar selectivamente la información de la organización del dispositivo. Para obtener más información, [consulta Borrar un dispositivo móvil en Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Temas relacionados

[Información general sobre Movilidad y seguridad básicas](overview.md)

[Capacidades de Movilidad y seguridad básicas](capabilities.md)