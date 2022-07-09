---
title: Solución de problemas de incorporación relacionados con la administración de seguridad para Microsoft Defender para punto de conexión
description: Solucione los problemas que puedan surgir durante la incorporación de dispositivos mediante Security Management para Microsoft Defender para punto de conexión.
keywords: solución de problemas de incorporación, incorporación, visor de eventos, recopilación de datos y compilaciones de versión preliminar, datos y diagnósticos del sensor
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 0ceb24b5da0947dbb2b79ca7560ffbb46b701b38
ms.sourcegitcommit: 2aa5c026cc06ed39a9c1c2bcabd1f563bf5a1859
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2022
ms.locfileid: "66696280"
---
# <a name="troubleshoot-onboarding-issues-related-to-security-management-for-microsoft-defender-for-endpoint"></a>Solución de problemas de incorporación relacionados con la administración de seguridad para Microsoft Defender para punto de conexión

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Se aplica a:**

- [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender para punto de conexión](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Administración de seguridad para Microsoft Defender para punto de conexión es una funcionalidad para dispositivos que no están administrados por un Endpoint Manager de Microsoft, ya sea Microsoft Intune o punto de conexión de Microsoft Configuration Manager , para recibir configuraciones de seguridad para Microsoft Defender para punto de conexión directamente desde Endpoint Manager.
Para obtener más información sobre la administración de seguridad para Microsoft Defender para punto de conexión, consulte [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration).

Para obtener instrucciones de incorporación de security management para Microsoft Defender para punto de conexión, consulte [Microsoft Defender para punto de conexión Security Configuration Management](security-config-management.md)

Esta incorporación de un extremo a otro está diseñada para no tener fricción y no requiere la entrada del usuario. Sin embargo, si encuentra problemas durante la incorporación, puede ver y solucionar errores dentro de la plataforma de Microsoft Defender para punto de conexión.

> [!NOTE]
> Si tiene problemas con el flujo de incorporación para nuevos dispositivos, revise los [requisitos previos de Microsoft Defender para punto de conexión](/mem/intune/protect/mde-security-integration#prerequisites) y asegúrese de que se siguen las instrucciones de incorporación.

Para obtener más información sobre el analizador de cliente, consulte [Solución de problemas de estado del sensor mediante Microsoft Defender para punto de conexión Analizador de cliente](/microsoft-365/security/defender-endpoint/overview-client-analyzer).

## <a name="registering-domain-joined-computers-with-azure-active-directory"></a>Registro de equipos unidos a un dominio con Azure Active Directory

Para registrar correctamente los dispositivos en Azure Active Directory, deberá asegurarse de lo siguiente:

- Los equipos pueden autenticarse con el controlador de dominio
- Los equipos tienen acceso a los siguientes recursos de Microsoft desde la red de su organización:
  - /windows/iot/iot-enterprise/commercialization/licensing
  - https://login.microsoftonline.com
  - https://device.login.microsoftonline.com
- Azure AD Connect está configurado para sincronizar los objetos de equipo. De forma predeterminada, las unidades organizativas del equipo se encuentran en el ámbito de sincronización de Azure AD Connect. Si los objetos de equipo pertenecen a unidades organizativas (OU) específicas, configure las unidades organizativas para que se sincronicen en Azure AD Connect. Para más información sobre cómo sincronizar objetos de equipo mediante Azure AD Connect, consulte [Filtrado basado en unidades organizativas](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering#organizational-unitbased-filtering).

> [!IMPORTANT]
> Azure AD Connect no sincroniza Windows Server 2012 objetos de equipo R2. Si necesita registrarlos en Azure AD for Security Management para Microsoft Defender para punto de conexión, deberá personalizar la regla de sincronización de Azure AD Connect para incluir esos objetos de equipo en el ámbito de sincronización. Consulte [Instrucciones para aplicar la regla de unión a equipos en Azure Active Directory Connect]().

> [!NOTE]
> Para completar correctamente el flujo de incorporación e independientemente del sistema operativo de un dispositivo, el estado de Azure Active Directory de un dispositivo puede cambiar en función del estado inicial de los dispositivos:
>
> <br>
>
>|Inicio del estado del dispositivo|Nuevo estado del dispositivo|
>|---|---|
>|Ya AADJ o HAADJ|Permanece tal y como está|
>|No AADJ ni Unión a Azure Active Directory híbrido (HAADJ) + Unido a un dominio|El dispositivo es HAADJ'd|
>|No AADJ o HAADJ + No unido a un dominio|El dispositivo es AADJ'd|
>
> Donde AADJ representa Unido a Azure Active Directory y HAADJ representa Unido a Azure Active Directory híbrido.

## <a name="troubleshoot-errors-from-the-microsoft-defender-for-endpoint-portal"></a>Solución de problemas de errores del portal de Microsoft Defender para punto de conexión

A través del portal de Microsoft Defender para punto de conexión, los administradores de seguridad ahora pueden solucionar problemas de administración de seguridad para la incorporación de Microsoft Defender para punto de conexión.

En **Administración de** configuración, se ha agregado el widget **Onboarded via MDE security management (Incorporación mediante administración de seguridad de MDE**) para presentar el desglose del estado de inscripción de los dispositivos administrados por Microsoft Defender para punto de conexión.

Para ver una lista de todos los dispositivos administrados por Microsoft Defender para punto de conexión, seleccione **Ver todos los dispositivos administrados por MDE**.

En la lista, si el estado de inscripción de un dispositivo no es "Correcto", seleccione el dispositivo para ver los detalles de la solución de problemas en el panel lateral, apuntando a la causa principal del error y la documentación correspondiente.


:::image type="content" source="./images/secconfig-mde-error.png" alt-text="Criterios de filtro aplicados en la página de inventario de dispositivos" lightbox="./images/secconfig-mde-error.png":::

> [!NOTE] 
> Somos conscientes de un problema que afecta a la detección precisa de MDM de terceros al intentar usar la característica de administración de seguridad y estamos trabajando en una corrección. 

## <a name="run-microsoft-defender-for-endpoint-client-analyzer-on-windows"></a>Ejecución de Microsoft Defender para punto de conexión Client Analyzer en Windows

Considere la posibilidad de ejecutar el Analizador de cliente en puntos de conexión que no pueden completar la administración de seguridad para Microsoft Defender para punto de conexión flujo de incorporación. Para obtener más información sobre el analizador de cliente, consulte [Solución de problemas de estado del sensor mediante Microsoft Defender para punto de conexión Analizador de cliente](overview-client-analyzer.md).

El archivo de salida de Client Analyzer (MDE Client Analyzer Results.htm) puede proporcionar información clave de solución de problemas:

- Compruebe que el sistema operativo del dispositivo está en el ámbito de Administración de seguridad para Microsoft Defender para punto de conexión flujo de incorporación en la sección **Detalles generales del dispositivo**.
- Compruebe que el dispositivo se ha registrado correctamente en Azure Active Directory en **Detalles de administración de configuración de dispositivos**.

  :::image type="content" source="images/client-analyzer-results.png" alt-text="Resultados del analizador de cliente" lightbox="images/client-analyzer-results.png":::

En la sección **Resultados detallados** del informe, el Analizador de cliente también proporciona instrucciones accionables.

> [!TIP]
> Asegúrese de que la sección Resultados detallados del informe no incluya ningún "Error" y asegúrese de revisar todos los mensajes de "Advertencia".

Por ejemplo, como parte del flujo de incorporación de Administración de seguridad, es necesario que el identificador de inquilino de Azure Active Directory del inquilino de Microsoft Defender para punto de conexión coincida con el identificador de inquilino scp que aparece en la sección **Detalles de administración de configuración de** dispositivos de los informes. Si procede, la salida del informe le recomendará realizar esta comprobación.

:::image type="content" source="images/detailed-results.png" alt-text="La página que muestra los resultados detallados" lightbox="images/detailed-results.png"

## <a name="general-troubleshooting"></a>Solución de problemas generales

Si no pudo identificar el dispositivo incorporado en AAD o MEM y no recibió un error durante la inscripción, comprobar la clave `Computer\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SenseCM\\EnrollmentStatus` del Registro puede proporcionar información adicional sobre la solución de problemas.

:::image type="content" source="images/enrollment-status.png" alt-text="Página que muestra el estado de la inscripción" lightbox="images/enrollment-status.png":::

En la tabla siguiente se enumeran los errores y las instrucciones sobre lo que se debe intentar o comprobar para solucionar el error. Tenga en cuenta que la lista de errores no está completa y se basa en los errores típicos o comunes encontrados por los clientes en el pasado:

|Código de error|Estado de inscripción|Acciones de administrador|
|---|---|---|
|`5-7`, `9`, `11-12`, `26-33`|Error general|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de la configuración de seguridad. Esto podría deberse a que el dispositivo no cumple [los requisitos previos para Microsoft Defender para punto de conexión canal de administración](security-config-management.md). La ejecución del [Analizador de cliente](https://aka.ms/BetaMDEAnalyzer) en el dispositivo puede ayudar a identificar la causa principal del problema. Si esto no ayuda, póngase en contacto con el soporte técnico.|
| `8`, `44` | Problema de configuración de Microsoft Endpoint Manager | El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, Microsoft Endpoint Manager no se ha configurado a través del Centro de Administración para permitir la configuración de seguridad de Microsoft Defender para punto de conexión. Asegúrese de que el [inquilino de Microsoft Endpoint Manager está configurado y de que la característica está activada](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-microsoft-defender-for-endpoint-security-configuration-management).|
|`13-14`,`20`,`24`,`25`|Problema de conectividad|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de la configuración de seguridad que podría deberse a un problema de conectividad. Compruebe que los [puntos de conexión de Azure Active Directory y Microsoft Endpoint Manager](security-config-management.md#connectivity-requirements) están abiertos en el firewall.|
|`10`,`42`|Error general de unión híbrida|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de la configuración de seguridad y el sistema operativo no pudo realizar la unión híbrida. Use [Solución de problemas de dispositivos híbridos unidos a Azure Active Directory](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-current) para solucionar errores de unión híbrida en el nivel de sistema operativo.|
|`15`|Error de coincidencia del inquilino|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de la configuración de seguridad porque el identificador de inquilino de Microsoft Defender para punto de conexión no coincide con el identificador de inquilino de Azure Active Directory. Asegúrese de que el identificador de inquilino de Azure Active Directory del inquilino de Defender para punto de conexión coincide con el identificador de inquilino en la entrada SCP del dominio. Para obtener más información, [solucione los problemas de incorporación relacionados con la administración de seguridad para Microsoft Defender para punto de conexión](troubleshoot-security-config-mgt.md).|
|`16`,`17`|Error híbrido: punto de conexión de servicio|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, el registro de punto de conexión de servicio (SCP) no está configurado correctamente y el dispositivo no se pudo unir a Azure AD. Esto podría deberse a que el SCP se configura para unirse a Enterprise DRS. Asegúrese de que el registro SCP apunta a AAD y SCP está configurado siguiendo los procedimientos recomendados. Para obtener más información, vea [Configurar un punto de conexión de servicio](/azure/active-directory/devices/hybrid-azuread-join-manual#configure-a-service-connection-point).|
|`18`|Error de certificado|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de configuración de seguridad debido a un error de certificado de dispositivo. El certificado de dispositivo pertenece a un inquilino diferente. Compruebe que se siguen los procedimientos recomendados al crear [perfiles de certificado de confianza](/mem/intune/protect/certificates-trusted-root#create-trusted-certificate-profiles).|
|`36` , `37`| Configuración incorrecta de AAD Connect |El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de configuración de seguridad debido a una configuración incorrecta en AAD Connect. Para identificar lo que impide que el dispositivo se registre en AAD, considere la posibilidad de ejecutar la [herramienta solucionador de problemas de registro de dispositivos](/samples/azure-samples/dsregtool/dsregtool). Para Windows Server 2012 R2, ejecute las [instrucciones de solución de problemas dedicadas](/azure/active-directory/devices/troubleshoot-hybrid-join-windows-legacy).  |
|`38`,`41`|Error de DNS|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de la configuración de seguridad debido a un error de DNS. Compruebe la conexión a Internet o la configuración de DNS en el dispositivo. La configuración de DNS no válida podría estar en el lado de la estación de trabajo. Active Directory requiere que use DNS de dominio para funcionar correctamente (y no la dirección del enrutador). Para obtener más información, consulte [Solución de problemas de incorporación relacionados con la administración de seguridad para Microsoft Defender para punto de conexión](troubleshoot-security-config-mgt.md).|
|`40`|Problema de sincronización de reloj|El dispositivo se incorporó correctamente a Microsoft Defender para punto de conexión. Sin embargo, se produjo un error en el flujo de administración de la configuración de seguridad. Compruebe que el reloj está configurado correctamente y que se sincroniza en el dispositivo donde se produce el error.|
|`43`|MDE y ConfigMgr|El dispositivo se administra mediante Configuration Manager y Microsoft Defender para punto de conexión. El control de directivas a través de ambos canales puede provocar conflictos y resultados no deseados. Para evitar esto, las directivas de seguridad de punto de conexión deben estar aisladas en un único plano de control. |

## <a name="azure-active-directory-runtime-troubleshooting"></a>Solución de problemas de Azure Active Directory Runtime

El mecanismo principal para solucionar problemas de Azure Active Directory Runtime (AADRT) es recopilar seguimientos de depuración. Azure Active Directory Runtime en Windows usa **el proveedor ETW con el identificador bd67e65c-9cc2-51d8-7399-0bb9899e75c1**. Los seguimientos ETW deben capturarse con la reproducción del error (por ejemplo, si se produce un error de combinación, los seguimientos deben estar habilitados durante el tiempo que se cubren las llamadas a las API de AADRT para realizar la unión).

Consulte a continuación un error típico en el registro de AADRT y cómo leerlo:

:::image type="content" source="images/event-properties.png" alt-text="Página de propiedades del evento" lightbox="images/event-properties.png":::

A partir de la información del mensaje, es posible en la mayoría de los casos comprender qué error se encontró, qué API win32 devolvió el error (si procede), qué dirección URL (si procede) se usó y qué error de API de tiempo de ejecución de AAD se encontró.

## <a name="instructions-for-applying-computer-join-rule-in-aad-connect"></a>Instrucciones para aplicar la regla de unión al equipo en AAD Connect

Para la administración de seguridad para Microsoft Defender para punto de conexión en equipos unidos a Windows Server 2012 dominio R2, se necesita una actualización de la regla de sincronización de Azure AD Connect "In from AD-Computer Join" (In from AD-Computer Join). Esto se puede lograr mediante la clonación y modificación de la regla, que deshabilitará la regla original "In from AD - Computer Join". Azure AD Connect ofrece esta experiencia de forma predeterminada para realizar cambios en las reglas integradas.

> [!NOTE]
>Estos cambios deben aplicarse en el servidor donde se ejecuta AAD Connect. Si tiene varias instancias de AAD Connect implementadas, estos cambios se deben aplicar a todas las instancias.

1. Abra la aplicación Editor de reglas de sincronización desde el menú inicio. En la lista de reglas, busque la regla denominada **In from AD – Computer Join (In from AD – Computer Join).** **Tome nota del valor de la columna "Precedencia" de esta regla.**

   :::image type="content" source="images/57ea94e2913562abaf93749d306dd6cf.png" alt-text="Editor de reglas de sincronización" lightbox="images/57ea94e2913562abaf93749d306dd6cf.png":::

2. Con la regla **In from AD – Computer Join (In from AD – Computer Join** ) resaltada, seleccione **Editar**. En el cuadro de diálogo **Editar confirmación de regla reservada** , seleccione **Sí**.

   :::image type="content" source="images/8854440d6180a5580efda24110551c68.png" alt-text="Página de confirmación de la regla reservada de edición" lightbox="images/8854440d6180a5580efda24110551c68.png":::

3. Se mostrará la ventana **Editar regla de sincronización de entrada** . Actualice la descripción de la regla para tener en cuenta que Windows Server 2012R2 se sincronizará con esta regla. Deje todas las demás opciones sin modificar, excepto el valor precedencia. Escriba un valor para Precedencia que sea mayor que el valor de la regla original (como se muestra en la lista de reglas).

   :::image type="content" source="images/ee0f29162bc3f2fbe666c22f14614c45.png" alt-text="Página Editar regla de sincronización de entrada en la que se escriben valores" lightbox="images/ee0f29162bc3f2fbe666c22f14614c45.png":::

4. Seleccione **Siguiente** tres veces. Esto navegará a la sección "Transformaciones" de la regla. No realice ningún cambio en las secciones "Filtro de ámbito" y "Reglas de combinación" de la regla. Ahora se debe mostrar la sección "Transformaciones".

   :::image type="content" source="images/296f2c2a705e41233631c3784373bc23.png" alt-text="Regla de sincronización de entrada" lightbox="images/296f2c2a705e41233631c3784373bc23.png":::

5. Desplácese hasta la parte inferior de la lista de transformaciones. Busque la transformación del atributo **cloudFiltered** . En el cuadro de texto de la columna **Origen** , seleccione todo el texto (Control-A) y elimínelo. El cuadro de texto ahora debe estar vacío.

6. Pegue el contenido de la nueva regla en el cuadro de texto.

    ```command
    IIF(
      IsNullOrEmpty([userCertificate])
      ||
      (
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        &&
        (Left([operatingSystemVersion],2) = "6.")
        &&
        (Left([operatingSystemVersion],3) <> "6.3")
      )
      ||
      (
        (Left([operatingSystemVersion],3) = "6.3")
        &&
        (InStr(UCase([operatingSystem]),"WINDOWS") > 0)
        &&
        With(
          $validCerts,
          Where(
            $c,
            [userCertificate],
            IsCert($c) && CertNotAfter($c) > Now() && RegexIsMatch(CertSubject($c), "CN=[{]*" & StringFromGuid([objectGUID]) & "[}]*", "IgnoreCase")),
          Count($validCerts) = 0)
      ),
      True,
      NULL
    )
    ```

7. Seleccione **Guardar** para guardar la nueva regla.

> [!NOTE]
> Una vez realizado este cambio de regla, se necesitará una sincronización completa de Active Directory. En entornos grandes, se recomienda programar este cambio de regla y la sincronización completa durante los períodos de silencio de Active Directory local.

## <a name="related-topic"></a>Tema relacionado

- [Administración de Microsoft Defender para punto de conexión en dispositivos con Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
