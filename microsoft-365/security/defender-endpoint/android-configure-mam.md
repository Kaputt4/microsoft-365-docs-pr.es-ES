---
title: Configuración de señales de riesgo Microsoft Defender para punto de conexión mediante directivas de protección de aplicaciones (MAM)
description: Describe cómo configurar señales de riesgo Microsoft Defender para punto de conexión mediante directivas de App Protection
keywords: microsoft, defender, Microsoft Defender para punto de conexión, mde, android, configuration, MAM, App Protectection Policies, Managed app
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: shthota
author: shthota
manager: dansimp
ms.localizationpriority: medium
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9918763732fa828f17b395a3f96b24e8fbed46f2
ms.sourcegitcommit: d7193ee954c01c4172e228d25b941026c8d92d30
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2022
ms.locfileid: "67174990"
---
# <a name="configure-microsoft-defender-for-endpoint-risk-signals-using-app-protection-policies-mam"></a>Configuración de señales de riesgo Microsoft Defender para punto de conexión mediante directivas de protección de aplicaciones (MAM)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



Microsoft Defender para punto de conexión en Android, que ya protege a los usuarios empresariales en escenarios de Mobile Administración de dispositivos (MDM), ahora amplía la compatibilidad con Mobile App Management (MAM) para los dispositivos que no están inscritos mediante Intune administración de dispositivos móviles (MDM). También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras siguen usando Intune para la administración de aplicaciones móviles (MAM). Esta funcionalidad le permite administrar y proteger los datos de su organización dentro de una aplicación.

Intune directivas de Protección contra aplicaciones aplica Microsoft Defender para punto de conexión en la información de amenazas de Android para proteger estas aplicaciones. Las directivas de protección de aplicaciones (APP) que garantizan los datos de la organización siguen siendo seguras o se encuentran en una aplicación administrada. Una aplicación administrada tiene directivas de protección de aplicaciones aplicadas y se puede administrar mediante Intune.  

Microsoft Defender para punto de conexión en Android admite ambas configuraciones de MAM
- **Intune MDM + MAM**: los administradores de TI solo pueden administrar aplicaciones mediante directivas de protección de aplicaciones en dispositivos inscritos con Intune administración de dispositivos móviles (MDM).
- **MAM sin inscripción de dispositivos**: MAM sin inscripción de dispositivos, o MAM-WE, permite a los administradores de TI administrar aplicaciones mediante [directivas de protección](/mem/intune/apps/app-protection-policy) de aplicaciones en dispositivos no inscritos con Intune MDM. Esta disposición significa que las aplicaciones se pueden administrar mediante Intune en dispositivos inscritos con proveedores de EMM de terceros. Para administrar aplicaciones en ambas configuraciones, los clientes deben usar Intune en el [Centro de administración de Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).

Para habilitar esta funcionalidad, un administrador debe configurar la conexión entre Microsoft Defender para punto de conexión y Intune, crear la directiva de protección de aplicaciones y aplicar la directiva en aplicaciones y dispositivos de destino. 
 
Los usuarios finales también deben realizar pasos para instalar Microsoft Defender para punto de conexión en su dispositivo y activar el flujo de incorporación.


## <a name="admin-prerequisites"></a>Administración requisitos previos

- **Validar que el conector de Microsoft Defender para Endpoint-Intune está habilitado**

  a. Ve a security.microsoft.com. 

  b. Seleccione **Configuración > puntos de conexión> Características avanzadas > Microsoft Intune conexión** está activada.

  c. Si la conexión no está activada, seleccione el botón de alternancia para activarla y, a continuación, seleccione **Guardar preferencias**.

  :::image type="content" source="images/enable-intune-connection.png" alt-text="La sección Características avanzadas del portal de Microsoft 365 Defender" lightbox="images/enable-intune-connection.png":::

  d. Vaya a **Microsoft Endpoint Manager (Intune)** y valide si el conector de Microsoft Defender para Endpoint-Intune está habilitado.

  :::image type="content" source="images/validate-intune-connector.png" alt-text="Panel de estado de intune-connector en el portal de Microsoft 365 Defender" lightbox="images/validate-intune-connector.png":::

- **Habilitación de Microsoft Defender para punto de conexión en Android Connector for App Protection Policy (APP)**
  
  Configure el conector en Intune Microsoft Endpoint Manager para directivas de Protección de aplicaciones:

  a. Vaya a **Administración de inquilinos > Conectores y tokens > Microsoft Defender para punto de conexión**.

  b. Active el botón de alternancia de la directiva de protección de aplicaciones para Android (como se muestra en la captura de pantalla siguiente).

  c. Seleccione **Guardar**.

  :::image type="content" source="images/app-settings.png" alt-text="Panel de configuración de la aplicación en el portal de Microsoft 365 Defender" lightbox="images/app-settings.png":::

