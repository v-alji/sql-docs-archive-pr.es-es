---
title: 'Lección 2: evaluar las directivas de prácticas recomendadas de forma programada | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 37ffad63-d6db-4609-8deb-786200659554
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: a454e38ec2f07bf9867183a3894ac4ea001a942e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/04/2020
ms.locfileid: "87670718"
---
# <a name="lesson-2-evaluate-best-practices-policies-on-a-scheduled-basis"></a><span data-ttu-id="ee9ef-102">Lección 2: Evaluación de las directivas de procedimientos recomendados de forma programada</span><span class="sxs-lookup"><span data-stu-id="ee9ef-102">Lesson 2: Evaluate Best Practices Policies on a Scheduled Basis</span></span>
  <span data-ttu-id="ee9ef-103">Puede configurar evaluaciones programadas de directivas de prácticas recomendadas en una o más instancias de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee9ef-103">You can configure scheduled evaluations of best practices policies on one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="ee9ef-104">Para configurar las directivas de prácticas recomendadas de modo que se ejecuten de forma programada, debe importar las directivas en la instancia de destino.</span><span class="sxs-lookup"><span data-stu-id="ee9ef-104">To configure best practices policies to run on a scheduled basis, you must import the policies into the target instance.</span></span>  
  
 <span data-ttu-id="ee9ef-105">Para implementar las directivas programadas en varios servidores, puede importarlas en una instancia, configurar las programaciones de cada directiva, exportar las directivas programadas en una carpeta y, a continuación, implementarlas de modo que se destinen a las instancias a través de servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="ee9ef-105">To deploy scheduled policies to multiple servers, you can import the policies to one instance, configure the schedules for each policy, export the scheduled policies to a folder, and then deploy the scheduled policies to target instances through Registered Servers.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="ee9ef-106">Las instancias de destino deben ejecutar [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="ee9ef-106">The target instances must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="ee9ef-107">La automatización requiere que las directivas estén almacenadas localmente en la instancia, lo que no se admite en versiones de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] anteriores a [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee9ef-107">Automation requires the policies to be stored locally on the instance, which is not supported by versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
 <span data-ttu-id="ee9ef-108">En esta lección, hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ee9ef-108">In this lesson, you will do the following:</span></span>  
  
-   <span data-ttu-id="ee9ef-109">Importar las directivas de prácticas recomendadas en una instancia de [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ee9ef-109">Import the best practices policies into an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="ee9ef-110">Configurar las directivas para ejecutarse según una programación.</span><span class="sxs-lookup"><span data-stu-id="ee9ef-110">Configure the policies to run on a schedule.</span></span>  
  
-   <span data-ttu-id="ee9ef-111">Implementar las directivas de prácticas recomendadas programadas en varias instancias mediante servidores registrados.</span><span class="sxs-lookup"><span data-stu-id="ee9ef-111">Deploy the scheduled best practices policies to multiple instances through Registered Servers.</span></span>  
  
 <span data-ttu-id="ee9ef-112">En esta lección se incluyen los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="ee9ef-112">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="ee9ef-113">Importar las directivas a una instancia única</span><span class="sxs-lookup"><span data-stu-id="ee9ef-113">Import the Policies to a Single Instance</span></span>](../../2014/tutorials/import-the-policies-to-a-single-instance.md)  
  
-   [<span data-ttu-id="ee9ef-114">Programar las directivas</span><span class="sxs-lookup"><span data-stu-id="ee9ef-114">Schedule the Policies</span></span>](../../2014/tutorials/schedule-the-policies.md)  
  
-   [<span data-ttu-id="ee9ef-115">Implementar directivas programadas en varias instancias</span><span class="sxs-lookup"><span data-stu-id="ee9ef-115">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
## <a name="see-also"></a><span data-ttu-id="ee9ef-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ee9ef-116">See Also</span></span>  
 [<span data-ttu-id="ee9ef-117">Administrar varios servidores mediante servidores de administración central</span><span class="sxs-lookup"><span data-stu-id="ee9ef-117">Administer Multiple Servers Using Central Management Servers</span></span>](../relational-databases/administer-multiple-servers-using-central-management-servers.md)  
  
  
