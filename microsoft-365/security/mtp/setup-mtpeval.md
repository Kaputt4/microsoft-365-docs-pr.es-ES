---
title: Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection
description: Obtener acceso al centro de seguridad 365 de Microsoft después de configurar el entorno de laboratorio de prueba de Microsoft Threat Protection
keywords: Instalación de prueba de Microsoft Threat Protection, pruebe Microsoft Threat Protection, instalación del laboratorio de evaluación de la protección contra amenazas de Microsoft
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 117681bd4722615e870594e46d6896e9128d0d0c
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209228"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Configurar el entorno de laboratorio de prueba de Microsoft Threat Protection 

**Se aplica a:**
- Protección contra amenazas de Microsoft 


La creación de un entorno de laboratorio de prueba de Microsoft Threat Protection y su implementación es un proceso de tres fases:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Preparar el laboratorio de evaluación de Microsoft Threat Protection" />
      <br/>Fase 1: preparación</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Configurar el laboratorio de evaluación de Microsoft Threat Protection" />
      <br/>Fase 2: configuración</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Configurar cada pilar de protección contra amenazas de Microsoft para el entorno de prueba de la protección contra amenazas de Microsoft y incorporar los puntos de conexión" />
      <br/>Fase 3: configurar & incorporado</a><br>
</td>


  </tr>
</table>

Actualmente se encuentra en la fase de configuración. Realice los pasos iniciales para acceder al centro de seguridad 365 de Microsoft y, a continuación, configure el entorno de laboratorio de prueba.

Regístrese para obtener una suscripción de Office 365 o Azure Active Directory para generar un inquilino *. onmicrosoft.com* que puede usar para registrarse en su licencia de Microsoft 365 E5. 

>[!NOTE]
>Si ya tiene una suscripción a Office 365 o Azure Active Directory existente, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.

En esta fase, se le guiará a:
- Crear un inquilino de prueba de Office 365 E5
- Habilitar la suscripción de prueba de Microsoft 365


## <a name="create-an-office-365-e5-trial-tenant"></a>Crear un inquilino de prueba de Office 365 E5
>[!NOTE]
>Si ya tiene una suscripción a Office 365 o Azure Active Directory existente, puede omitir los pasos de creación de inquilinos de prueba de Office 365 E5.

1. Vaya al [portal de producto de Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) y seleccione **prueba gratuita**.
![Página de prueba gratuita de Image of_Office 365 E5](../../media/mtp-eval-9.png) <br>
  
2. Para completar el registro de prueba, escriba su dirección de correo electrónico (personal o Corporate). Haga clic en **configurar cuenta**.
![Página de configuración de registro de prueba de of_Office de Image 365 E5](../../media/mtp-eval-10.png) <br> 

