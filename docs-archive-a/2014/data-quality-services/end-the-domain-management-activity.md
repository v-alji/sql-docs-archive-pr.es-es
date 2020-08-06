---
title: Finalizar la actividad de administración de dominios | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: ab6505ad-3090-453b-bb01-58435e7fa7c0
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: c776674a369bfae8c7da6fa0deabfbd932029570
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87745980"
---
# <a name="end-the-domain-management-activity"></a><span data-ttu-id="ab7da-102">Finalizar la actividad Administración de dominios</span><span class="sxs-lookup"><span data-stu-id="ab7da-102">End the Domain Management Activity</span></span>
  <span data-ttu-id="ab7da-103">En este tema se describe cómo completar, cerrar o cancelar la actividad de administración de dominios en [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span><span class="sxs-lookup"><span data-stu-id="ab7da-103">This topic describes how to complete, close, or cancel the domain management activity in [!INCLUDE[ssDQSnoversion](../includes/ssdqsnoversion-md.md)] (DQS).</span></span> <span data-ttu-id="ab7da-104">La administración de dominios no se realiza mediante un asistente, por lo que los controles descritos a continuación se pueden utilizar desde cualquiera de las páginas de la actividad de administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="ab7da-104">Domain management is not performed by a wizard, so the controls described below can used from any of the pages of the domain management activity.</span></span>  
  
## <a name="end-domain-management"></a><span data-ttu-id="ab7da-105">Finalizar la administración de dominios</span><span class="sxs-lookup"><span data-stu-id="ab7da-105">End Domain Management</span></span>  
 <span data-ttu-id="ab7da-106">**Finalizar**</span><span class="sxs-lookup"><span data-stu-id="ab7da-106">**Finish**</span></span>  
 <span data-ttu-id="ab7da-107">Haga clic en esta opción para finalizar la administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="ab7da-107">Click to complete domain management.</span></span> <span data-ttu-id="ab7da-108">Aparecerá un cuadro con las opciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="ab7da-108">A popup will be displayed enabling you to do the following:</span></span>  
  
-   <span data-ttu-id="ab7da-109">**Sí - Publicar la base de conocimiento y salir**: se publicará la base de conocimiento para que pueda usarla el usuario actual u otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="ab7da-109">**Yes - Publish the knowledge base and exit**: The knowledge base will be published for the current user or others to use.</span></span> <span data-ttu-id="ab7da-110">La base de conocimiento no se bloqueará, su estado se establecerá en "vacía" (en la tabla de bases de conocimiento), y las actividades Administración de dominios y Detección de conocimiento estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="ab7da-110">The knowledge base will not be locked, the state of the knowledge base (in the knowledge base table) will be set to empty, and both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="ab7da-111">Volverá a la pantalla Abrir base de conocimiento.</span><span class="sxs-lookup"><span data-stu-id="ab7da-111">You will be returned to the Open Knowledge Base screen.</span></span>  
  
-   <span data-ttu-id="ab7da-112">**No-guardar el trabajo en la base de conocimiento y salir**: se guardará el trabajo, la base de conocimiento permanecerá bloqueada y el estado de la base de conocimiento se establecerá en trabajando.</span><span class="sxs-lookup"><span data-stu-id="ab7da-112">**No - Save the work on the knowledge base and exit**: Your work will be saved, the knowledge base will remained locked, and the state of the knowledge base will be set to In work.</span></span> <span data-ttu-id="ab7da-113">Las actividades Administración de dominios y Detección de conocimiento estarán disponibles.</span><span class="sxs-lookup"><span data-stu-id="ab7da-113">Both the Domain Management and Knowledge Discovery activities will be available.</span></span> <span data-ttu-id="ab7da-114">Volverá a la página de inicio.</span><span class="sxs-lookup"><span data-stu-id="ab7da-114">You will be returned to the home page.</span></span>  
  
-   <span data-ttu-id="ab7da-115">**Cancelar - Permanecer en la pantalla actual**: se cerrará el cuadro emergente y se volverá a la pantalla Administración de dominios.</span><span class="sxs-lookup"><span data-stu-id="ab7da-115">**Cancel - Stay on the current screen**: The popup will be closed and you will be returned to the Domain Management screen.</span></span>  
  
 <span data-ttu-id="ab7da-116">**Cancelar**</span><span class="sxs-lookup"><span data-stu-id="ab7da-116">**Cancel**</span></span>  
 <span data-ttu-id="ab7da-117">Haga clic en esta opción para terminar la actividad Administración de dominios (perdiendo los cambios realizados) y volver a la página de inicio de DQS.</span><span class="sxs-lookup"><span data-stu-id="ab7da-117">Click to terminate the Domain Management activity, losing your work, and return to the DQS home page.</span></span>  
  
 <span data-ttu-id="ab7da-118">**Close**</span><span class="sxs-lookup"><span data-stu-id="ab7da-118">**Close**</span></span>  
 <span data-ttu-id="ab7da-119">Haga clic en esta opción para guardar el trabajo y volver a la página de inicio de DQS.</span><span class="sxs-lookup"><span data-stu-id="ab7da-119">Click to save your work, and return to the DQS home page.</span></span> <span data-ttu-id="ab7da-120">La base de conocimiento se bloqueará, y su estado en la tabla de bases de conocimiento de la pantalla **Abrir base de conocimiento** será **Administración de dominios**.</span><span class="sxs-lookup"><span data-stu-id="ab7da-120">The knowledge base will be locked, and the state of the knowledge base in the knowledge base table in the **Open Knowledge Base** screen will be **Domain Management**.</span></span> <span data-ttu-id="ab7da-121">Después de hacer clic en **Cerrar**, para realizar la actividad Detección de conocimiento tendría que volver a la pantalla **Administración de dominios** , hacer clic en **Finalizar**y, por último, hacer clic en **Sí** para publicar la base de conocimiento o en **No** para guardar el trabajo en la base de conocimiento y salir.</span><span class="sxs-lookup"><span data-stu-id="ab7da-121">After clicking **Close**, to perform the Knowledge Discovery activity, you would have to return to the **Domain Management** screen, click **Finish**, and then click either **Yes** to publish the knowledge base or **No** to save the work on the knowledge base and exit.</span></span>  <span data-ttu-id="ab7da-122">Para obtener más información sobre cómo abrir una base de conocimiento bloqueada, vea [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span><span class="sxs-lookup"><span data-stu-id="ab7da-122">For more information on opening a locked knowledge base, see [Open a Knowledge Base](../../2014/data-quality-services/open-a-knowledge-base.md).</span></span>  
  
  
