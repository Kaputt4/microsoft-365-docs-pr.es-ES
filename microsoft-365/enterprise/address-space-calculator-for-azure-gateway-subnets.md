---
title: Calculadora de espacio de direcciones para subredes de puerta de enlace de Azure
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/07/2021
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: 'Resumen: calcule el espacio de direcciones de una subred de puerta de enlace de Azure con C3, Python o PowerShell.'
ms.openlocfilehash: d92bea5c36fde6277154d19365ed0bdaa5df4254
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780573"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a><span data-ttu-id="09c74-103">Calculadora de espacio de direcciones para subredes de puerta de enlace de Azure</span><span class="sxs-lookup"><span data-stu-id="09c74-103">Address space calculator for Azure gateway subnets</span></span>

<span data-ttu-id="09c74-104">Una red virtual (VNet) en servicios de infraestructura de Azure que esté conectada a otras redes debe tener una subred de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="09c74-104">A virtual network (VNet) in Azure infrastructure services that is connected to other networks must have a gateway subnet.</span></span> <span data-ttu-id="09c74-105">Los procedimientos recomendados para definir la subred de puerta de enlace son:</span><span class="sxs-lookup"><span data-stu-id="09c74-105">The best practices for defining the gateway subnet are:</span></span>

- <span data-ttu-id="09c74-106">La longitud del prefijo de la subred de puerta de enlace puede tener una longitud máxima de prefijo de 29 (por ejemplo, 10.119.255.248/29), pero la recomendación actual es que use una longitud de prefijo de 27 (por ejemplo, 10.119.255.224/27).</span><span class="sxs-lookup"><span data-stu-id="09c74-106">The prefix length of the gateway subnet can have a maximum prefix length of 29 (for example, 10.119.255.248/29), but the current recommendation is that you use a prefix length of 27 (for example, 10.119.255.224/27).</span></span>
- <span data-ttu-id="09c74-107">Al definir el espacio de direcciones de la subred de puerta de enlace, use la última parte del espacio de direcciones de la red virtual.</span><span class="sxs-lookup"><span data-stu-id="09c74-107">When defining the address space of the gateway subnet, use the last part of the VNet address space.</span></span>

<span data-ttu-id="09c74-108">Para la segunda recomendación, puede determinar el espacio de direcciones de la subred de puerta de enlace estableciendo los bits usados para la subred de puerta de enlace en 0 y los bits restantes en el espacio de direcciones de la red virtual en 1.</span><span class="sxs-lookup"><span data-stu-id="09c74-108">For the second recommendation, you can determine the address space of the gateway subnet by setting the bits used for the gateway subnet to 0 and the remaining bits in the VNet address space to 1.</span></span> <span data-ttu-id="09c74-109">Para calcular rápidamente el espacio de direcciones de subred de puerta de enlace sin tener que convertir a binario y volver a decimal, puede usar una aplicación de consola escrita en C# o Python o con un bloque de comandos de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09c74-109">To quickly calculate the gateway subnet address space without having to convert to binary and back to decimal, you can use a console application written in C# or Python or with a PowerShell command block.</span></span>

<span data-ttu-id="09c74-110">Este artículo contiene C#, Python y bloques de código de PowerShell que calculan el espacio de direcciones de subred de puerta de enlace en función de los valores de w.x.y.z/n para el prefijo de dirección de red virtual y la longitud del prefijo de subred de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="09c74-110">This article contains C#, Python, and PowerShell code blocks that calculate the gateway subnet address space based on the values of w.x.y.z/n for the VNet address prefix and the gateway subnet prefix length.</span></span>

## <a name="c-code-block"></a><span data-ttu-id="09c74-111">C# de código</span><span class="sxs-lookup"><span data-stu-id="09c74-111">C# code block</span></span>

<span data-ttu-id="09c74-112">Usa este bloque de código para crear una aplicación de consola en C#.</span><span class="sxs-lookup"><span data-stu-id="09c74-112">Use this code block to create a console app in C#.</span></span>

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("**_ Gateway subnet address space calculator for Azure virtual networks _*_");             
            Console.WriteLine("_*************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a><span data-ttu-id="09c74-113">Bloque de código de Python</span><span class="sxs-lookup"><span data-stu-id="09c74-113">Python code block</span></span>

<span data-ttu-id="09c74-114">Usa este bloque de código para crear una aplicación de consola en Python.</span><span class="sxs-lookup"><span data-stu-id="09c74-114">Use this code block to create a console app in Python.</span></span>

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("**_ Gateway subnet address space calculator for Azure virtual networks _*_")  
print("_*************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a><span data-ttu-id="09c74-115">Bloque de comandos de PowerShell</span><span class="sxs-lookup"><span data-stu-id="09c74-115">PowerShell command block</span></span>

<span data-ttu-id="09c74-116">Rellene los valores y ejecute el bloque de comandos resultante en una ventana de PowerShell o en el Entorno de script integrado (ISE) de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09c74-116">Fill in the values and run the resulting command block in a PowerShell window or in the PowerShell Integrated Script Environment (ISE).</span></span>

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a><span data-ttu-id="09c74-117">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="09c74-117">Related topics</span></span>

[<span data-ttu-id="09c74-118">Administrar Microsoft 365 con PowerShell</span><span class="sxs-lookup"><span data-stu-id="09c74-118">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)