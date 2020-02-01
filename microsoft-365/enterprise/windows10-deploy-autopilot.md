---
title: Implementar Windows 10 Enterprise para dispositivos nuevos con Windows AutoPilot
description: Proporciona instrucciones sobre cómo configurar e implementar Windows 10 Enterprise con Windows AutoPilot.
keywords: Microsoft 365, Microsoft 365 Enterprise, documentación de Microsoft 365, Windows 10 Enterprise, implementación, Windows AutoPilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: e5e3e4fb48a0eb2af1978cbd5a687c67c72bea0c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596647"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>Paso 3: implementar Windows 10 Enterprise para dispositivos nuevos con Windows AutoPilot

*Este artículo se aplica a las versiones E3 y E5 de Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Si tienes nuevos equipos con Windows 10, puedes usar Windows AutoPilot para personalizar la experiencia rápida (OOBE) de tu organización e implementar un nuevo sistema con aplicaciones y configuración ya configurada. No hay imágenes para implementar, no hay controladores para insertar y no hay infraestructura que administrar. Los usuarios pueden pasar por el proceso de implementación de manera independiente, sin necesidad de consultar a su administrador de ti.

Puede configurar y preconfigurar nuevos dispositivos Windows 10 y prepararlos para un uso productivo mediante Windows AutoPilot. Para obtener más información acerca de Windows AutoPilot, incluidas las ventajas y los escenarios de Windows AutoPilot, consulte [Overview of Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot). Cuando esté listo, siga estas partes para empezar a configurar nuevos dispositivos.

## <a name="the-windows-autopilot-deployment-process-poster"></a>Póster del proceso de implementación de Windows AutoPilot

El póster de Windows AutoPilot es de dos páginas en modo vertical (11 x 17). Haga clic en la imagen siguiente para ver un PDF en el explorador. 

