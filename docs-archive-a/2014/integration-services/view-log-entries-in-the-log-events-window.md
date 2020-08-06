---
title: Ver entradas del registro en la ventana registrar eventos | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- logs [Integration Services], viewing
- Integration Services packages, logs
- packages [Integration Services], logs
ms.assetid: c02123c3-67fc-4370-ad14-91ed259f1873
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16b6f11758d7de2c833731cd007426000a01d8ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87744175"
---
# <a name="view-log-entries-in-the-log-events-window"></a><span data-ttu-id="5ccd4-102">Ver entradas del registro en la ventana Registrar eventos</span><span class="sxs-lookup"><span data-stu-id="5ccd4-102">View Log Entries in the Log Events Window</span></span>
  <span data-ttu-id="5ccd4-103">En este procedimiento se describe cómo ejecutar un paquete y ver las entradas de registro que escribe.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-103">This procedure describes how to run a package and view the log entries it writes.</span></span> <span data-ttu-id="5ccd4-104">Se pueden ver las entradas del registro en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-104">You can view the log entries in real time.</span></span> <span data-ttu-id="5ccd4-105">Las entradas del registro escritas en la ventana **Registrar eventos** también se pueden copiar y guardar para futuros análisis.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-105">The log entries that are written to the **Log Events** window can also be copied and saved for further analysis.</span></span>  
  
 <span data-ttu-id="5ccd4-106">No es necesario escribir las entradas en un registro para que se escriban en la ventana **Registrar eventos** .</span><span class="sxs-lookup"><span data-stu-id="5ccd4-106">It is not necessary to write the log entries to a log to write the entries to the **Log Events** window.</span></span>  
  
### <a name="to-view-log-entries"></a><span data-ttu-id="5ccd4-107">Para ver entradas del registro</span><span class="sxs-lookup"><span data-stu-id="5ccd4-107">To view log entries</span></span>  
  
1.  <span data-ttu-id="5ccd4-108">En [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], abra el proyecto de [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que contiene el paquete que desea.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="5ccd4-109">En el menú **SSIS** , haga clic en **Registrar eventos**.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-109">On the **SSIS** menu, click **Log Events**.</span></span> <span data-ttu-id="5ccd4-110">Opcionalmente, se puede mostrar la ventana **Registrar eventos** asignando el comando View.LogEvents a una combinación de teclas elegida por el usuario en la página **Teclado** del cuadro de diálogo **Opciones** .</span><span class="sxs-lookup"><span data-stu-id="5ccd4-110">You can optionally display the **Log Events** window by mapping the View.LogEvents command to a key combination of your choosing on the **Keyboard** page of the **Options** dialog box.</span></span>  
  
3.  <span data-ttu-id="5ccd4-111">En el menú **Depurar**, haga clic en **Iniciar depuración**.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-111">On the **Debug** menu, click **Start Debugging**.</span></span>  
  
     <span data-ttu-id="5ccd4-112">A medida que el tiempo de ejecución encuentra eventos y mensajes personalizados que están habilitados para el registro, las entradas del registro para cada evento o mensaje se escriben en la ventana **Registrar eventos** .</span><span class="sxs-lookup"><span data-stu-id="5ccd4-112">As the runtime encounters the events and custom messages that are enabled for logging, log entries for each event or message are written to the **Log Events** window.</span></span>  
  
4.  <span data-ttu-id="5ccd4-113">En el menú **Depurar**, haga clic en **Detener depuración**.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-113">On the **Debug** menu, click **Stop Debugging**.</span></span>  
  
     <span data-ttu-id="5ccd4-114">Las entradas del registro permanecen disponibles en la ventana **Registrar eventos** hasta que vuelve a ejecutar el paquete, ejecuta un paquete diferente o cierra [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5ccd4-114">The log entries remain available in the **Log Events** window until you rerun the package, run a different package, or close [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)].</span></span>  
  
5.  <span data-ttu-id="5ccd4-115">Vea las entradas del registro en la ventana **Registrar eventos** .</span><span class="sxs-lookup"><span data-stu-id="5ccd4-115">View the log entries in the **Log Events** window.</span></span>  
  
6.  <span data-ttu-id="5ccd4-116">También puede hacer clic en las entradas del registro que quiere copiar, hacer clic con el botón derecho y luego hacer clic en **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-116">Optionally, click the log entries to copy, right-click, and then click **Copy**.</span></span>  
  
7.  <span data-ttu-id="5ccd4-117">O bien, puede hacer doble clic en una entrada del registro y, en el cuadro de diálogo **Entrada del registro** , ver los detalles de una única entrada.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-117">Optionally, double-click a log entry, and in the **Log Entry** dialog box, view the details for a single log entry.</span></span>  
  
8.  <span data-ttu-id="5ccd4-118">En el cuadro de diálogo **Entrada del registro** , haga clic en las flechas arriba y abajo para mostrar la entrada del registro anterior o siguiente, y haga clic en el icono de copiar para copiar la entrada del registro.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-118">In the **Log Entry** dialog box, click the up and down arrows to display the previous or next log entry, and click the copy icon to copy the log entry.</span></span>  
  
9. <span data-ttu-id="5ccd4-119">Abra un editor de texto, pegue y luego guarde la entrada del registro en un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="5ccd4-119">Open a text editor, paste, and then save the log entry to a text file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ccd4-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5ccd4-120">See Also</span></span>  
 [<span data-ttu-id="5ccd4-121">Registro de Integration Services &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="5ccd4-121">Integration Services &#40;SSIS&#41; Logging</span></span>](performance/integration-services-ssis-logging.md)  
  
  
