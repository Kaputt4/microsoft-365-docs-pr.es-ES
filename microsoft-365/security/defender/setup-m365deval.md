---
title: Configuración del laboratorio de prueba de Microsoft 365 Defender o entorno piloto
description: Acceda a Microsoft 365 Defender portal y configure el entorno de laboratorio de prueba de Microsoft 365 Defender
keywords: Microsoft 365 Defender configuración de prueba, Microsoft 365 Defender configuración piloto, pruebe Microsoft 365 Defender, Microsoft 365 Defender configuración del laboratorio de evaluación.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.service: microsoft-365-security
ms.subservice: m365d
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
- highpri
ms.topic: article
ms.openlocfilehash: 116efc949edace902b8e71abb27f5c091407fb14
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2022
ms.locfileid: "67482282"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>Configuración de la prueba de Microsoft 365 Defender en un entorno de laboratorio 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender 

Este tema le guía para configurar un entorno de laboratorio dedicado. Para obtener información sobre cómo configurar una prueba en producción, consulte la nueva guía [de evaluación y prueba piloto Microsoft 365 Defender](eval-overview.md). 

## <a name="create-an-office-365-e5-trial-tenant"></a>Creación de un inquilino de prueba de Office 365 E5
>[!NOTE]
>Si ya tiene una Office 365 existente o una suscripción de Azure Active Directory, puede omitir los pasos de creación de inquilinos de prueba Office 365 E5.

1. Vaya al [portal Office 365 E5 producto](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) y seleccione **Evaluación gratuita**.

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="Página de evaluación gratuita Office 365 E5" lightbox="../../media/mtp-eval-9.png":::
  
2. Complete el registro de prueba escribiendo su dirección de correo electrónico (personal o corporativa). Haga clic en **Configurar cuenta**.

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="Página de configuración del registro de prueba de Office 365 E5" lightbox="../../media/mtp-eval-10.png":::

3. Rellene el nombre, el apellido, el número de teléfono de la empresa, el nombre de la empresa, el tamaño de la empresa y el país o región.  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="La página de configuración del registro de prueba Office 365 E5 en la que se solicitan los detalles del nombre, el teléfono y la empresa" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > El país o región que establezca aquí determina la región del centro de datos en la que se hospedará el Office 365.
  
4. Elija su preferencia de verificación: a través de un mensaje de texto o una llamada. Haga clic en **Enviar código de verificación**. 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="La página Office 365 E5 configuración del registro de prueba que solicita preferencias de comprobación" lightbox="../../media/mtp-eval-12.png":::

5. Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **Siguiente**.

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="La página de configuración del registro de prueba de Office 365 E5 donde puede configurar el nombre de dominio personalizado." lightbox="../../media/mtp-eval-13.png":::
 
6. Configure la primera identidad, que será un administrador global para el inquilino. Rellene **El nombre** y la **contraseña**. Haga clic en **Iniciar sesión**.

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="Página de configuración del registro de prueba de Office 365 E5 donde puede establecer su identidad empresarial" lightbox="../../media/mtp-eval-14.png":::

7. Haga clic en **Ir al programa de instalación** para completar el Office 365 E5 aprovisionamiento de inquilinos de prueba.

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="La página de configuración del registro de prueba Office 365 E5 solicitando hacer clic en el botón Ir a la instalación" lightbox="../../media/mtp-eval-15.png":::

8. Conecte el dominio corporativo al inquilino de Office 365. [Opcional] Elija **Conectar un dominio que ya posee** y escriba el nombre de dominio. Haga clic en **Siguiente**.

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="Página de configuración de Office 365 E5 en la que debe personalizar el inicio de sesión y el correo electrónico" lightbox="../../media/mtp-eval-16.png":::
 
9. Agregue un registro TXT o MX para validar la propiedad del dominio. Una vez que haya agregado el registro TXT o MX al dominio, seleccione **Comprobar**.

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="La página de configuración de Office 365 E5 donde debe agregar un TXT de registro MX para comprobar el dominio." lightbox="../../media/mtp-eval-17.png":::
 
10. [Opcional] Cree más cuentas de usuario para el inquilino. Para omitir este paso, haga clic en **Siguiente**.

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="Página de configuración de Office 365 E5 donde puede agregar más usuarios" lightbox="../../media/mtp-eval-18.png":::
 
