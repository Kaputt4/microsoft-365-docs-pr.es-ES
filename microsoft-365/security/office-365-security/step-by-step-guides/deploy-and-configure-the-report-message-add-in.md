---
title: Implementación y configuración del complemento de mensajes de informe
description: Los pasos para implementar y configurar los complementos de informes de phish de Microsoft dirigidos a administradores de seguridad
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTBen
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: 36e3fe25444f57de4cd43d67cab5a99f546a0f13
ms.sourcegitcommit: a209c9f86a7b4340a426c4cfed2d36a388c71124
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "66798218"
---
# <a name="deploy-and-configure-the-report-message-add-in-to-users"></a>Implemente y configure el complemento de mensaje de informe para los usuarios.

El complemento de suplantación de identidad de informes y mensajes de informe para Outlook facilita la notificación de suplantación de identidad (phishing) a Microsoft y sus filiales para su análisis, junto con una fácil evaluación para los administradores en el [portal de envíos](https://security.microsoft.com/reportsubmission?viewid=user). 

En función de si tiene licencia para Defender para Office 365, también obtendrá funcionalidad adicional, como alertas & investigación y respuesta automatizadas (AIR), que quitarán la carga del personal de operaciones de seguridad. Esta guía le guiará a través de la configuración de la implementación del complemento según lo recomendado por el equipo de Microsoft Defender para Office 365.

## <a name="choose-between-which-add-in-to-deploy"></a>Elegir entre qué complemento se va a implementar

- El complemento De suplantación de identidad de informe proporciona la opción de notificar solo mensajes de suplantación de identidad (phishing)
- El complemento Mensaje de informe proporciona la opción de informar de mensajes no deseados, no de correo no deseado (falsos positivos) y de suplantación de identidad (phishing).


## <a name="what-youll-need"></a>Lo que necesitará

-   Exchange Online Protection (algunas características requieren Defender para Office 365 plan 2)
-   Permisos suficientes (administrador global para la implementación de complementos, administrador de seguridad para la personalización)
- 5-10 minutos para realizar los pasos siguientes

## <a name="deploy-the-add-in-for-users"></a>Implementación del complemento para usuarios

1.  **Inicie sesión** en el Centro de administración de Microsoft 365.  https://admin.microsoft.com.
1.  En el panel de navegación izquierdo, presione **Mostrar todo** , expanda **Configuración** y seleccione **Aplicaciones integradas**.
1.  En la página que se carga, presione **Obtener aplicaciones**.
1.  En la página que aparece, en el cuadro de búsqueda superior derecho, escriba **Mensaje de informe** o **Suplantación de identidad de** informe y, a continuación, seleccione **Buscar**.
1.  Presione **Obtener ahora** en la aplicación elegida dentro de los resultados de búsqueda (publisher es **Microsoft Corporation**).
1.  En el control flotante que aparece, seleccione en quién implementar el complemento. Si quiere usar un grupo específico en las pruebas, configúrelo para toda la **organización** , cuando haya hecho una selección, presione **Siguiente**.
1.  Revise los permisos, la información y las funcionalidades y presione **Siguiente**.
1.  Presione **Finalizar implementación** (el complemento puede tardar entre 12 y 24 horas en aparecer automáticamente en los clientes de Outlook).

## <a name="configure-the-add-in-for-users"></a>Configuración del complemento para usuarios
1.  **Inicie sesión en** el portal de seguridad de Microsoft en https://security.microsoft.com.
2.  En el panel de navegación izquierdo, en **Email & colaboración**, seleccione **Directivas & reglas**.
3.  Seleccione **Directivas de amenazas**.
4.  Seleccione **Configuración de mensajes notificados por el usuario** debajo del encabezado **Otros** .
5.  Asegúrese de que el **botón Mensaje de informe de Microsoft Outlook** esté **activado.**
6.  En **Enviar los mensajes notificados para** elegir **Microsoft** (recomendado).
7.  Asegúrese de **que permitir que los usuarios elijan si quieren informar** está desactivada y **siempre informe de que el mensaje** está seleccionado.
8.  Presione **Guardar**.

## <a name="optional-steps--configure-notifications"></a>Pasos opcionales: configuración de notificaciones

1.  En la página de configuración de los pasos anteriores, debajo de la **experiencia de informes de usuario**, configure el título y el cuerpo de los elementos emergentes antes y después si lo desea. Los usuarios finales verán el elemento emergente antes de informar si **preguntarme antes de informar** también está habilitado.
2.  Si desea que las notificaciones procedan de un buzón organizativo interno, seleccione **Especificar Office 365 dirección de correo electrónico para usarla como remitente** y busque un buzón válido en su organización desde el que enviar las notificaciones.
3.  Presione **Personalizar notificaciones** para configurar el texto enviado a los usuarios de informes después de que el administrador revise un mensaje notificado mediante Marcar & Notificar, configure las opciones **Phishing**, **No se** encontraron amenazas no **deseados** & .
4.  En la pestaña **Pie de página** , seleccione el pie de página global que se enviará para recibir notificaciones, junto con el logotipo de su organización, si procede.


### <a name="further-reading"></a>Lectura adicional
Más información sobre la configuración de mensajes notificados por el usuario [Configuración de mensajes notificados por el usuario: Office 365 | Microsoft Docs](../user-submission.md)

Habilitar el mensaje de informe o el complemento de suplantación de identidad del informe [Habilite el mensaje de informe o los complementos de suplantación de identidad de informe( Office 365 | Microsoft Docs](../enable-the-report-message-add-in.md)
