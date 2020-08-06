---
title: Ejecutar un archivo de script de Reporting Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- scripts [Reporting Services], running
ms.assetid: 0de4995c-85ec-4d4c-aaef-fbd30edfb20f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c787d860838a57a2bd0f51aac1e9159833f038d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87747946"
---
# <a name="run-a-reporting-services-script-file"></a><span data-ttu-id="fce48-102">Ejecutar un archivo de script de Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fce48-102">Run a Reporting Services Script File</span></span>
  [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] <span data-ttu-id="fce48-103">los archivos de script se ejecutan desde el símbolo del sistema con el entorno de scripts de [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] (RS.exe).</span><span class="sxs-lookup"><span data-stu-id="fce48-103">script files are run from the command prompt using the [!INCLUDE[ssRSnoversion](../../includes/ssrsnoversion-md.md)] script environment (RS.exe).</span></span> <span data-ttu-id="fce48-104">RS.exe tiene muchos argumentos del símbolo del sistema disponibles para su uso.</span><span class="sxs-lookup"><span data-stu-id="fce48-104">RS.exe has many command prompt arguments available for you to use.</span></span> <span data-ttu-id="fce48-105">Para más información sobre las opciones del símbolo del sistema, vea [Utilidad RS.exe &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="fce48-105">For more information about the command prompt options, see [RS.exe Utility &#40;SSRS&#41;](rs-exe-utility-ssrs.md).</span></span> <span data-ttu-id="fce48-106">Para obtener mas muestras de script, vea [Muestras de productos de SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="fce48-106">For more script samples, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="sample-command-lines"></a><span data-ttu-id="fce48-107">Líneas de comandos de ejemplo</span><span class="sxs-lookup"><span data-stu-id="fce48-107">Sample Command Lines</span></span>  
  
-   <span data-ttu-id="fce48-108">Ejecute Script.rss en el entorno de script que designa el servidor de informes de destino.</span><span class="sxs-lookup"><span data-stu-id="fce48-108">Run Script.rss in the script environment designating the target report server.</span></span> <span data-ttu-id="fce48-109">De forma predeterminada, se aplica la Autenticación de Windows:</span><span class="sxs-lookup"><span data-stu-id="fce48-109">Windows Authentication is applied by default:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver  
    ```  
  
-   <span data-ttu-id="fce48-110">Ejecute Script.rss en el entorno de script que especifica un nombre de usuario y contraseña para autenticar las llamadas del servicio web:</span><span class="sxs-lookup"><span data-stu-id="fce48-110">Run Script.rss in the script environment specifying a user name and password for authenticating the Web service calls:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -u myusername -p mypassword  
    ```  
  
-   <span data-ttu-id="fce48-111">Ejecute Script.rss en el entorno de script que especifica un tiempo de espera de servidor de 30 segundos:</span><span class="sxs-lookup"><span data-stu-id="fce48-111">Run Script.rss in the script environment specifying a server time-out of 30 seconds:</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -l 30  
    ```  
  
-   <span data-ttu-id="fce48-112">Ejecute Script.rss en el entorno de script que especifica una variable de script global denominada *report*.</span><span class="sxs-lookup"><span data-stu-id="fce48-112">Run Script.rss in the script environment specifying a global script variable called *report*.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -v report="Company Sales"  
    ```  
  
-   <span data-ttu-id="fce48-113">Ejecute Script.rss en el entorno de script que especifica que las operaciones del servicio web del archivo de script se ejecutan como lote.</span><span class="sxs-lookup"><span data-stu-id="fce48-113">Run Script.rss in the script environment specifying that the Web service operations in the script file are run as a batch.</span></span>  
  
    ```  
    rs -i Script.rss -s http://servername/reportserver -b  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fce48-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fce48-114">See Also</span></span>  
 [<span data-ttu-id="fce48-115">Referencia técnica &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="fce48-115">Technical Reference &#40;SSRS&#41;</span></span>](../technical-reference-ssrs.md)  
  
  
