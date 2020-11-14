---
title: Analizador de configuración de cumplimiento de Microsoft para el administrador de cumplimiento
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
description: Aprenda a usar Microsoft Compliance Configuration Analyzer para ponerlo en marcha rápidamente con el administrador de cumplimiento de Microsoft.
ms.openlocfilehash: 1f7d987262a7d390cb9efe2162ae9be9f56c8757
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49072021"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager"></a>Analizador de configuración de cumplimiento de Microsoft para el administrador de cumplimiento

**En este artículo:** Obtenga información sobre cómo instalar y ejecutar la herramienta Microsoft Compliance Configuration Analyzer para empezar rápidamente con el administrador de cumplimiento de Microsoft.

## <a name="microsoft-compliance-configuration-analyzer-mcca-overview"></a>Información general sobre el analizador de configuración de cumplimiento de Microsoft (MCCA)

El analizador de configuración de cumplimiento de Microsoft (MCCA) es una herramienta que puede ayudarle a empezar a trabajar con el [Administrador de cumplimiento de Microsoft](compliance-manager.md). MCCA es una utilidad basada en PowerShell que recupera las configuraciones actuales de su organización y las valida con los procedimientos recomendados de Microsoft 365. Estos procedimientos recomendados se basan en un conjunto de controles que incluye normas y estándares clave para la protección de datos y el gobierno de datos.

MCCA puede ayudarle a ver rápidamente qué acciones de mejora en el administrador de cumplimiento se aplican a su entorno actual de Microsoft 365. Cada acción identificada por MCCA le dará recomendaciones para la implementación, con vínculos directos al administrador de cumplimiento y la solución correspondiente para comenzar a tomar medidas correctivas.

