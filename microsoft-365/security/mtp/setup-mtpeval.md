---
title: Configurar el entorno piloto o el laboratorio de prueba de Microsoft 365 Defender
description: Accede al Centro de seguridad de Microsoft 365 y configura el entorno de laboratorio de prueba de Microsoft 365 Defender
keywords: Configuración de prueba de Microsoft Threat Protection, configuración piloto de Microsoft Threat Protection, prueba Microsoft Threat Protection, Configuración del laboratorio de evaluación de Protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 76f46f5205380580cbe5b68d7ede91dddb848036
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918899"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Configurar el entorno de laboratorio de prueba de Microsoft 365 Defender 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender 


Crear un entorno piloto o un laboratorio de prueba de Microsoft 365 Defender e implementarlo es un proceso de tres fases:

|[![Fase 1: Preparar](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Fase 1: Preparar](prepare-mtpeval.md) |![Fase 2: Configurar](../../media/phase-diagrams/setup.png)<br/>Fase 2: Configurar |[![Fase 3: Incorporación](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: Incorporación](config-mtpeval.md) | [![Volver al piloto](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Volver al libro de reproducción piloto](mtp-pilot.md) |
|--|--|--|--|
||*¡Estás aquí!*  | | |


Actualmente está en la fase de configuración. Siga los pasos iniciales para acceder al Centro de seguridad de Microsoft 365 y, a continuación, configure el entorno piloto o el laboratorio de prueba.

Regístrese para una suscripción a Office 365 o Azure Active Directory para generar un inquilino *.onmicrosoft.com* que pueda usar para registrarse en su licencia de Microsoft 365 E5. 

>[!NOTE]
>Si ya tiene una suscripción existente de Office 365 o Azure Active Directory, puede omitir los pasos de creación de inquilinos piloto o de prueba de Office 365 E5.

En esta fase, se le guiará a:
- Crear un inquilino de prueba de Office 365 E5
- Habilitar la suscripción de prueba de Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Crear un inquilino de prueba de Office 365 E5
>[!NOTE]
>Si ya tiene una suscripción existente a Office 365 o Azure Active Directory, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.

1. Vaya al [portal de productos de Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) y seleccione Prueba **gratuita.**

   ![Página of_Office prueba gratuita de 365 E5](../../media/mtp-eval-9.png)
  
2. Complete el registro de prueba especificando su dirección de correo electrónico (personal o corporativa). Haga **clic en Configurar cuenta**.

   ![Página of_Office configuración de registro de prueba de 365 E5](../../media/mtp-eval-10.png)

3. Rellene el nombre, el apellido, el número de teléfono de empresa, el nombre de la empresa, el tamaño de la empresa y el país o región.  

   ![Página of_Office configuración de registro de prueba de 365 E5 que pide detalles de nombre, teléfono y empresa](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > El país o región que establezca aquí determina la región del centro de datos en la que se hospedará Office 365.
  
4. Elija su preferencia de verificación: a través de un mensaje de texto o una llamada. Haga clic **en Enviar código de verificación**. 

   ![Página of_Office configuración de registro de prueba 365 E5 que pide preferencia de verificación](../../media/mtp-eval-12.png)

5. Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **Siguiente**.

   ![Página of_Office configuración de registro de prueba de 365 E5 donde puede configurar el nombre de dominio personalizado](../../media/mtp-eval-13.png)
 
6. Configure la primera identidad, que será un administrador global para el inquilino. Rellene Nombre **y** **contraseña.** Haga clic en **Iniciar sesión**.

   ![Página of_Office configuración de registro de prueba de 365 E5 donde puede establecer su identidad empresarial](../../media/mtp-eval-14.png)

7. Haga **clic en Ir al programa de** instalación para completar el aprovisionamiento del inquilino de prueba de Office 365 E5.

   ![Imagen de la página de instalación del registro de prueba de Office 365 E5 que pide hacer clic en El botón Ir a la instalación](../../media/mtp-eval-15.png)

8. Conecte el dominio corporativo al inquilino de Office 365. [Opcional] Elija **Conectar un dominio que ya posee** y escriba el nombre de dominio. Haga clic en **Siguiente**.

   ![Página of_Office configuración de 365 E5 donde debes personalizar el inicio de sesión y el correo electrónico](../../media/mtp-eval-16.png)
 
9. Agregue un registro TXT o MX para validar la propiedad del dominio. Una vez que haya agregado el registro TXT o MX al dominio, seleccione **Comprobar**.

   ![Página de of_Office de instalación de 365 E5 donde debe agregar un registro TXT de MX para comprobar su dominio](../../media/mtp-eval-17.png)
 
10. [Opcional] Cree más cuentas de usuario para el inquilino. Puede omitir este paso haciendo clic en **Siguiente**.

    ![Página de of_Office de instalación de 365 E5 donde puede agregar más usuarios](../../media/mtp-eval-18.png)
 
11. [Opcional] Descargar aplicaciones de Office. Haga **clic en** Siguiente para omitir este paso. 

    ![Página of_Office 365 E5 donde puede instalar las aplicaciones de Office](../../media/mtp-eval-19.png)

12. [Opcional] Migrar mensajes de correo electrónico. De nuevo, puede omitir este paso.

    ![Imagen of_Office 365 E5 donde puede establecer si desea migrar mensajes de correo electrónico o no](../../media/mtp-eval-20.png)
 
13. Elija servicios en línea. Seleccione **Exchange** y haga clic en **Siguiente**. 

    ![Imagen of_Office 365 E5 donde puede elegir sus servicios en línea](../../media/mtp-eval-21.png)

14. Agregue registros MX, CNAME y TXT al dominio. Cuando se complete, seleccione **Comprobar**.

    ![Image of_Office 365 E5 aquí puede agregar los registros DNS](../../media/mtp-eval-22.png)
 
15. Enhorabuena, ha completado el aprovisionamiento de su inquilino de Office 365.

    ![Página de of_Office de finalización de instalación de 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar la suscripción de prueba de Microsoft 365

>[!NOTE]
>Registrarse para una versión de prueba le ofrece 25 licencias de usuario para usarlas durante un mes. Consulta [Probar o comprar una suscripción a M365](../../commerce/try-or-buy-microsoft-365.md#try-or-buy-a-microsoft-365-subscription-1) para obtener más información.

1. En [el Centro de administración de Microsoft 365,](https://admin.microsoft.com/)haga clic en **Facturación** y, a continuación, vaya a **Servicios de compra.**

2. Seleccione **Microsoft 365 E5** y haga clic **en Iniciar prueba gratuita.** 

   ![Página of_Microsoft 365 E5 Start free trial](../../media/mtp-eval-24.png)

3. Elija su preferencia de verificación: a través de un mensaje de texto o una llamada. Una vez que haya decidido, escriba el número de teléfono, seleccione **Enviarme** un mensaje de texto o **Llamarme** según la selección.

   ![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)
 
4. Escriba el código de verificación y haga clic **en Iniciar la prueba gratuita.**

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita inicio donde puede rellenar el código de verificación que el sistema envió para demostrar que no es un robot](../../media/mtp-eval-26.png)

5. Haga **clic en Probar ahora** para confirmar la versión de prueba de Microsoft 365 E5.

   ![Imagen of_Microsoft 365 E5 Página de prueba gratuita inicio donde debería reloj el botón Probar ahora para iniciarse](../../media/mtp-eval-27.png)
 
6. Vaya a Usuarios activos del Centro de administración de **Microsoft 365.**  >    >   Seleccione su cuenta de usuario, seleccione **Administrar** licencias de productos y, a continuación, cambie la licencia de Office 365 E5 a **Microsoft 365 E5**. Haga clic en **Guardar**.

   ![Página of_Microsoft centro de administración de 365 donde puede seleccionar la licencia de Microsoft 365 E5](../../media/mtp-eval-28.png)
 
7. Vuelva a seleccionar la cuenta de administrador global y, a continuación, **haga clic en Administrar nombre de usuario.**

   ![Imagen of_Microsoft página del Centro de administración de 365, donde puede seleccionar Cuenta y, a continuación, Administrar nombre de usuario](../../media/mtp-eval-29.png)

8. [Opcional] Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que haya elegido en los pasos anteriores. Haga clic en **Guardar cambios**.

   ![Página of_Microsoft centro de administración de 365 donde puede cambiar su preferencia de dominio](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Paso siguiente
|[Fase 3: Configurar & incorporación](config-mtpeval.md) | Configure cada pilar de Microsoft 365 Defender para su entorno piloto o laboratorio de prueba de Microsoft 365 Defender e incorpore los puntos de conexión.
|:-------|:-----|