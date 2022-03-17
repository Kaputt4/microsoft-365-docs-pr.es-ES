---
title: Configurar Microsoft Defender para señales de riesgo de extremo mediante directivas de protección de aplicaciones (MAM)
description: Describe cómo configurar Microsoft Defender para señales de riesgo de extremo con directivas de App Protection
keywords: microsoft, defender, Microsoft Defender para Endpoint, mde, android, configuration, MAM, App Protectection Policies, Managed app
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
ms.openlocfilehash: 5c18d5e9fbf628f5d4e4373b866fa300c193ac30
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525534"
---
# <a name="configure-microsoft-defender-for-endpoint-risk-signals-using-app-protection-policies-mam"></a>Configurar Microsoft Defender para señales de riesgo de extremo mediante directivas de protección de aplicaciones (MAM)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Se aplica a:**
- [Microsoft Defender para punto de conexión Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender para punto de conexión Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



Microsoft Defender para Endpoint en Android, que ya protege a los usuarios empresariales en escenarios de administración de dispositivos móviles (MDM), ahora amplía la compatibilidad con Mobile App Management (MAM), para dispositivos que no están inscritos con la administración de dispositivos móviles (MDM) de Intune. También amplía esta compatibilidad a los clientes que usan otras soluciones de administración de movilidad empresarial, mientras que sigue usando Intune para la administración de aplicaciones móviles (MAM). Esta funcionalidad le permite administrar y proteger los datos de su organización dentro de una aplicación.

Las directivas de Protección de aplicaciones de Intune aprovechan la información de las amenazas de Microsoft Defender para Endpoint en Android para proteger estas aplicaciones. Las directivas de protección de aplicaciones (APP) que garantizan los datos de la organización siguen siendo seguras o se encuentran en una aplicación administrada. Una aplicación administrada tiene directivas de protección de aplicaciones aplicadas a ella y Intune puede administrarla.  

Microsoft Defender para Endpoint en Android admite ambas configuraciones de MAM
- **MDM de Intune + MAM**: los administradores de TI solo pueden administrar aplicaciones con directivas de Protección de aplicaciones en dispositivos inscritos con la administración de dispositivos móviles (MDM) de Intune.
- **MAM sin inscripción de** dispositivos: MAM sin inscripción de dispositivos, o MAM-WE, permite a los administradores de TI administrar aplicaciones mediante directivas de protección de aplicaciones en dispositivos que no están inscritos con MDM de Intune.[](/mem/intune/app/app-protection-policy) Esto significa que las aplicaciones pueden administrarse mediante Intune en dispositivos inscritos con proveedores de EMM de terceros. Para administrar las aplicaciones que usan en las dos configuraciones anteriores, los clientes deben usar Intune en el [Centro de administración Microsoft Endpoint Manager administración](https://go.microsoft.com/fwlink/?linkid=2109431)

Para habilitar esta funcionalidad, un administrador debe configurar la conexión entre Microsoft Defender para Endpoint e Intune, crear la directiva de protección de aplicaciones y aplicar la directiva en dispositivos y aplicaciones de destino. 
 
Los usuarios finales también deben tomar medidas para instalar Microsoft Defender para Endpoint en su dispositivo y activar el flujo de incorporación.


## <a name="admin-prerequisites"></a>Requisitos previos de administración

- **Validar que el conector de Microsoft Defender para Endpoint-Intune está habilitado**

  a. Vaya a security.microsoft.com. 

  b. Seleccione **Configuración > endpoints> Advanced Features > Microsoft Intune Connection** está activada.

  c. Si la conexión no está activada, seleccione el botón de alternancia para activarla y, a continuación, seleccione **Guardar preferencias**.

  ![Imagen de Defender para endpoint -Intune connector](images/enable-intune-connection.png)

  d. Vaya a **Microsoft Endpoint Manager (Intune)** y valide si Microsoft Defender para Endpoint-Intune está habilitado.

  ![Imagen de Defender for Endpoint-Intune connector en Intune](images/validate-intune-connector.png)

- **Habilitar Microsoft Defender para endpoint en Android Connector para la directiva de protección de aplicaciones (APP)**
  
  Configure el conector en Intune Microsoft Endpoint Manager directivas de protección de aplicaciones:

  a. Vaya a **Administración de inquilinos > conectores y tokens > Microsoft Defender para endpoint**.

  b. Activa la alternancia de la directiva de protección de aplicaciones para Android (como se ve en la siguiente captura de pantalla).

  c. Seleccione **Guardar**.

  ![Configuración de la aplicación](images/app-settings.png)

- **Crear una directiva de protección de aplicaciones** 
 
Bloquear el acceso o borrar datos de una aplicación administrada basada en señales de riesgo de Microsoft Defender para puntos de conexión mediante la creación de una directiva de protección de aplicaciones.
Microsoft Defender para endpoint se puede configurar para enviar señales de amenaza que se usarán en las directivas de protección de aplicaciones (APP, también conocidas como MAM). Con esta funcionalidad, puedes usar Microsoft Defender para Endpoint para proteger las aplicaciones administradas.

1. Crear una directiva <br>
Las directivas de protección de aplicaciones (APP) que garantizan los datos de la organización siguen siendo seguras o se encuentran en una aplicación administrada. Una directiva puede ser una regla que se aplica cuando el usuario intenta acceder o mover datos "corporativos", o un conjunto de acciones que se prohíben o supervisan cuando el usuario está dentro de la aplicación. 

![Imagen de creación de directivas](images/create-policy.png)

2. Agregar aplicaciones <br>
    a. Elige cómo quieres aplicar esta directiva a aplicaciones en diferentes dispositivos. A continuación, agrega al menos una aplicación. <br>
    Use esta opción para especificar si esta directiva se aplica a dispositivos no administrados. En el caso de Android, puedes especificar que la directiva se aplica a dispositivos android Enterprise, administrador de dispositivos o dispositivos no administrados. También puedes elegir dirigir la directiva a aplicaciones en dispositivos de cualquier estado de administración.
Debido a que la administración de aplicaciones móviles no requiere la administración de dispositivos, puede proteger los datos de la empresa en dispositivos administrados y no administrados. La administración se centra en la identidad del usuario, lo que elimina la necesidad de administrar dispositivos. Las empresas pueden usar directivas de protección de aplicaciones con o sin MDM al mismo tiempo. Por ejemplo, piense el caso de un empleado que utiliza tanto un teléfono proporcionado por la empresa como su propia tableta personal. El teléfono de la empresa está inscrito en MDM y protegido por directivas de protección de aplicaciones mientras que el dispositivo personal está protegido solo por directivas de protección de aplicaciones.

    b. Seleccionar aplicaciones<br>
    Una aplicación administrada es aquella que tiene las directivas de protección de aplicaciones aplicadas y puede ser administrada por Intune. Cualquier aplicación que se haya integrado con [el SDK de Intune](/mem/intune/developer/app-sdk) o se haya ajustado mediante el App Wrapping Tool [Intune](/mem/intune/developer/apps-prepare-mobile-application-management) se puede administrar mediante directivas de protección de aplicaciones de Intune. Consulte la lista oficial de [aplicaciones protegidas de Microsoft Intune](/mem/intune/apps/apps-supported-intune-apps) que se han creado con estas herramientas y están disponibles para uso público.

    *Ejemplo: Outlook como una aplicación administrada*

    ![Imagen Outlook como aplicación administrada](images/managed-app.png)

 3. Establezca los requisitos de seguridad de inicio de sesión para la directiva de protección. <br>
Selecciona **Establecer > nivel máximo de amenaza de dispositivo permitido** en **Condiciones del dispositivo** y escribe un valor. A  **continuación, seleccione Acción: "Bloquear acceso"**. Microsoft Defender para Endpoint en Android comparte este nivel de amenaza de dispositivo.

    ![Imagen del inicio condicional](images/conditional-launch.png)


- **Asignar grupos de usuarios a los que se debe aplicar la directiva.**<br>
  Seleccione **Grupos incluidos**. A continuación, agregue los grupos relevantes. 

    ![Imagen de assigments](images/assignment.png)


## <a name="end-user-prerequisites"></a>Requisitos previos del usuario final
- La aplicación de agente debe instalarse
    - Portal de empresa de Intune
    
- Los usuarios tienen las licencias necesarias para la aplicación administrada y tienen instalada la aplicación

### <a name="end-user-onboarding"></a>Incorporación de usuario final 

1. Inicie sesión en una aplicación administrada, por ejemplo, Outlook. El dispositivo está registrado y la directiva de protección de aplicaciones se sincroniza con el dispositivo. La directiva de protección de aplicaciones reconoce el estado de mantenimiento del dispositivo.  

2. Seleccione **Continuar**. Se presenta una pantalla que recomienda descargar y configurar Microsoft Defender para endpoint en la aplicación Android.

3. Seleccione **Descargar**. Se te redirigirá a la tienda de aplicaciones (Google Play). 

4.  Instala la aplicación Microsoft Defender para puntos de conexión (móvil) e inicia la pantalla de incorporación de aplicaciones administradas.

  ![Instalar MDE y volver a iniciar la pantalla de incorporación de aplicaciones administradas](images/download-mde.png)

5.  Haga **clic en Continuar > iniciar**. Se inicia el flujo de incorporación/activación de aplicaciones de Microsoft Defender para endpoint. Siga los pasos para completar la incorporación. Se te redirigirá automáticamente a la pantalla de incorporación de aplicaciones administradas, que ahora indica que el dispositivo está en buen estado.

6. Seleccione **Continuar** para iniciar sesión en la aplicación administrada. 



## <a name="related-topics"></a>Temas relacionados

- [Introducción a Microsoft Defender para punto de conexión en Android](microsoft-defender-endpoint-android.md)
- [Implementar Microsoft Defender para punto de conexión en Android con Microsoft Intune](android-intune.md)
