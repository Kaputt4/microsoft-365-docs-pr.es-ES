---
title: Configurar el laboratorio Microsoft 365 Defender prueba o entorno piloto
description: Access Microsoft 365 Defender portal y, a continuación, configure el entorno Microsoft 365 Defender laboratorio de prueba
keywords: Microsoft 365 Defender de prueba, Microsoft 365 Defender piloto, pruebe Microsoft 365 Defender, Microsoft 365 Defender laboratorio de evaluación
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 681d9798c6f16f5829bdb4e5272abc3eac719a59
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2022
ms.locfileid: "64500989"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>Configurar la prueba Microsoft 365 Defender en un entorno de laboratorio 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Se aplica a:**
- Microsoft 365 Defender 

En este tema se le guía para configurar un entorno de laboratorio dedicado. Para obtener información sobre cómo configurar una versión de prueba en producción, consulte la nueva Guía de evaluación [y Microsoft 365 Defender](eval-overview.md) prueba. 

## <a name="create-an-office-365-e5-trial-tenant"></a>Crear un inquilino Office 365 E5 de prueba
>[!NOTE]
>Si ya tiene una suscripción Office 365 o Azure Active Directory, puede omitir los pasos de creación Office 365 E5 inquilino de prueba.

1. Vaya al portal [Office 365 E5 producto y](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) seleccione **Prueba gratuita**.

   :::image type="content" source="../../media/mtp-eval-9.png" alt-text="La Office 365 E5 de prueba gratuita" lightbox="../../media/mtp-eval-9.png":::
  
2. Complete el registro de prueba especificando su dirección de correo electrónico (personal o corporativa). Haga **clic en Configurar cuenta**.

   :::image type="content" source="../../media/mtp-eval-10.png" alt-text="La Office 365 E5 de configuración del registro de prueba" lightbox="../../media/mtp-eval-10.png":::

3. Rellene el nombre, el apellido, el número de teléfono de empresa, el nombre de la empresa, el tamaño de la empresa y el país o región.  

   :::image type="content" source="../../media/mtp-eval-11.png" alt-text="La Office 365 E5 de configuración de registro de prueba que pide detalles de nombre, teléfono y empresa" lightbox="../../media/mtp-eval-11.png":::
   
   > [!NOTE]
   > El país o región que establezca aquí determina la región del centro de datos que Office 365 se hospedará.
  
4. Elija su preferencia de verificación: a través de un mensaje de texto o una llamada. Haga clic **en Enviar código de verificación**. 

   :::image type="content" source="../../media/mtp-eval-12.png" alt-text="La Office 365 E5 de configuración del registro de prueba que pide la preferencia de verificación" lightbox="../../media/mtp-eval-12.png":::

5. Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **Siguiente**.

   :::image type="content" source="../../media/mtp-eval-13.png" alt-text="La Office 365 E5 de configuración de registro de prueba donde puede configurar el nombre de dominio personalizado" lightbox="../../media/mtp-eval-13.png":::
 
6. Configure la primera identidad, que será un administrador global para el inquilino. Rellene **Nombre y** **contraseña**. Haga clic en **Iniciar sesión**.

   :::image type="content" source="../../media/mtp-eval-14.png" alt-text="La Office 365 E5 de configuración del registro de prueba donde puede establecer su identidad empresarial" lightbox="../../media/mtp-eval-14.png":::

7. Haga **clic en Ir al programa de** instalación para completar el aprovisionamiento Office 365 E5 inquilino de prueba.

   :::image type="content" source="../../media/mtp-eval-15.png" alt-text="La Office 365 E5 de configuración de registro de prueba que pide hacer clic en Ir al botón De instalación" lightbox="../../media/mtp-eval-15.png":::

8. Conectar el dominio corporativo al Office 365 inquilino. [Opcional] Elija **Conectar dominio que ya posee** y escriba el nombre de dominio. Haga clic en **Siguiente**.

   :::image type="content" source="../../media/mtp-eval-16.png" alt-text="La Office 365 E5 de instalación donde debe personalizar el inicio de sesión y el correo electrónico" lightbox="../../media/mtp-eval-16.png":::
 
9. Agregue un registro TXT o MX para validar la propiedad del dominio. Una vez que haya agregado el registro TXT o MX al dominio, seleccione **Comprobar**.

   :::image type="content" source="../../media/mtp-eval-17.png" alt-text="La Office 365 E5 de configuración donde debe agregar un registro TXT de MX para comprobar el dominio" lightbox="../../media/mtp-eval-17.png":::
 
10. [Opcional] Cree más cuentas de usuario para el inquilino. Puede omitir este paso haciendo clic en **Siguiente**.

    :::image type="content" source="../../media/mtp-eval-18.png" alt-text="La Office 365 E5 de instalación donde puede agregar más usuarios" lightbox="../../media/mtp-eval-18.png":::
 
