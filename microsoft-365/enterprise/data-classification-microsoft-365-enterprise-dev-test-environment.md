---
title: Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- scotvorg
- M365-security-compliance
ms.custom:
- Ent_TLGs
- admindeeplinkMAC
- admindeeplinkDEFENDER
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de pruebas para crear y usar etiquetas de retención en documentos del entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 959492fc2cd8402165b5222dbafc6d718fc9d14b
ms.sourcegitcommit: 0b7070ec119e00e0dafe030bbfbef0ae5c9afa19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2022
ms.locfileid: "68168801"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas

*Esta guía de laboratorio de pruebas se puede usar para Microsoft 365 para entornos de prueba empresariales y Office 365 Enterprise.*

En este artículo se describe cómo configurar la clasificación de datos mediante etiquetas de retención en el entorno de prueba de Microsoft 365 para empresas.

La clasificación de datos en el entorno de prueba implica tres fases:
- [Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Creación de etiquetas de retención](#phase-2-create-retention-labels)
- [Fase 3: Aplicación de etiquetas de retención a documentos](#phase-3-apply-retention-labels-to-documents)

![Guías de laboratorio de prueba para la nube de Microsoft.](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila guía del laboratorio de pruebas de Microsoft 365 para empresas, vaya a [Microsoft 365 para enterprise Test Lab Guide Stack (Pila de guía del laboratorio de pruebas empresariales).](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Compilación del entorno de prueba de Microsoft 365 para empresas

Si solo quiere configurar las etiquetas de retención de forma ligera con los requisitos mínimos, siga las instrucciones de [Configuración base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar etiquetas de retención en una empresa simulada, siga las instrucciones de [Autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Las pruebas de etiquetas de retención no requieren el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de Servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar las licencias automatizadas y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: Creación de etiquetas de retención

En esta fase, cree las etiquetas de retención para los distintos niveles de retención para carpetas de documentos de SharePoint Online:

1. Inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">portal de Microsoft 365 Defender</a> con su cuenta de administrador global.
1. En la pestaña **Inicio: Seguridad de Microsoft 365** del explorador, seleccione **Etiquetas de retención** de **clasificación** > .
1. Seleccione **Crear una etiqueta**.
1. En el panel **Nombre de la etiqueta** , escriba **Público interno** en **Nombre de la etiqueta** y, a continuación, seleccione **Siguiente**.
1. En el panel **Descriptores del plan de** archivos, seleccione **Siguiente**.
1. En el panel **Configuración de etiqueta** , si es necesario, establezca **Retención** **en Activado** y, a continuación, seleccione **Siguiente**.
1. En el panel **Revisar la configuración** , seleccione **Crear la etiqueta**.
1. Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:
  - Private
  - Confidencial
  - Extremadamente confidencial
1. En el panel **Etiquetas de retención** , seleccione **Publicar etiquetas**.
1. En el panel **Elegir etiquetas para publicar** , seleccione **Elegir etiquetas para publicar**.
1. En el panel **Elegir etiquetas** , seleccione **Agregar** y seleccione las cuatro etiquetas.
1. Seleccione **Agregar** y, a continuación, haga **clic en Listo**.
1. En el panel **Elegir etiquetas para publicar** , seleccione **Siguiente**.
1. En el panel **Elegir ubicaciones** , seleccione **Siguiente**.
1. En el panel **Nombre de la directiva** , escriba **Organización de ejemplo** en **Nombre** y, a continuación, seleccione **Siguiente**.
1. En el panel **Revisar la configuración** , seleccione **Publicar etiquetas**.
 
Las etiquetas de retención pueden tardar unos minutos en publicarse.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: Aplicación de etiquetas de retención a documentos

En esta fase, detectará el comportamiento predeterminado de la etiqueta de retención de los archivos de la carpeta Documentos de un sitio de SharePoint Online y cambiará manualmente la etiqueta de retención de un documento.

En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:
  
1. Con una instancia privada del explorador, inicie sesión en el <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Centro de administración de Microsoft 365</a> con su cuenta de administrador global.
1. En la lista de iconos, seleccione **SharePoint**.
1. En la nueva pestaña **De SharePoint** en el explorador, seleccione **Crear sitio**.
1. En la página **Crear un sitio**, seleccione **Sitio de grupo**.
1. En el cuadro **Nombre del sitio del equipo** , escriba **SensitiveFiles**.
1. En el cuadro **Descripción del sitio del equipo** , escriba Sitio de **SharePoint para archivos confidenciales**.
1. En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden acceder a este sitio** y, a continuación, seleccione **Siguiente**.
1. En el panel **¿Quién desea agregar?** , seleccione **Finalizar**.
    
A continuación, configure la carpeta Documentos del sitio de equipo SensitiveFiles para la etiqueta de retención confidencial.
  
1. En la pestaña **SensitiveFiles** del explorador, seleccione **Documentos**.
1. Seleccione el icono **Configuración** y, a continuación, seleccione **Configuración de biblioteca**.
1. En **Permisos y administración**, seleccione **Aplicar etiqueta a los elementos de esta lista o biblioteca**. Si esta opción no aparece, las etiquetas de retención aún no se publican. Pruebe este paso más adelante.
1. En **Configuración-Aplicar etiqueta**, seleccione **Confidencial** en el cuadro desplegable y, a continuación, seleccione **Guardar**.

A continuación, cree un nuevo documento en el sitio SensitiveFiles y cambie su etiqueta de retención.
    
1. En la carpeta documentos, seleccione **Nuevo** > **documento de Word**.
1. Escriba texto en el documento en blanco. Espere a que se guarde el texto.
1. En la barra de menús, seleccione **Documentos compartidos**.
1. Junto al nombre de archivo **Document.docx** , seleccione los puntos suspensivos verticales y, a continuación, seleccione **Detalles**.
1. En el panel derecho, en la sección **Propiedades** , en **Aplicar etiqueta de retención**, tenga en cuenta que el documento ha aplicado automáticamente la etiqueta de retención **confidencial** .
1. Haga clic en **Editar todo**.
1. En el panel **Document.docx** , en **Aplicar etiqueta de retención**, seleccione la etiqueta **Extremadamente confidencial** y, a continuación, seleccione **Guardar**.

## <a name="next-step"></a>Paso siguiente

Explore características y funcionalidades adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) en el entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación para Microsoft 365 Enterprise](/microsoft-365-enterprise/)
