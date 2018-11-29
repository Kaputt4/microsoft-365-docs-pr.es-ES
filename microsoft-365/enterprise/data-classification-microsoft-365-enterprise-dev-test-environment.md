---
title: Entorno de prueba de clasificación de datos para la empresa de 365 de Microsoft
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Use esta guía de laboratorio de prueba para crear y usar Office 365 etiquetas en documentos en el entorno de prueba de Microsoft 365 Enterprise.
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2018
ms.locfileid: "26871773"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Entorno de prueba de clasificación de datos para la empresa de 365 de Microsoft

Con las instrucciones de este artículo, configure una clasificación de datos mediante las etiquetas de Office 365 en su entorno de prueba de Microsoft 365 Enterprise.

![Guías del laboratorio de pruebas para Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Haga clic [aquí](https://aka.ms/m365etlgstack) para acceder a un mapa visual de todos los artículos de la pila Guía del laboratorio de pruebas de Microsoft 365 Enterprise.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Generar el entorno de prueba de Microsoft 365 Enterprise

Si desea configurar las etiquetas de Office 365 en una forma sencilla con los requisitos mínimos, siga las instrucciones de [configuración básica ligero](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Si desea configurar las etiquetas de Office 365 en una empresa simulada, siga las instrucciones que aparecen en la [autenticación de paso a través](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Probar Office 365 etiquetas no requiere que el entorno de prueba simulado enterprise, que incluye una intranet simulada conectada a Internet y sincronización de Active directory para un bosque de Windows Server AD. Se proporciona aquí como una opción para que pueda probar licencias automatizada y la pertenencia a grupos y experimentar con él en un entorno que representa una organización típica. 

## <a name="phase-2-create-office-365-labels"></a>Fase 2: Crear etiquetas de Office 365

En esta fase, cree las etiquetas para los diferentes niveles de seguridad para las carpetas de documentos de SharePoint Online.
  
1. Si es necesario, use una instancia privada de su explorador de Internet e inicie sesión el portal de Office 365 con su cuenta de administrador global. Para obtener ayuda, consulte [Where iniciar sesión en Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. En la pestaña **Inicio de Microsoft Office**, haga clic en el icono **Administrador**.
    
3. En la nueva pestaña **Centro de administración de Office** del explorador, haga clic en **Centros de administración Seguridad &amp; Cumplimiento**.
    
4. En la nueva pestaña **Inicio - Seguridad y cumplimiento** del explorador, haga clic en **Clasificaciones > Etiquetas**.
    
5. En el panel **Inicio > Etiquetas**, haga clic en **Crear una etiqueta**.
    
6. En el panel **Nombre de la etiqueta**, escriba **Interno público** y, después, haga clic en **Siguiente**.
    
7. En el panel **Configuración de etiquetas**, haga clic en **Siguiente**.
    
8. En el panel **Revise su configuración**, haga clic en **Crear esta etiqueta** y luego en **Cerrar**.
    
9. Repita los pasos del 5 al 8 para estas etiquetas adicionales:
    
  - Private
    
  - Confidencial
    
  - Extremadamente confidencial
    
10. En el panel **Inicio > Etiquetas**, haga clic para **Publish labels** (Publicar etiquetas).
    
11. En el panel **Elegir etiquetas para publicar**, haga clic en **Elegir etiquetas para publicar**.
    
12. En el panel de **elección de etiquetas**, haga clic en **Agregar** y seleccione las cuatro etiquetas.
    
13. Haga clic en **Listo**.
    
14. En el panel **Elegir etiquetas para publicar**, haga clic en **Siguiente**.
    
15. En el panel **Seleccionar ubicaciones**, haga clic en **Siguiente**.
    
16. En el panel **Escriba un nombre para la directiva**, escriba **Organización de ejemplo** en **Nombre** y haga clic en **Siguiente**.
    
17. En el panel **Revise la configuración**, haga clic en **Publicar etiquetas** y, después, en **Cerrar**.

Tenga en cuenta que puede tardar unos minutos para las etiquetas que se va a publicar.

## <a name="phase-3-apply-office-365-labels-to-documents"></a>Fase 3: Aplicar etiquetas de Office 365 a los documentos

En esta fase, detectar el comportamiento de la etiqueta predeterminada para los archivos en la carpeta de documentos de un sitio de SharePoint Online y cambiar manualmente la etiqueta de un documento.

En primer lugar, cree un sitio de grupo de SharePoint Online confidenciales nivel:
  
1. Abra un explorador en el equipo local e inicie sesión en el portal de Office 365 con la cuenta de administrador global. Para obtener ayuda, vea [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4) (Dónde iniciar sesión en Office 365).
    
2. En la lista de iconos, haga clic en **SharePoint**.
    
3. En la ficha nuevo de **SharePoint** en el explorador, haga clic en **Crear sitio**.
    
4. En la página **Crear un sitio**, haga clic en **Sitio de grupo**.
    
5. En **nombre del sitio del equipo**, escriba **SensitiveFiles**.
    
6. En **Descripción del sitio del equipo**, escriba el **sitio de SharePoint para archivos confidenciales**.
    
7.  En **Configuración de privacidad**, seleccione **Privado: solo los miembros pueden obtener acceso a este sitio** y, después, haga clic en **Siguiente**.
    
8. En el panel **Usuarios que quiere agregar**, haga clic en **Finalizar**.
    
A continuación, configure la carpeta de documentos del sitio del equipo de SensitiveFiles para la etiqueta confidencial.
  
1. En la ficha **SensitiveFiles** del explorador, haga clic en **documentos**.
    
2. Haga clic en el icono de configuración y luego en **Configuración de biblioteca**.
    
3. En **Permisos y administración**, haga clic en **Apply label to items in this library** (Aplicar la etiqueta a los elementos de esta biblioteca).
    
4. En **Aplicar a la configuración de etiqueta**, seleccione **confidencial** en el cuadro de lista desplegable y, a continuación, haga clic en **Guardar**.

A continuación, cree un nuevo documento en el sitio de SensitiveFiles y cambiar su etiqueta.
    
1. En la carpeta de documentos, haga clic en **Nuevo > documento de Word**.
    
2. Escriba algún texto en el documento en blanco. Espere a que el texto que se va a guardar.
    
3. En la barra de menús, haga clic en **Documentos compartidos**.
    
4. Haga clic en el icono de Word junto al nombre de archivo **Document.docx** .
    
5. En el panel derecho, en la sección de **Propiedades** , en **Aplicar etiqueta**, tenga en cuenta que el documento ha tenido la etiqueta **confidencial** aplica automáticamente.
    
6. Haga clic en **Editar todos**.
    
7. En el panel de **Document.docx** , en **Aplicar etiqueta**, seleccione la etiqueta **Altamente confidencial** y, a continuación, haga clic en **Guardar**.

En la fase de **protección de la información** para obtener información y vínculos a las etiquetas de Office 365 en producción, vea el paso [Configurar clasificación para su entorno](data-classification-microsoft-365-enterprise-dev-test-environment.md) .

## <a name="next-step"></a>Paso siguiente

Explorar las características adicionales de [protección de la información](m365-enterprise-test-lab-guides.md#information-protection) y funcionalidades en su entorno de prueba.

## <a name="see-also"></a>Vea también

[Guías de laboratorio de pruebas de Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Implementar Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentación y recursos de Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

 