11. [Opcional] Descargue aplicaciones de Office. Haga clic en **Siguiente** para omitir este paso. 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="Página de Office 365 E5 donde puede instalar las aplicaciones de Office" lightbox="../../media/mtp-eval-19.png":::

12. [Opcional] Migrar mensajes de correo electrónico. De nuevo, puede omitir este paso.

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="El Office 365 E5 donde puede establecer si desea migrar mensajes de correo electrónico o no" lightbox="../../media/mtp-eval-20.png":::
 
13. Elija servicios en línea. Seleccione **Exchange** y haga clic en **Siguiente**. 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="El Office 365 E5 donde puede elegir el servicios en línea" lightbox="../../media/mtp-eval-21.png":::

14. Agregue registros MX, CNAME y TXT al dominio. Cuando se complete, seleccione **Comprobar**.

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="La Office 365 E5 aquí puede agregar los registros DNS." lightbox="../../media/mtp-eval-22.png":::
 
15. Enhorabuena, ha completado el aprovisionamiento del inquilino de Office 365.

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="Página de confirmación de finalización de la instalación Office 365 E5" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitación de la suscripción de prueba de Microsoft 365

>[!NOTE]
>Registrarse en una prueba le ofrece 25 licencias de usuario para usarlas durante un mes. Consulte [Probar o comprar una suscripción a Microsoft 365](../../commerce/try-or-buy-microsoft-365.md) para obtener más información.

1. En [Administración de Microsoft 365 Centro](https://admin.microsoft.com/), haga clic en **Facturación** y, a continuación, vaya a **Comprar servicios**.

2. Seleccione **Microsoft 365 E5** y haga clic en **Iniciar evaluación gratuita**. 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="Página de evaluación gratuita de inicio Microsoft 365 E5" lightbox="../../media/mtp-eval-24.png":::

3. Elija su preferencia de verificación: a través de un mensaje de texto o una llamada. Una vez que haya decidido, escriba el número de teléfono, seleccione **Text me** or **Call me** dependiendo de su selección.

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="La página de evaluación gratuita de Microsoft 365 E5 Start (Iniciar) en la que se solicitan los detalles de contacto para enviar código para demostrar que no es un robot" lightbox="../../media/mtp-eval-25.png":::
 
4. Escriba el código de verificación y haga clic en **Iniciar la evaluación gratuita**.

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="La Microsoft 365 E5 página de prueba gratuita Iniciar, donde puede rellenar el código de verificación que el sistema envió para demostrar que no es un robot." lightbox="../../media/mtp-eval-26.png":::

5. Haga clic en **Probar ahora** para confirmar la prueba de Microsoft 365 E5.

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="La página de evaluación gratuita Microsoft 365 E5 Iniciar, donde debe reloj el botón Probar ahora para iniciar" lightbox="../../media/mtp-eval-27.png":::
 
6. Vaya a usuarios **activos** del **Centro** >  >  de Administración de Microsoft 365. Seleccione su cuenta de usuario, seleccione **Administrar licencias de productos** y, a continuación, cambie la licencia de Office 365 E5 a **Microsoft 365 E5**. Haga clic en **Guardar**.

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="Página del Centro de Administración de Microsoft 365 donde puede seleccionar la licencia de Microsoft 365 E5" lightbox="../../media/mtp-eval-28.png":::
 
7. Vuelva a seleccionar la cuenta de administrador global y haga clic en **Administrar nombre de usuario**.

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="Página del Centro de Administración de Microsoft 365 donde puede seleccionar Cuenta y Administrar nombre de usuario" lightbox="../../media/mtp-eval-29.png":::

8. [Opcional] Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que haya elegido en los pasos anteriores. Haga clic en **Guardar cambios**.

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="Página del Centro de Administración de Microsoft 365 en la que puede cambiar sus preferencias de dominio" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>Paso siguiente
|[Fase 3: Configuración de la incorporación de &](config-m365d-eval.md) | Configure cada pilar de Microsoft 365 Defender para el laboratorio de prueba de Microsoft 365 Defender o entorno piloto e incorpore los puntos de conexión.
|:-------|:-----|