11. [Opcional] Descarga Office aplicaciones. Haga **clic en** Siguiente para omitir este paso. 

    :::image type="content" source="../../media/mtp-eval-19.png" alt-text="La Office 365 E5 donde puedes instalar las aplicaciones Office aplicaciones" lightbox="../../media/mtp-eval-19.png":::

12. [Opcional] Migrar mensajes de correo electrónico. De nuevo, puede omitir este paso.

    :::image type="content" source="../../media/mtp-eval-20.png" alt-text="El Office 365 E5 donde puede establecer si desea migrar mensajes de correo electrónico o no" lightbox="../../media/mtp-eval-20.png":::
 
13. Elija servicios en línea. Seleccione **Exchange** y haga clic en **Siguiente**. 

    :::image type="content" source="../../media/mtp-eval-21.png" alt-text="El Office 365 E5 donde puede elegir sus servicios en línea" lightbox="../../media/mtp-eval-21.png":::

14. Agregue registros MX, CNAME y TXT al dominio. Cuando se complete, seleccione **Comprobar**.

    :::image type="content" source="../../media/mtp-eval-22.png" alt-text="La Office 365 E5 aquí puede agregar los registros DNS" lightbox="../../media/mtp-eval-22.png":::
 
15. Enhorabuena, ha completado el aprovisionamiento de su Office 365 inquilino.

    :::image type="content" source="../../media/mtp-eval-23.png" alt-text="La página Office 365 E5 confirmación de finalización de la instalación" lightbox="../../media/mtp-eval-23.png":::
    

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar Microsoft 365 de prueba

>[!NOTE]
>Registrarse para una versión de prueba le ofrece 25 licencias de usuario para usarlas durante un mes. Consulta [Probar o comprar una suscripción Microsoft 365 para](../../commerce/try-or-buy-microsoft-365.md) obtener más información.

1. En [Administración de Microsoft 365, haga](https://admin.microsoft.com/) clic en **Facturación** y, a continuación, vaya a **Servicios de compra**.

2. Seleccione **Microsoft 365 E5** y haga clic **en Iniciar prueba gratuita**. 

   :::image type="content" source="../../media/mtp-eval-24.png" alt-text="La Microsoft 365 E5 de prueba gratuita De inicio" lightbox="../../media/mtp-eval-24.png":::

3. Elija su preferencia de verificación: a través de un mensaje de texto o una llamada. Una vez que haya decidido, escriba el número de teléfono, seleccione **Enviarme un mensaje** de texto o **Llamarme** según la selección.

   :::image type="content" source="../../media/mtp-eval-25.png" alt-text="La Microsoft 365 E5 de prueba gratuita que pide detalles de contacto para enviar código para demostrar que no es un robot" lightbox="../../media/mtp-eval-25.png":::
 
4. Escribe el código de verificación y haz clic **en Iniciar la prueba gratuita**.

   :::image type="content" source="../../media/mtp-eval-26.png" alt-text="La Microsoft 365 E5 de prueba gratuita en la que puede rellenar el código de verificación que el sistema envió para demostrar que no es un robot" lightbox="../../media/mtp-eval-26.png":::

5. Haga **clic en Probar ahora** para confirmar la Microsoft 365 E5 prueba.

   :::image type="content" source="../../media/mtp-eval-27.png" alt-text="La Microsoft 365 E5 iniciar la versión de prueba gratuita en la que debería reloj el botón Probar ahora para iniciarse" lightbox="../../media/mtp-eval-27.png":::
 
6. Vaya a los **Administración de Microsoft 365** **CenterUsersActive** >  > . Seleccione su cuenta de usuario, seleccione **Administrar licencias de productos** y, a continuación, cambie la licencia de Office 365 E5 a **Microsoft 365 E5**. Haga clic en **Guardar**.

   :::image type="content" source="../../media/mtp-eval-28.png" alt-text="Página del Administración de Microsoft 365 donde puede seleccionar la Microsoft 365 E5 licencia" lightbox="../../media/mtp-eval-28.png":::
 
7. Vuelva a seleccionar la cuenta de administrador global y, a continuación, **haga clic en Administrar nombre de usuario**.

   :::image type="content" source="../../media/mtp-eval-29.png" alt-text="La página Administración de Microsoft 365 centro donde puede seleccionar Cuenta y Administrar nombre de usuario" lightbox="../../media/mtp-eval-29.png":::

8. [Opcional] Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que haya elegido en los pasos anteriores. Haga clic en **Guardar cambios**.

   :::image type="content" source="../../media/mtp-eval-30.png" alt-text="Página del Administración de Microsoft 365 donde puede cambiar su preferencia de dominio" lightbox="../../media/mtp-eval-30.png":::

## <a name="next-step"></a>Paso siguiente
|[Fase 3: Configurar & incorporación](config-m365d-eval.md) | Configure cada Microsoft 365 Defender para su entorno Microsoft 365 Defender prueba o entorno piloto e incorpore los puntos de conexión.
|:-------|:-----|