- **Crear una directiva de protección de aplicaciones** 
 
Bloquee el acceso o borre los datos de una aplicación administrada en función de Microsoft Defender para punto de conexión señales de riesgo mediante la creación de una directiva de protección de aplicaciones.
Microsoft Defender para punto de conexión se puede configurar para enviar señales de amenaza que se usarán en las directivas de protección de aplicaciones (APP, también conocida como MAM). Con esta funcionalidad, puede usar Microsoft Defender para punto de conexión para proteger las aplicaciones administradas.

1. Crear una directiva <br>
Las directivas de protección de aplicaciones (APP) que garantizan los datos de la organización siguen siendo seguras o se encuentran en una aplicación administrada. Una directiva puede ser una regla que se aplica cuando el usuario intenta acceder o mover datos "corporativos", o un conjunto de acciones que se prohíben o supervisan cuando el usuario está dentro de la aplicación. 

:::image type="content" source="images/create-policy.png" alt-text="La pestaña Crear directiva de la página directivas de Protección de aplicaciones del portal de Microsoft 365 Defender" lightbox="images/create-policy.png":::

2. Agregar aplicaciones <br>
    a. Elija cómo desea aplicar esta directiva a las aplicaciones de distintos dispositivos. A continuación, agregue al menos una aplicación. <br>
    Use esta opción para especificar si esta directiva se aplica a dispositivos no administrados. En Android, puede especificar que la directiva se aplique a dispositivos Android Enterprise, Device Administración o Unmanaged. También puede elegir dirigir la directiva a aplicaciones en dispositivos de cualquier estado de administración.
Debido a que la administración de aplicaciones móviles no requiere la administración de dispositivos, puede proteger los datos de la empresa en dispositivos administrados y no administrados. La administración se centra en la identidad del usuario, lo que elimina la necesidad de administrar dispositivos. Las empresas pueden usar directivas de protección de aplicaciones con o sin MDM al mismo tiempo. Por ejemplo, piense el caso de un empleado que utiliza tanto un teléfono proporcionado por la empresa como su propia tableta personal. El teléfono de la empresa está inscrito en MDM y protegido por directivas de protección de aplicaciones, mientras que el dispositivo personal está protegido únicamente por directivas de protección de aplicaciones.

    b. Seleccionar aplicaciones<br>
    Una aplicación administrada es aquella que tiene las directivas de protección de aplicaciones aplicadas y puede administrarse mediante Intune. Cualquier aplicación que se haya integrado con el [SDK de Intune](/mem/intune/developer/app-sdk) o que esté encapsulada por el [Intune App Wrapping Tool](/mem/intune/developer/apps-prepare-mobile-application-management) se puede administrar mediante Intune directivas de protección de aplicaciones. Consulte la lista oficial de [aplicaciones protegidas de Microsoft Intune](/mem/intune/apps/apps-supported-intune-apps) que se han creado con estas herramientas y están disponibles para uso público.

    *Ejemplo: Outlook como una aplicación administrada*

  :::image type="content" source="images/managed-app.png" alt-text="Panel Aplicaciones públicas en el portal de Microsoft 365 Defender" lightbox="images/managed-app.png":::


 3. Establezca los requisitos de seguridad de inicio de sesión para la directiva de protección. <br>
Seleccione **Establecer > nivel máximo de amenaza de dispositivo permitido** en **Condiciones del dispositivo** y escriba un valor. A continuación, seleccione  **Acción: "Bloquear acceso"**. Microsoft Defender para punto de conexión en Android comparte este nivel de amenaza de dispositivo.

  :::image type="content" source="images/conditional-launch.png" alt-text="Panel Condiciones del dispositivo en el portal de Microsoft 365 Defender" lightbox="images/conditional-launch.png":::
  
- **Asigne grupos de usuarios a los que se debe aplicar la directiva.**<br>
  Seleccione **Grupos incluidos**. A continuación, agregue los grupos pertinentes. 

    :::image type="content" source="images/assignment.png" alt-text="Panel Grupos incluidos en el portal de Microsoft 365 Defender" lightbox="images/assignment.png":::


## <a name="end-user-prerequisites"></a>Requisitos previos del usuario final
- La aplicación de agente debe estar instalada
    - Portal de empresa de Intune
    
- Los usuarios tienen las licencias necesarias para la aplicación administrada y tienen instalada la aplicación.

### <a name="end-user-onboarding"></a>Incorporación del usuario final 

1. Inicie sesión en una aplicación administrada, por ejemplo, Outlook. El dispositivo está registrado y la directiva de protección de aplicaciones se sincroniza con el dispositivo. La directiva de protección de aplicaciones reconoce el estado de mantenimiento del dispositivo.  