[![El póster para la implementación de Windows 10 con piloto automático](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://docs.microsoft.com/windows/deployment/media/Windows10AutopilotFlowchart.pdf)

También puede descargar este póster en [PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) o en formato de [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx).

## <a name="part-1-start-windows-autopilot-deployment"></a>Parte 1: iniciar la implementación de Windows AutoPilot
Vea [información general de Windows AutoPilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) para:

1. Obtenga información y cómo completar los requisitos previos para la implementación de Windows AutoPilot. Entre los requisitos previos se incluyen:
    - **El registro de dispositivos y la personalización de la configuración rápida**

        Para registrar dispositivos, debe adquirir su identificador de hardware y registrarlo. Estamos trabajando activamente con varios proveedores de hardware para que puedan proporcionarle la información necesaria o cargarlo en su nombre. También tiene la opción de capturar esta información mediante un script de PowerShell que genera un archivo. csv con el identificador de hardware del dispositivo.

        Una vez que se han registrado los dispositivos, hay opciones de personalización de OOBE que puede configurar, lo que permite omitir la configuración de privacidad y el CLUF.

    - **Personalización de marca para configuración rápida**

        Esto le permite agregar personalización de marca para que aparezca durante la OOBE del dispositivo.

    - **Inscripción automática de MDM en Microsoft Intune**
        
        La inscripción automática permite a los usuarios inscribir sus dispositivos Windows 10 en Intune para la administración de dispositivos cuando conectan sus dispositivos a Azure AD. Para inscribirse, los usuarios agregan su cuenta profesional a sus dispositivos de propiedad personal o se unen a los dispositivos de propiedad corporativa para Azure AD. En segundo plano, el dispositivo también está inscrito para la administración con Intune.

    - **Conectividad de red a servicios en la nube usados por Windows Autopilot**

        El programa de implementación de Windows AutoPilot usa una cantidad de servicios en la nube para obtener los dispositivos en un estado productivo y estos servicios deben ser accesibles desde dispositivos registrados como dispositivos de Windows AutoPilot. 

    - **Los dispositivos deben tener preinstalado Windows 10, versión 1703 o posterior**

2. Obtenga información sobre y seleccione el programa de implementación de Windows AutoPilot para su organización. Puede seleccionar entre estos programas de implementación:
    - **Microsoft Store para Empresas**
    - **Microsoft Intune**
    - **Centro para socios**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>Parte 2: configurar un dispositivo con Windows 10 para Microsoft 365
Para poder configurar dispositivos Windows para los usuarios de Microsoft 365, asegúrese de que todos los dispositivos Windows ejecutan Windows 10, versión 1703 (Creators Update) o posterior.

Una vez que todos los dispositivos Windows de su organización hayan sido actualizados a Windows 10 Creators Update o que ya estén ejecutando Windows 10 Creators Update, puede unir estos dispositivos al Azure Active Directory de la organización.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>Configurar un dispositivo de Windows 10 nuevo o con una marca recién actualizada
Siga estos pasos para configurar un dispositivo con Windows 10 OOBE en un dispositivo nuevo que ejecute Windows 10 Creators Update (o posterior) o en un dispositivo que se haya actualizado a Windows 10 Creators Update (o posterior), pero que no haya pasado por una configuración rápida.

1. Si no tiene una red inalámbrica configurada, asegúrese de conectar el dispositivo a Internet a través de una conexión cableada o Ethernet.
2. Pasar por la experiencia de instalación de dispositivos de Windows. En un dispositivo nuevo o de restablecimiento, la experiencia del programa de instalación comienza con la **región comencemos. ¿Es este el derecho?** Screen.
3. Siga el proceso de configuración de dispositivos Windows 10 hasta que llegue a la página **¿Cómo quiere realizar la configuración?**. Seleccione **configurar para una organización**.
4. Inicie sesión con la cuenta y la contraseña del usuario de Microsoft 365. Según la configuración de contraseña de usuario, es posible que se le pida que actualice la contraseña. 
5. Finalice la configuración del dispositivo Windows 10.

Una vez que haya terminado, el dispositivo se conectará a Azure AD de la organización.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>Configurar un dispositivo que ya ha completado la configuración de instalación
Si el dispositivo tiene Windows 10 Creators Update (o posterior) y ya ha pasado mediante la configuración preconfigurada, siga estos pasos.

1. En el PC Windows del usuario que ejecuta la versión 1703 de (Creators Update), seleccione el logotipo de **Windows** y, a continuación, seleccione el icono de **configuración** .
2. En **Configuración**, vaya a **Cuentas**.
3. En la página **su información** , seleccione **Access Work o School** > **Connect**.
4. En el cuadro de diálogo **configurar una cuenta profesional o educativa** , en **acciones alternativas**, seleccione **unir este dispositivo a Azure Active Directory**.
5. En la página **vamos a iniciar sesión** , escriba su cuenta profesional o educativa y seleccione **siguiente**.
6. En la página **escribir contraseña** , escriba la contraseña y seleccione **iniciar sesión**.
7. En la página Asegúrese de que **es su organización** , compruebe que la información es correcta y seleccione **unirse**.
8. En la de **todo está juego.** en la página, seleccione **listo**.

Una vez que haya terminado, el usuario se conectará a Azure AD de la organización.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>Comprobar que un dispositivo está conectado a Azure AD
Siga estos pasos para comprobar el estado de sincronización del dispositivo con Azure AD y, a continuación, empiece a usar su cuenta de Microsoft 365 en el dispositivo. 

1. Abra **configuración**.
2. En la **Página tener acceso a la escuela o el trabajo** , seleccione el área **conectado a <organization name> ** para mostrar la **información** de los botones y **desconectar**.
3. Seleccione **información** para obtener el estado de sincronización.
4. En la página **Estado de sincronización** , seleccione **sincronizar** para obtener las directivas de administración de dispositivos móviles más recientes en el equipo.
5. Para empezar a usar la cuenta de Microsoft 365, vaya al botón **Inicio** de Windows, haga clic con el botón secundario en la imagen de cuenta actual y seleccione **cambiar** de cuenta.
6. Inicie sesión con el correo electrónico y la contraseña de la organización.

Si experimenta problemas al usar Windows 10 en un entorno empresarial, puede consultar [las principales soluciones de soporte técnico de Microsoft para los problemas más comunes](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Estos recursos incluyen artículos de Knowledge base, actualizaciones y artículos de bibliotecas.

Como control provisional, puede consultar los [criterios de salida](windows10-exit-criteria.md#crit-windows10-step3) correspondientes a este paso.

## <a name="next-step"></a>Siguiente paso

|||
|:-------|:-----|
|![Paso 4](./media/stepnumbers/Step4.png)| [Supervisar el estado y el cumplimiento del dispositivo](windows10-enable-windows-analytics.md) |
