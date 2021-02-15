---
title: Analizador de configuración de cumplimiento de Microsoft para el Administrador de cumplimiento
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Obtenga información sobre cómo usar el Analizador de configuración de cumplimiento de Microsoft para empezar a trabajar rápidamente con el Administrador de cumplimiento de Microsoft.
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122400"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Analizador de configuración de cumplimiento de Microsoft para el Administrador de cumplimiento (versión preliminar)

**En este artículo:** Obtenga información sobre cómo instalar y ejecutar la herramienta Analizador de configuración de cumplimiento de Microsoft para empezar rápidamente con el Administrador de cumplimiento de Microsoft.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Introducción al Analizador de configuración de cumplimiento de Microsoft (MCCA) (versión preliminar)

Microsoft Compliance Configuration Analyzer (MCCA) es una herramienta de vista previa que puede ayudarle a empezar a trabajar con [el Administrador de cumplimiento de Microsoft.](compliance-manager.md) MCCA es una utilidad basada en PowerShell que recuperará las configuraciones actuales de su organización y las validará con los procedimientos recomendados de Microsoft 365. Estos procedimientos recomendados se basan en un conjunto de controles que incluyen normas y estándares clave para la protección de datos y el gobierno de datos.

MCCA puede ayudarle a ver rápidamente qué acciones de mejora del Administrador de cumplimiento se aplican a su entorno actual de Microsoft 365. Cada acción identificada por MCCA le dará recomendaciones para la implementación, con vínculos directos al Administrador de cumplimiento y la solución aplicable para empezar a tomar medidas correctivas.

Un recurso adicional para comprender MCCA es visitar las instrucciones [README en GitHub.](https://github.com/OfficeDev/MCCA#overview) Esta página proporciona información detallada sobre los requisitos previos y proporciona instrucciones de instalación completas. No necesita una cuenta de GitHub para acceder a esta página.

**Disponibilidad:** MCCA está disponible para todas las organizaciones con licencias de Office 365 y Microsoft 365 y clientes moderados de us Government Community (GCC), con planes en curso para ampliar el servicio a los clientes de GCC High.

## <a name="install-mcca-and-run-a-report"></a>Instalar MCCA y ejecutar un informe

Puede instalar la herramienta MCCA con Windows PowerShell. Una vez que descargue e instale la herramienta, no es necesario repetir esos pasos para ejecutar informes. Cada vez que abra MCCA, le pedirá sus credenciales de inicio de sesión y generará un nuevo informe actualizado.

#### <a name="step-1-install-windows-powershell"></a>Paso 1: Instalar Windows PowerShell
Para empezar, necesitará el módulo de PowerShell de Exchange Online (v2.0.3 o superior) que esté disponible en la galería de PowerShell. [Obtener instrucciones de instalación.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Paso 2: Instalar MCCA

Para instalar MCCA, empiece por usar PowerShell en modo de administrador. Siga los pasos siguientes:

1. Selecciona el botón **Inicio de** Windows.
2. Escriba **PowerShell,** haga clic con el botón secundario **en Windows PowerShell** y, a continuación, seleccione Ejecutar como **administrador.**
1. En el símbolo del sistema, escriba:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Paso 3: Ejecutar un informe

Después de instalar MCCA, puede ejecutar MCCA y generar un informe. Para ejecutar un informe:

1. Abrir PowerShell
2. Ejecute el cmdlet:

    ```powershell
    Get-MCCAReport
    ```
3. Una vez que se ejecuta MCCA, realiza una comprobación de versión inicial y pide credenciales. At the Input the user name prompt, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)). A continuación, escriba su contraseña en el símbolo del sistema de contraseña.

A continuación, el informe tarda aproximadamente entre 2 y 5 minutos en generarse. Cuando termine, se abrirá una ventana del explorador y se mostrará el informe HTML. Cada vez que ejecute la herramienta, pedirá sus credenciales y generará un nuevo informe. Este informe se almacena localmente en el directorio siguiente:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Puede obtener acceso a los informes generados anteriormente desde este directorio.

## <a name="understanding-your-report"></a>Descripción del informe

El informe refleja los datos en función de la fecha y hora en que se generó. En la sección superior se proporcionan detalles sobre cuándo se generó, el nombre de la organización y el id. de inquilino.

#### <a name="geolocation-based-reporting"></a>Informes basados en geolocalización

La **sección** Nota muestra que el informe se personaliza en función de la ubicación geográfica de su espacio empresarial. Las recomendaciones enumeradas en la herramienta serán específicas de su país o región.

La selección de geolocalización se usa para evaluar los tipos de información confidencial (SIT) que son relevantes para esa geolocalización y generar un informe que se alinee con su país o región. Elija geolocalizaciones en función de los datos que tenga en su espacio empresarial.

Para cambiar la información de ubicación del informe, debe proporcionar un parámetro de entrada de geolocalización (-Geo). Puede elegir una o varias geolocalizaciones aplicables a su espacio empresarial.

