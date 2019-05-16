---
title: Clasificación de datos para su entorno de prueba de Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía del laboratorio de pruebas para crear y usar las etiquetas de retención de Office 365 en documentos de su entorno de prueba empresarial de Microsoft 365.
ms.openlocfilehash: 66e06f9a89b102c131bc29af17c4564fabbab9b4
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072420"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Clasificación de datos para su entorno de prueba de Microsoft 365 Enterprise

Con las instrucciones de este artículo, podrá configurar la clasificación de datos con las etiquetas de retención de Office 365 en su entorno de prueba empresarial de Microsoft 365.

![Guías de laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para ver un mapa visual de todos los artículos de la pila Guía de laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: crear el entorno de prueba de Microsoft 365 Enterprise

Si solo quiere configurar las etiquetas de retención de Office 365 de manera ligera con los requisitos mínimos, siga las instrucciones de [configuración básica](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar las etiquetas de retención de Office 365 en una empresa simulada, siga las instrucciones de la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> La prueba de las etiquetas de retención de Office 365 no requiere el entorno de prueba empresarial simulado, que incluye una intranet simulada conectada a Internet y la sincronización de directorios para un bosque de servicios de dominio de Active Directory (AD DS). Se proporciona aquí como una opción para que pueda probar la concesión de licencias automatizada y la pertenencia a grupos y experimentar con ella en un entorno que representa una organización típica. 

## <a name="phase-2-create-office-365-retention-labels"></a>Fase 2: crear etiquetas de retención de Office 365

En esta fase, creará las etiquetas de retención para los distintos niveles de retención para las carpetas de documentos de SharePoint Online.

1. Inicie sesión en el [portal de cumplimiento de Microsoft 365](https://compliance.microsoft.com) con su cuenta de administrador global.
    
2. En la pestaña **Inicio: cumplimiento de Microsoft 365** del navegador, haga clic en **Clasificaciones > Etiquetas**.
    
3. Haga clic en **Etiquetas de retención > Crear una etiqueta**.
    
4. En el panel **Nombre de la etiqueta**, escriba **Público interno** en **el espacio provisto**, y después haga clic en **Siguiente**.

5. En el panel **descriptores de plan de archivos**, haga clic en **Siguiente**.
    
6. En el panel **Configuración de etiqueta**, si es necesario, marque **Retención** como **Activada** y haga clic en **Siguiente**.
    
7. En el panel **Revise su configuración**, haga clic en **Crear la etiqueta**.
    
8. Repita los pasos del 3 al 7 para etiquetas adicionales con los siguientes nombres:
    
  - Private
    
  - Confidencial
    
  - Extremadamente confidencial
  
9. En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).
    
10. En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.
    
11. En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.
    
12. Haga clic en **Listo**.
    
13. En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.
    
14. En el panel **Seleccionar ubicaciones**, haga clic en **Siguiente**.
    
15. En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.
    
16. En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.
 
Tenga en cuenta que la publicación de las etiquetas de retención puede tardar unos minutos.

## <a name="phase-3-apply-office-365-retention-labels-to-documents"></a>Fase 3: aplicar las etiquetas de retención de Office 365 a los documentos

En esta fase, se detecta el comportamiento predeterminado de la etiqueta de retención para los archivos de la carpeta documentos de un sitio de SharePoint Online y se cambia manualmente la etiqueta de retención de un documento.

En primer lugar, cree un sitio de grupo de SharePoint Online de nivel confidencial:
  
1. Abra un explorador en el equipo local e inicie sesión en el [portal de Office 365](https://portal.office.com) con la cuenta de administrador global.
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la nueva pestaña de **SharePoint** del explorador, haga clic en **crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **nombre del sitio de grupo**, escriba **SensitiveFiles**.
    
6. En **Descripción del sitio de grupo**, escriba **sitio de SharePoint para archivos confidenciales**.
    
7.  En **Configuración de privacidad**, seleccione **Private - only members can access this site** (Privado: solo los miembros tienen acceso a este sitio) y haga clic en **Siguiente**.
    
8. En el panel **Who do you want to add?** (Usuarios que quiere agregar), haga clic en **Finalizar**.
    
A continuación, configure la carpeta documentos del sitio de grupo de SensitiveFiles para la etiqueta retención confidencial.
  
1. En la pestaña **SensitiveFiles** del explorador, haga clic en **documentos**.
    
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Configuración: aplicar etiqueta**, seleccione **confidencial** en el cuadro desplegable y, a continuación, haga clic en **Guardar**.

A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambie su etiqueta de retención.
    
1. En la carpeta documentos, haga clic en **nuevo documento de Word >**.
    
2. Escriba texto en el documento en blanco. Espere a que se guarde el texto.
    
3. En la barra de menús, haga clic en **documentos**compartidos.
    
4. Haga clic en el icono de Word junto al nombre del archivo **Document. docx** .
    
5. En el panel derecho, en la sección **propiedades** , en **Aplicar etiqueta de retención**, tenga en cuenta que se ha aplicado automáticamente la etiqueta **confidencial** al documento.
    
6. Haga clic en **Editar todo**.
    
7. En el panel **Document. docx** , en **Aplicar etiqueta**, seleccione la etiqueta **extremadamente confidencial** y, a continuación, haga clic en **Guardar**.

Consulte el paso [configurar la clasificación del entorno](infoprotect-configure-classification.md) en la fase de protección de la **información** para obtener información y vínculos sobre cómo implementar las etiquetas de retención de Office 365 en producción.

## <a name="next-step"></a>Paso siguiente

Explore otras características y funcionalidades de protección de la [información](m365-enterprise-test-lab-guides.md#information-protection) en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 