---
title: Configuración de un servidor para ejecutar la directiva Desactivado de forma predeterminada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 41c3022d-ab13-443e-ac64-ba1d64584f79
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c0842a30b7d0bbcd1b01ee9e98ed1ed9a74f0f35
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87663433"
---
# <a name="configure-a-server-to-run-the-off-by-default-policy"></a><span data-ttu-id="77562-102">Configurar un servidor para ejecutar la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="77562-102">Configure a Server to Run the Off By Default Policy</span></span>
  <span data-ttu-id="77562-103">Ahora hay una directiva denominada Desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77562-103">Now you have a policy named Off By Default.</span></span> <span data-ttu-id="77562-104">En esta tarea, comprobará si el servidor cumple los requisitos de la directiva Desactivado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="77562-104">In this task, you will check to see whether your server complies with the requirements of this policy.</span></span>  
  
### <a name="to-run-the-off-by-default-policy"></a><span data-ttu-id="77562-105">Para ejecutar la directiva Desactivado de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="77562-105">To run the Off By Default policy</span></span>  
  
1.  <span data-ttu-id="77562-106">En el Explorador de objetos, haga clic con el botón derecho en la instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], seleccione **Directivas**y haga clic en **Evaluar**.</span><span class="sxs-lookup"><span data-stu-id="77562-106">In Object Explorer, right-click your instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], point to **Policies**, and then click **Evaluate**.</span></span>  
  
2.  <span data-ttu-id="77562-107">En el cuadro de diálogo **Evaluar directivas** puede seleccionar las directivas de otra instancia de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o de un archivo.</span><span class="sxs-lookup"><span data-stu-id="77562-107">In the **Evaluate Policies** dialog box you can select policies from another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] or from a file.</span></span> <span data-ttu-id="77562-108">Para este paso, deje **Origen** establecido en su instancia de [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="77562-108">For this step, leave **Source** set to your instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
3.  <span data-ttu-id="77562-109">En la sección **Directivas** , seleccione la directiva **Desactivado de forma predeterminada** .</span><span class="sxs-lookup"><span data-stu-id="77562-109">In the **Policies** section, select the **Off By Default** policy.</span></span>  
  
4.  <span data-ttu-id="77562-110">Para ver si el servidor cumple la directiva, haga clic en **Evaluar**.</span><span class="sxs-lookup"><span data-stu-id="77562-110">To see whether the server is in compliance with the policy, click **Evaluate**.</span></span>  
  
5.  <span data-ttu-id="77562-111">En el área **Resultados** , verá un círculo verde con una marca de verificación si el [!INCLUDE[ssDE](../../includes/ssde-md.md)] cumple la directiva.</span><span class="sxs-lookup"><span data-stu-id="77562-111">In the **Results** area, you will see a green circle with a check mark if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] complies with the policy.</span></span> <span data-ttu-id="77562-112">Verá un círculo rojo con una X si el [!INCLUDE[ssDE](../../includes/ssde-md.md)] no cumple la directiva.</span><span class="sxs-lookup"><span data-stu-id="77562-112">You will see a red circle with an X if the [!INCLUDE[ssDE](../../includes/ssde-md.md)] does not comply with the policy.</span></span>  
  
6.  <span data-ttu-id="77562-113">En el área **Detalles del destino** , verá información adicional en la columna **Mensaje** si se produce un error.</span><span class="sxs-lookup"><span data-stu-id="77562-113">In the **Target Details** area, you will see additional information in the **Message** column if an error occurs.</span></span> <span data-ttu-id="77562-114">En la columna **Mensaje** , haga clic en **Ver** para ver un informe que contiene los resultados de la comprobación de cada propiedad de faceta que se comprobó.</span><span class="sxs-lookup"><span data-stu-id="77562-114">In the **Message** column, click **View** to see a report that contains the results of the check for each facet property that was checked.</span></span>  
  
7.  <span data-ttu-id="77562-115">La descripción de la directiva se muestra en la parte inferior de la página y la sección **Ayuda adicional** muestra el hipervínculo que ha configurado para la directiva.</span><span class="sxs-lookup"><span data-stu-id="77562-115">The policy description is displayed at the bottom of the page, and the **Additional help** section displays the hyperlink that you have configured for the policy.</span></span> <span data-ttu-id="77562-116">Haga clic en el hipervínculo de mensaje para abrir la página web que especificó al crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="77562-116">Click the message hyperlink to open the Web page that you specified when you created the policy.</span></span>  
  
8.  <span data-ttu-id="77562-117">Cierre el explorador y, después, cierre el cuadro de diálogo **Vista detallada de resultados** .</span><span class="sxs-lookup"><span data-stu-id="77562-117">Close the browser, and then close the **Results Detailed View** dialog box.</span></span>  
  
9. <span data-ttu-id="77562-118">Si el servidor no cumple la directiva y quiere deshabilitar Correo electrónico de base de datos, haga clic en **Aplicar** en la página **Resultados de la evaluación** .</span><span class="sxs-lookup"><span data-stu-id="77562-118">If the server is out of compliance and you want to disable Database Mail, click **Apply** in the **Evaluation Results** page.</span></span>  
  
10. <span data-ttu-id="77562-119">Cierre los cuadros de diálogo **Vista detallada de resultados** y **Evaluar directivas** .</span><span class="sxs-lookup"><span data-stu-id="77562-119">Close both the **Results Detailed View** and the **Evaluate Policies** dialog boxes.</span></span>  
  
## <a name="next-lesson"></a><span data-ttu-id="77562-120">Lección siguiente</span><span class="sxs-lookup"><span data-stu-id="77562-120">Next Lesson</span></span>  
 [<span data-ttu-id="77562-121">Lección 2: Creación y aplicación de una directiva de normas de denominación</span><span class="sxs-lookup"><span data-stu-id="77562-121">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
