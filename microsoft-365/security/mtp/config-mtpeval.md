---
title: Configuración de los pilares de 365 defender de Microsoft para el entorno de prueba o el entorno piloto
description: Configure los pilares de 365 defender de Microsoft, como Microsoft defender para Office 365, Microsoft defender para identidad, Microsoft Cloud App Security y Microsoft defender for Endpoint, para su laboratorio de pruebas o entorno piloto.
keywords: configurar Microsoft Threat Protection prueba, configuración de prueba de protección contra amenazas de Microsoft, configurar el proyecto piloto de Microsoft Threat Protection Pilot, configurar los pilares de la protección contra amenazas de Microsoft, pilares de la protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131302"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>Configuración de los pilares de 365 defender de Microsoft para el entorno de prueba o el entorno piloto

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender


La creación de un entorno de prueba de Microsoft 365 defender o un entorno piloto y su implementación es un proceso de tres fases:

|[![Fase 1: preparación](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: preparación](prepare-mtpeval.md) |[![Fase 2: configurar](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: configurar](setup-mtpeval.md) |![Fase 3: incorporada](../../media/phase-diagrams/onboard.png)<br/>Fase 3: incorporada | [![Volver a la prueba piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Volver a la guía piloto](mtp-pilot.md) |
|--|--|--|--|
|| |*Ya está aquí.* | |

Actualmente se encuentra en la fase de configuración.

La preparación es fundamental para todas las implementaciones correctas. En este artículo, se le guiará en los puntos que debe tener en cuenta a la hora de preparar la implementación de Microsoft defender para el punto de conexión.


## <a name="microsoft-365-defender-pillars"></a>Pilares de 365 defender de Microsoft
Microsoft 365 defender consta de cuatro pilares. Aunque un pilar ya puede proporcionar valor a la seguridad de su organización de red, la habilitación de los cuatro pilares de Microsoft 365 defender dará mayor valor a su organización.

![Imagen of_Microsoft solución de 365 defender para usuarios, Microsoft defender para identidad, para extremos Microsoft defender para Endpoint, para aplicaciones en la nube, Microsoft Cloud App Security y para datos, Microsoft defender para Office 365](../../media/mtp/m365pillars.png)

Esta sección le guiará para configurar:
-   Microsoft Defender para Office 365
-   Microsoft Defender for Identity 
-   Microsoft Cloud App Security
-   Microsoft Defender para punto de conexión


## <a name="configure-microsoft-defender-for-office-365"></a>Configurar Microsoft defender para Office 365

>[!NOTE]
>Omita este paso si ya ha habilitado defender para Office 365. 

Hay un módulo de PowerShell denominado analizador de configuración de la *protección contra amenazas avanzada de Office 365 (Orca)* que ayuda a determinar algunas de estas opciones. Cuando se ejecuta como administrador en su espacio empresarial, Get-ORCAReport le ayudará a generar una evaluación de la configuración de protección contra correo electrónico no deseado, anti-phish y otros mensajes. Puede descargar este módulo desde https://www.powershellgallery.com/packages/ORCA/ . 

1. Vaya a la Directiva de administración de amenazas [& cumplimiento del centro de cumplimiento de Office 365](https://protection.office.com/homepage)  >  **Threat management**  >  **Policy**.

   ![Página de la Directiva de administración de amenazas de seguridad of_Office 365 de & de seguridad del centro de cumplimiento](../../media/mtp-eval-32.png)
 
2. Haga clic en **anti-phishing**, seleccione **crear** y rellene el nombre y la descripción de la Directiva. Haga clic en **Siguiente**.

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede asignar un nombre a la Directiva](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Edite su Directiva antiphishing avanzada en Microsoft defender para Office 365. Cambiar el **umbral de suplantación de identidad avanzado** a **2-agresivo**.

3. Haga clic en el menú desplegable **Agregar condición** y seleccione su dominio o dominios como dominio del destinatario. Haga clic en **Siguiente**.

   ![Página de la Directiva de la Directiva antiphishing del centro de cumplimiento de la & de seguridad of_Office 365, donde puede Agregar una condición para su aplicación](../../media/mtp-eval-34.png)
 
4. Revise la configuración. Haga clic en **crear esta directiva** para confirmar. 

   ![Imagen of_Office 365 de seguridad & página de la Directiva de antiphishing del centro de cumplimiento, donde puede revisar la configuración y hacer clic en el botón crear esta Directiva](../../media/mtp-eval-35.png)
 
5. Seleccione **datos adjuntos seguros** y seleccione la opción **Activar ATP para SharePoint, OneDrive y Microsoft Teams** .

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar ATP para SharePoint, OneDrive y Microsoft Teams](../../media/mtp-eval-36.png)

6. Haga clic en el icono + para crear una nueva Directiva de datos adjuntos seguros, aplíquela como dominio del destinatario en sus dominios. Haga clic en **Guardar**.

   ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede crear una nueva Directiva de datos adjuntos seguros](../../media/mtp-eval-37.png)
 
7. A continuación, seleccione la directiva **vínculos seguros** y, a continuación, haga clic en el icono de lápiz para editar la directiva predeterminada.

8. Asegúrese de que la opción no **realizar seguimiento cuando los usuarios hagan clic en vínculos seguros** no esté seleccionada, mientras que el resto de las opciones están seleccionadas. Vea [configuración de vínculos seguros](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) para obtener más información. Haga clic en **Guardar**. 

   ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la opción no realiza un seguimiento cuando los usuarios hacen clic en seguro no está seleccionado](../../media/mtp-eval-38.png)

9. A continuación, seleccione la directiva **antimalware** , seleccione la opción predeterminada y elija el icono de lápiz.

10. Haga clic en **configuración** y seleccione **sí y use el texto de notificación predeterminado** para habilitar la **respuesta de detección de malware**. Active el **filtro tipos de datos adjuntos comunes** en. Haga clic en **Guardar**.

    ![Página of_Office 365 de seguridad & de centro de cumplimiento que muestra que la respuesta de detección de malware está activada con notificación predeterminada y el filtro tipos de datos adjuntos comunes está activado](../../media/mtp-eval-39.png)
  
11. Vaya a [Office 365 Security & cumplimiento del centro](https://protection.office.com/homepage)  >  **Search**  >  de **Auditoría** búsqueda y active la auditoría.

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar la búsqueda de registros de auditoría](../../media/mtp-eval-40.png)

12. Integración de Microsoft defender para Office 365 con Microsoft defender para el punto de conexión. Vaya a [Office 365 Security & cumplimiento](https://protection.office.com/homepage)  >  del centro de **Administración de amenazas**  >  **Explorer** y seleccione **Microsoft defender for Endpoint Settings** en la esquina superior derecha de la pantalla. En el cuadro de diálogo defender para conexión de extremo, Active **conectar con Microsoft defender para el extremo**.

    ![Imagen of_Office 365 la página del centro de cumplimiento de & de seguridad donde puede activar Microsoft defender para la conexión de extremo](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Configurar Microsoft defender para identidad

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft defender para identidad

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info) > seleccione **más recursos**  >  **Microsoft defender para identidad**.

   ![Página del centro de seguridad de of_Microsoft de imágenes 365 donde hay una opción para abrir Microsoft defender para identidad](../../media/mtp-eval-42.png)

2. Haga clic en **crear** para iniciar el Asistente de Microsoft defender para identidad. 

   ![Imagen del asistente de of_Microsoft defender para la identidad donde debe hacer clic en el botón crear](../../media/mtp-eval-43.png)

3. Elija **proporcionar un nombre de usuario y una contraseña para conectar con el bosque de Active** Directory.  

   ![Imagen of_Microsoft defender para la página de bienvenida de identidad](../../media/mtp-eval-44.png)

4. Escriba sus credenciales locales de Active Directory. Puede ser cualquier cuenta de usuario que tenga acceso de lectura a Active Directory.

   ![Imagen of_Microsoft defender para la página de servicios de directorio de identidad donde debe colocar sus credenciales](../../media/mtp-eval-45.png)

5. A continuación, seleccione **descargar la configuración del sensor** y transferir el archivo a su controlador de dominio.

   ![Imagen of_Microsoft defender para la página de identidad donde puede seleccionar Descargar configuración del sensor](../../media/mtp-eval-46.png)

6. Ejecute Microsoft defender para la configuración del sensor de identidad y comience a seguir el asistente.

   ![Imagen of_Microsoft defender para la página de identidad donde debe hacer clic en siguiente para seguir el Asistente de Microsoft defender para el sensor de identidad](../../media/mtp-eval-47.png)
 
7. Haga clic en **siguiente** en el tipo de implementación de sensor.

   ![Imagen of_Microsoft defender para la página de identidad donde debe hacer clic en siguiente para ir a la página siguiente](../../media/mtp-eval-48.png)
 
8. Copie la clave de acceso porque tiene que escribirla a continuación en el asistente.

   ![Página de of_the de imágenes de sensores donde debe copiar la clave de acceso que necesita introducir en la próxima página del Asistente para la instalación de Microsoft defender para el sensor de identidad](../../media/mtp-eval-49.png)
 
9. Copie la clave de acceso en el asistente y haga clic en **instalar**. 

   ![Imagen of_Microsoft defender para el Asistente para el sensor de identidad donde debe proporcionar la clave de acceso y, a continuación, haga clic en el botón instalar](../../media/mtp-eval-50.png)

10. Enhorabuena, ha configurado correctamente Microsoft defender para identidad en el controlador de dominio.

    ![Imagen of_Microsoft defender para el Asistente para el sensor de identidad finalizó la instalación donde debe hacer clic en el botón Finalizar](../../media/mtp-eval-51.png)
 
11. En la sección [Microsoft defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings, seleccione * * Microsoft defender for Endpoint * * y, a continuación, active la opción de alternancia. Haga clic en **Guardar**. 

    ![Imagen of_the página de Microsoft defender para obtener la configuración de la identidad en la que se debe activar o desactivar el cambio de Microsoft defender para el punto de conexión](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP ha cambiado de marca como Microsoft defender para el punto de conexión. Los cambios de personalización de marca en todos nuestros portales se están implementando para lograr coherencia.


## <a name="configure-microsoft-cloud-app-security"></a>Configurar Microsoft Cloud App Security

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft Cloud App Security. 

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **Microsoft Cloud App Security**.

   ![Página del centro de seguridad de of_Microsoft de imágenes 365 donde puede ver la tarjeta de Microsoft Cloud App y debe hacer clic en el botón abrir](../../media/mtp-eval-53.png)

2. En la información solicitada para integrar Microsoft defender para identidad, seleccione **Habilitar Microsoft defender para la integración de datos de identidad**.
  
   ![Image of_the información del mensaje para integrar Microsoft defender para identidad donde debe seleccionar el vínculo habilitar Microsoft defender para la integración de datos de identidades](../../media/mtp-eval-54.png)

   > [!NOTE]
   > Si no ve este mensaje, puede significar que ya se ha habilitado Microsoft defender para la integración de datos de identidad. Sin embargo, si no está seguro, póngase en contacto con su administrador de TI para confirmarlo. 

3. Vaya a **configuración**, active el botón de alternancia **de Microsoft defender para integración de identidades** y, a continuación, haga clic en **Guardar**. 

   ![Página de configuración de of_the de imágenes donde debe activar el botón de alternancia de Microsoft defender para la integración de identidades y, a continuación, haga clic en guardar](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > En el caso de los nuevos Microsoft defender para instancias de identidad, este cambio de integración se activa automáticamente. Confirme que se haya habilitado Microsoft defender para la integración de identidad antes de continuar con el paso siguiente.
 
4. En configuración de detección en la nube, seleccione **Microsoft defender for Endpoint Integration** y, a continuación, habilite la integración. Haga clic en **Guardar**.

   ![Imagen of_the página Microsoft defender para el punto de conexión donde está seleccionada la casilla bloquear aplicaciones sin autorizar en Microsoft defender para la integración de extremos. Haga clic en guardar.](../../media/mtp-eval-56.png)

5. En configuración de detección en la nube, seleccione **enriquecimiento de usuario** y, a continuación, habilite la integración con Azure Active Directory.

   ![Imagen de la sección enriquecimiento de usuario donde está seleccionada la casilla enriquecer los identificadores de usuario detectados con nombres de usuario de Azure Active Directory](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>Configurar Microsoft defender para el punto de conexión

>[!NOTE]
>Omita este paso si ya ha habilitado Microsoft defender para el punto de conexión.

1. Vaya a [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **más recursos**  >  **centro de seguridad de Microsoft defender**. Haga clic en **Open** (Abrir).

   ![Imagen of_Microsoft defender Security Center Option en la página del centro de seguridad de Microsoft 365](../../media/mtp-eval-58.png)
 
2. Siga el Asistente de Microsoft defender para extremo. Haga clic en **Siguiente**. 

   ![Imagen of_the página del asistente de bienvenida del centro de seguridad de Microsoft defender](../../media/mtp-eval-59.png)

3. Elija en función de la ubicación de almacenamiento de datos preferida, la Directiva de retención de datos, el tamaño de la organización y las características de vista previa.

   ![Imagen of_the página para seleccionar su país de almacenamiento de datos, la Directiva de retención y el tamaño de la organización. Haga clic en siguiente cuando haya terminado de seleccionar.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > No puede cambiar algunos de los valores, como la ubicación de almacenamiento de datos, más adelante. 

   Haga clic en **Siguiente**. 

4. Haga clic en **continuar** y se aprovisionará su Microsoft defender para inquilino de punto de conexión.

   ![Imagen of_the página que le pide que haga clic en el botón continuar para crear su instancia de nube](../../media/mtp-eval-61.png)

5. Incorpore los puntos de conexión a través de directivas de grupo, Microsoft Endpoint Manager o mediante la ejecución de un script local a Microsoft defender para el punto de conexión. Para simplificar, esta guía usa el script local.

6. Haga clic en **Descargar paquete** y copie el script de incorporación en los extremos.

   ![Imagen of_page le pregunta si desea hacer clic en el botón Descargar paquete para copiar el script de incorporación en el extremo o los extremos](../../media/mtp-eval-62.png)

7. En el punto de conexión, ejecute el script de incorporación como administrador y elija Y. 

   ![Image of_the CommandLine donde se ejecuta el script de incorporación y elija y para continuar.](../../media/mtp-eval-63.png)

8. Enhorabuena, ha incorporado el primer punto de conexión.

   ![Image of_the CommandLine donde recibirá la confirmación de que ha incorporado el primer punto de conexión. Presione cualquier tecla para continuar](../../media/mtp-eval-64.png)

9. Copie y pegue la prueba de detección desde el Asistente de Microsoft defender para extremo.

   ![Imagen of_the ejecute un paso de prueba de detección en el que debe hacer clic en copiar para copiar el script de prueba de detección que debe pegar en el símbolo del sistema](../../media/mtp-eval-65.png)

10. Copie el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecútelo. 

    ![Image of_command prompt donde debe copiar el script de PowerShell en un símbolo del sistema con privilegios elevados y ejecutarlo](../../media/mtp-eval-66.png)

11. Seleccione **empezar a usar Microsoft defender para el extremo** desde el asistente.

    ![Imagen of_the mensaje de confirmación del asistente donde debe hacer clic en empezar a usar Microsoft defender para el punto de conexión](../../media/mtp-eval-67.png)
 
12. Visite el [centro de seguridad de Microsoft defender](https://securitycenter.windows.com/). Vaya a **configuración** y, a continuación, seleccione **características avanzadas**. 

    ![Menú de configuración del centro de seguridad de imágenes of_Microsoft defender donde debe seleccionar características avanzadas](../../media/mtp-eval-68.png)

13. Active la integración con **Microsoft defender para identidad**.  

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, Microsoft defender para la opción de identidad para alternar entre los que debe activar](../../media/mtp-eval-69.png)

14. Active la integración con la **inteligencia sobre amenazas de Office 365**.

    ![Características avanzadas del centro de seguridad de imágenes of_Microsoft defender, Office 365 Threat Intelligence opción para alternar la activación](../../media/mtp-eval-70.png)

15. Active la integración con **Microsoft Cloud App Security**.

    ![Image of_Microsoft defender Security Center Advanced Security Features, Microsoft Cloud App Security opción alternar la activación](../../media/mtp-eval-71.png)

16. Desplácese hacia abajo y haga clic en **Guardar preferencias** para confirmar las nuevas integraciones.

    ![Botón de preferencias de of_Save de imagen en el que debe hacer clic](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Iniciar el servicio de Microsoft 365 Defender

>[!NOTE]
>A partir del 1 de junio de 2020, Microsoft habilita automáticamente las características de Microsoft 365 defender para todos los inquilinos elegibles. Consulte este [artículo de la comunidad tecnológica de Microsoft sobre la elegibilidad de licencias](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) para obtener más información. 


Vaya al [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage). Vaya a **configuración** y, a continuación, seleccione **Microsoft 365 defender**.

![Captura de pantalla de la opción imagen of_Microsoft 365 defender desde la página Configuración del centro de seguridad de Microsoft 365 ](../../media/mtp-eval-72b.png) <br>

Para obtener una guía más completa, consulte [Activar Microsoft 365 defender](mtp-enable.md). 

¡Enhorabuena! Acaba de crear su entorno de prueba de Microsoft 365 defender o un entorno piloto. Ahora puede familiarizarse con la interfaz de usuario de Microsoft 365 defender. Vea lo que puede aprender de la siguiente guía interactiva de Microsoft 365 defender y sepa cómo usar cada panel para las tareas de la operación de seguridad diaria.


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

A continuación, puede simular un ataque y ver cómo las capacidades cruzadas del producto detectan, crean alertas y responden automáticamente a un ataque de archivos no deseados en un extremo.

## <a name="next-step"></a>Paso siguiente
|[Fase de simulación de ataques](mtp-pilot-simulate.md) | Ejecute la simulación de ataques para su entorno piloto de Microsoft 365 defender.
|:-------|:-----|
