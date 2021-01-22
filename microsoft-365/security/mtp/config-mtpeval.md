---
title: Configurar los pilares de Microsoft 365 Defender para el entorno de prueba o piloto
description: Configure los pilares de Microsoft 365 Defender, como Microsoft Defender para Office 365, Microsoft Defender para Identidad, Microsoft Cloud App Security y Microsoft Defender para Endpoint, para su entorno de prueba o piloto.
keywords: configurar la prueba de Protección contra amenazas de Microsoft, la configuración de prueba de la Protección contra amenazas de Microsoft, configurar el proyecto piloto de La Protección contra amenazas de Microsoft, configurar los pilares de la Protección contra amenazas de Microsoft, los pilares de la Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 78b37d9d435eabce47d360efd630c2e55cadacd1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932243"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configurar los pilares de Microsoft 365 Defender para su entorno de prueba o piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


Crear un entorno de prueba o piloto de Microsoft 365 Defender e implementarlo es un proceso de tres fases:

|[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: Preparar](prepare-mtpeval.md) |[![Fase 2: Configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: Configurar](setup-mtpeval.md) |![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)<br/>Fase 3: Incorporación | [![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Volver al libro de juegos piloto](mtp-pilot.md) |
|--|--|--|--|
|| |*¡Estás aquí!* | |

Actualmente se encuentra en la fase de configuración.

La preparación es clave para una implementación correcta. En este artículo, se te guiará sobre los puntos que debes tener en cuenta a medida que te preparas para implementar Microsoft Defender para Endpoint.


## <a name="microsoft-365-defender-pillars"></a>Pilares de Microsoft 365 Defender
Microsoft 365 Defender consta de cuatro pilares. Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, habilitar los cuatro pilares de Microsoft 365 Defender dará a su organización el máximo valor.

![Imagen of_Microsoft solución de Defender 365 para usuarios, Microsoft Defender para Identidad, para puntos de conexión de Microsoft Defender para puntos de conexión, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft Defender para Office 365](../../media/mtp/m365pillars.png)

Esta sección le guiará a configurar:
-   Microsoft Defender para Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender para punto de conexión


## <a name="configure-microsoft-defender-for-office-365"></a>Configurar Microsoft Defender para Office 365

>[!NOTE]
>Omita este paso si ya ha habilitado Defender para Office 365. 

Hay un módulo de PowerShell denominado Analizador de configuración recomendado de Protección contra amenazas *avanzada (ORCA) de Office 365* que ayuda a determinar algunas de estas opciones de configuración. Cuando se ejecuta como administrador en su espacio empresarial, get-ORCAReport le ayudará a generar una evaluación de la configuración de higiene de mensajes, antiphishing y contra correo no deseado. Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ . 

1. Vaya a La directiva de administración de amenazas del Centro & seguridad de [Office 365.](https://protection.office.com/homepage)  >    >  

   ![Página de of_Office de administración de amenazas del Centro & seguridad y cumplimiento de 365](../../media/mtp-eval-32.png)
 
2. Haga **clic en Anti-phishing,** seleccione **Crear** y rellene el nombre y la descripción de la directiva. Haga clic en **Siguiente**.

   ![Imagen of_Office página de directiva anti-phishing del Centro de seguridad & cumplimiento 365 donde puede nombrar la directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite la directiva contra suplantación de identidad avanzada en Microsoft Defender para Office 365. Cambie **el umbral de suplantación de** identidad avanzada a **2: agresivo.**

3. Haga clic **en el menú desplegable Agregar** una condición y seleccione los dominios como dominio del destinatario. Haga clic en **Siguiente**.

   ![Imagen of_Office página de directiva contra suplantación de identidad del Centro de seguridad & cumplimiento 365 donde puede agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. Revisa la configuración. Haga **clic en Crear esta directiva** para confirmar. 

   ![Imagen of_Office página de directiva contra suplantación de identidad del Centro de seguridad & cumplimiento 365 donde puede revisar la configuración y hacer clic en el botón crear esta directiva](../../media/mtp-eval-35.png)
 
5. Seleccione **Datos adjuntos** seguros y seleccione **la opción Activar ATP para SharePoint, OneDrive y Microsoft Teams.**

   ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365 donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. Haga clic en el icono + para crear una nueva directiva de datos adjuntos seguros y aplíquela como dominio de destinatario a sus dominios. Haga clic en **Guardar**.

   ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365 donde puede crear una nueva directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. A continuación, seleccione la **directiva de vínculos** seguros y, a continuación, haga clic en el icono de lápiz para editar la directiva predeterminada.

8. Asegúrese de que la **opción No realizar seguimiento cuando** los usuarios hacen clic en vínculos seguros no está seleccionada, mientras que el resto de las opciones están seleccionadas. Consulte [la configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obtener más información. Haga clic en **Guardar**. 

   ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365, que muestra que la opción No realizar seguimiento cuando los usuarios hacen clic en seguro no está seleccionada](../../media/mtp-eval-38.png)

9. A continuación, **seleccione la directiva antimalware,** seleccione la predeterminada y elija el icono de lápiz.

10. Haga **clic en** Configuración y seleccione Sí y use el texto de notificación **predeterminado** para habilitar la respuesta **de detección de malware.** Activar el **filtro de tipos comunes de datos adjuntos.** Haga clic en **Guardar**.

    ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365 que muestra que la respuesta de detección de malware está activada con la notificación predeterminada y que el filtro de tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. Vaya a la búsqueda del registro de auditoría del Centro de & seguridad y cumplimiento de [Office 365](https://protection.office.com/homepage)y  >    >   active la auditoría.

    ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365, donde puede activar la búsqueda del registro de auditoría](../../media/mtp-eval-40.png)

12. Integre Microsoft Defender para Office 365 con Microsoft Defender para Endpoint. Vaya al Explorador de administración de amenazas del Centro de seguridad & Cumplimiento de [Office 365](https://protection.office.com/homepage)y seleccione Microsoft Defender para Configuración de puntos de conexión en la esquina superior  >    >   derecha de la pantalla.  En el cuadro de diálogo Conexión de Defender para extremo, active **Conectar a Microsoft Defender para Endpoint.**

    ![Imagen of_Office página del Centro de seguridad & cumplimiento de 365, donde puede activar la conexión de Microsoft Defender para puntos de conexión](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurar Microsoft Defender para la identidad

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Defender para Identity

1. Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info) > más **recursos** de Microsoft Defender  >  **para identidad.**

   ![Imagen of_Microsoft página del Centro de seguridad 365 donde hay una opción para abrir Microsoft Defender para Identidad](../../media/mtp-eval-42.png)

2. Haga **clic en** Crear para iniciar el Asistente de Microsoft Defender para identidades. 

   ![Imagen of_Microsoft asistente de Defender para identidad donde debería hacer clic en el botón Crear](../../media/mtp-eval-43.png)

3. Elija **Proporcionar un nombre de usuario y una contraseña para conectarse al bosque de Active Directory.**  

   ![Página principal de Image of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. Escriba sus credenciales locales de Active Directory. Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.

   ![Página de of_Microsoft defender para los servicios de directorio de identidad donde debe colocar las credenciales](../../media/mtp-eval-45.png)

5. A continuación, **elija Descargar configuración del sensor** y transferir el archivo al controlador de dominio.

   ![Página de Image of_Microsoft Defender for Identity en la que puedes seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. Ejecuta Microsoft Defender para la configuración del sensor de identidad y empieza a seguir el asistente.

   ![Página de of_Microsoft Defender para identidad en la que debes hacer clic junto para seguir el asistente del sensor de Microsoft Defender para identidad](../../media/mtp-eval-47.png)
 
7. Haz **clic en Siguiente** en el tipo de implementación del sensor.

   ![Página de of_Microsoft Defender para identidad donde debe hacer clic junto para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. Copie la tecla de acceso porque tiene que escribirla a continuación en el Asistente.

   ![Página de of_the sensores de imagen en la que debes copiar la tecla de acceso que necesitas escribir en la siguiente página del Asistente para configuración del sensor de Microsoft Defender para identidad](../../media/mtp-eval-49.png)
 
9. Copie la clave de acceso en el Asistente y haga clic en **Instalar**. 

   ![Página of_Microsoft asistente del sensor defender para identidad donde debes proporcionar la tecla de acceso y, a continuación, hacer clic en el botón de instalación](../../media/mtp-eval-50.png)

10. Enhorabuena, ha configurado correctamente Microsoft Defender para Identity en el controlador de dominio.

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. En la [sección Configuración de Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2040449) para identidad, selecciona **Microsoft Defender para punto de conexión **y, a continuación, activa el botón de alternancia. Haga clic en **Guardar**. 

    ![Imagen of_the página de configuración de Microsoft Defender para identidad donde debes activar el botón de alternancia de Microsoft Defender para punto de conexión](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender se ha cambiado el nombre de ATP como Microsoft Defender para Endpoint. El cambio de marca de los cambios en todos nuestros portales se está implantando para mantener la coherencia.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Cloud App Security. 

1. Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info)Más  >  **recursos** de  >  **Microsoft Cloud App Security.**

   ![Imagen of_Microsoft página del Centro de seguridad 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón Abrir](../../media/mtp-eval-53.png)

2. En el símbolo del sistema de información para integrar Microsoft Defender for Identity, seleccione **Habilitar Microsoft Defender para la integración de datos de identidad.**
  
   ![Mensaje de of_the de información de imagen para integrar Microsoft Defender for Identity donde debe seleccionar el vínculo Habilitar Microsoft Defender para la integración de datos de identidad](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Si no ve este mensaje, puede significar que la integración de datos de Microsoft Defender para Identidad ya está habilitada. Sin embargo, si no está seguro, póngase en contacto con el administrador de TI para confirmarlo. 

3. Vaya a **Configuración,** active el botón de alternancia de **integración** de Microsoft Defender para identidad y, a continuación, haga clic en **Guardar.** 

   ![Página de of_the configuración de la imagen en la que debería activar el botón de alternancia de integración de Microsoft Defender para identidades y, a continuación, haga clic en Guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Para las nuevas instancias de Microsoft Defender para identidad, este botón de alternancia de integración se activa automáticamente. Confirme que la integración de Microsoft Defender para identidades se ha habilitado antes de continuar con el paso siguiente.
 
4. En la configuración de detección de nube, **selecciona Microsoft Defender para la integración** de puntos de conexión y, a continuación, habilita la integración. Haga clic en **Guardar**.

   ![Imagen of_the página de Microsoft Defender para puntos de conexión en la que está seleccionada la casilla bloquear aplicaciones no seleccionadas en Microsoft Defender para la integración de puntos de conexión. Haga clic en Guardar.](../../media/mtp-eval-56.png)

5. En Configuración de detección de nube, seleccione **Enriquecimiento de usuarios** y, a continuación, habilite la integración con Azure Active Directory.

   ![Imagen de la sección de enriquecimiento de usuarios en la que está activada la casilla de verificación de enriquecimiento de los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurar Microsoft Defender para endpoint

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Defender para Endpoint.

1. Vaya al [Centro de seguridad de Microsoft 365](https://security.microsoft.com/info)Más  >  **recursos** del  >  **Centro de seguridad de Microsoft Defender.** Haga clic en **Open** (Abrir).

   ![Imagen of_Microsoft Centro de seguridad de Defender en la página Centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. Sigue el Asistente de Microsoft Defender para puntos de conexión. Haga clic en **Siguiente**. 

   ![Página de of_the del Centro de seguridad de Microsoft Defender](../../media/mtp-eval-59.png)

3. Elija en función de la ubicación de almacenamiento de datos preferida, la directiva de retención de datos, el tamaño de la organización y la participación en las características de vista previa.

   ![Página de of_the imagen para seleccionar el país de almacenamiento de datos, la directiva de retención y el tamaño de la organización. Haz clic a continuación cuando termines de seleccionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > No puede cambiar algunas de las opciones de configuración, como la ubicación de almacenamiento de datos, más adelante. 

   Haga clic en **Siguiente**. 

4. Haz **clic en Continuar** y aprovisionará el inquilino de Microsoft Defender para Endpoint.

   ![Imagen of_the página en la que se le pide que haga clic en el botón Continuar para crear la instancia de nube](../../media/mtp-eval-61.png)

5. Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local en Microsoft Defender para Endpoint. Por motivos de simplicidad, esta guía usa el script local.

6. Haz **clic en Descargar paquete** y copia el script de incorporación en tus puntos de conexión.

   ![Imagen of_page que te pide que hagas clic en el botón Descargar paquete para copiar el script de incorporación a tu punto de conexión o puntos de conexión](../../media/mtp-eval-62.png)

7. En el punto de conexión, ejecuta el script de incorporación como administrador y elige Y. 

   ![Imagen of_the línea de comandos donde se ejecuta el script de incorporación y se elige Y para continuar](../../media/mtp-eval-63.png)

8. Enhorabuena, ha incorporado su primer punto de conexión.

   ![Imagen of_the línea de comandos donde obtienes la confirmación de que has incorporado el primer punto de conexión. Presione cualquier tecla para continuar](../../media/mtp-eval-64.png)

9. Copiar y pegar la prueba de detección desde el Asistente de Microsoft Defender para puntos de conexión.

   ![Image of_the run a detection test step where you should click Copy to copy the detection test script that you should paste in the command prompt](../../media/mtp-eval-65.png)

10. Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo. 

    ![Mensaje de of_command imagen donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. Selecciona **Empezar a usar Microsoft Defender para Endpoint** en el Asistente.

    ![Mensaje of_the confirmación del asistente en el que debes hacer clic en Empezar a usar Microsoft Defender para puntos de conexión](../../media/mtp-eval-67.png)
 
12. Visite el Centro [de seguridad de Microsoft Defender.](https://securitycenter.windows.com/) Vaya a **Configuración** y, a continuación, seleccione **Características avanzadas.** 

    ![Imagen of_Microsoft configuración del Centro de seguridad de Defender donde debes seleccionar características avanzadas](../../media/mtp-eval-68.png)

13. Active la integración con **Microsoft Defender para Identity.**  

    ![Image of_Microsoft Defender Security Center Advanced features, Microsoft Defender for Identity option toggle that you need to turn on](../../media/mtp-eval-69.png)

14. Active la integración con inteligencia **de amenazas de Office 365.**

    ![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)

15. Active la integración con **Microsoft Cloud App Security.**

    ![Imagen of_Microsoft características avanzadas del Centro de seguridad de Defender, alternancia de opción de Microsoft Cloud App Security que necesitas activar](../../media/mtp-eval-71.png)

16. Desplácese hacia abajo y haga **clic en Guardar** preferencias para confirmar las nuevas integraciones.

    ![Botón of_Save preferencias de imagen en el que necesitas hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Iniciar el servicio de Microsoft 365 Defender

>[!NOTE]
>A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de Microsoft 365 Defender para todos los inquilinos elegibles. Consulta este [artículo de Microsoft Tech Community sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información. 


Vaya al [Centro de seguridad de Microsoft 365.](https://security.microsoft.com/homepage) Vaya a **Configuración** y, a continuación, **seleccione Microsoft 365 Defender.**

![Imagen of_Microsoft captura de pantalla de la opción defender 365 de la página Configuración del Centro de seguridad de Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obtener una guía más completa, [vea Activar Microsoft 365 Defender.](mtp-enable.md) 

¡Enhorabuena! Acaba de crear el entorno piloto o el entorno de prueba de Microsoft 365 Defender. Ahora puede familiarizarse con la interfaz de usuario de Microsoft 365 Defender. Vea lo que puede aprender de la siguiente guía interactiva de Microsoft 365 Defender y sepa cómo usar cada panel para sus tareas diarias de operación de seguridad.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

A continuación, puedes simular un ataque y ver cómo las funcionalidades entre productos detectan, crean alertas y responden automáticamente a un ataque sin archivos en un punto de conexión.

## <a name="next-step"></a>Paso siguiente
|[Fase de simulación de ataques](mtp-pilot-simulate.md) | Ejecute la simulación de ataques para su entorno piloto de Microsoft 365 Defender.
|:-------|:-----|