Un recurso adicional para comprender MCCA es visitando las [instrucciones para el archivo Léame en github](https://github.com/OfficeDev/MCCA#overview). En esta página se proporciona información detallada sobre los requisitos previos y se proporcionan instrucciones completas para la instalación. No necesita una cuenta de GitHub para obtener acceso a esta página.

## <a name="install-mcca-and-run-a-report"></a>Instalación de MCCA y ejecución de un informe

Puede instalar la herramienta MCCA con Windows PowerShell. Una vez que haya descargado e instalado la herramienta, no es necesario que repita estos pasos para poder ejecutar los informes. Cada vez que abra MCCA, se le pedirán sus credenciales de inicio de sesión y se generará un nuevo informe actualizado.

#### <a name="step-1-install-windows-powershell"></a>Paso 1: instalar Windows PowerShell
Para empezar, necesitará el módulo de PowerShell de Exchange Online (v 2.0.3 o superior) que está disponible en la galería de PowerShell. [Obtener instrucciones de instalación](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>Paso 2: instalar MCCA

Para instalar MCCA, empiece con PowerShell en el modo de administrador. Siga los pasos siguientes:

1. Seleccione el botón **Inicio** de Windows.
2. Escriba **PowerShell** , haga clic con el botón derecho en **Windows PowerShell** y seleccione **Ejecutar como administrador**.
1. En el símbolo del sistema, escriba:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Paso 3: ejecutar un informe

Después de instalar MCCA, puede ejecutar MCCA y generar un informe. Para ejecutar un informe:

1. Abrir PowerShell
2. Ejecute el cmdlet:

    ```powershell
    Get-MCCAReport
    ```
3. Una vez que se ejecuta MCCA, realiza una comprobación de la versión inicial y solicita las credenciales. En el símbolo del sistema escriba el nombre de usuario, inicie sesión con su dirección de correo electrónico de cuenta de 365 de Microsoft ([vea las funciones aptas para crear informes](#role-based-reporting)). A continuación, escriba la contraseña en el mensaje de contraseña.

El informe tardará aproximadamente 2-5 minutos en generarse. Cuando termine, se abrirá una ventana del explorador y mostrará el informe HTML. Cada vez que ejecute la herramienta, le pedirá sus credenciales y generará un nuevo informe. Este informe se almacena de forma local en el siguiente directorio:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Puede tener acceso a informes generados previamente desde este directorio.

## <a name="understanding-your-report"></a>Descripción del informe

El informe refleja los datos en función de la fecha y hora en que se generó. En la sección superior se proporcionan detalles sobre cuándo se generó, el nombre de la organización y el identificador del espacio empresarial.

#### <a name="geolocation-based-reporting"></a>Informes basados en la ubicación geográfica

En la sección **Nota** se muestra que el informe está personalizado en función de la ubicación geográfica del espacio empresarial. Las recomendaciones que aparecen en la herramienta serán específicas de su país o región.

La selección de ubicación geográfica se usa para evaluar los tipos de información confidencial (ubicación) que son relevantes para dicha ubicación y generar un informe que se alinee con su país o región. Elija geolocations en función de los datos que tenga en su espacio empresarial.

Para cambiar la información de ubicación del informe, necesita proporcionar un parámetro de entrada geolocation (-geogeográfico). Puede elegir entre una o varias geolocaciones que sean aplicables a su espacio empresarial.

Siga estas instrucciones para ejecutar un informe basado en una ubicación específica:

1. Abrir PowerShell
2. Para especificar una región determinada, ejecutará un cmdlet usando los números de la tabla siguiente que se corresponden con el país o la región. Para escribir varios números, sepárelos con una coma. Por ejemplo, el cmdlet siguiente ejecutará un informe personalizado para Asia-Pacific y Japón:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  País o región | 
  | :------------- | :------------: |
  | 1  | Asia-Pacífico |
  | 2  | Australia |
  | 3 | Canadá |
  | 4  | Europa (excepto Francia)/Oriente Medio/África |
  | 5  | Francia |
  | 6  | India |
  | 7  | Japón |
  | 8  | Corea |
  | 9  | Norteamérica (excepto Canadá) |
  | 10  | Sudamérica |
  | 11  | Sudáfrica |
  | 12  | Suiza |
  | 13  | Emiratos Árabes Unidos |
  | 14  | Reino Unido |


 > [!NOTE]
> El informe siempre incluirá MCCA tipos de información confidencial admitidos, como código SWIFT, número de tarjeta de crédito, etc.

#### <a name="role-based-reporting"></a>Informes basados en roles

El informe también se personalizará en función de su rol.

En la tabla siguiente se muestran los roles que tienen acceso a qué secciones del informe. Es posible que otros roles de la organización (que no aparecen en la tabla siguiente) no puedan ejecutar la herramienta, o bien que la ejecuten y tengan acceso limitado a la información en el informe final.

![MCCA-roles](../media/compliance-manager-mcca-roles.png "Roles MCCA")

Las
1. El usuario no podrá generar informes para IP aparte de la sección "usar IRM para Exchange Online".
2. El usuario podrá generar un informe para IP aparte de la sección "usar IRM para Exchange Online".
3. El usuario podrá generar informes para IP aparte de la sección "habilitar el cumplimiento de la comunicación en O365".
4. El usuario no podrá generar informes para IP aparte de la sección "habilitar la auditoría en Office 365".
5. El usuario podrá generar un informe para IP aparte de la sección "habilitar la auditoría en Office 365".

#### <a name="solutions-summary-section"></a>Sección de Resumen de soluciones

La sección de **Resumen de soluciones** del informe ofrece una descripción general de las acciones de mejora que su organización puede llevar a cabo en el administrador de cumplimiento para ayudarle a mejorar su postura de cumplimiento.

![MCCA: Resumen de soluciones](../media/compliance-manager-mcca-solutions.png "Pantalla de Resumen de soluciones de MCCA")

MCCA evalúa la configuración actual en función de las acciones de mejora recomendadas en el administrador de cumplimiento. En esta sección se enumerarán todas las acciones de mejora identificadas por la herramienta de MCCA que necesiten atención.

Junto a cada solución de Microsoft hay cuadros codificados por colores que indican el número de elementos que corresponden a las acciones de mejora en el administrador de cumplimiento. Las acciones se dividen en tres Estados de estado:

- **Aceptar** : las acciones que cumplen las condiciones recomendadas y no necesitan atención en este momento
- **Mejora** : acciones que necesitan atención
- **Recomendación** : acciones que no necesitan atención, pero para las que se recomiendan los procedimientos recomendados
 
Seleccione un cuadro para ver mejoras y recomendaciones.

**Elementos con el estado de mejora**

Seleccione la lista desplegable situada junto a la etiqueta de **mejora** a la derecha de la acción de mejora. Verá un resumen rápido y detalles sobre la configuración actual y las acciones de mejora recomendadas. El resumen incluye vínculos directos en el administrador de cumplimiento, la solución aplicable en el centro de cumplimiento de Microsoft 365 y la documentación correspondiente.

Al hacer clic en el vínculo administrador de cumplimiento, se obtiene una vista filtrada de todas las acciones de mejora de la solución que aún no se han implementado. Desde allí, puede ver el número de puntos que puede lograr para aumentar la [puntuación de cumplimiento](compliance-score-calculation.md)y las evaluaciones a las que se aplican, así como las regulaciones y las certificaciones aplicables.

Para DLP, hay un botón **script de corrección** que proporciona un script de PowerShell que se ha generado previamente en función de lo recomendado. Puede copiarlo y pegarlo directamente en la consola de PowerShell. Se creará una directiva de DLP en modo de prueba

**Elementos con estado de recomendación**

Seleccione la lista desplegable situada junto a la etiqueta **recomendación** a la derecha de la acción mejora. Verá un resumen del entorno actual de Microsoft 365 de su organización relacionado con la acción de mejora, junto con los procedimientos recomendados.

## <a name="resources"></a>Recursos

Para obtener información más detallada sobre la instalación, la configuración y el uso de MCCA, consulte las [instrucciones del archivo Léame en github](https://github.com/OfficeDev/MCCA#overview) (no se requiere ninguna cuenta de GitHub).

Para obtener más información sobre Windows PowerShell, comience a [usar la documentación de PowerShell](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7). Consulte también [iniciar Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