3. Escriba su nombre, apellidos, número de teléfono del trabajo, nombre de la compañía, tamaño de la compañía y país o región.  
<br>![Página de configuración del registro de prueba de of_Office de la imagen de 365 E5 que solicita el nombre, el teléfono y los detalles de la compañía](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>El país o la región que establezca aquí determina la región del centro de datos donde se hospedará Office 365.
  
4. Elija su preferencia de comprobación: mediante un mensaje de texto o una llamada. Haga clic en **Enviar código de verificación**. 
![Página de configuración del registro de prueba de of_Office de imagen de 365 E5 que solicita preferencia de comprobación](../../media/mtp-eval-12.png) <br>

5. Establezca el nombre de dominio personalizado para el inquilino y, a continuación, haga clic en **siguiente**.
<br>![Página de configuración de registro de prueba de 365 E5 de Image of_Office E5, donde puede configurar su nombre de dominio personalizado](../../media/mtp-eval-13.png) <br>
 
6. Configure la primera identidad que será un administrador global del espacio empresarial. Escriba un **nombre** y una **contraseña**. Haga clic en **Iniciar sesión**.
![Página de configuración de registro de prueba de 365 E5 de Image of_Office E5, donde puede configurar la identidad de la empresa](../../media/mtp-eval-14.png) <br>

7. Haga clic en **ir al programa de instalación** para completar el aprovisionamiento de inquilino de prueba de Office 365 E5.
<br>![Imagen de la página de configuración del registro de prueba de Office 365 E5 solicitando hacer clic en el botón de configuración de Go](../../media/mtp-eval-15.png) <br>

8. Conecte el dominio corporativo al inquilino de Office 365. Opcional Elija **conectar un dominio que ya posee** y escriba el nombre de dominio. Haga clic en **Siguiente**.
<br>![Página de instalación de Image of_Office 365 E5 donde debe personalizar el inicio de sesión y el correo electrónico](../../media/mtp-eval-16.png) <br>
 
9. Tendrá que agregar un registro TXT o MX para validar la propiedad del dominio. Una vez que haya agregado el registro TXT o MX a su dominio, seleccione **comprobar**.
<br>![Página de instalación de Image of_Office 365 E5 donde debe agregar un TXT del registro MX para comprobar su dominio](../../media/mtp-eval-17.png) <br>
 
10. Opcional Cree más cuentas de usuario para el inquilino. Puede omitir este paso haciendo clic en **siguiente**.
![Página de instalación de Image of_Office 365 E5 donde puede agregar más usuarios](../../media/mtp-eval-18.png) <br>
 
11. Opcional Descargue las aplicaciones de Office. Haga clic en **siguiente** para omitir este paso. 
<br>![Página de imagen of_Office 365 E5 donde puede instalar las aplicaciones de Office](../../media/mtp-eval-19.png) <br>

12. Opcional Migrar mensajes de correo electrónico. De nuevo, puede omitir este paso.
<br>![Image of_Office 365 E5 donde puede establecer si desea migrar los mensajes de correo electrónico o no.](../../media/mtp-eval-20.png) <br>
 
13. Elija servicios en línea. Seleccione **Exchange** y haga clic en **siguiente**. 
<br>![Image of_Office 365 E5 donde puede elegir sus servicios en línea como Exchangem Skype for Business o Mibile Device Management for Office 365](../../media/mtp-eval-21.png) <br>

14. Agregue los registros MX, CNAME y TXT a su dominio. Una vez completada, seleccione **comprobar**.
<br>![Image of_Office 365 E5 aquí puede agregar sus registros DNS](../../media/mtp-eval-22.png) <br>
 
15. Enhorabuena, ha completado el aprovisionamiento de su inquilino de Office 365.
<br>![Página de confirmación de finalización de la instalación de Image of_Office 365 E5](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Habilitar la suscripción de prueba de Microsoft 365

>[!NOTE]
>Al registrarse para obtener una prueba, se le da 25 licencias de usuario para usarla durante un mes. Consulte [probar o comprar una suscripción a M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) para obtener más información.

1. En [centro de administración de 365 de Microsoft](https://admin.microsoft.com/), haga clic en **facturación** y navegue a **servicios de compra**.

2. Seleccione **Microsoft 365 E5** y haga clic en **iniciar prueba gratuita**. 
![Página de prueba de inicio gratuito de Image of_Microsoft 365 E5](../../media/mtp-eval-24.png) <br>

3. Elija su preferencia de comprobación: mediante un mensaje de texto o una llamada. Una vez que haya decidido, escriba el número de teléfono, seleccione **texto me** o **llámeme** en función de la selección.
![Image of_Microsoft 365 E5 página de prueba gratuita de inicio para solicitar detalles de contacto para enviar código para demostrar que no es un robot](../../media/mtp-eval-25.png) <br>
 
4. Escriba el código de verificación y haga clic en **iniciar la versión de prueba gratuita**. 
<br>![Image of_Microsoft 365 E5 página de prueba gratuita de inicio, donde puede rellenar el código de verificación que el sistema ha enviado para demostrar que no es un robot](../../media/mtp-eval-26.png) <br>

5. Haga clic en **probar ahora** para confirmar la prueba de Microsoft 365 E5.
<br>![Página de prueba de inicio gratuita de Image of_Microsoft 365 E5 donde debe entrar en el botón probar ahora para iniciar](../../media/mtp-eval-27.png) <br>
 
6. Vaya a los usuarios activos del **centro de administración de Microsoft 365**  >  **Users**  >  **Active users**. Seleccione su cuenta de usuario, seleccione **administrar licencias de producto**y, a continuación, intercambie la licencia de Office 365 E5 a **Microsoft 365 E5**. Haga clic en **Guardar**.
![Imagen of_Microsoft 365 página del centro de administración donde puede seleccionar la licencia de Microsoft 365 E5](../../media/mtp-eval-28.png) <br>
 
7. Seleccione la cuenta de administrador global de nuevo y haga clic en **administrar nombre de usuario**.
<br>![Imagen of_Microsoft 365 página del centro de administración donde puede seleccionar cuenta y, a continuación, administrar el nombre de usuario](../../media/mtp-eval-29.png) <br>

8. Opcional Cambie el dominio de *onmicrosoft.com* a su propio dominio, en función de lo que elija en los pasos anteriores. Haga clic en **Guardar cambios**.
<br>![Imagen of_Microsoft 365 página del centro de administración donde puede cambiar su preferencia de dominio](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Paso siguiente
||| |:-------|:-----| config-onboard. png) <br>[Fase 3: configuración & incorporada](config-mtpeval.md) | Configure cada pilar de protección contra amenazas de Microsoft para el entorno de prueba de la protección contra amenazas de Microsoft y incorpore los puntos de conexión.