Siga estas instrucciones para ejecutar un informe basado en una ubicación específica:

1. Abrir PowerShell
2. Para especificar una región determinada, ejecutará un cmdlet con los números de la tabla siguiente que correspondan al país o región. Escriba varios números separándolos con una coma. Por ejemplo, el siguiente cmdlet ejecutará un informe personalizado para Asia-Pacific y Japón:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  País o región | 
  | :------------- | :------------: |
  | 1  | Asia-Pacífico |
  | 2  | Australia |
  | 3  | Canadá |
  | 4  | Europa (excluyendo Francia) / Oriente Medio /África |
  | 5  | Francia |
  | 6  | India |
  | 7  | Japón |
  | 8  | Corea |
  | 9  | Norteamérica (excepto Canadá) |
  | 10   | Sudamérica |
  | 11  | Sudáfrica |
  | 12  | Suiza |
  | 13  | Emiratos Árabes Unidos |
  | 14  | Reino Unido |


 > [!NOTE]
> El informe siempre incluirá tipos de información confidencial internacional compatibles con MCCA, como código SWIFT, número de tarjeta de crédito, etc.

#### <a name="role-based-reporting"></a>Informes basados en roles

El informe también se personalizará en función de su rol.

La tabla siguiente muestra qué roles tienen acceso a qué secciones del informe. Es posible que otros roles de la organización (no incluidos en la tabla siguiente) no puedan ejecutar la herramienta o que ejecuten la herramienta y tengan acceso limitado a la información del informe final.

![MCCA: roles](../media/compliance-manager-mcca-roles.png "Roles de MCCA")

Excepciones:
1. El usuario no podrá generar un informe para IP aparte de la sección "Usar IRM para Exchange Online".
2. El usuario podrá generar un informe para IP aparte de la sección "Usar IRM para Exchange Online".
3. El usuario podrá generar un informe para IP aparte de la sección "Habilitar cumplimiento de comunicaciones en O365".
4. El usuario no podrá generar un informe para IP aparte de la sección "Habilitar auditoría en Office 365".
5. El usuario podrá generar un informe para IP aparte de la sección "Habilitar auditoría en Office 365".

#### <a name="solutions-summary-section"></a>Sección Resumen de soluciones

La **sección Resumen de** soluciones del informe ofrece información general sobre las acciones de mejora que su organización puede realizar en el Administrador de cumplimiento para ayudar a mejorar su posición de cumplimiento.

![MCCA: resumen de soluciones](../media/compliance-manager-mcca-solutions.png "Pantalla resumen de soluciones de MCCA")

MCCA evalúa las configuraciones actuales con respecto a las acciones de mejora recomendadas en el Administrador de cumplimiento. En esta sección se enumeran todas las acciones de mejora identificadas por la herramienta MCCA que necesitan atención.

Junto a cada solución de Microsoft hay cuadros codificados por colores que indican el número de elementos que corresponden a acciones de mejora en el Administrador de cumplimiento. Las acciones se desglosan en tres estados de estado:

- **Aceptar:** las acciones que cumplen las condiciones recomendadas y no necesitan atención en este momento
- **Mejora:** acciones que necesitan atención
- **Recomendación:** acciones que no necesitan atención, pero para las que se recomiendan procedimientos recomendados
 
Seleccione un cuadro para ver las mejoras y recomendaciones.

**Elementos con el estado de mejora**

Seleccione la lista desplegable situada junto a la **etiqueta Mejora** a la derecha de la acción de mejora. Verá un resumen rápido y detalles sobre la configuración actual y las acciones de mejora recomendadas. El resumen incluye vínculos directos al Administrador de cumplimiento, la solución aplicable en el Centro de cumplimiento de Microsoft 365 y la documentación pertinente.

Al hacer clic en el vínculo Administrador de cumplimiento, podrá obtener una vista filtrada de todas las acciones de mejora de esa solución que aún no ha implementado. Desde allí, puede ver el número de puntos [](compliance-score-calculation.md)que puede lograr para aumentar la puntuación de cumplimiento, y las evaluaciones a las que se aplican, así como las normas y certificaciones aplicables.

Para DLP, hay un botón **de script** de corrección que le proporciona un script de PowerShell generado previamente en función de lo que se recomienda. Puede copiarla y pegarla directamente en la consola de PowerShell. Creará una directiva DLP en modo de prueba

**Elementos con estado de recomendación**

Seleccione la lista desplegable situada junto a la **etiqueta** Recomendación a la derecha de la acción de mejora. Verá un resumen del entorno actual de Microsoft 365 de su organización relacionado con la acción de mejora, junto con los procedimientos recomendados.

## <a name="resources"></a>Recursos

Para obtener información más detallada sobre cómo instalar, configurar y usar MCCA, consulta las instrucciones README en [GitHub](https://github.com/OfficeDev/MCCA#overview) (no se requiere ninguna cuenta de GitHub).

Para obtener más información Windows PowerShell, empiece [por cómo usar la documentación de PowerShell.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7) Vea también [Inicio Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