2. Seleccione **Continuar**. Se presenta una pantalla que recomienda descargar y configurar Microsoft Defender para punto de conexión en la aplicación Android.

3. Seleccione **Descargar**. Se le redirigirá a la tienda de aplicaciones (Google Play). 

4.  Instale la aplicación Microsoft Defender para punto de conexión (móvil) e inicie la pantalla de incorporación de aplicaciones administradas.

  :::image type="content" source="images/download-mde.png" alt-text="Páginas ilustrativas que contienen el procedimiento de descarga de MDE e inicio de la pantalla de incorporación de aplicaciones" lightbox="images/download-mde.png":::
  

5.  Haga clic en **Continuar > Iniciar**. Se inicia el flujo de incorporación o activación de la aplicación de Microsoft Defender para punto de conexión. Siga los pasos para completar la incorporación. Se le redirigirá automáticamente a la pantalla de incorporación de aplicaciones administradas, lo que ahora indica que el dispositivo está en buen estado.

6. Seleccione **Continuar** para iniciar sesión en la aplicación administrada. 

### <a name="configure-privacy-controls"></a>Configuración de controles de privacidad 
Los administradores pueden usar los pasos siguientes para habilitar la privacidad y no recopilar el nombre de dominio, los detalles de la aplicación y la información de red como parte del informe de alertas de las amenazas correspondientes.

1. En el Centro de administración de Microsoft Endpoint Manager, vaya a **Aplicaciones > Directivas de configuración de aplicaciones > Agregar aplicaciones administradas >**.

2. Asignar a la directiva un **nombre**.

3. En Seleccionar aplicaciones públicas, elija **Microsoft Defender para punto de conexión** como la aplicación de destino.

4. En la página Configuración, en Configuración general, agregue **DefenderExcludeURLInReport**, **DefenderExcludeAppInReport** como las claves y el valor como true.

5. Asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en false.

6. Revise y cree la directiva.

## <a name="optional-permissions"></a>Permisos opcionales 

Microsoft Defender para punto de conexión en Android habilita permisos opcionales en el flujo de incorporación. Actualmente, los permisos requeridos por MDE son obligatorios en el flujo de incorporación. Con esta característica, el administrador puede implementar MDE en dispositivos Android con directivas MAM sin aplicar los permisos obligatorios de VPN y accesibilidad durante la incorporación. Los usuarios finales pueden incorporar la aplicación sin los permisos obligatorios y pueden revisarlos más adelante. 

### <a name="configure-optional-permission"></a>Configuración del permiso opcional

Siga estos pasos para habilitar permisos opcionales para dispositivos.

1. En el Centro de administración de Microsoft Endpoint Manager, vaya a **Aplicaciones > Directivas de configuración de aplicaciones > Agregar aplicaciones administradas >**.

2. Asignar a la directiva un **nombre**.

3. Seleccione **Microsoft Defender para punto de conexión*** en aplicaciones públicas.

4. En la página Configuración, seleccione **Usar diseñador de configuración** y agregue **DefenderOptionalVPN** o **DefenderOptionalAccessibility** o **como** tipo de clave y valor como booleano. 

5. Para habilitar permisos opcionales, escriba el valor como **true** y asigne esta directiva a los usuarios. De forma predeterminada, este valor se establece en false.
Para los usuarios con el conjunto de claves como true, los usuarios podrán incorporar la aplicación sin conceder estos permisos.

6. Seleccione **Siguiente** y asigne este perfil a los dispositivos o usuarios de destino.

### <a name="user-flow"></a>Flujo de usuario 

Los usuarios pueden instalar y abrir la aplicación para iniciar el proceso de incorporación.

1. Si un administrador tiene la configuración Permisos opcionales, los usuarios pueden optar por omitir el permiso vpn o de accesibilidad o ambos y completar la incorporación.
2. Incluso si el usuario ha omitido estos permisos, el dispositivo podrá incorporarse y se enviará un latido.
3. Dado que los permisos están deshabilitados, la protección web no estará activa. Estará parcialmente activo si se concede uno de los permisos.
4. Más adelante, los usuarios pueden habilitar la protección web desde dentro de la aplicación. Esto instalará la configuración de VPN en el dispositivo.

>[!NOTE] 
> La configuración Permisos opcionales es diferente de la opción Deshabilitar protección web. Los permisos opcionales solo ayudan a omitir los permisos durante la incorporación, pero está disponible para que el usuario final revise y habilite más adelante, mientras que Deshabilitar protección web permite a los usuarios incorporar la aplicación Microsoft Defender para punto de conexión sin La protección web. No se puede habilitar más adelante.

## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
