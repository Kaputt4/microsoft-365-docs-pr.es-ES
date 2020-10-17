---
title: Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del entorno de pruebas para crear y usar etiquetas de retención en documentos en el entorno de prueba de Microsoft 365 para empresas.
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487737"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Clasificación de datos para el entorno de prueba de Microsoft 365 para empresas

*Esta guía del entorno de pruebas se puede usar tanto para entornos de prueba empresariales de Microsoft 365 para empresas como para Office 365.*

En este artículo se describe cómo configurar la clasificación de datos con etiquetas de retención en el entorno de prueba de Microsoft 365 para empresas.

La clasificación de datos en el entorno de prueba implica tres fases:
- [Fase 1: crear el entorno de prueba de Microsoft 365 para empresas](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: crear etiquetas de retención](#phase-2-create-retention-labels)
- [Fase 3: aplicar etiquetas de retención a los documentos](#phase-3-apply-retention-labels-to-documents)

![Guías de laboratorio de pruebas para Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Para obtener un mapa visual de todos los artículos de la pila de la guía del entorno de pruebas de 365 para empresas, vaya a la [pila de la guía de entorno de pruebas 365 de Microsoft para empresas](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 para empresas

Si solo quiere configurar las etiquetas de retención de una manera ligera con los requisitos mínimos, siga las instrucciones de [configuración de base ligera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar las etiquetas de retención en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de las etiquetas de retención no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica.

## <a name="phase-2-create-retention-labels"></a>Fase 2: crear etiquetas de retención

En esta fase, cree las etiquetas de retención para los distintos niveles de retención para las carpetas de documentos de SharePoint Online:

1. Inicie sesión en el [centro de seguridad 365 de Microsoft](https://security.microsoft.com/homepage) con su cuenta de administrador global.
1. En la pestaña **Inicio-seguridad de Microsoft 365** del explorador, seleccione **Classification**  >  **etiquetas de retención**de clasificación.
1. Seleccione**Crear una etiqueta**.
1. En el panel **asignar un nombre a la etiqueta** , escriba **público interno** en **nombre de la etiqueta**y, a continuación, seleccione **siguiente**.
1. En el panel **descriptores del plan de archivos** , seleccione **siguiente**.
1. En el **panel Configuración de etiqueta** , si es necesario, establezca **retenciones** en **activado**y, a continuación, seleccione **siguiente**.
1. En el panel **Revise su configuración** , seleccione **crear la etiqueta**.
1. Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:
  - Private
  - Confidencial
  - Extremadamente confidencial
1. En el panel **etiquetas de retención** , seleccione **publicar etiquetas**.
1. En el panel **elegir etiquetas para publicar** , seleccione **elegir etiquetas para publicar**.
1. En el panel **elegir etiquetas** , seleccione **Agregar** y seleccione las cuatro etiquetas.
1. Seleccione **Agregar**y, a continuación, haga clic en **listo**.
1. En el panel **elegir etiquetas para publicar** , seleccione **siguiente**.
1. En el panel **elegir ubicaciones** , seleccione **siguiente**.
1. En el panel escriba **un nombre para la Directiva** , escriba **organización de ejemplo** en **nombre**y, a continuación, seleccione **siguiente**.
1. En el panel **Revise su configuración** , seleccione **publicar etiquetas**.
 
La publicación de las etiquetas de retención puede tardar unos minutos.

## <a name="phase-3-apply-retention-labels-to-documents"></a>Fase 3: aplicar etiquetas de retención a los documentos

En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención para los archivos de la carpeta documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.

En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:
  
1. Con una instancia privada del explorador, inicie sesión en el [centro de administración de Microsoft 365](https://admin.microsoft.com) mediante su cuenta de administrador global.
1. En la lista de mosaicos, seleccione **SharePoint**.
1. En la nueva pestaña de **SharePoint** del explorador, seleccione **crear sitio**.
1. En la página **Crear un sitio**, seleccione **Sitio de grupo**.
1. En el cuadro **nombre del sitio de grupo** , escriba **SensitiveFiles**.
1. En el cuadro **Descripción del sitio de grupo** , escriba **sitio de SharePoint para los archivos confidenciales**.
1. En **configuración de privacidad**, seleccione **privado: solo los miembros pueden acceder a este sitio**y, a continuación, seleccione **siguiente**.
1. En el panel **¿quién desea agregar?** , seleccione **Finalizar**.
    
A continuación, configure la carpeta documentos del sitio de grupo de SensitiveFiles para la etiqueta retención confidencial.
  
1. En la pestaña **SensitiveFiles** del explorador, seleccione **documentos**.
1. Seleccione el icono de **configuración** y, a continuación, seleccione **configuración de biblioteca**.
1. En **permisos y administración**, seleccione **Aplicar etiqueta a los elementos de esta lista o biblioteca**. Si esta opción no aparece, las etiquetas de retención aún no se publican. Pruebe este paso más tarde.
1. En **Configuración: aplicar etiqueta**, seleccione **confidencial** en el cuadro desplegable y, a continuación, seleccione **Guardar**.

A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambie su etiqueta de retención.
    
1. En la carpeta documentos, seleccione **nuevo**  >  **documento de Word**.
1. Escriba texto en el documento en blanco. Espere a que se guarde el texto.
1. En la barra de menús, seleccione **documentos compartidos**.
1. Junto al nombre de archivo **Document.docx** , seleccione los puntos suspensivos verticales y, a continuación, seleccione **detalles**.
1. En el panel derecho, en la sección **propiedades** , en **Aplicar etiqueta de retención**, tenga en cuenta que se ha aplicado automáticamente la etiqueta retención **sensible** al documento.
1. Haga clic en **Editar todo**.
1. En el panel de **Document.docx** , en **Aplicar etiqueta de retención**, seleccione la etiqueta **extremadamente confidencial** y, después, seleccione **Guardar**.

## <a name="next-step"></a>Paso siguiente

Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de entornos de pruebas de Microsoft 365 para empresas](m365-enterprise-test-lab-guides.md)

[Información general de Microsoft 365 Enterprise](microsoft-365-overview.md)

[Documentación de Microsoft 365 para empresas](https://docs.microsoft.com/microsoft-365-enterprise/)
