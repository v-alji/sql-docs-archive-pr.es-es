---
title: Importar las directivas a una sola instancia | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: bc5bcd87-663f-41d9-bb7b-b3e083cd63df
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 0464bc6f4dcd6326a4b8f222cb4b3128f21561ca
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87749532"
---
# <a name="import-the-policies-to-a-single-instance"></a><span data-ttu-id="42785-102">Importar las directivas a una instancia única</span><span class="sxs-lookup"><span data-stu-id="42785-102">Import the Policies to a Single Instance</span></span>
  <span data-ttu-id="42785-103">En esta tarea, importará las directivas de prácticas recomendadas que desea programar en la administración basada en directivas en una única instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42785-103">In this task, you will import the best practices policies that you want to schedule into Policy-Based Management on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="42785-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="42785-104">Prerequisites</span></span>  
 <span data-ttu-id="42785-105">Debe realizar este procedimiento en un servidor que ejecute [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="42785-105">You must perform this procedure on a server that is running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span>  
  
### <a name="import-the-best-practices-policies-for-the-database-engine"></a><span data-ttu-id="42785-106">Importar las directivas de prácticas recomendadas para el Motor de base de datos</span><span class="sxs-lookup"><span data-stu-id="42785-106">Import the best practices policies for the Database Engine</span></span>  
  
1.  <span data-ttu-id="42785-107">Inicie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]y después conéctese a [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="42785-107">Start [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="42785-108">En el Explorador de objetos, expanda **Administración**y, a continuación, expanda **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="42785-108">In Object Explorer, expand **Management**, and then expand **Policy Management**.</span></span>  
  
3.  <span data-ttu-id="42785-109">Haga clic con el botón secundario en **Directivas**y, a continuación, haga clic en **Importar directiva**.</span><span class="sxs-lookup"><span data-stu-id="42785-109">Right-click **Policies**, and then click **Import Policy**.</span></span>  
  
4.  <span data-ttu-id="42785-110">En el cuadro de diálogo **importar** , junto al cuadro **archivos para importar** , haga clic en el botón de puntos suspensivos (**...**).</span><span class="sxs-lookup"><span data-stu-id="42785-110">In the **Import** dialog box, next to the **Files to import** box, click the ellipsis (**...**) button.</span></span>  
  
5.  <span data-ttu-id="42785-111">En la lista **Buscar en** , busque la carpeta siguiente, que contiene las directivas de prácticas recomendadas:</span><span class="sxs-lookup"><span data-stu-id="42785-111">In the **Look in** list, browse to the following folder, which contains the best practices policies:</span></span>  
  
     <span data-ttu-id="42785-112">**C:\Archivos de programa (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="42785-112">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="42785-113">La ruta de acceso puede variar según dónde instalara los archivos de programa de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , si ejecuta un sistema operativo de 32 bits o de 64 bits y el identificador de idioma.</span><span class="sxs-lookup"><span data-stu-id="42785-113">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
6.  <span data-ttu-id="42785-114">En el cuadro de diálogo **Seleccionar directiva** , seleccione uno o más archivos de directivas.</span><span class="sxs-lookup"><span data-stu-id="42785-114">In the **Select Policy** dialog box, select one or more policy files.</span></span>  
  
     <span data-ttu-id="42785-115">Para seleccionar archivos no consecutivos, haga clic en uno, mantenga presionada la tecla CTRL y, a continuación, haga clic en cada archivo adicional.</span><span class="sxs-lookup"><span data-stu-id="42785-115">To select nonadjacent files, click one file, hold down the CTRL key, and then click each additional file.</span></span> <span data-ttu-id="42785-116">Para seleccionar archivos consecutivos, haga clic en el primero de la secuencia, mantenga presionada la tecla MAYÚS y, a continuación, haga clic en el último archivo.</span><span class="sxs-lookup"><span data-stu-id="42785-116">To select adjacent files, click the first file in the sequence, hold down the SHIFT key, and then click the last file.</span></span>  
  
7.  <span data-ttu-id="42785-117">Cuando termine de seleccionar los archivos, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="42785-117">When you are finished selecting files, click **Open**.</span></span>  
  
8.  <span data-ttu-id="42785-118">En el cuadro de diálogo **Importar** , asegúrese de que la lista **Estado de directiva** está establecida en **Conservar el estado de las directivas al importar** (el valor predeterminado) y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="42785-118">In the **Import** dialog box, make sure that the **Policy state** list is set to **Preserve policy state on import** (the default), and then click **OK**.</span></span>  
  
     <span data-ttu-id="42785-119">Las directivas se importan en el nodo **Directivas** en **Administración de directivas**.</span><span class="sxs-lookup"><span data-stu-id="42785-119">The policies are imported into the **Policies** node under **Policy Management**.</span></span> <span data-ttu-id="42785-120">De forma predeterminada, las directivas importadas se establecen en el modo de evaluación "A petición".</span><span class="sxs-lookup"><span data-stu-id="42785-120">By default, the imported policies are set to "On demand" evaluation mode.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="42785-121">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="42785-121">Next Steps</span></span>  
 [<span data-ttu-id="42785-122">Programar las directivas</span><span class="sxs-lookup"><span data-stu-id="42785-122">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
  
