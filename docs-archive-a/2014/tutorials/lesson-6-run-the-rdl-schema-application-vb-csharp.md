---
title: 'Lección 6: ejecutar la aplicación de esquema RDL (VB-C #) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: a2cd2386-2df8-4b69-ab81-9ad1a31f6d27
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: 5a0fc2cd9c12b4b1602f517dc215ca44e686c663
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87743703"
---
# <a name="lesson-6-run-the-rdl-schema-application-vb-c"></a><span data-ttu-id="9fcb3-102">Lección 6: ejecutar la aplicación de esquema RDL (VB-C #)</span><span class="sxs-lookup"><span data-stu-id="9fcb3-102">Lesson 6: Run the RDL Schema Application (VB-C#)</span></span>
  [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] <span data-ttu-id="9fcb3-103">ofrece dos métodos para generar y ejecutar una aplicación de consola desde el entorno de desarrollo integrado (IDE):</span><span class="sxs-lookup"><span data-stu-id="9fcb3-103">offers two methods to build and run a console application from the integrated development environment (IDE):</span></span>  
  
-   <span data-ttu-id="9fcb3-104">Iniciar (con depuración)</span><span class="sxs-lookup"><span data-stu-id="9fcb3-104">Start (with Debugging)</span></span>  
  
-   <span data-ttu-id="9fcb3-105">Iniciar sin depuración</span><span class="sxs-lookup"><span data-stu-id="9fcb3-105">Start without Debugging</span></span>  
  
### <a name="to-build-and-run-the-samplerdlschema-application"></a><span data-ttu-id="9fcb3-106">Para generar y ejecutar la aplicación SampleRDLSchema</span><span class="sxs-lookup"><span data-stu-id="9fcb3-106">To build and run the SampleRDLSchema application</span></span>  
  
1.  <span data-ttu-id="9fcb3-107">En el menú **Depurar**, haga clic en **Iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="9fcb3-107">From the **Debug** menu, click **Start Without Debugging**.</span></span> <span data-ttu-id="9fcb3-108">Esto garantiza que la ventana de la consola seguirá abierta cuando el programa se haya acabado de ejecutar.</span><span class="sxs-lookup"><span data-stu-id="9fcb3-108">This ensures that the console window remains open after the program has finished executing.</span></span>  
  
     <span data-ttu-id="9fcb3-109">La aplicación escribe lo siguiente en la consola:</span><span class="sxs-lookup"><span data-stu-id="9fcb3-109">The application prints the following output to the console:</span></span>  
  
    ```  
    Loading Report Definition  
    Updating Report Definition  
    - Old Description: <Old Report Description>  
    - New Description: <New Report Description>  
    Publishing Report Definition  
    ```  
  
2.  <span data-ttu-id="9fcb3-110">Presione cualquier tecla para cerrar la consola.</span><span class="sxs-lookup"><span data-stu-id="9fcb3-110">Press any key to close the console.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="9fcb3-111">Los errores que se produzcan se escribirán en la consola.</span><span class="sxs-lookup"><span data-stu-id="9fcb3-111">Any errors that occur are written to the console.</span></span>  
  
3.  <span data-ttu-id="9fcb3-112">Cuando la aplicación de ejemplo finaliza la ejecución de una copia actualizada del informe, la guarda en el servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="9fcb3-112">When the sample application is finished running an updated copy of the report will be saved to the report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcb3-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fcb3-113">See Also</span></span>  
 <span data-ttu-id="9fcb3-114">[Actualizar informes con clases generadas a partir del esquema RDL &#40;tutorial de SSRS&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span><span class="sxs-lookup"><span data-stu-id="9fcb3-114">[Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md) </span></span>  
 [<span data-ttu-id="9fcb3-115">Lenguaje RDL (Report Definition Language) &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="9fcb3-115">Report Definition Language &#40;SSRS&#41;</span></span>](../reporting-services/reports/report-definition-language-ssrs.md)  
  
  
